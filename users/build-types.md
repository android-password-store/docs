# Build Types

APS can optionally bundle proprietary code through Google Play Services to add extra functionality, making it FOSS-incompatible.

To counter that, and continue providing FOSS-only binaries through F-Droid, APS implements the `free` and `nonFree` (free as in freedom) build types to allow the same codebase to be able to generate both FOSS-friendly binaries as well as ones with optional proprietary code that enables extra features.

Below are the feature differences between the `free` and `nonFree` build variants. Any features not mentioned below are available to both build types.

Feature | `free` | `nonFree`
----------------------|--------|----------
Autofill from SMS OTP | ❌ | ✅
