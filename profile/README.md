<div align="center" style="background-color: white;">
<a href="https://www.transportforthenorth.com/">
<img src="https://www.transportforthenorth.com/wp-content/themes/tfn-theme/img/logo.svg"
  alt="Transport for the North logo">
</a>
</div>

# About Us

Transport for the North (TfN) is the first Sub-national Transport Body (STB) in England. We were formed in 2018 to transform the transport system across the North of England, providing the infrastructure needed to drive economic growth.
TfN adds strategic value by ensuring that funding and strategy decisions about transport in the North are informed by local knowledge, requirements, and analytically backed evidence; more details on our work can be found on our website at [transportforthenorth.com](https://www.transportforthenorth.com/).

# Open Source Analytics

TfN has been building analytical tools for business cases since its inception in 2018. We believe that the best way to achieve the highest value for money from these tools is to share them with partners and other public bodies in the UK. Therefore, we share many of our analytics tools and processes on GitHub, allowing for transparency, scrutiny, and use by others.
The repositories fall into one of two categories: internal TfN, or Common Analytical Framework.

## Common Analytical Framework (CAF)

The Common Analytical Framework (CAF) is a collaboration between transport bodies in the UK to develop and maintain commonly used transport analytics and appraisal tools.
The tools and processes that fall into this category generally are branded as "caf.X" and are built in collaboration with other transport bodies. CAF tools are generic and flexible processes which allow others to pick up and use in their analytics. The CAF has been built in many smaller modules to allow a range of use-cases, from taking an entire model as is, to selecting just to relevant components.
For further information on the CAF, please see the [CAF Handbook](https://transport-for-the-north.github.io/CAF-Handbook), this is a guide that details the CAF and its various tools and process.

| Repository                                                                        | Description                                                 |
| :-------------------------------------------------------------------------------: | :---------------------------------------------------------- |
| [caf.toolkit](https://github.com/Transport-for-the-North/caf.toolkit)             | Generic tools and functions that are used across transport analysis. |
| [caf.space](https://github.com/Transport-for-the-North/caf.space)                 | Tool for generating standard weighting translations in .csv format describing how to convert between different zoning systems |
| [caf.distribute](https://github.com/Transport-for-the-North/caf.distribute)       | Matrix distribution including gravity model and furnessing. |
| [caf.carbon](https://github.com/Transport-for-the-North/caf.carbon)               | Carbon analysis toolkit |
| [caf.base](https://github.com/Transport-for-the-North/caf.base)                   | Core classes and definitions for use in other models, including zone systems, segmentation and DVectors. |
| [caf.viz](https://github.com/Transport-for-the-North/caf.viz)                     | Python visualisations and styling. |

## TfN

Internal TfN tools are those which we use internally, but we have not migrated into the CAF. These tend to be tools that we have had some external interest in, but lack the resource to generalise at this time.
We use and develop these tools within TfN, sharing them to allow for others to benefit from our work, view our analytics, and maybe build upon them in their own work.
The tools and process that fall into this category are sometimes more specific to the transport analytics needs of the North of England.

| Repository                                                                        | Description                                                            |
| :-------------------------------------------------------------------------------: | :--------------------------------------------------------------------- |
| [NorMITs-Demand](https://github.com/Transport-for-the-North/NorMITs-Demand)       | Collection of tools for taking land use data and converting into synthetic demand matrices, including forecasting travel demand. |
| [Land-Use](https://github.com/Transport-for-the-North/Land-Use)                   | Collection of tools for generating and forecasting detailed land use data. |
| [NTS-Processing](https://github.com/Transport-for-the-North/NTS-Processing)       | Standardised tools for sampling and interacting with the National Travel Survey in a consistent way. |
| [BODS-Extractor](https://github.com/Transport-for-the-North/BODS-Extractor)       | Extracts and analyses BODS (Bus Open Data Service) data. |
| [otp4gb-py](https://github.com/Transport-for-the-North/otp4gb-py)                 | Produces cost metrics for public transport routing between origins and destinations using Open Trip Planner. |
| [DLIT_LU](https://github.com/Transport-for-the-North/DLIT_LU)                     | The Land Use Component of the Development Log Integration Tool |
| [caf-freight-tools](https://github.com/Transport-for-the-North/caf-freight-tools) | LGV model and HGV processing tools. |

# Contribution

We encourage use of, and contributions to, the repositories within this organisation, licenses are provided within our repositories and contribution guidelines are outlined [here](https://github.com/Transport-for-the-North/.github/blob/main/CONTRIBUTING.rst).

# Useful Links

- [CAF Handbook](https://transport-for-the-north.github.io/CAF-Handbook)
- [Contributing Guidelines](https://github.com/Transport-for-the-North/.github/blob/main/CONTRIBUTING.rst)

# Contact Us

- <TfNOffer@transportforthenorth.com>
