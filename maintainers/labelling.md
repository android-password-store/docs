# Labels in the APS repository

The APS repository liberally uses GitHub's labelling functionalities to sort issues and pull requests. Our labels enumerate the following properties:

- Area
- Category
- Effort
- Priority
- Status

### Area

This refers to the part of the app that is affected by the issue or pull request. New entries keep getting added here as and when issues for them are field. These labels are of the format `A-<area>`, like `A-Git` or `A-autofill`. All issues and pull requests must apply these.

### Category

This pertains to the type of issue/pull request. Whether this is a bug, or a feature, a regression from the previous stable release, or a RFC. These labels are mandatory for all issues and pull requests, and have the `C-` prefix (`C-bug`, `C-rfc`, `C-regression`, and so on).

### Effort

Indicator of the expected effort required to resolve an issue. This is not mandatory, and is a easy way to flag issues that are easy for new contributors to triage and fix. Denoted by the `E-` prefix, and can be one of `E-easy`, `E-medium` or `E-hard`. It is not mandatory, and is only applicable to issues or draft pull requests.

### Priority

Indicates the priority of an issue or pull request. Issues marked with `P-high` are to be considered critical and new stable releases should ideally not go out with a high priority issue still open. As evident, the group prefix is `P-`, and it follows the same `P-low`, `P-medium`, and `P-high` pattern as effort. Necessary label for issues, and optional but recommended for pull requests.

### Status

Shows the current status of the issue or pull request. This is a fairly involved group and embodies the different states of issues and pull requests.

- `S-awaiting-triage`: Automatically applied to new issues to indicate that a maintainer needs to take a look at them.
- `S-blocked`: Applicable for issues or pull requests that have external dependencies and cannot move forward until they're resolved.
- `S-design`: Applied to issues or PRs that are stumped on a technical challenge where no solution exists or current options are not satisfactory.
- `S-needs-reproduction-steps`: Applied to issues where maintainers have been unable to reproduce the bug in their environments.
- `S-waiting-for-comment`: Automatically applied to RFCs that need to be given a first review.
- `S-waiting-on-author`: Applied to pull requests that have been reviewed and now need the author to make changes.
- `S-waiting-on-reporter`: Applied to issues where the reporter of the bug needs to offer additional information.
- `S-waiting-on-review`: Applied to pull requests that need to be reviewed.
- `S-wontfix`: Applied to issues that contain proposals which have been rejected or contain a bug description that is intended behavior.
