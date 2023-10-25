---
bibliography:
- NIST-analytics.bib
---

# Abstract {#abstract .unnumbered}

This document summarizes the NIST Analytics Service Framework that
targets to analytics functionalities to be hosted on computational
resources including Clouds, Containers, and High Performance Computing
(HPC). Although we use the RE presentational State Transfer (REST) to
formulate some details of the architecture, it is independent from REST
and can be formulated in other frameworks. While using REST we use a
familiar pattern for architect, implementers, and strategists. Due to
the many frameworks, programming languages and services supporting REST
the architecture can easily be enhanced and implemented with various
technical solutions. The analytics framework also targets big data. Big
data is a term used to describe extensive datasets, primarily in the
characteristics of volume, variety, velocity, and veracity. While
opportunities exist with Big Data analytics, the data characteristics
can overwhelm traditional technical approaches, and the growth of data
is outpacing scientific and technological advances in data analytics. To
advance progress in Big Data analytics, the NIST Big Data Public Working
Group (NBD-PWG) is working to develop consensus on important fundamental
concepts related to Big Data. The results are reported in the NIST Big
Data Interoperability Framework (NBDIF) series of volumes.\

# Key words {#key-words .unnumbered}

Adoption; barriers; implementation; interfaces; market maturity;
organizational maturity; project maturity; system modernization.\

# Executive Summary {#sec:summary}

# Introduction

## Background

With Big Data's compound annual growth rate at 61 percent and its
ever-increasing deluge of information in the mainstream, the collective
sum of world data will grow from 33 zettabytes (ZB, 1021) in 2018 to 175
ZB by 2025 . The presence of such a rich source of information requires
a massive analysis that can effectively bring about much insight and
knowledge discovery. While previous work focused on developing a Big
Data Reference Architecture. This work specifically focused on the
definition of ***Analytics Services***.

We leverage activities conducted previously as part of the NIST Big Data
Reference Architecture (NBD-RA) and NBD-RA Interfaces. However, the work
here targets explicitly ***Big Data Analytics*** while integrationg
legacy analytics with machine and deep learning analytics. We will focus
on a service oriented framework.

## Scope and Objectives

NBD-PWG[^1] is exploring how to extend NBDIF [^2] for packaging scalable
analytics as services to meet the challenges of today's information
analytics. These services are intended to be reusable, deployable, and
operational for Big Data, High Performance Computing, AI machine
learning (ML), and deep learning (DL) applications, regardless of the
underlying computing environment.

This document explores key focus areas and document level of interest
from industry, government, and academia in extending the NBDIF to
develop scalable analytics as services that are reusable, deployable,
and operational, regardless of the underlying computing environment.

The document is organized as follows and motivated by the tasks
identified in the previous section. Each section is augmented with the
key area it contributes to.

-   Section [3](#sec:definitions){reference-type="ref"
    reference="sec:definitions"}: Definitions and Concepts: Develop a
    brief list of definitions that can be used to improve communication
    between different interdisciplinary groups while allowing them to
    use the same language.

-   Section [4](#sec:usecases){reference-type="ref"
    reference="sec:usecases"}: Use Cases for Analytic Services: A
    compilation and organization of use cases focusing on analytic
    services including traditional statistical, AI/ML/DL, and emerging
    analytics application domains. It will help identifying the meta-
    and technical requirements.

-   Section [5](#sec:defining){reference-type="ref"
    reference="sec:defining"}: Defining and Finding Reusable Analytics
    Services. This section will include the definition and conceptual
    architecture of reusable analytics services. This includes the
    following concerns that are organized as subsections.

    -   Section [5.1](#sec:fair){reference-type="ref"
        reference="sec:fair"}: Adaptation of the FAIR principle to
        supprt an Analytics Service FAIR Principle.

    -   Section [5.2](#sec:catalog){reference-type="ref"
        reference="sec:catalog"}: Service Catalog: To communicate the
        existence of the services to others service registries can be
        used.

    -   Section [5.3](#sec:registry){reference-type="ref"
        reference="sec:registry"}: Service Registry: To communicate the
        the features of the services to others service registries can be
        used.

-   Section [6](#sec:federation){reference-type="ref"
    reference="sec:federation"} Service Analytics Federation: To
    leverage multiple existing services federated services can be used
    to integarte them.

-   Section [7](#sec:data){reference-type="ref" reference="sec:data"}:
    Data in Reusable Analytics Services: Here we explore a number of
    important issues related to data that is used by the analytics
    services.

-   Section [8](#sec:package){reference-type="ref"
    reference="sec:package"}: Package Analytic Algorithms as Service
    Payloads: Here we explore how to package analytic algorithms with
    well-defined input and output parameters as service payloads that
    can be reusable, deployable, and operational across multi-cores,
    CPUs, and GPU computing platforms.

-   Section [9](#sec:interfaces){reference-type="ref"
    reference="sec:interfaces"}: Analytics Service Interfaces and
    Encapsulation: Here we explore a minimal set of services and their
    interfaces to be used as part of a generalized analytics framework.
    It includes to encapsulate the service payload with well-defined
    format, interface, and end-to-end access control for open and secure
    computing environment.

-   Section [10](#sec:resources){reference-type="ref"
    reference="sec:resources"}: Resource Management: Here we investigate
    and define a minimal set of resource management services and
    interfaces for application orchestration and workflow between
    processes.

-   Section [11](#sec:security){reference-type="ref"
    reference="sec:security"}: Security Considerations in Reusable
    Analytics Services: Here we explore a number of important security
    considerations related to reusable analytics services.

-   Section [12](#sec:outreach){reference-type="ref"
    reference="sec:outreach"}: Outreach Activity: In our outreach
    activity we investigate the inclusion and collaboration with other
    interested parties.

# Definitions and Concepts {#sec:definitions}

In this section we provide a list of definitions and doncepts that help
communication between different interdisciplinary groups while allowing
them to use the same language.

A comprehensive glossary (Appendix
[13](#sec:glossary){reference-type="ref" reference="sec:glossary"}) is
provided in the appendix.

Analytics Service

:   

Analytics Catalog

:   

Analytics Registry

:   

Analytics Workflow

:   

Payload

:   

Analytics:

:   The systematic analysis of data, to uncover patterns and
    relationships between data, historical trends, and attempts at
    predictions of future behaviors and events.

Analytics management:

:   A sub function within the \[metadata\] registry. Analytics services
    azure cognitive, google analytics, aws \[dozens\], watson
    analytics\... in contrast to ML frameworks like tensorflow, pytorch,
    caffe2, and in contrast to Programming libraries like python,
    scikit, shiny, or R Studio \[??\]

Analytics Workflow:

:   The sequence of processes or tasks part of the analysis

# Use Cases for Analytics Services {#sec:usecases}

## Use Case Development Process

To specify use cases for our analytics framework, we encourage
contributors to contact us and provide us with their high-level
descriptions of their use cases. The use cases should be focusing on
highlighting one or multiple aspects of the features related to
analytics frameworks. While inspecting the various features we intend to
collect and analyze them in various contexts that are relevant for
analytics users. The lessons learned from this analysis are to be
integrated into this document in order to formulate a comprehensive
vendor neutral analytics framework. Use cases can be formulated in
various format but should include diagrams that make them easy to
comprehend as well as allowing the reader to extract the specific
analytical aspects. Such diagrams can include functional cross diagrams,
process diagrams and others. Use cases should especially address the use
of metadata describing the functional and the data related properties.
This includes metadata related to time, space, exchange/protocols,
privacy, and security related aspects. A functional description of the
use case is to be included as a subsection called Functionalities and
Activities. This section is mirroring our experience with documenting
use cases as part of the Big Data Application Provider of NBDIF
Reference Architecture. Hence, we assume the following draft form for a
use case:

Title:

:   Title of the use case

Contributor:

:   The list co contributors

Description:

:   One to two sentences about major functionalities and activities with
    respect to the sample cross-functional diagram

    Cross-Functional Diagram:

    :   Inclusion of a cross functional Diagram, alternatively other
        diagrams could be chosen.

    Functionality Activities:

    :   1.  Activity #1 -- description...

        2.  \...

        3.  Activity #n -- description...

        4.  Use Case Summaries

![Cross-functional
Diagram](images/cross-functional-diagram.png){#fig:cross-functional-diagram
width="100%"}

Next, we will list use case summaries and if available point to specific
publications on the NBDIF Web page that include more details. The
expectation of this section is to

-   Provide an overview of use cases that motivate this document

-   It will summarize requirements that we obtain from these use cases
    that influence how we proceed.

As a result, we identify how they fit into the workflow of data
analytics. This includes the description of a subset of functionality
that is used in general by data analytics. In particular, it described
the relationship between input and output of data analytics components
and interfaces. The use case summaries are expected to be available
through the BigDataWG Web page and includes currently the following
examples:

1.  [M0701](https://bigdatawg.nist.gov/_uploadfiles/M0701_v1_2020102001.docx)
    -- Use case template [@nist-usecase-template]

2.  [M0702](https://bigdatawg.nist.gov/_uploadfiles/M0702_v1_2020102002.pdf) -
    Numeric weather prediction [@nist-wrf]

3.  [M0703](https://bigdatawg.nist.gov/_uploadfiles/M0703_v1_2020102003.pdf) -
    HVAC Heat ventilation and air conditioning [@nist-hvac]

## Use Case: Numeric Weather Prediction

#### Background. {#background. .unnumbered}

Large amounts of weather data ar e produced continually and stored in
many different databases. Accurate weather predictions require large
amount s of processing power to accurately simulate conditions worldwide
at a high resolution and fre quent intervals. One of the most
computationally consuming parts of a reliable weather model is th e
microphysics scheme. The current microphysics scheme, Weather Research
and Forecasting (WRF) Single Moment 6-class Microphysics (WSM6),
simulates the processes in the atmosphere that leadto the formation and
precipitation of rain, snow, and graupel and requires complex
floating-point operations needing to be performed on vast amounts of
data for accurate simulations. As computer performanceimproves, so does
the Numerical Weather Prediction (NWP) models' resolution and accuracy.
However, there is still much progress to be made, as simulation accuracy
still falls off sign ificantly for predictions more than 36 hours in
advance. Figure [2](#fig:weather-1){reference-type="ref"
reference="fig:weather-1"} shows the general WRF modeling system flow
chat.

![WRF Modeling System Flow Chart with Various
Configuration.](usecase/nwp-arch.png "fig:"){#fig:weather-1 width="80%"}
[\[fig:weather-1\]]{#fig:weather-1 label="fig:weather-1"}

#### Functionalities and Activities {#functionalities-and-activities .unnumbered}

(based on Big Data Application Provider of NBDIF Ref. Architecture). In
this case study, we only focus on two main functionalities, namely WPS
and WRF, and their activities. Figure
[3](#fig:weather-2){reference-type="ref" reference="fig:weather-2"}
shows the cross-functional diagram for their actions.

WPS Activities:

![Cross-Functional Diagram Numerical Weather
Prediction.](usecase/weather.png "fig:"){#fig:weather-2 width="60%"}
[\[fig:weather-2\]]{#fig:weather-2 label="fig:weather-2"}

1.  geogrid -- defines simulation domains and interpolate various
    terrestrial data sets to the model grids. Input data available at
    \[1\].

2.  ungrib -- extracts needed meteorological data and packs it into an
    intermediate file format. Input data available at \[2\]

3.  medgrid -- prepares horizontally interpolate the meteorological data
    onto the model domain. Input data from the output of geogrid and
    ungrib.

WRF Activities:

1.  real -- prepares vertically interpolates the output from metgrid,
    and creates a boundary and initial condition files with some
    consistency checks.

2.  wrf -- generates a model forecast.

#### Datasets. {#datasets. .unnumbered}

1.  WRF Users Page, WPS V4 Geographical Static Data Downloads Page
    [@wrf-data]

2.  NCEP FNL Operational Model Global Tropospheric Analyses, continuing
    from July 1999 [@cisl_rda_ds083.2]

## Use Case: HVAC Recommendation

#### Background. {#background.-1 .unnumbered}

Continuous streaming data is produced by heat ventilation and air
conditioning (HVAC) systems every day from the residential houses. This
data is stored in a databased on the cloud as it arrives. The data is
used to calculate what should be the next HVAC set point in the house
with respect to user preferences. Periodic recommendations considering
environmental parameters, user comfort level and past user preferences
require advanced machine learning algorithm called reinforcement
learning . Accurate recommendations can save energy and reduce cost.
This functionality has three parts Environmental Forecasting (EF),
Learning from the past, (LP), and Set-Point Recommendation (SPR). EF
calculates weather temperature and price predictions. LP learns from the
behavior in the past. SPR model calculates next set-point based on past
experience and EF predictions. Figure
[4](#fig:hvac-1){reference-type="ref" reference="fig:hvac-1"} shows the
general modeling system flow chat.

![HVAC general modeling system flow
chat.](usecase/hvac.png "fig:"){#fig:hvac-1 width="60%"}
[\[fig:hvac-1\]]{#fig:hvac-1 label="fig:hvac-1"}

#### Functionalities and Activities {#functionalities-and-activities-1 .unnumbered}

(based on Big Data Application Provider of NBDIF Ref. Architecture).

In this case study, we only focus on three main functionalities, namely
EF, LP and SPR, and their activities. Figure
[5](#fig:hvac-2){reference-type="ref" reference="fig:hvac-2"} shows the
cross-functional diagram for their actions.

![Cross-Functional Diagram HVAC
Recommendation.](usecase/hvac-2.png "fig:"){#fig:hvac-2 width="60%"}
[\[fig:hvac-2\]]{#fig:hvac-2 label="fig:hvac-2"}

EF Activities:

1.  weatherD -- Collects current weather temperature and predicted
    temperature for timestamp X.

2.  priceD -- Collects current electricity price and predicted price for
    timestamp X.

3.  pred -- Extract needed data fields and packs it into an intermediate
    file format. Input data from the output of weatherD and priceD.

LP Activities:

1.  hist -- Prepares history data points and creates initial condition
    weights.

2.  reward -- Generates reward based on the current weatherD and priceD.

3.  learn -- Collects data from current weatherD, priced, reward.

SPR Activities:

1.  rules -- Creates rules based on user preferences and conversion
    preferences.

2.  rlmodel -- Interpolates the output from learn, rules and generates
    set point recommendation

# Defining and Finding Reusable Analytics Services {#sec:defining}

Defining and Finding Reusable Analytics Services. This section will
include the definition and conceptual architecture of reusable analytics
services. This includes the following concerns that are organized as
subsections.

## AS-FAIR-DO: Analytics Service FAIR Principle {#sec:fair}

To project easy reusability, we strive towards the implementation of the
AS-FAIR-DO principle for analytics services. The FAIR principle is
typically applied to data and as such we can apply it the metadata
associated with analytics services. The FAIR principal addresses who to
be findable, be accessible, be interoperable, and be reusable. In Figure
[\[fig:as-fair-do\]](#fig:as-fair-do){reference-type="ref"
reference="fig:as-fair-do"} we explicitly augmented the general FAIR
principle with terminology so it can apply to analytics services. The
augmentations are colored in red.

## Analytics Service Catalogue {#sec:catalog}

#### Motivation. {#motivation. .unnumbered}

Cloud providers offered a considerable set of analytics services to
their customers. There are many analytics services available. A user
needs to be able to quickly obtain an overview of such available
services. This helps identifying further actions in order to evaluate
them and identify if further investigation is justified. The catalouge
contains enough details to locate the service and evaluate if it is
useful. However, it may not provide technical details which are captured
by a service registry instead.

#### Access Requirements. {#access-requirements. .unnumbered}

The catalogue may be public or may be restricted while authorized
entities may access it. As analytics services may evolve over time, time
dependent versioned descriptions of the services must be able to be
included. An organizational entity may manage their own catalogues. It
is desirable to have the catalogues be uniform, so that they can be
combined into a larger catalogue combining entries of multiple
organizations.

#### Federation. {#federation. .unnumbered}

The offerings are typically limited to a particular vendor. Users can
benefit from a federates service catalogue to search and explore for
needed services by the user. In contrast to a registry a catalogue may
not include all technical details but could in contrast include services
that lack such details and thus can be the basis of an exploratory
process. A Federated analytics service repository is planned to be
hosted on GitHub (LINK TBD) The catalogue contains the following
attributes, many of which are also used in an analytics service
registry.

The catalogue is organized as a list of entries, where each entry
contains a number of attributes. These attributes may be required or
optional. We list in Table [1](#tab:cat){reference-type="ref"
reference="tab:cat"}.

::: {#tab:cat}
  Name                    Description                                                                                             Required
  ----------------------- ------------------------------------------------------------------------------------------------------- ----------
  ID                      UUID, globally unique                                                                                   
  Name                    Name of the service                                                                                     
  Title                   Human readable title                                                                                    
  Public                  True if Public (needs use case to delineate what pub private means)                                     
  Description             Human readable short Description of the Service                                                         
  Version                 The version number or tag of the service                                                                
  License                 The license description                                                                                 
  Microservice            /No/Mixed                                                                                               
  Protocol                REST                                                                                                    
  Owner                   Name of the distributing entity, organization or individual. It could be a vendor.                      
  Modified                Modification Timestamp (when first same as created)                                                     
  Created                 Date on which the entry was first created                                                               
  Documentation           Link to a URL with detailed description of the service                                                  O
  Source                  Link to the source code if available                                                                    O
  Tag(s)                  Human readable common tags that are used to identify the service that are associated with the service   O
  Category(s)             A category that this service belongs to (NLB, Finance, \...)                                            O
  Specification/ Schema   Pointer to where schema is located                                                                      O
  Additional metadata     Pointer to where additional is located including the one here.                                          O
  Endpoint                The endpoint of the service                                                                             O
  SLA/Cost                                                                                                                        O
  Authors                 contact details of the people or organization responsible for the service (freeform string)             O
  Data                    Description on how data is managed                                                                      O

  : Catalouge attributes
:::

= Required; O = Optional

## Analytics Service Registry {#sec:registry}

#### Motivation. {#motivation.-1 .unnumbered}

The goal of a federated analytics service registry is to establish
federated registries to locate and consume analytics services with
persistent identifiers across organizations.

A service registry can serve as a public, private, or federated
registry. The first two properties define if the registry is public or
private. In case of a private registry proper security measures need to
be taken into account to govern access. Our framework does not make any
recommendations about the security framework chosen and it is up to the
implementer to specify it. In case of a federated registry, more than
one registry can be joined, to provide the user the impression of a
single registry.

Within the analytics services we distinguish two classes. The first
class are instantiated (running) services that are offered by a service
provider and allow direct reuse. The second class are library providers
that distribute analytics activity not as an instantiated service, but
as a source code library which can be deployed as a service.

A user wants to find an analytics service and needs to identify
candidate services based on their descriptions and features. A user
wants to find services quickly and therefor expects modern keyword
search and taxonomy, faceted search, query functionalities; as well as
descriptions that facilitate location and identification of relevant and
appropriate analytics services, from the registry.

The registry contains enough details to not only locate the service, but
also how to use it.

#### Access Requirements. {#access-requirements.-1 .unnumbered}

Public Analytics Service Registry. Public analytics discovery services
are intended to allow users to find publicly hosted services. The
information provided includes the provider, \[x\], and \[y\], and / thus
reduce users' efforts in locating relevant services.

Levels of Assurance (LoA) in User Identity

:   Most readers should be familiar with functionality to *sign in with
    ORCHID, or Facebook* or something known to the user. In general
    identity management scenarios, this provision enables what is
    referred to as *guest identities*, which is useful for many users
    who are interested in invoking low level activities or less
    sensitive operations. With respect to federated service
    authentication and authorization, OIDC guest identities meet a low
    level of assurance. In contrast, users with higher LoAs are afforded
    permissions to perform to privileged activities or gain access to
    more sensitive xyz.

Multi factor Authentication in User Identity

:   A means for authenticating users via two or more types of
    authentication. An MFA instrument can elevate a user's level of
    assurance profile. RAF and IGTF are examples of such assurance
    framework standards. OpenID Connect, SAML, and X.509 are examples of
    services that expose interfaces for multiple authentication.

Private Analytics Service Registry. Analytics Services stored in private registries are only available to authenticated and authorized / member users. Private registries allow providers to build virtual organizations \[/ VOMS

:   that advertise specialized services to its user community. In
    contrast to a public analytics registry, access controls in private
    registries are more restricted. In addition, different group
    privileges may restrict the visible analytics service to the user.
    See related sub sections on user identity and levels of user
    priveledge \...

Federated Analytics Service Registry.

:   A user wants to make selection decisions regarding which service to
    use. Analytics service brokers / providers therefore offer a
    federated analytics service in which multiple services from multiple
    providers are included. Rather than having to visit multiple,
    separate providers' registries, the user can visit the federated
    registry of the analytics broker to lookup all potentially suitable
    services, via a single interface / browser. It may be expected that
    federated registries abstract the technical effort that casual users
    would experience during location and inspection of published
    analytics services. Underlying analytics service registry
    technologies leverage cross - organization persistent identifiers,
    enhanced with information that the original service provider may not
    have available, and xyz. such \"enrichment\" may could include for
    example, cost comparisons, or (some type of) ratings from its user
    community.

Enhanced Analytics Service Registry.

:   Both public and private registries my need to be enhanced by
    providing detailed information so the user has a better
    understanding of the offering and allows comparison to similar
    artefacts maintained and published in the registry. Information
    details may include for example, benchmark information, service
    level agreements, or cost measures such as carbon cost, or technical
    limitations such as storage access and availability for big data.

#### Registry Namespace. {#registry-namespace. .unnumbered}

To allow uniform integration of entries into a unified namespace, URLs
are used to distinguish the services. This includes two different
entities. Firstly, an entity that defines the code base of a service.
Such a code base could be for example hosted on publicly accessible code
repositories. Secondly, the namespace could include instantiated
analytics service endpoints that define a running instance of an
analytics service.

The attributes are listed in Table
[\[tab:reg\]](#tab:reg){reference-type="ref" reference="tab:reg"}. Some
attributes may be optional and may be dependent on if they are deployed
services, or contain a library that may be deployed.

= Required; O = Optional

#### Benefits of a federated analytics service registry {#benefits-of-a-federated-analytics-service-registry .unnumbered}

A service registry can publicize and improve end user access to data
from different sources, by overcoming some of the challenges inherent in
describing and surfacing document content and format. Publication, and
discovery of information resources are enriched with metadata enabling
the findability and reusability of a service supporting the FAIR
principle. While describing the interfaces and allow for the
instantiation or the reuse of already instantiated services we address
the accessibility and interoperability. With respect to analytics as a
service, end users should be able to find various analytic services and
similar services without having to individually search multiple
'locations' or databases, each built to operate on its own, unique
storage and retrieval constructs. Through these descriptions automated
service integration can be provisioned while targeting not only the
functionality involved, but also allowing service level considerations
to be addressed. Furthermore, such analytics services could provide
significant security implications such as the protection of a database
while only exposing a subset of approved analytics functions that are
executed on the data sets. This includes partial and controlled sharing
of data mashup that can be made available to the community and
registered to make reuse easier without everyone having to replicate the
service.

# Service Federation {#sec:federation}

This section discusses aspect of federated registries to locate and
consume analytics services with persistent identifiers across
organizations.

This is not the term is at this time in the document not properly used.

We use so far

\(1\) federation of catalog and registry

\(2\) federation of services stored in the registry and catalog

\(3\) federaion of services through high level services delegatiing to
other services.

We will clarify this and appropriately address.

# Data {#sec:data}

# Package Analytic Algorithms as Service Payloads {#sec:package}

Here we explore how to package analytic algorithms with well-defined
input and output parameters as service payloads that can be reusable,
deployable, and operational across multi-cores, CPUs, and GPU computing
platforms.

# Analytics Interfaces {#sec:interfaces}

# Resource Management {#sec:resources}

Here we investigate and define a minimal set of resource management
services and interfaces for application orchestration and workflow
between processes.

# Security {#sec:security}

## Artifacts

function data logs / audit

## Privacy

privacy input output function

asynchronous events, how does privacy apply batch functions streaming
functions

data

## Federation

NIST document on federation

## Authentication

## Authorization

## Potential role of blockchain

# Outreach {#sec:outreach}

TBD

# References {#references .unnumbered}

# Glossary {#sec:glossary}

THis Glossary provides terms that aur used in this document. In addition
we have provided a definitions in Section
[5](#sec:defining){reference-type="ref" reference="sec:defining"} to
focus on the details of some terms and terminology used in this document
specifically focussing on Analytics Servoces.

AAI:

:   Authentication and Authorization Infrastructure. Facilitates single,
    virtualized identities (issued by the *user's home organization.*)

AARC:

:   

ABAC:

:   attribute based access control

ACL:

:   

ACID:

:   Atomicity, Consistency, Isolation, Durability.

Analytics:

:   The systematic analysis of data, to uncover patterns and
    relationships between data, historical trends, and attempts at
    predictions of future behaviors and events.

Analytics management:

:   A sub function within the \[metadata\] registry.

Analytics services

:   azure cognitive, google analytics, aws \[dozens\], watson
    analytics\... in contrast to ML frameworks like tensorflow, pytorch,
    caffe2, and in contrast to Programming libraries like python,
    scikit, shiny, or R Studio \[??\]

Analytics Workflow:

:   The sequence of processes or tasks part of the analysis

API:

:   Application Programming Interface

ASCII:

:   American Standard Code for Information Interchange

BASE:

:   Basically Available, Soft state, Eventual consistency Classification
    scheme per 11179, a container of the classifiers for all kinds of
    administered items including common data elements \[CDE\]s.

CIA:

:   Confidentiality, Integrity, and Availability.

CLI:

:   Command Line Interface.

Consumer:

:   Ametadata consumer, per IHE, is responsible for the import of
    metadata created by the source. In the context of section A.3,

Container:

:   See
    <http://csrc.nist.gov/publications/drafts/800-180/sp800-180_draft.pdf>
    Cloud Computing The practice of using a network of remote servers
    hosted on the Internet to store, manage, and process data, rather
    than a local server or a personal computer. See
    <http://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-145.pdf>.

CDE:

:   Common data element = smallest meaningful data container in a given
    context.

DDC:

:   data dictionary component. library of data elements that are used to
    establish common understanding of the meaning of coding systems.

Data element:

:   Describes \[or defines\] the logical unit of data. Per 11179, the
    element refers to the structure of the data, distinct from a data
    instance.

Data element concept:

:   the combination of an object class, and a related property.

DEX:

:   Data element exchange = interoperability profile. Enables retrieval
    of extraction specifications for data elements which are defined in
    particular domains. "Options" including the cross enterprise doc
    sharing \[XDS\] doc type binding option and the cross community
    access \[XCA\] doc type binding option, extend basic DEX
    functionality, addressing interoperability with Secondary Data
    Usage\[s\]. Allowing secondary users to know if and where \[data\]
    is available when it is organized as a doc sharing environment, I.e.
    XDS, MPQ, XCA.

DevOps:

:   A clipped compound \[?\] \[portmanteau?\] of software DEVelopment
    and information technology OPerationS

LDAP:

:   Lightweight Directory Access Protocol. A directory/registry
    standard.

Metadata generator:

:   A sub function within the repository Metadata Registry \[MDR\] a
    database that manages the semantics of data elements, and this case,
    provides discovery and analytics management services.

MRR:

:   Metadata registry / repository = specialized DB of metadata which
    describe data constructs.

Microservice:

:   Architecture Is an approach to build applications based on many
    smaller modular services. Each module supports a specific goal and
    uses a simple, well-defined interface to communicate with other sets
    of services.

NBDIF

:   

NBD-PWG:

:   NIST Big Data Public Working Group.

NBDRA:

:   NIST Big Data Reference Architecture.

NBDRAI:

:   NIST Big Data Reference Architecture Interface.

NIEM:

:   National information exchange model = government wide standards
    based approach to exchanging information in the US.

NIST:

:   National Institute of Standards and Technology.

OGF:

:   Open Grid Forum.

OS:

:   Operating System.

P2P:

:   Peer to Peer.

PKI:

:   Public Key Infrastructure. a security related certificate aka X.509.

Proxy:

:   

Registry:

:   

Registry, federated:

:   

REST:

:   REpresentational State Transfer Retrieval a transaction where a
    system returns a selection I.e. a list of data elements from a
    database, or in the scope of this document, a list of elements in a
    metadata registry.

SAML:

:   Security assertion markup language. a security standard; web browser
    service that defines "syntax and semantics to exchange auth and auth
    data between security domains." Not compatible with other
    authentication protocols such as Secure socket?, OIDC, etc.

Serverless Computing:

:   Serverless computing specifies the paradigm of function as a service
    (FaaS). It is a cloud computing code execution model in which a
    cloud provider manages the function deployment and utilization while
    clients can utilize them. The charge model is based on execution of
    the function rather than the cost to manage and host the VM or
    container.

Services:

:   

Service registry:

:   in the context of an SOA architecture, this registry is a network
    based directory that contains available services.

Software stack:

:   A set of programs and services that are installed on a resource to
    support applications. Value domain the description of a permissible
    set of values for the property of a data element definition.

XACML

:   eXtensible Access Control Markup Language. a security related
    standard developed by OASIS, circa 2005.

# Changelog

1.  [add
    appendix](http://github.com/cyberaide/NIST-analytics/commit/84bdf19aeefb2cb43e15b6d510124ca981351df8)

2.  [add
    registry](http://github.com/cyberaide/NIST-analytics/commit/a782ac047775467a34b12c8cae427a353cc761e4)

3.  [add
    gitignore](http://github.com/cyberaide/NIST-analytics/commit/636d0070d7ea7c46e5d9f52039f853e3ee7a5a7d)

4.  [split up in
    sections](http://github.com/cyberaide/NIST-analytics/commit/fda44c83feff652e54e67a18fd6e0d64fdb80e47)

5.  [add
    makefile](http://github.com/cyberaide/NIST-analytics/commit/0112ac8a4c2bcec52a38ab693dc527bc83eaaa95)

6.  [\* removed duplication of wrf, \* added file
    macro](http://github.com/cyberaide/NIST-analytics/commit/b92024d27cc06841a4206b8aec0a9443506fe004)

7.  [russels
    changes](http://github.com/cyberaide/NIST-analytics/commit/f1f74902a13bcc8e1be1454458f7f6c41b0dc2fb)

8.  [update russell.md: example text
    changes](http://github.com/cyberaide/NIST-analytics/commit/bf2124568c4cc2864f3843e466f0fd597383fdbb)

9.  [initial russell overleaf commit check for
    russel.md](http://github.com/cyberaide/NIST-analytics/commit/54f25e383f833cf088af7a5dfd8bb308817d35c1)

10. [removed the use case line in
    ali.md](http://github.com/cyberaide/NIST-analytics/commit/b10eca9e52c30b858ea8277eca093eed2ceba168)

11. [setup](http://github.com/cyberaide/NIST-analytics/commit/104a00ebe48d5c0689eae9377ee1fa97ab2a411c)

12. [add alis
    document](http://github.com/cyberaide/NIST-analytics/commit/81da7f201983e042cf1e18bdce9017fd21f5e898)

13. [update use case
    images](http://github.com/cyberaide/NIST-analytics/commit/03e9330ff6f481a5888d3a09f01643da103a24c9)

14. [add
    tree](http://github.com/cyberaide/NIST-analytics/commit/af80b245c8abe41500956fa8d5b7100a79d56cb2)

15. [Merge overleaf-2022-01-11-1526 into
    main](http://github.com/cyberaide/NIST-analytics/commit/0e4dd12b11d895bded6de7a1530f72e774933cbf)

16. [Updates from
    Overleaf](http://github.com/cyberaide/NIST-analytics/commit/5ec710512be4c2512652771339c29cf1aa18df4d)

17. [Delete
    realtime.md](http://github.com/cyberaide/NIST-analytics/commit/afe421ffea425883062fe9cafbad9c876a833c92)

18. [add
    wrf](http://github.com/cyberaide/NIST-analytics/commit/acb6e9c8b1fe144c80afa6c725f0bd9793f3d0e0)

19. [real time
    analysis](http://github.com/cyberaide/NIST-analytics/commit/578ee1923df65968a4996b37b0deb8c0558a5691)

20. [Merge overleaf-2021-12-14-1748 into
    main](http://github.com/cyberaide/NIST-analytics/commit/706ebbce394a688cb38b4a73ab7132bf2d2dbd8f)

21. [Updates from
    Overleaf](http://github.com/cyberaide/NIST-analytics/commit/f9a0ab646916a0de795afb8e144ec67dc617ab5d)

22. [Update
    README.md](http://github.com/cyberaide/NIST-analytics/commit/e3091a355f5d17c6cbbf17575673cbf35def8ffc)

23. [Create
    README.md](http://github.com/cyberaide/NIST-analytics/commit/2d8f7ca9e2a6ea85a3e4ba072aac3f8b9380914b)

24. [Initial Overleaf
    Import](http://github.com/cyberaide/NIST-analytics/commit/dfbddcff1caa6513223638cdc9e243e23cd9843c)

[^1]: 

[^2]: 
