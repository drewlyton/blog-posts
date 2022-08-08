At work, when we release a new version of our Capacitor app, we always deploy to the web, but we conditionally deploy to CodePush instead of the AppStore based on whether it is a minor (or patch) release or a major release.

To automate this system and have our deploys run in Github Actions, we need to conditionally run `jobs` based on the tag name of the release. There wasn't a lot of documentation on how to set this up. So, I thought I'd write this quick blog post on how to do it.

**Quick Note**
We setup this workflow to be conditional on the semantic version number (i.e. vMajor.Minor.Patch). However, you could also setup a similar system by reading anything in the release tag name (i.e. appending `-apk`, `-web`, `-codepush`). It's just up to you and how you'd like to work.

## Getting the version number
Let's define a job that will expose each component of our version number so we can use them in conditional logic for future jobs. To do that, we'll need to:
1. Access the tag name
2. Parse the tag name for each component of the version number (v**1**.**2**.**3**)
3. Use Github's `outputs` feature to set those numbers as variables we can use throughout our workflow file.

### Accessing the tag name
Let's start with a new, dummy `workflow.yml` file with a blank job that runs whenever we publish a new release.

```yaml
name: Deploy Release
on: 
  release:
    types:
      - "published"
jobs:
  GetVersion:
    runs-on: ubuntu-latest
    steps:
      - run: echo "A new release!"

```

In order to use our version number in conditionals for future jobs, we need to extract it from the tag name or the release. Lucky for us that's available via the job context using `github.ref_name` . So, let's expose that to the global workflow `env`.

```yaml
name: Deploy Release
on: 
  release:
    types:
      - "published"
env:
  VERSION: ${{ github.ref_name }}
jobs:
  GetVersion:
    runs-on: ubuntu-latest
    steps:
	  # This is just bash 👇
      - run: echo "A new release with version number ${VERSION}!"

```

Nice! Now our version number is globally available! Let's use it to grab each component of the semantic version.

### Parsing bash strings using `cut`
Let's examine our tag name / versioning string: `v1.2.3`

In order to parse out each component of the number, we first need to get rid of that `v` at the start. We can do that by using bash paramater expansion like so:

```sh
echo ${VERSION##*v}
"1.2.3"
```

And once we have that purely period (`.`) delineated string, we can use bash's `cut` command with the `-d` flag to get each individual component.

```sh
echo "$(echo ${VERSION##*v} | cut -d'.' -f1)"
1
echo "$(echo ${VERSION##*v} | cut -d'.' -f2)"
2
echo "$(echo ${VERSION##*v} | cut -d'.' -f3)"
3
```

Perfect! Now, all we have left to do is integrate this script into our workflow.

### Setting `outputs` for a job


```yaml
name: Deploy Release
on: 
  release:
    types:
      - "published"
env:
  VERSION: ${{ github.ref_name }}
jobs:
  GetVersion:
    runs-on: ubuntu-latest
    outputs:
      minor: ${{ steps.minor.outputs.number }}
      patch: ${{ steps.patch.outputs.number }}
    steps:
      - id: minor
        run: echo "::set-output name=number::$(echo ${VERSION##*v} | cut -d'.' -f2)"
      - id: patch
        run: echo "::set-output name=number::$(echo ${VERSION##*v} | cut -d'.' -f3)"
  AllReleases:
    runs-on: ubuntu-latest
    steps:
      - run: echo "🎉 The job was automatically triggered by creating the ${{ github.ref_type }} ${{ github.ref_name }}."
      - run: echo "Do things that all releases require..."
  Major:
    runs-on: ubuntu-latest
    needs: GetVersion
    env:
      minor: ${{ needs.GetVersion.outputs.minor }}
      patch: ${{ needs.GetVersion.outputs.patch }}
    if: ${{ env.minor == 0 && env.patch == 0 }}
    steps:
      - run: echo "Doing the things for MAJOR version change..."
  Minor:
    runs-on: ubuntu-latest
    needs: GetVersion
    env:
      minor: ${{ needs.GetVersion.outputs.minor }}
      patch: ${{ needs.GetVersion.outputs.patch }}
    if: ${{ env.minor != 0 && env.patch == 0 }}
    steps:
      - run: echo "Doing the things for MINOR version change..."
  Patch:
    runs-on: ubuntu-latest
    needs: GetVersion
    env:
      patch: ${{ needs.GetVersion.outputs.patch }}
    if: ${{ env.patch != 0 }}
    steps:
      - run: echo "Doing the things for PATCH version change..."
```



## And that's it!
