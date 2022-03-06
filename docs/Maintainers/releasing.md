---
sidebar_position: 2
---

# Releasing new versions

The central [Android-Password-Store] repository houses three subprojects that are released separately from each other and with different methods.

## Library modules

The `autofill-parser` and `openpgp-ktx` libraries are available on the [APS JCenter] repository. The process for creating a new release is as follows:

1. Bump the version number for the library in `$projectDir/gradle.properties`

2. Push a new tag following the format `$projectDir-v$version`, for example, `v4.0.0` for `autofill-parser` needs a `autofill-parser-v4.0.0` tag.

## Password Store app

Releasing a new major version of the app is a slightly more involved process.

1. Each release is accompanied by a [milestone], so go ahead and close it. This will set off a GitHub Action that will generate a pull request with the changelog and the version updated.

2. Merge the pull request, and note the target branch against which it was created.

3. Tag the new state of the aforementioned branch following the exact semantic version as in the milestone. This means the tag should be `v1.2.0`, not `1.2.0` or `1.2` or `v1.2`.

4. Push the tag to GitHub, and allow CI to generate artifacts and a draft release that can then be reviewed and made public.

5. The maintainer in charge of Play Store deployment then takes the generated binaries from this GitHub release and uploads them to Play Store. In the future this manual step should be eliminated in favour of a Gradle-backed automatic deployment setup, using tools like [Gradle-Play-Publisher].

[android-password-store]: https://github.com/android-password-store/Android-Password-Store
[aps jcenter]: https://bintray.com/android-password-store
[gradle-play-publisher]: https://github.com/Triple-T/gradle-play-publisher
[milestone]: https://github.com/android-password-store/Android-Password-Store/milestones