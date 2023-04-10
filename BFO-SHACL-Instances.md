
```turtle
@prefix dash: <http://datashapes.org/dash#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix schema: <http://schema.org/> .
@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix dc: <http://purl.org/dc/elements/1.1/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .

obo:BFO_0000016
  a owl:Class ;
  a sh:NodeShape ;
  dc:identifier "062-BFO" ;
  rdfs:label "disposition"@en ;
  rdfs:subClassOf obo:BFO_0000017 ;
  skos:altLabel "internally-grounded realizable entity"@en ;
  skos:definition "(Elucidation) b is a disposition means: b is a realizable entity & b is such that if it ceases to exist, then its bearer is physically changed, & b's realization occurs when and because this bearer is in some special physical circumstances, & this realization occurs in virtue of the bearer's physical make-up"@en ;
  skos:example "An atom of element X has the disposition to decay to an atom of element Y; the cell wall is disposed to transport cellular material through endocytosis and exocytosis; certain people have a predisposition to colon cancer; children are innately disposed to categorize objects in certain ways."@en ;
  skos:prefLabel "disposition"@en ;
  sh:property [
      a sh:PropertyShape ;
      sh:path obo:BFO_0000113 ;
      sh:class obo:BFO_0000040 ;
    ] ;
  sh:property [
      a sh:PropertyShape ;
      sh:path obo:BFO_0000218 ;
      sh:class obo:BFO_0000040 ;
    ] ;
.

ex:someDisposition
    a obo:BFO_0000016 ;
    obo:BFO_0000113 ex:someImmaterialEntity .

```

```turtle
[
	a sh:ValidationResult ;
	sh:resultSeverity sh:Violation ;
	sh:sourceConstraintComponent sh:ClassConstraintComponent ;
	sh:sourceShape _:n242 ;
	sh:focusNode <http://example.org/ns#someDisposition> ;
	sh:value <http://example.org/ns#someImmaterialEntity> ;
	sh:resultPath obo:BFO_0000113 ;
	sh:resultMessage "Value does not have class obo:BFO_0000040" ;
] .
```
