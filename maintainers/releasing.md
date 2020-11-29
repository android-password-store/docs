# Releasing new versions

The central [Android-Password-Store] repository houses three released subprojects that are released separately and by separate methods.

## Library modules

The `autofill-parser` and `openpgp-ktx` libraries are available on the [APS JCenter] repository. The process for doing a new release is as follows:

1. Bump the version number for the library in `$projectDir/gradle.properties`
2. Push a new tag following the format `$projectDir-v$version`, for example, `v4.0.0` for `autofill-parser` needs a `autofill-parser-v4.0.0` tag.

## Password Store app

Releasing a new major version of the app is a slightly more involved process.

1. Create a new branch named `release-$major.$minor` from the `develop` branch, i.e. `release-4.3` for the `4.3.5` release.
2. Bump the app version to match the version you're releasing.

The version name should match the version we want to release, and the version code should be of type `$major_$minor_$patch`, adding a leading zero as necessary. To make the abovementioned release, the version would look like this:

```kotlin
versionCode = 4_03_05
versionName = "4.3.5"
```

3. Tag the current state of the release branch, `v4.3.5` following our example.

4. Push the release branch and tag to GitHub, and allow CI to generate artifacts and a draft release that can then be reviewed and made public.

5. The maintainer in charge of Play Store deployment then takes the generated binaries from this GitHub release and uploads them to Play Store. In the future this manual step should be eliminated in favour of a Gradle-backed automatic deployment setup.

[android-password-store]: https://github.com/android-password-store/Android-Password-Store
[aps jcenter]: https://bintray.com/android-password-store
