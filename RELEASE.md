<!--
SPDX-FileCopyrightText: Contributors to the Power Grid Model project <powergridmodel@lfenergy.org>

SPDX-License-Identifier: MPL-2.0
-->

# Release strategy

This project uses a rolling release strategy on the `main` branch.
A new push (merge) to the `main` branch will trigger GitHub Actions to automatically 
build and upload a new version to PyPI with a unique version number. In
addition, we may create alpha candidates that are not released, manually
via workflow dispatch, for testing purposes only.

**All the bug fixes will be committed directly into the `main` branch and published in the latest release. 
No effort will be spent on backporting bug fixes to previous versions!**

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

For the actively supported versions as of January 2025, the following release cycle is expected:

| Python version | Currently supported | Scheduled/expected end of active support |
| -------------- | ------------------- | ---------------------------------------- |
| Python 3.8     | &#10060;            | 10-January-2024 (dropped)                |
| Python 3.9     | &#10060;            | 15-July-2024 (dropped)                   |
| Python 3.10    | &#10060;            | 27-January 2025 (dropped)                |
| Python 3.11    | &#9989;             | January 2026 (expected)                  |
| Python 3.12    | &#9989;             | January 2027 (expected)                  |
| Python 3.13    | &#9989;             | January 2028 (expected)                  |

Starting with Python 3.10, the expected date of end of active support for a given Python version
is three years and three months after it comes out.
