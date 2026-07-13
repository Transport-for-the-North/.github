<div align="center" style="background-color: white;">
<a href="https://www.transportforthenorth.com/">
<img src="https://www.transportforthenorth.com/logo.svg"
  alt="Transport for the North logo">
</a>
</div>

# About Us

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

To find out more about the tools and data we have available, please visit our [resource hub](https://www.transportforthenorth.com/resources).

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
| [caf.space](https://github.com/Transport-for-the-North/caf.space/)           | Creates translations between different zoning systems using geography, population or other weighting factors.                                                                                                                              | GIS Specialists and Transport Planners / Modellers              | Code, CLI, GUI | Release   | Python     |
| [caf.toolkit](https://github.com/Transport-for-the-North/caf.toolkit/)       | Provides reusable Python tools for transport analysis, including matrix processing, logging and model configuration.                                                                                | Python developers and data analysts                             | Code, CLI      | Release   | Python     |
| [caf.distribute](https://github.com/Transport-for-the-North/caf.distribute/) | Builds transport demand matrices using established distribution methods, including gravity models and iterative proportional fitting.                                                                           | Trip distribution modelling                                     | Code Only      | Beta      | Python     |
| [caf.viz](https://github.com/Transport-for-the-North/caf.viz/)               | Supports the creation of charts and visual outputs for analysis and model quality assurance.                                                                                                                                                                                                    | Data analysts for model QA outputs                              | Code Only      | Pre-Alpha | Python     |
| [caf.ntem](https://github.com/Transport-for-the-North/caf.ntem/)             | Extracts and processes data from the Department for Transport's National Trip End Model (NTEM). | Transport planners using DfT's NTEM datasets                    | Code, CLI      | Beta      | Python     |
| [caf.base](https://github.com/Transport-for-the-North/caf.base/)             | Provides common transport data structures, zone systems and segmentations used across CAF.       | Transport modelling and planning, basis for other tools         | Code Only      | Beta      | Python     |
| [caf.mat](https://github.com/Transport-for-the-North/caf.mat/)               | Reads, writes and processes transport modelling matrices using a consistent approach.                        | Transport modelling and analysis                                | Code, CLI      | Beta      | Python     |
| [caf.brain](https://github.com/Transport-for-the-North/caf.brain/)           | Simplifies the use of machine learning techniques within transport analytics workflows.                                                                                           | Data analysts for machine learning                              | Code Only      | Beta      | Python     |
| [OTP4GB-py](https://github.com/Transport-for-the-North/OTP4GB-py/)           | Runs public transport routing analysis using OpenTripPlanner and produces travel cost measures.                                                                                    | Transport routing analysis                                      | Code, CLI      | Release   | Python     |
| [BODS-Extractor](https://github.com/Transport-for-the-North/BODS-Extractor/) | Downloads and processes bus timetable and vehicle location data from the Bus Open Data Service. Allows for downloading bus schedules (GTFS format), live location data and producing "observed" bus schedules.                                                                                                                | Gathering bus timetables evidence                               | Code, CLI      | Release   | Python     |
| [vis-core](https://github.com/Transport-for-the-North/vis-core/)             | A web mapping and dashboard framework used to build interactive visualisations and data products.                                                                                                                                                                                            | Data analysts, GIS specialists and web developers for web maps. | Code           | Beta      | Javascript |

## CAF Models

CAF models are models in their own right, able to generate modelled data such as demand matrices (NorMITs-Demand) or carbon emissions (CAF.carbon). Inputs remain largely the same across runs, but arguments/segmentation etc. may change for specific use-cases.

List of some of the key models available under CAF.

| Name                                                                               | Description                                                                                                                                                                                                                                                             | Users / Usecase         | Usability      | Status  | Language |
|------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------|----------------|---------|----------|
| [NorMITs-demand](https://github.com/Transport-for-the-North/NorMITs-demand/)       | Produces synthetic travel demand matrices and forecasts future travel demand across different transport modes.                                                             | Travel demand modelling | Code, CLI      | Release | Python   |
| [Land-Use](https://github.com/Transport-for-the-North/Land-Use/)                   | Builds detailed population and employment datasets and can produce future development scenarios.                                | Land-use modelling      |                | Release | Python   |
| [caf.van](https://github.com/Transport-for-the-North/caf.van/)                     | Estimates van travel demand for commuting, service, delivery and personal travel. | Travel demand modelling | Code, CLI      | Release | Python   |
| [caf-freight-tools](https://github.com/Transport-for-the-North/caf-freight-tools/) | Supports the analysis and modelling of heavy goods vehicle (HGV) movements.                                                                                                                                                                                              | Travel demand modelling | Code, CLI, GUI | Release | Python   |
| [caf.carbon](https://github.com/Transport-for-the-North/caf.carbon/)               | Forecasts transport-related carbon emissions and fleet impacts.                                                                                                                                                                                       | Carbon modelling        | Code, CLI      | Release | Python   |
| [caf.cvt](https://github.com/Transport-for-the-North/caf.cvt/)               | Assesses climate hazards and vulnerability across transport networks.                                                                                                                                                                                      | Climate modelling        | Code, CLI      | Beta | Python   |

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
