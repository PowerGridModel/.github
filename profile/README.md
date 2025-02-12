<!--
SPDX-FileCopyrightText: Contributors to the Power Grid Model project <powergridmodel@lfenergy.org>

SPDX-License-Identifier: MPL-2.0
-->

# Power Grid Model

[![License: MPL2.0](https://img.shields.io/badge/License-MPL2.0-informational.svg)](https://github.com/PowerGridModel/.github/blob/main/LICENSE)
[![OpenSSF Best Practices](https://bestpractices.coreinfrastructure.org/projects/7298/badge)](https://bestpractices.coreinfrastructure.org/projects/7298)
[![Downloads](https://static.pepy.tech/badge/power-grid-model)](https://pepy.tech/project/power-grid-model)
[![Downloads](https://static.pepy.tech/badge/power-grid-model/month)](https://pepy.tech/project/power-grid-model)

[![](https://github.com/PowerGridModel/.github/blob/main/artwork/svg/color.svg)](#)

Power Grid Model is an open-source project aiming for high-performance calculation of steady-state distribution power system.

This project is part of [Linux Foundation Energy](https://lfenergy.org/projects/power-grid-model/).
Please subscribe our [mailing list](https://lists.lfenergy.org/g/powergridmodel) to be kept updated. You can easily subscribe by sending an empty email to: [powergridmodel+subscribe@lists.lfenergy.org](mailto:powergridmodel+subscribe@lists.lfenergy.org)

The calculation core package [`power-grid-model`](https://github.com/PowerGridModel/power-grid-model) is available at [PyPI repository](https://pypi.org/project/power-grid-model/), 
with its [documentation](https://power-grid-model.readthedocs.io/).

The data conversion package [`power-grid-model-io`](https://github.com/PowerGridModel/power-grid-model-io) is available at [PyPI repository](https://pypi.org/project/power-grid-model-io/),
with its [documentation](https://power-grid-model-io.readthedocs.io/).

The data science package [`power-grid-model-ds`](https://github.com/PowerGridModel/power-grid-model-ds) is available at [PyPI repository](https://pypi.org/project/power-grid-model-ds/),
with its [documentation](https://power-grid-model-ds.readthedocs.io/).

Please have a look at the [workshop](https://github.com/PowerGridModel/power-grid-model-workshop) to see some examples and tutorials.

Want to join the discussion? Look at our [discussion board](https://github.com/orgs/PowerGridModel/discussions)!

## Description

To face the challenges of the energy transition, many statistical and machine learning methods are required for distribution power system analysis, which usually requires power system calculations (preferably in parallel) for a substantial number of simulation cases/scenarios.

This project matches the demand by providing with following strengths:

- Optimized algorithms for the characteristics of the distribution grid.
- Full support of three-phase asymmetric calculation.
- Efficient C++ implementation with native parallel computing support.

**_NOTE:_** Looking for a project for transmission power system analysis, please also take a look at [PowSyBl Open Load Flow](https://github.com/powsybl/powsybl-open-loadflow). This is another LF Energy initiative that focuses on the transmission grid.  

## License

This project is licensed under the Mozilla Public License, version 2.0 - see [LICENSE](https://github.com/PowerGridModel/.github/blob/main/LICENSE) for details.

## Licenses third-party libraries

This project includes third-party libraries, which are licensed under their own respective Open-Source licenses. SPDX-License-Identifier headers are used to show which license is applicable. The concerning license files can be found in the LICENSES directory.

## Contributing

Please read [CODE_OF_CONDUCT.md](https://github.com/PowerGridModel/.github/blob/main/CODE_OF_CONDUCT.md), [CONTRIBUTING.md](https://github.com/PowerGridModel/.github/blob/main/CONTRIBUTING.md) and [GOVERNANCE.md](https://github.com/PowerGridModel/.github/blob/main/GOVERNANCE.md) for details on the process for submitting pull requests to us.

## Citations

If you are using Power Grid Model in your research work, please consider citing our library using the references in [CITATION.md](https://github.com/PowerGridModel/.github/blob/main/CITATION.md).

## Security policy and release strategy

For our security policy and release strategy, please visit [SECURITY.md](https://github.com/PowerGridModel/.github/blob/main/SECURITY.md) and [RELEASE.md](https://github.com/PowerGridModel/.github/blob/main/RELEASE.md), respectively.

## Contact

Please read [SUPPORT.md](https://github.com/PowerGridModel/.github/blob/main/SUPPORT.md) for how to connect and get into contact with the Power Grid Model project.
