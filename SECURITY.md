<!--
SPDX-FileCopyrightText: Contributors to the Power Grid Model project <powergridmodel@lfenergy.org>

SPDX-License-Identifier: MPL-2.0
-->

# Security Policy

## Supported Versions

This project uses a rolling release strategy.
A new push(merge) to the `main` branch will trigger GitHub Actions to automatically release a new version.
**All the bug fixes will be committed directly into the `main` branch and published in the latest release.
No effort will be spent on backporting bug fixes to previous versions!**

| Version            | Supported |
| ------------------ | --------- |
| last `main`        | &#9989;   |
| all other releases | &#10060;  |

In addition, Python libraries in this project are only released for [recent Python versions](./RELEASE.md#supported-python-versions).

## Reporting a Vulnerability

This project contains multiple repositories, each with different responsibilities, and therefore also different risks
regarding vulnerabilities.
If you find a vulnerability, please report it.

If Private Vulnerability Reporting feature of GitHub is enabled for the repository on which you found the vulnerabilty,
please use it to report the vulnerability.
The administrators and maintainers of the project will actively monitor this and respond at the earliest occasion
possible.

On repositories for which Private Vulnerability Reporting is not enabled, please report vulnerabilities as bugs via the
GitHub issues tab.

### power-grid-model

[![OpenSSF Best Practices](https://bestpractices.coreinfrastructure.org/projects/7298/badge)](https://bestpractices.coreinfrastructure.org/projects/7298)

[`power-grid-model`](https://github.com/PowerGridModel/power-grid-model) is a calculation library without network
connection or authentications.
It is, however, possible that there are vulnerabilities in the form of (C++) bugs.
Please refer to our assurance case regarding
[different types of bugs and vulnerabilities](https://power-grid-model.readthedocs.io/en/stable/advanced_documentation/terminology.html#bug)
and [undefined behavior](https://power-grid-model.readthedocs.io/en/stable/advanced_documentation/terminology.html#undefined-behavior),
as well as the respective trust boundaries.
You can report vulnerabilities in private via the [Private Vulnerability Reporting](https://github.com/PowerGridModel/power-grid-model/security/advisories)
tab on the repository.

### power-grid-model-ds

[`power-grid-model-ds`](https://github.com/PowerGridModel/power-grid-model-ds) is a data science library that processes
datasets and configuration that may be user-provided.
Treat all external inputs as untrusted, validate formats/schemas where possible and avoid unsafe deserialization
(e.g. `pickle`) for untrusted files.
If the visualizer is installed and used, note that it runs a local web server and opens a TCP port.
You can report vulnerabilities in the issues as a bug.

### power-grid-model-io

[`power-grid-model-io`](https://github.com/PowerGridModel/power-grid-model-io) is a data conversion library and
constains user configuration in the form of custom mappings and filters via a YAML file.
To prevent code injection during loading, `yaml.safe_load` is used.
In addition, execution is restricted to specific white-listed functions and modules.
Please refer to the relevant
[security considerations](https://power-grid-model-io.readthedocs.io/en/stable/converters/tabular_converter.html#security-considerations)
for more information.
You can report vulnerabilities in the issues as a bug.
