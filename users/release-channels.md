# Release Channels

Official binary releases of Android Password Store are available through 4 different channels, each serving their own purpose.

- [Play Store]
- [GitHub Releases]

Play Store and GitHub Releases always contain the latest stable release as built by our CI infrastructure. GitHub Releases contains both the `free` and `nonFree` variants, of which the `nonFree` variant then gets uploaded to the Play Store (refer to [build types] for what `free` and `nonFree` mean for you).

- [F-Droid]

F-Droid is a FOSS-only store that takes our open source code and generates their own builds from it. F-Droid usually lags behind our primary release channels, and a subset of functionality might be missing due to the requirement that binaries only contain FOSS code (refer to [build types]).

- [Snapshot builds]

These are builds that are generated on each push to the development branch of APS and may contain unfinished and broken features, or more often, early access to bugfixes. These also ship with additional debugging code that simplify reporting of issues to us.


[play store]: https://play.google.com/store/apps/details?id=dev.msfjarvis.aps
[github releases]: https://github.com/Android-Password-Store/Android-Password-Store/releases
[f-droid]: https://f-droid.org/en/packages/dev.msfjarvis.aps
[build types]: build-types
[snapshot builds]: https://github.com/android-password-store/Android-Password-Store/releases/tag/latest
