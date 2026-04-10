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

# Common Analytical Framework (CAF)

The Common Analytical Framework (CAF) is a collaboration between transport bodies in the UK to develop and maintain commonly used transport analytical and appraisal tools. The tools and processes that fall into this category generally are branded as "caf.X" and are built in collaboration with other transport bodies. CAF tools are generic and flexible processes which allow others to pick up and use in their analytics. The CAF has been built in many smaller modules to allow a range of use-cases, from taking an entire model as is, to selecting just to relevant components.

For further information on the CAF, please see the <https://www.transportforthenorth.com/tame>.

- [What is CAF?](#what-is-caf)
- [Who is CAF for?](#who-is-caf-for)
- [When should I use CAF?](#when-should-i-use-caf)
- [CAF Tools](#caf-tools)
- [CAF Models](#caf-models)
- [How CAF fits within the analytical process](#how-caf-fits-within-the-analytical-process)
- [Getting Started](#getting-started)
  - [Installation](#installation)
- [CAF Development](#caf-development)
  - [CAF Design Principles](#caf-design-principles)
    - [Processing Layer](#processing-layer)
    - [Interface Layer](#interface-layer)
  - [Governance and Development](#governance-and-development)
  - [Future Enhancements and Contributions](#future-enhancements-and-contributions)
- [Useful Links](#useful-links)
- [Contact Us](#contact-us)

## What is CAF?

CAF is Transport for the North's structured suite of analytical tools designed to support transport modelling, appraisal, and strategic decision-making.

CAF provides a consistent, transparent and reusable approach to:

- Processing transport datasets
- Developing modelling inputs
- Running analytical workflows
- Supporting forecasting and appraisal
- Generating outputs for policy and business case development

CAF improves confidence, consistency and efficiency across TfN projects and partner organisations.

## Who is CAF for?

CAF is designed for:

- Transport modellers and planners
- Transport data analysts and engineers
- Consultants delivering TfN-aligned work
- Partner organisations exploring TfN tools

> [!NOTE]
> The use of most CAF tools currently require some programming knowledge, usually Python.

## When should I use CAF?

You should consider CAF when you need to:

- Standardise and process transport data
- Analyse land use data
- Prepare modelling inputs, including NTEM datasets
- Develop highway / public transport / freight matrices
- Manipulate and transform matrices
- Conduct carbon or appraisal analysis
- Be consistent with other organisations

CAF tools can be used independently or as part of a wider analytical pipeline.

> [!NOTE]
> Some of CAF is not yet publicly available, these tend to be tools that we have had some external
> interest in, but lack the resource to generalise at this time.
>
> Please contact <TfNOffer@transportforthenorth.com> for more details on any unpublished tools /
> analytics.

## CAF Tools

CAF tools are usually focused in scope, doing one specific thing, and have relatively small inputs/outputs.

List of some of the key tools available under CAF.

| Name                                                                         | Description                                                                                                                                                                                                                                                                                                     | Users / Usecase                                         | Usability        | Status    |
|------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------|------------------|-----------|
| [caf.space](https://github.com/Transport-for-the-North/caf.space/)           | A tool for generating spatial translation definitions between two different zoning systems. Can handle translations based on weightings (such as population) or pure spatial area.                                                                                                                              | GIS Specialists and Transport Planners / Modellers      | Python, CLI, GUI | Release   |
| [caf.toolkit](https://github.com/Transport-for-the-North/caf.toolkit/)       | A generalised toolkit of Python functionality that is useful for transport models, and other analytics. Includes functionality for things such as: common matrix manipulations, multiprocessing, logging, and model setup files.                                                                                | Python developers and data analysts                     | Python, CLI      | Release   |
| [caf.distribute](https://github.com/Transport-for-the-North/caf.distribute/) | A collection of generalised tools for distributing transport data across a matrix. Includes a standard gravity model, a gravity model capable of handling multiple calibration areas, and an iterative proportional fitting algorithm                                                                           | Trip distribution modelling                             | Python Only      | Beta      |
| [caf.viz](https://github.com/Transport-for-the-North/caf.viz/)               | A generalised toolkit of visualisation functionality. Currently limited on capability, but under development                                                                                                                                                                                                    | Data analysts for model QA outputs                      | Python Only      | Pre-Alpha |
| [caf.ntem](https://github.com/Transport-for-the-North/caf.ntem/)             | A tool for extracting data from DfT's National Trip End Model (NTEM), including base year, forecast years and interpolation to produce intermediary years. Datasets include trip ends, car ownership and planning data. Performs a similar task to DfT's TEMPro but allows for easier and automated extraction. | Transport planners using DfT's NTEM datasets            | Python, CLI      | Beta      |
| [caf.base](https://github.com/Transport-for-the-North/caf.base/)             | Python package containing definitions of zone systems and segmentations used across CAF tools. Introduces classes specific to transport (such as DVector), which are used to easily store and manipulate data formats often used in transport modelling and analysis, such as trip end and land use data.       | Transport modelling and planning, basis for other tools | Python Only      | Beta      |
| [caf.brain](https://github.com/Transport-for-the-North/caf.brain/)           | Package to simplify the use of common machine learning techniques within Python. The packages builds on top of scikit-learn and others and simplifies the process of setting up and running machine learning models.                                                                                            | Data analysts for machine learning                      | Python Only      | Beta      |
| [OTP4GB-py](https://github.com/Transport-for-the-North/OTP4GB-py/)           | A Python package which uses Open Trip Planner to run public transport routing analysis. Outputs travel cost metrics for any modes for which data is given. Has some work-in-progress functionality for isochrone generation.                                                                                    | Transport routing analysis                              | Python, CLI      | Release   |
| [BODS-Extractor](https://github.com/Transport-for-the-North/BODS-Extractor/) | A Python package for extracting data from DfT's Bus Open Data Service (BODS) API. Allows for downloading bus schedules (GTFS format), live location data and producing "observed" bus schedules.                                                                                                                | Gathering bus timetables evidence                       | Python, CLI      | Release   |

## CAF Models

CAF models are models in their own right, able to generate modelled data such as demand matrices (NorMITs-Demand) or carbon emissions (CAF.carbon). Inputs remain largely the same across runs, but arguments/segmentation etc. may change for specific use-cases.

List of some of the key models available under CAF.

| Name                                                                               | Description                                                                                                                                                                                                                                                             | Users / Usecase         | Usability        | Status  |
|------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------|------------------|---------|
| [NorMITs-demand](https://github.com/Transport-for-the-North/NorMITs-demand/)       | Bespoke transport demand model for taking land use data and using it to calculate synthetic travel demand matrices for different modes of travel. Additionally, contains travel forecasting functionality.                                                              | Travel demand modelling | Python, CLI      | Release |
| [Land-Use](https://github.com/Transport-for-the-North/Land-Use/)                   | NorMITs Land Use is Transport for the North's (TfN) mainland GB population and employment model. it builds detailed population and employment vectors for a given base year, and can also build a range of scenario specific forecasts.                                 | Land-use modelling      |                  | Release |
| [caf.van](https://github.com/Transport-for-the-North/caf.van/)                     | A bespoke Python transport model that produces van demand for commute, service, delivery and personal trips. The model uses land use and van survey data to produce trip ends and a gravity model, calibrated to observed trip lengths, to produce the demand matrices. | Travel demand modelling | Python, CLI      | Release |
| [caf-freight-tools](https://github.com/Transport-for-the-North/caf-freight-tools/) | HGV analytics and processing tools to produce HGV travel demands matrices.                                                                                                                                                                                              | Travel demand modelling | Python, CLI, GUI | Release |
| [caf.carbon](https://github.com/Transport-for-the-North/caf.carbon/)               | Bespoke carbon emissions model to forecast travel fleet data and their emissions.                                                                                                                                                                                       | Carbon modelling        | Python, CLI      | Release |

## How CAF fits within the analytical process

CAF tools align to different stages of the transport planning and modelling lifecycle.

![CAF Analytical Process Diagram](ProcessDiagram.png)

CAF tools are tagged with the relevant modes and stage of assessment within their individual repository README.

---

## Getting Started

Each CAF tool is maintained within its own repository, and most of CAF is Python-based.

To explore a tool navigate to the repository and review the README for a brief overview of the tools
features and usage, most also have an *online user guide with more details and examples*.

CAF tool's often provide user interfaces to allow for use of the tools without any specific
programming knowledge, these are most-likely command-line interfaces (CLI) but some tools
also have graphical user interfaces (both desktop and web-based).

### Installation

The usage of the tools varies, so the individual user guide should be consulted, but most of
the Python tools are published on the [Python Package Index (PyPI)](https://pypi.org/project/caf.space)
and on [Conda-forge](https://anaconda.org/conda-forge/). Therefore, installation of most Python tools
can be done with one of the following commands:

```sh
conda install -c conda-forge {package_name}
```

```sh
pip install {package_name}
```

> [!NOTE]
> Any tools written in other languages will be published based on standards from that language,
> see the individual repositories for details.

The largest portion of CAF which isn't Python based is the Visualisation Framework
([vis-core](https://github.com/Transport-for-the-North/vis-core)), which is TfN's web framework.
Vis-core is a JavaScript framework which is used for TfN's web dashboards but is also publicly available.

---

## CAF Development

### CAF Design Principles

Where possible, CAF tools follow consistent architectural principles:

#### Processing Layer

- Core logic separated from user interface
- Structured inputs
- Standardised result objects (e.g., JSON)
- Clear logging and error messages

#### Interface Layer

- CLI-based execution
- Consistent command structures
- Designed to support web-based interfaces in future development

### Governance and Development

CAF is maintained by Transport for the North.

Please use the Issues or Pull Requests section within the relevant repository to:

- Raise an issue
- Suggest enhancements
- Contribute improvements

### Future Enhancements and Contributions

CAF continues to evolve, including:

- Improved discoverability and accessibility
- Enhanced documentation consistency
- Additional tools aligned with TfN's aspirations and goals
- Greater integration with other TfN resources, such as visualisation dashboards

We encourage use of, and contributions to, the repositories within this organisation, licenses are
provided within our repositories and we have organisation [contribution guidelines](https://github.com/Transport-for-the-North/.github/blob/main/CONTRIBUTING.md).

---

## Useful Links

- [Contribution Guidelines](https://github.com/Transport-for-the-North/.github/blob/main/CONTRIBUTING.md)
- [Transport for the North's website](https://www.transportforthenorth.com/)

## Contact Us

For further information, explore the repositories above, or contact
Transport for the North - <TfNOffer@transportforthenorth.com>

---

[Go to Top](#common-analytical-framework-caf)
