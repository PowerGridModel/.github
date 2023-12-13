<!--
SPDX-FileCopyrightText: 2022 Contributors to the Power Grid Model project <dynamic.grid.calculation@alliander.com>

SPDX-License-Identifier: MPL-2.0
-->

# Release strategy

This project uses a rolling release strategy on the `main` branch.
A new push (merge) to the `main` branch will trigger GitHub Actions to automatically 
build and upload a new version to PyPI with a unique version number.

**All the bug fixes will be committed directly into the `main` branch and published in the latest release. 
No effort will be spent on backporting bug fixes to previous versions!**

Sometimes a `release/` branch will be created temporarily for 
a big new version with new features and/or breaking changes.
A push (merge) to the release branch will tigger GitHub Actions to automatically 
build and upload a new version to PyPI with a unique release-candidate version number (suffix `rc`).

**NOTE: Release candidate versions are for testing only. You should not use them in production!**

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

For the actively supported versions as of December 2023, the following release cycle is expected:

| Python version | Scheduled/expected end of active support |
| -------------- | ---------------------------------------- |
| Python 3.8     | January 2024                             |
| Python 3.9     | July 2024                                |
| Python 3.10    | January 2024                             |
| Python 3.11    | January 2025                             |
| Python 3.12    | January 2026                             |

After support for Python 3.9 is dropped, the expected life time for active support for a given
Python version is three years and three months after it comes out.
