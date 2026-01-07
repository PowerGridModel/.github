<!--
SPDX-FileCopyrightText: Contributors to the Power Grid Model project <powergridmodel@lfenergy.org>

SPDX-License-Identifier: MPL-2.0
-->

# Security Policy

## Supported Versions

This project uses a rolling release strategy. A new push(merge) to the `main` branch will trigger GitHub Actions to automatically release a new version. **All the bug fixes will be committed directly into the `main` branch and published in the latest release. 
No effort will be spent on backporting bug fixes to previous versions!**

| Version            | Supported |
| ------------------ | --------- |
| last `main`        | &#9989;   |
| all other releases | &#10060;  |

In addition, Python libraries in this project are only released for [recent Python versions](./RELEASE.md#supported-python-versions).

## Reporting a Vulnerability

This project is a calculation library without network connection or authentications.
There could be however vulnerabilities in the form of (C++) bugs.
Please refer to our assurance case regarding
[different types of bugs and vulnerabilities](https://power-grid-model.readthedocs.io/en/stable/advanced_documentation/terminology.html#bug)
and [undefined behavior](https://power-grid-model.readthedocs.io/en/stable/advanced_documentation/terminology.html#undefined-behavior),
as well as the respective trust boundaries.
You can report the vulnerabilities in the issues as a bug.
