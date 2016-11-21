# eGeodesy

### About

GitHub project `eGeodesy` groups together several related projects, which
define GeodesyML and facilitate Geoscience Australia and its collaborating
partners in adopting GeodesyML as a common domain language.

The following dependency diagram and the brief descriptions below give an overview.

![component-overview](https://cloud.githubusercontent.com/assets/5760996/14482081/20ab8864-017c-11e6-94dc-ba0943b7b274.png)

*Note:* All components are in active development.

#### GeodesyML

GeodesyML is an GML application schema for representation and exchange of
geodetic information. For more information, see http://www.geodesyml.org.

The project contains XML schema files for GeodesyML and all third-party schemas
that GeodesyML depends on. It contains schematron validation rules to enforce
conformance to published code lists, like GNSS antenna and receiver types and
GMD responsible party roles. It also contains bash driver scripts to perform
validation of GeodesyML documents and report on XML schema and schematron
violations.

http://github.com/GeoscienceAustralia/geodesyml


#### OGC Schemas for JAXB

Third-party project `ogc-schemas` provides JAXB (and Jsonix) bindings for some of the XML
schemas defined by OGC. Geoscience Australia's fork of `ogc-schemas` adds
GeodesyML to the list of supported schemas. We leverage existing bindings for
OGC schemas GCO, GMD, GMX, and OM, on which GeodesyML is built.

http://github.com/GeoscienceAustralia/ogc-schemas/tree/geodesyml

#### GeodesyML Java Bindings

Project `geodesyml-java-bindings` augments the binding classes
generated in `ogc-schemas` with a utility class to perform marshalling and
unmarshalling of any entity defined by GeodesyML or the schemas it depends on.
This project is the first port of call for Java software needing to parse
GeodesyML documents.

http://github.com/GeoscienceAustralia/geodesyml-java-bindings

#### eGeodesy parent project 
The parent project is an aggregation of maven modules that work together and generally need to be built together.
The pom contains shared dependencies and declares modules that can be built and installed 
in sequence.
  These are: 
  geodesey-domain-model  
  geodesey-web-services
  (see below)

#### Geodesy Domain Model and Services

GeodesyML binding classes are automatically generated from XML schema files and
using them exensively for purposes other than of data serialisation can be
awkward. Project `geodesy-domain-model` maps the generated GeodesyML entities
to a set of domain classes more suited to persistence and data processing.
It provides a set of domain services relevant to GA's operational requirements,
like business validation of incoming data, processing of GNSS CORS site logs to
broker eGeodesy node and setup entities, and broadcasting of significant domain
events, like availability of final solutions or rejection of invalid site log
submissions.

http://github.com/GeoscienceAustralia/geodesy-domain-model

#### Geodesy Web Services

Project `geodesy-web-services` is part of the public HTTP-based API for interacting with
Geodesy domain services offered by Geoscience Australia. First services to
be published will offer validation, submission, and retrieval of
GeodesyML site log documents.

http://github.com/GeoscienceAustralia/geodesy-web-services


### Contact Information

Contributions and bug reports are welcome!

Please feel free to contact us through GitHub or at geodesy@ga.gov.au.

-Lazar Bodor (lazar.bodor@ga.gov.au)






