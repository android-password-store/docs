# Build Types

We generate release binaries under two separate configurations titled `free` and `nonFree`. The distinction was created following the merge of [#900](https://msfjarvis.dev/aps/pr/900), that introduced a dependency on closed source GMS libraries. Since F-Droid is a FOSS-only app store, we created the `free` flavor where we do not ship the GMS dependency and thus the feature to fill SMS OTPs is unavailable.
