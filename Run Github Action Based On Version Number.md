At work, when we release a new version of our Capacitor app, we always deploy to the web, but we conditionally deploy to CodePush instead of the AppStore based on whether it is a minor/patch release or a major release.

To automate this system and have our deploys run in Github Actions, we needed to conditionally run `jobs` based on the version number of the release. There wasn't a lot of documentation on how to set this up. So, I thought I'd write this quick blog post on how to do it.

## Getting the version number
Let's start with a new, dummy `workflow.yml` file that runs whenever we publish a new release.

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

### Quick Aside
We setup this workflow to be conditional on the semantic version type (i.e. major, minor, patch). However, you could also setup a similar system by appending the deploy target (i.e. `-apk`, `-web`, `-codepush`) after the version number in the tag name. It's just up to you and how you'd like to work (and whether you can remember to append the target type 😆)

## And that's it!
