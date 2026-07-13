<div align="center">
<a href="https://www.transportforthenorth.com/">
<img src="https://www.transportforthenorth.com/">
</a>
</div>

# About us

Transport for the North (TfN) is England’s first Sub-national Transport Body.

We work with our members and partners to improve transport across the North of England. Better transport helps people access jobs, education and services. It also supports economic growth and creates opportunities for communities and businesses.

We provide evidence, analysis and advice to help shape transport investment and policy. Our work ensures decisions are informed by local knowledge and robust analysis.

Find out more on the [Transport for the North website](https://www.transportforthenorth.com/).

# Open source analytics

We develop data, modelling and analytical tools to support transport planning, appraisal and decision-making.

We believe public sector tools should be transparent, accessible and deliver value for money. We publish many of our tools, methods and processes on GitHub so that partners and other public bodies can use, review and improve them.

Our repositories fall into two categories:

- Internal TfN tools
- Common Analytical Framework (CAF) tools

# Common Analytical Framework (CAF)

The Common Analytical Framework (CAF) is a partnership between transport organisations across the UK.

CAF provides a shared set of tools and processes for transport modelling, appraisal and analysis. It helps organisations work in a more consistent, transparent and efficient way.

CAF tools are usually developed jointly with other transport bodies and are typically branded as "caf.X". They are designed to be flexible. Organisations can use individual components or combine them into larger analytical workflows.

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
  - [Governance and Development](#governance-and-development)
  - [Future Enhancements and Contributions](#future-enhancements-and-contributions)
- [Useful Links](#useful-links)
- [Contact Us](#contact-us)

## What is CAF?

CAF is a suite of analytical tools and models that supports transport modelling, appraisal and strategic planning.

CAF provides a consistent approach to:

- Processing transport data
- Preparing modelling inputs
- Running analytical workflows
- Producing forecasts
- Supporting business cases and policy development

CAF helps improve confidence, consistency and efficiency across projects.

## Who is CAF for?

CAF is designed for:

- Transport modellers
- Transport planners
- Data analysts and engineers
- Consultants working on transport projects
- Organisations interested in using TfN tools

> [!NOTE]
> Most CAF tools currently require some knowledge of Python.

## When should I use CAF?

You should consider using CAF when you need to:

- Process transport data
- Analyse land-use data
- Prepare modelling inputs
- Build highway, public transport or freight matrices
- Transform and analyse matrices
- Assess carbon impacts
- Support transport appraisal
- Work in a consistent way with other organisations

CAF tools can be used on their own or as part of a wider analytical process.

> [!NOTE]
> Some CAF tools are not yet publicly available.
>
> If you would like to know more about unpublished tools, please contact:
> TfNOffer@transportforthenorth.com


## CAF Tools

CAF tools are usually focused in scope, doing one specific thing, and have relatively small inputs/outputs.

List of some of the key tools available under CAF.

| Name                                                                         | Description                                                                                                                                                                                                                                                                                                     | Users / Usecase                                                 | Usability      | Status    | Language   |
|------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|----------------|-----------|------------|
| [caf.space](https://github.com/Transport-for-the-North/caf.space/)           | A tool for generating spatial translation definitions between two different zoning systems. Can handle translations based on weightings (such as population) or pure spatial area.                                                                                                                              | GIS Specialists and Transport Planners / Modellers              | Code, CLI, GUI | Release   | Python     |
| [caf.toolkit](https://github.com/Transport-for-the-North/caf.toolkit/)       | A generalised toolkit of Python functionality that is useful for transport models, and other analytics. Includes functionality for things such as: common matrix manipulations, multiprocessing, logging, and model setup files.                                                                                | Python developers and data analysts                             | Code, CLI      | Release   | Python     |
| [caf.distribute](https://github.com/Transport-for-the-North/caf.distribute/) | A collection of generalised tools for distributing transport data across a matrix. Includes a standard gravity model, a gravity model capable of handling multiple calibration areas, and an iterative proportional fitting algorithm                                                                           | Trip distribution modelling                                     | Code Only      | Beta      | Python     |
| [caf.viz](https://github.com/Transport-for-the-North/caf.viz/)               | A generalised toolkit of visualisation functionality. Currently limited on capability, but under development                                                                                                                                                                                                    | Data analysts for model QA outputs                              | Code Only      | Pre-Alpha | Python     |
| [caf.ntem](https://github.com/Transport-for-the-North/caf.ntem/)             | A tool for extracting data from DfT's National Trip End Model (NTEM), including base year, forecast years and interpolation to produce intermediary years. Datasets include trip ends, car ownership and planning data. Performs a similar task to DfT's TEMPro but allows for easier and automated extraction. | Transport planners using DfT's NTEM datasets                    | Code, CLI      | Beta      | Python     |
| [caf.base](https://github.com/Transport-for-the-North/caf.base/)             | Python package containing definitions of zone systems and segmentations used across CAF tools. Introduces classes specific to transport (such as DVector), which are used to easily store and manipulate data formats often used in transport modelling and analysis, such as trip end and land use data.       | Transport modelling and planning, basis for other tools         | Code Only      | Beta      | Python     |
| [caf.mat](https://github.com/Transport-for-the-North/caf.mat/)               | Python package or reading, writing and performing calculations with transport modelling matrices. The aim is to provide a consistent method for interacting with all types of transport matrices from Python, with some additional front-end features for more common matrix operations.                        | Transport modelling and analysis                                | Code, CLI      | Beta      | Python     |
| [caf.brain](https://github.com/Transport-for-the-North/caf.brain/)           | Package to simplify the use of common machine learning techniques within Python. The packages builds on top of scikit-learn and others and simplifies the process of setting up and running machine learning models.                                                                                            | Data analysts for machine learning                              | Code Only      | Beta      | Python     |
| [OTP4GB-py](https://github.com/Transport-for-the-North/OTP4GB-py/)           | A Python package which uses Open Trip Planner to run public transport routing analysis. Outputs travel cost metrics for any modes for which data is given. Has some work-in-progress functionality for isochrone generation.                                                                                    | Transport routing analysis                                      | Code, CLI      | Release   | Python     |
| [BODS-Extractor](https://github.com/Transport-for-the-North/BODS-Extractor/) | A Python package for extracting data from DfT's Bus Open Data Service (BODS) API. Allows for downloading bus schedules (GTFS format), live location data and producing "observed" bus schedules.                                                                                                                | Gathering bus timetables evidence                               | Code, CLI      | Release   | Python     |
| [vis-core](https://github.com/Transport-for-the-North/vis-core/)             | Core React library for TfN Visualisation Framework frontend, used for producing interactive web maps and dashboards.                                                                                                                                                                                            | Data analysts, GIS specialists and web developers for web maps. | Code           | Beta      | Javascript |

## CAF Models

CAF models are models in their own right, able to generate modelled data such as demand matrices (NorMITs-Demand) or carbon emissions (CAF.carbon). Inputs remain largely the same across runs, but arguments/segmentation etc. may change for specific use-cases.

List of some of the key models available under CAF.

| Name                                                                               | Description                                                                                                                                                                                                                                                             | Users / Usecase         | Usability      | Status  | Language |
|------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------|----------------|---------|----------|
| [NorMITs-demand](https://github.com/Transport-for-the-North/NorMITs-demand/)       | Bespoke transport demand model for taking land use data and using it to calculate synthetic travel demand matrices for different modes of travel. Additionally, contains travel forecasting functionality.                                                              | Travel demand modelling | Code, CLI      | Release | Python   |
| [Land-Use](https://github.com/Transport-for-the-North/Land-Use/)                   | NorMITs Land Use is Transport for the North's (TfN) mainland GB population and employment model. it builds detailed population and employment vectors for a given base year, and can also build a range of scenario specific forecasts.                                 | Land-use modelling      |                | Release | Python   |
| [caf.van](https://github.com/Transport-for-the-North/caf.van/)                     | A bespoke Python transport model that produces van demand for commute, service, delivery and personal trips. The model uses land use and van survey data to produce trip ends and a gravity model, calibrated to observed trip lengths, to produce the demand matrices. | Travel demand modelling | Code, CLI      | Release | Python   |
| [caf-freight-tools](https://github.com/Transport-for-the-North/caf-freight-tools/) | HGV analytics and processing tools to produce HGV travel demands matrices.                                                                                                                                                                                              | Travel demand modelling | Code, CLI, GUI | Release | Python   |
| [caf.carbon](https://github.com/Transport-for-the-North/caf.carbon/)               | Bespoke carbon emissions model to forecast travel fleet data and their emissions.                                                                                                                                                                                       | Carbon modelling        | Code, CLI      | Release | Python   |
| [caf.cvt](https://github.com/Transport-for-the-North/caf.cvt/)               | Climate Vulnerability model to assign climate hazard risks to the transport network.                                                                                                                                                                                       | Climate modelling        | Code, CLI      | Beta | Python   |

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
