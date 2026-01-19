<!--
SPDX-FileCopyrightText: Contributors to the Power Grid Model project <powergridmodel@lfenergy.org>

SPDX-License-Identifier: MPL-2.0
-->

# Release strategy

This project uses a semantic versioning release strategy.
All major and minor features will be announced via our communication channels.

- **Major** version bumps contain:
  - Breaking changes
  - Removal of features that were marked deprecated in a previous version and are expected to affect users
- **Minor** version bumps contain:
  - New features with full support
  - Removal of minor features that were marked deprecated in a previous version
    and that are unlikely to affect users significantly
- **Patch** version bumps may contain:
  - Bug fixes
  - Deprecations (no removal!)
  - Small quality-of-life improvements
  - Experimental/preview features
  - Performance improvements
  - Improvements to the code that do not affect the user

Some additional remarks:

- Deprecated behavior shall be signalled via a deprecation warning.
- The maintainers of the [power-grid-model](https://github.com/PowerGridModel/power-grid-model)
  core package shall use the option to remove deprecated behavior in minor version bumps very sparingly.
- In more feature-rich packages, like [power-grid-model-ds](https://github.com/PowerGridModel/power-grid-model-ds)
  and [power-grid-model-io](https://github.com/PowerGridModel/power-grid-model-io), removal may be slightly more common
  due to their nature and focus on usability.

This project uses a rolling release strategy on the `main` branch.
A new push (merge) to the `main` branch will trigger GitHub Actions to automatically
build and upload a new version to PyPI with a unique version number. In
addition, we may manually create alpha (pre-)releases for testing purposes only
via workflow dispatch.

**All the bug fixes will be committed directly into the `main` branch and published in the latest release.**
**No effort will be spent on backporting bug fixes to previous versions!**

## Actively supported Python versions

Core Python libraries in this project are released for at least the latest three stable Python versions.
This means that for these Python versions, active support will be provided,
including new versions of the library, bugfixes and security patches.
Older Python versions may not be supported for security and maintainability reasons,
both of this project itself, its direct and indirect dependencies
and that of [Python](https://devguide.python.org/versions/) as a language.

An older Python version may be removed from the automatic release cycle if:

- there are at least three newer stable Python versions (e.g. 3.x); and
- at least three of those newer Python versions have been stable for at least three months; and
- at least six months have passed since support for a previous stable Python version was dropped.

For the actively supported versions as of January 2026, the following release cycle is expected:

| Python version | Currently supported | Scheduled/expected end of active support |
| -------------- | ------------------- | ---------------------------------------- |
| Python 3.8     | &#10060;            | 10-January-2024 (dropped)                |
| Python 3.9     | &#10060;            | 15-July-2024 (dropped)                   |
| Python 3.10    | &#10060;            | 27-January 2025 (dropped)                |
| Python 3.11    | &#10060;            | 14-January 2026 (dropped)                |
| Python 3.12    | &#9989;             | January 2027 (expected)                  |
| Python 3.13    | &#9989;             | January 2028 (expected)                  |
| Python 3.14    | &#9989;             | January 2029 (expected)                  |

Starting with Python 3.10, the expected date of end of active support for a given Python version
is approximately three years and three months after it comes out.
