# eGeodesy

### About

GitHub project `eGeodesy` groups together several related projects, which
define GeodesyML and facilitate Geoscience Australia and its collaborating
partners in adopting GeodesyML as a common domain language.

[\\]: <> (The following dependency diagram and the brief descriptions below give an overview.)

[\\]: <> (![Github Project Overview Diagram](http://g.gravizo.com/svg?)
[\\]: <> (@startuml;)
[\\]: <> ([GML] <<XML Schema>>;)
[\\]: <> ([GeodesyML] <<XML Schema>>;)
[\\]: <> ([GeodesyML] - -> GML;)
[\\]: <> ([OGC Schemas Java Bindings] <<Java Library>> as OGC;)
[\\]: <> ([OGC] - -> GeodesyML;)
[\\]: <> ([GeodesyML Java Bindings] <<Java Library>> as Bindings;)
[\\]: <> ([Bindings] - -> [OGC];)
[\\]: <> ([Geodesy Web Services] <<HTTP API>> as Web;)
[\\]: <> ([Web] - -> [Bindings];)
[\\]: <> (@enduml;)
[\\]: <> (\))

*Note:* All components are in active development.

#### GeodesyML

GeodesyML is a GML application schema for representation and exchange of
geodetic information. For more information, see http://www.geodesyml.org.

This repository contains XML schema files for GeodesyML and all third-party schemas
that GeodesyML depends on. It contains schematron validation rules to enforce
conformance to published code lists, like GNSS antenna and receiver types and
GMD responsible party roles.

http://github.com/GeoscienceAustralia/GeodesyML

#### OGC Schemas for JAXB

Third-party project `ogc-schemas` provides JAXB (and Jsonix) bindings for some of the XML
schemas defined by OGC. Geoscience Australia's fork of `ogc-schemas` adds
GeodesyML to the list of supported schemas. We leverage existing bindings for
OGC schemas GCO, GMD, GMX, and OM, on which GeodesyML is built.

http://github.com/GeoscienceAustralia/ogc-schemas

#### GeodesyML Java Bindings

Project `geodesyml-java-bindings` augments the binding classes
generated in `ogc-schemas` with a utility class to perform marshalling and
unmarshalling of any entity defined by GeodesyML or the schemas it depends on.
This project is the first port of call for Java software needing to parse
GeodesyML documents.

http://github.com/GeoscienceAustralia/GeodesyML-Java-Bindings

#### Geodesy Web Services

GeodesyML binding classes are automatically generated from XML schema files and
using them exensively for purposes other than of data serialisation can be
awkward. Project `geodesy-web-services` maps the generated GeodesyML entities
to a set of domain classes more suited to persistence and data processing.
It provides a set of domain services relevant to GA's operational requirements,
like business validation of incoming data, processing of GNSS CORS site logs to
broker eGeodesy node and setup entities, and broadcasting of significant domain
events, like availability of final solutions or rejection of invalid site log
submissions. It offers a public HTTP API for validation, submission, and retrieval of
GeodesyML site log documents.

http://github.com/GeoscienceAustralia/Geodesy-Web-Services

#### GNSS Site Manager

GNSS Site Manager is an Angular/TypeScript single-page web application for managing GNSS site metadata.

http://github.com/GeoscienceAustralia/GNSS-Site-Manager

### Contact Information

Contributions and bug reports are welcome!

Please feel free to contact us through GitHub or at geodesy@ga.gov.au.

-Lazar Bodor (lazar.bodor@ga.gov.au)
