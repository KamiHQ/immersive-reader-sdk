# Azure Applied AI Immersive Reader - Immersive Reader SDK

The Immersive Reader SDK is a set of libraries that allow you to easily and quickly integrate the [Immersive Reader](https://azure.microsoft.com/services/immersive-reader) into your application.

## Kami Fork Instructions

We fork Immersiver Reader solely to remove a reference to external Javascript files that is not permitted by the Chrome Web Store rules.

Here are rough steps to update the fork:

```
# Add the upstream repo (unless you already have it)
git remote add upstream git@github.com:microsoft/immersive-reader-sdk.git

# Pull the latest code from upstream
git fetch upstream

# Branch off the previous Kami branch with today's date
git checkout kami-2026-03-20 -b kami-2026-06-01

# Rebase on top of upstream, removing the "Build Immersive Reader" commit that included the previous build artifacts.
# There should only be 1 commit to rebase.
git rebase upstream/dev --interactive

# Build the new version
cd js
yarn
cd ..

# Copy the build output back to the root of the project and commit
cp -r js/package.json js/lib .
git add package.json lib
git commit -m "Build Immersive Reader"

# Push the branch up to our fork.
git push origin kami-2026-06-01

# Done! Reference the new branch in the extension's package.json file.
```

## Usage

* [JavaScript](./js)
* [Usage](https://docs.microsoft.com/azure/cognitive-services/immersive-reader/reference)

## Contributing

We welcome [contributions](CONTRIBUTING.md) to this project.

* [Submit bugs](https://github.com/microsoft/immersive-reader-sdk/issues) and help us verify fixes as they are checked in.
* Submit and review [source code changes](https://github.com/microsoft/immersive-reader-sdk/pulls).
* Join the discussion on [StackOverflow](https://stackoverflow.com/questions/tagged/immersive-reader) and [Twitter](https://twitter.com/hashtag/ImmersiveReader).

Please submit pull requests to the [dev](https://github.com/microsoft/immersive-reader-sdk/tree/dev) branch.

## Reporting Security Issues

Security issues and bugs should be reported privately, via email, to the Microsoft Security Response Center (MSRC) at
[secure@microsoft.com](mailto:secure@microsoft.com). You should receive a response within 24 hours. If for some reason
you do not, please follow up via email to ensure we received your original message. Further information, including the
[MSRC PGP](https://technet.microsoft.com/security/dn606155) key, can be found in the
[Security TechCenter](https://technet.microsoft.com/security/default).

## License

Copyright (c) Microsoft Corporation. All rights reserved.

Licensed under the [MIT](LICENSE.txt) License.
