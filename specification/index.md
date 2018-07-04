# PART I: Common Specification for Information Packages

In this part of the document we build the argument for a Common Specification for Information Packages and present the main concepts and requirements for the purpose.

# 2.	Need for establishing common ground

**The vision:** *All digital preservation systems receive, store and provide access to information, regardless of its size, type or format, according to a set of agreed principles which allow institutions to identify, verify and validate the information in a uniform way.*

**The goal:** *Interoperability between data sources, archives and reuse environments is improved to a point where digital preservation tools can be reused across borders and institutions. This opens up new possibilities for collaboration and limits greatly the need for development resources for any
single institution.*

The amount of digital information being created, held and exchanged is continuously growing. This information is created with the help of numerous software tools and systems, comes in a variety of technical formats, and covers most aspects of our daily lives. Regardless of the formats and systems in question we always need to consider whether the information is needed to be retained and managed for longer periods of time. The reasons for this might be, for example:

- to meet legal and regulatory obligations
- to provide for efficient reuse
- to satisfy historical, cultural, scientific and business interest.

As of now, most tools and systems used to create information are not built for coping with long-term
requirements of keeping information safe and accessible. Instead, implementations separate the short-
term and long-term management of information into different systems, for example business and records
systems on one hand and archival systems on the other (Figure 5).

<a name="fig5"></a>
![OAIS Entities](../fig/fig-5-spec.png "Information flow between live and archival systems")

**Figure 5:** Information flow between live and archival systems

The implication for data owners and system managers is that information which has to be kept for
extended time periods needs to be exchanged between a set of different locations, including archival
systems:

- as effectively as possible,
- without endangering the authenticity and integrity of the information,
- and without limiting the possibilities for discovering and reusing the information.

As such, what we need in order to make the long-term availability of crucial information possible under
(usually limited) resources is a set of principles which allow exchanging information in a common way
across the systems participating in archival workflows and processes, i.e. create a set of interoperability
specifications. For archival information packages we have identified the following interoperability scenarios
(Figure 6):

- Export of data and metadata from source systems and transfer to SIP creation tools (or directly, as
an SIP, into preservation systems);
- Transfer of SIPs from SIP creation tools to preservation systems;
- Exchange of preservation system where all AIPs need to be transferred (ingested) into a new
technological platform;
- Distributed storage and synchronisation of AIPs between multiple (technologically different)
preservation systems;
- Exchange of DIPs between preservation systems and access platforms or portals;
- Exchange of DIPs between various access platforms of portals.

<a name="fig6"></a>
![OAIS Entities](../fig/fig-6-spec.png "Archival workflow and tool ecosystem")

**Figure 6:** Archival workflow and tool ecosystem

As of 2014 (the start of the development of this specification) the state of interoperability in digital preservation was rather poor. While national and institutional practical implementation-level specifications existed to serve the need for data and metadata packaging and exchange, these were by large not
interoperable with each other. On the contrary, available and widely used international specifications (most notably METS  and PREMIS ) lack the necessary implementation-level detail, needed in order to serve as an authoritative source for practical interoperability.

This situation has a remarkable effect on the cost of digital preservation. Namely, the tools developed in individual institutions are not reusable across institutional and state borders and therefore need to be redeveloped at each single location. Globally, this raises the cost of digital preservation to a level which makes it not affordable for smaller institutions and, at the same time, does often not allow developing tools which would be sufficiently mature, user-friendly and prone to errors. As well, the multitude of national or institutional specifications does not allow internationally active source system providers (e.g. Oracle, Microsoft) to build a single native archiving functionality into their products, meaning that there is a need for bespoke development (and therefore added cost) for each installation of these source systems across all sectors and countries.

To overcome these limitations this document proposes a universal common specification, which can be implemented across borders, for how data and metadata should be structured and packaged when transferred to archival systems, ingested and preserved in these, and re-used. Such a specification will allow data owners to build standardised interfaces for the export of their data regardless of the archives in question; and digital archives to build standardised interfaces for data ingest and access, regardless of the
data providers and users in question.

Further, the aim of the common specification is to be sufficiently detailed and technical to allow for extended collaboration in regard to software development and pooling. Ideally the tools which implement the common specification for data export, transfer, ingest, preservation and reuse are exchangeable between institutions and administrations with minimal effort. This in turn shall lead to a significant decrease in resources needed from any single institution and at the same time opens up an extended market for commercial software providers.
 
# 3. Requirements for CS IP Information Packages
At the heart of any standardisation activity has to be a clear understanding of the needs and aims which have to be addressed. This is also the goal of this Section, which presents a series of high level principles to
guide the technical details delivered in Part II of this specification.

Most of the requirements are driven by the aim of interoperability –Information Packages shall be easy to exchange, identify, validate and (re)use with a wide variety of software tools and systems.

Another crucial factor to take into account is long-term sustainability. Practical technical and semantic interoperability is possible only when a certain set of technologies have been agreed upon and implemented. However, any technology will become outdated sooner or later and previously agreed-upon
approaches have to be updated to accommodate new, better and more efficient technologies and standards. Because of this, the developers of this Common Specification for Information Packages have reused, as much as possible, existing powerful, standardised and well-established best practices for the
technical implementation of an Information Package (Part II of this document). This does not mean that the technical implementation details will not need to be changed in future, only that the need will arise later rather than sooner. So, to achieve long-term sustainability of the Common Specification for Information Packages, we present below a set of generic requirements which must be followed when updating any of the technologies used in a technical implementation at any given point in time.

Ultimately the requirements below present a conceptual view of an Information Package, including an overall IP data model, and use of data and metadata. An implementation of this conceptual view is presented later, in Part II of this document.

The requirements are described in a straightforward way – each requirement has a sequential number and a short description. The description includes always a MoSCoW (MUST/MUST NOT, SHOULD/SHOULD NOT, COULD, WOULD) prioritisation statement .  The short description of each requirement is followed by a  rationale which describes the reason and background for the requirement.

## 3.1. General requirements

### Requirement 1.1
*It MUST be possible to include any data or metadata, regardless of its type or format, in a CS IP Information Package.*

This is one of the most crucial requirements of the CS IP. In order to be truly “common”, technical
implementations of the CS IP MUST NOT introduce limitations or restrictions which are only applicable to
certain data or metadata types. If an Information Package definition fails to meet this requirement it is not
possible to use it across different sectors and tools, thereby limiting practical interoperability.

### Requirement 1.2:
*A CS IP Information Package MUST NOT restrict the means, methods or tools for
exchanging it.*

Tools and methods for transferring Information Packages between locations are constantly evolving. It is also possible that different methods are preferred for packages of varying sizes. In order to achieve that a CS IP Information Package is truly interoperable across different platforms it therefore MUST NOT
introduce limitations or restrictions which would be impossible to be met by specific information exchange tools or channels.

As such the CS IP does also not define the requirement to use a particular transfer package or envelope. The scope of the CS IP is limited to the structure and requirements for data and metadata within the
package. Different implementers are welcome to choose their own methods on top of the CS IP.

### Requirement 1.3
*The CS IP MUST NOT define the scope of data and metadata which constitutes an
Information Package.*

One of the fundamental principles of the CS IP is that it MUST allow each individual repository to define the (intellectual) scope of an Information Package and its relations to real life entities. As such, any implementation of the CS IP MUST be equally usable for packaging, for example, the whole content of an ERMS as an single IP; or for extracting only one record and its metadata from the ERMS and packaging as an single IP.

Out of the previous we can also derive that a CS IP specification MUST NOT define that, for example, a SIP should conform to exactly one AIP. Instead the CS IP MUST allow for the inclusion of “anything that the implementer wants to define as a SIP, AIP or DIP” and allow for “any relationships (1-1; 1-n; n-1; n-m) between SIPs, AIPs and DIPs.

### Requirement 1.4:
*A CS IP Information Package SHOULD be scalable.*

One of the practical concerns for Information Packages is their size. Many digital repositories have problems with data objects and metadata of increasing sizes, making it especially difficult to carry out tasks
related to data or metadata validation, and identification and modification. For example, Information Packages including relational databases or born-digital 3D movies can easily reach TB sizes.

Consequently, any current or future implementation of the CS IP is required to provide for appropriate scalability mechanisms (for example: mechanisms for splitting large-scale data or metadata).

### Requirement 1.5:
*A CS IP Information Package MUST be machine-readable*

To support the goal of automating ingest, preservation and access workflows each of the implementations of the CS IP must be machine-actionable. This means that decisions about the use of metadata syntax and semantics as well as the physical structure must be expressed explicitly and in a clear way. This, in turn, allows the specification to be implemented in the same way across different tools and environments.

### Requirement 1.6:
*A CS IP Information Package SHOULD be human-readable*

In long-term preservation we also need to take into account that “forgotten” Information Packages might be found long after details about the implementation are gone and no tools to access the package are available. For these scenarios it is crucial to ensure that the structure and metadata of the Information Package are understandable with minimal effort by using simple tools like text editors and file viewers.

In practice this means that any implementation of the CS IP should ensure that folder and file naming conventions allow for the human identification of package components, and that the semantics of the package is explicit.

### Requirement 1.7:
*A CS IP Information Package MUST support the preservation method best suited for the data.*

Different preservation institutions and different types of data need to use different methods for long-term
preservation; migration and emulation being the most usual choices. A CS IP Information Package
implementation MUST NOT prescribe the use of a specific preservation method but instead allow to
document and/or add any data or metadata which is needed for any method.

## 3.2. Identification of the Information Package

### Requirement 2.1:
*The Information Package type (SIP, AIP or DIP) MUST be clearly indicated.*

One of the first tasks in analysing any Information Package is to identify its current status in the overall archival process. Therefore, any Information Package must explicitly and uniformly include metadata which
identifies it as a SIP, AIP or DIP.

### Requirement 2.2:
*Any CS IP  Information Package MUST clearly identify the Content Information Type(s) of its data and metadata.*

As stated in Requirement 1.1 any CS IP Information Package MUST be able to include any kind of data and metadata. At the same time we have introduced in earlier Sections the concept of Content Information Types which allow users to achieve more detailed control and fine-grained interoperability. As such, any CS IP Information Package MUST include a statement about which Content Information Type specification(s) has been followed within the Information Package, or on the contrary, indicate clearly that no specific Content Information Type Specification has been followed.

The practical implication of requirements 1.1, 2.1 and 2.2 is that, once these have been followed in implementations, we can in fact develop modular identification and validation tools and workflows. While generic components can carry out high level tasks regardless of the Content Information Type, it is possible to detect automatically which additional content-aware modules need to be executed.

### Requirement 2.3:
*Any CS IP Information Package MUST bear an identifier which is unique and persistent within the repository.*

In order to manage a digital repository and provide access services each Information Package stored in the repository MUST be identified uniquely at least within the repository. At the same time a CS IP implementation MUST NOT limit the choice of the exact identification mechanism, as long as the
mechanism is implemented consistently throughout the repository.

### Requirement 2.4:
*Any CS IP Information Package SHOULD bear an identifier which is globally unique and persistent.*

In addition to the previous requirement, it is recommended that the identification mechanism used at the repository provides for global uniqueness and persistence of Information Package IDs. The application of globally unique and persistent identifiers allows repositories to participate more easily in cross-institutional information exchange and reuse scenarios (for example participation in national or international portals, or cross-repository duplication of AIP preservation). However, the CS IP MUST NOT limit the choice of the exact identification mechanism.

### Requirement 2.5:
*All components of a CS IP Information Package MUST bear an identifier which is unique and persistent within the repository.*

As stated above, a CS IP Information Package MUST be flexible enough to allow for the inclusion of any data or metadata depending on the needs of the repository and its users. As well, an Information Package might include additional support documentation like metadata schemas, user guidelines, contextual documentation etc. Regardless of which and how many components constitute a full Information Package, all components MUST bear a unique and persistent identifier which allows for the appropriate linking of data, metadata and all other components. This, in turn, is one of the most crucial aspects towards achieving an interoperable way towards maintaining package integrity.

It is also worth mentioning that in any implementation it is only necessary to achieve identifier uniqueness and persistence within an individual Information Package. If this is the case, repository-wide uniqueness is easily achieved when combining the package ID (unique according to requirement 2.3) and the component ID.

The components of a CS IP Information Package are explained in more detail in the following section.

## 3.3.	Structure of the Information Package

### Requirement 3.1:
*A Common Specification Information Package MUST be built in such a way that its data and metadata can be logically separated from one another.*

At the highest level each Information Package can be divided into data and metadata. In order to minimise the effort needed for the identification and validation of both, and to simplify long-term preservation actions it is reasonable to clearly separate data and metadata. This allows, for example, ingest tools to streamline and separate metadata identification and validation tasks, and file format identification and normalisation. Throughout long-term preservation such a separation allows also The most crucial (MUST) aspect of such separation is that it is achieved on the logical level of the
Information Package.

### Requirement 3.2:
*A Common Specification Information Package SHOULD be built in such a way that its data and metadata can be physically separated from one another.*

In addition to the logical separation of components it is beneficial to have data and metadata physically separated (i.e. formatted as individual computer files or clearly separated bitstreams). This allows digital preservation tools and systems to update respective data or metadata portions of an Information Package without endangering the integrity of the whole package.

### Requirement 3.3:
*The structure of the Information Package SHOULD allow for the separation of different types of metadata*

In addition to the previous requirement it is recommended to explicitly divide metadata into more specific components. While the definitions of metadata types vary a lot between implementations it is our recommendation to divide metadata logically and physically at least into descriptive and preservation
metadata.

### Requirement 3.4:
*The structure of the Information Package MUST allow for the separation of data and metadata representations.*

The concept of representations is one of the fundamental building blocks in digital preservation. As technologies evolve and get obsolete, data and metadata is constantly updated in order to ensure long-term accessibility, therefore creating new versions or representations of the data and metadata.

Expressing representations within the logical and physical structure of an Information Package helps institutions to explicitly understand the various states of the information throughout its lifecycle, therefore improving also the ease of long-term management and reuse of the information.

### Requirement 3.5:
*The structure of a CS IP Information Package MUST explicitly define the possibilities for adding additional components into the Information Package.*

In addition to data and metadata, institutions might have the need to include additional information in an Information Package. For example, implementers might decide that XML Schemas about metadata structures and additional binary documentation about the original IT environment have to be added to the
package.

If this is the case, the CS IP Information Package MUST NOT limit which components can constitute an Information Package, and MUST offer clearly defined extension points for the inclusion of these additional
components into the Information Package. At the same time these extension points MUST be defined in a way which does not interfere with other components (i.e. the extension points MUST be clearly separated from other components of an Information Package).

### Requirement 3.6:
*A CS IP Information Package MUST follow a common conceptual structure regardless of its technical implementation.*

Based on requirements 3.1 – 3.4 we now present a common structure for any CS IP Information Package ([Figure 7](#fig7)).

Figure 7: Conceptual structure of the Common Specification

Following Requirement 3.4 the structure separates explicitly the representations of data and metadata into a separate structural component.

Following Requirement 3.1 the package MUST include a high-level structural component for metadata which includes at least relevant metadata for the whole package. In addition the representations MUST internally separate between data and metadata (though note that the CS IP does not mandate that both data and metadata must be available in all representations).

In addition we highly recommend dividing the metadata portion of the Information Package to separate different types of metadata (SHOULD Requirement 3.3).

Following Requirement 3.5 repositories and their users have the possibility to add any additional components (as an example for schemas and binary support documentation) either as extensions to the whole Information Package or into a specific representation.

This common structure MUST be followed throughout all specific physical implementations of the CS IP.

### Requirement 3.7:
*A CS IP Information Package MUST be implemented by one and only one implementation at any point in time.*

The conceptual structure presented above can be implemented in various ways – for example the components might be defined by accompanying package metadata or explicitly through a physical structure. However, it is not reasonable to have multiple (competing) implementations available at once as this would lead to unnecessary complexity in developing interoperable tools for creating, processing and managing Information Packages.

At the same time it is clear that any given technical implementation will become obsolete in time, for example as new transfer methods and storage solutions emerge. As such this requirement does not prohibit the take-up of any emerging logical of physical technical solutions but merely requires to have one and only one of these to be implemented at any given point in time.

At the time being, the CS IP  mandates a fixed physical folder structure (see Section 4) as the implementation of this and the previous requirements.

## 3.4.	Information Package Metadata

### Requirement 4.1:
*Metadata in a CS IP Information Package MUST be based on standards.*

In order to exchange, validate, process and reuse Information Packages in an interoperable and automated way we need to standardise how crucial metadata are presented in the package. “Crucial metadata”, is defined in this specification as the core information about how the package content has been created and managed (administrative and preservation metadata), explicit descriptions about of the structure of the package (structural metadata) and the technical details of the data themselves (technical metadata).

In order to ensure that these metadata are understood and implemented in a common and interoperable way in any Information Package, the use of established and widely used metadata standards is highly recommended. In the current implementation a large proportion of such metadata is covered by the widely used METS and PREMIS standards (see Section 5).

### Requirement 4.2:
*Metadata in a CS IP Information Package MUST allow for unambiguous use.*

Many metadata standards support multiple options for describing specific details of an Information Package. However, such interpretation possibilities can also lead to different implementations and ultimately to the loss of interoperability.

To overcome this risk the CS IP requires that, while developing a specific implementation, the chosen metadata standard MUST be reviewed in regard to potential ambiguity. If needed, the selected metadata standard MUST be further refined to meet the needs of interoperability and automation.

### Requirement 4.3:
*A CS IP Information Package MUST NOT restrict the addition of any additional metadata.*

Previous requirements state the importance of highly controlled administrative, preservation, structural and technical metadata for interoperability purposes. At the same time the opposite applies for other types of metadata, most prominently for resource discovery (also called descriptive) or Content Information Type specific technical and structural metadata. In order to not limit the widespread adoption of the CS IP it has
to be possible for any implementer to add any metadata next to the mandatory metadata components needed for package level automation and interoperability.

In case organisations need to prescribe further details about descriptive or Content Information Type specific metadata for a deeper level of interoperability it is possible to use the mechanism of Content Information Type Specifications described above.

To summarise the requirements above from a more technical perspective, the CS IP foresees a modular approach towards Information Package metadata:

- All Information Packages share a common core of metadata which allows for the common development of high-level package creation, validation, identification and reuse tools;

- The rest of the metadata in the Information Package might follow additional agreements which have been made in order to develop specific tools such as, for example, tools to manage archival descriptions in EAD, or for specific Content Information Types like relational databases in the SIARD2 format.
