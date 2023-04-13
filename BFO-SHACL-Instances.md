# BFO SHACL Validations
* Validated with https://shacl.org/playground/

```turtle
@prefix ex: <http://example.org/ns#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix schema: <http://schema.org/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix bfo: <http://purl.obolibrary.org/obo/BFO_> .


ex:someDisposition
    a obo:BFO_0000016 ;
    obo:BFO_0000113 ex:someImmaterialEntity .
```

```turtle
[
	a sh:ValidationResult ;
	sh:resultSeverity sh:Violation ;
	sh:sourceConstraintComponent sh:ClassConstraintComponent ;
	sh:sourceShape <https://astrea.linkeddata.es/shapes#a453a69976b08f4d603ac970b01f6414> ;
	sh:focusNode <http://example.org/ns#someDisposition> ;
	sh:value <http://example.org/ns#someImmaterialEntity> ;
	sh:resultPath obo:BFO_0000113 ;
	sh:resultMessage "Value does not have class obo:BFO_0000040" ;
] .
```
