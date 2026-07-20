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

## Third-Party Software and Development Tools

Like most software projects, our repositories rely on external dependencies.
We aim to keep these dependencies to a minimum and select sources that are mature, widely used, and trusted.
Users remain responsible for evaluating whether these dependencies satisfy their own security requirements.

We also provide recommendations for development tools in our build guides and VS Code extensions in the `.vscode/extentions.json` for each repository.
These recommendations are optional.
Developers should evaluate them against their own security policies before installation and use.

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
You can report vulnerabilities in private via the [Private Vulnerability Reporting](https://github.com/PowerGridModel/power-grid-model-ds/security/advisories)
tab on the repository.

### power-grid-model-io

[`power-grid-model-io`](https://github.com/PowerGridModel/power-grid-model-io) is a data conversion library and
constains user configuration in the form of custom mappings and filters via a YAML file.
To prevent code injection during loading, `yaml.safe_load` is used.
In addition, execution is restricted to specific white-listed functions and modules.
Please refer to the relevant
[security considerations](https://power-grid-model-io.readthedocs.io/en/stable/converters/tabular_converter.html#security-considerations)
for more information.
You can report vulnerabilities in private via the [Private Vulnerability Reporting](https://github.com/PowerGridModel/power-grid-model-io/security/advisories)
tab on the repository.

## Verifying releases

Projects in the PowerGridModel organization, including [`power-grid-model`](https://github.com/PowerGridModel/power-grid-model), [`power-grid-model-io`](https://github.com/PowerGridModel/power-grid-model-io), and [`power-grid-model-ds`](https://github.com/PowerGridModel/power-grid-model-ds), publish cryptographically verifiable releases through GitHub and PyPI.

Both platforms use [Sigstore](https://www.sigstore.dev)-based keyless signing. No project-managed,long-lived private signing key or public verification key is required. Verification relies on short-lived, identity-bound signing certificates and the corresponding Sigstore trust infrastructure.

### GitHub releases

The PowerGridModel repositories use [GitHub immutable releases](https://docs.github.com/en/code-security/concepts/supply-chain-security/immutable-releases).

For each immutable release, GitHub generates a cryptographically signed release attestation covering the release tag, associated commit, and attached release assets. Immutable release tags and attached release assets cannot be modified or replaced after publication.

To verify a complete release with the GitHub CLI, run:
```shell
gh release verify <tag> \
--repo PowerGridModel/<repository>
```

### PyPI releases

Python distributions published through PyPI Trusted Publishing carry a PEP [740](https://peps.python.org/pep-0740/) attestation. Each attestation binds an exact wheel to the GitHub Actions Trusted Publisher identity that published it. PyPI verifies these attestations during upload and displays the provenance for each distribution file.

For example, a locally downloaded `power-grid-model` wheel can be verified from the directory containing the wheel using:
```shell
uv run pypi-attestations verify pypi \
--repository https://github.com/PowerGridModel/power-grid-model \
./<wheel-filename>.whl
```

This verifies that the local wheel matches the distribution attested on PyPI and that it was published by the expected repository identity. For more information, refer to the `pypi-attestations` [documentation](https://pypi.org/project/pypi-attestations/).

### Homebrew formula

Only the `power-grid-model` library is distributed via Homebrew, however, precompiled bottles aren't distributed. Instead, the `powergridmodel/pgm` tap provides a formula that builds the library locally from source. The formula references a version tag associated with an immutable and cryptographically attested GitHub release. In addition, Homebrew verifies the `power-grid-model` checksum before building the library.

### conda-forge releases

Only the `power-grid-model` library is distributed via conda-forge. These packages are independently rebuilt and published by the conda-forge project instead of by the PowerGridModel organization. The conda-forge feedstock pins the upstream source by SHA-256, but at the time of writting, cryptographic package attestations are not exposed for the `power-grid-model` packages through the conda-forge distribution channel.
