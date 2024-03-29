# Build types

APS can optionally bundle additional code that is either proprietary or typically frowned upon within the FOSS community (like telemetry) to provide user-facing features and assist development efforts through anonymized usage data.

To counter that, and continue providing FOSS-only binaries through F-Droid, APS implements the `free` and `nonFree` (free as in freedom) build types to allow the same codebase to be able to generate both FOSS-friendly binaries as well as ones with optional proprietary code that enables extra features.

Below are the feature differences between the `free` and `nonFree` build variants. Any features not mentioned below are available to both build types.

Feature | `free` | `nonFree`
----------------------|--------|----------
[Autofill OTPs from SMSes](https://msfjarvis.dev/aps/pr/900) | ❌ | ✅
Error reporting via [Sentry](https://sentry.io/) | ❌ | ✅

## Building

For more information on how to build these variants, see the [contribution guidelines](https://github.com/android-password-store/Android-Password-Store/blob/develop/CONTRIBUTING.md#building-the-project)