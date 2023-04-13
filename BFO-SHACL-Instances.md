# BFO SHACL Validations
* Validated with https://shacl.org/playground/
* The contents of [BFO_2020_Knowledge Graph.ttl](/BFO_2020_Knowledge%20Graph.ttl) and [BFO_SHACL_SCHEMA_3.0.ttl](/BFO_SHACL_SCHEMA_3.0.ttl) were added, then used to validate the instance data shown below

Instance data:
```turtle
@prefix ex: <http://example.org/ns#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix schema: <http://schema.org/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix bfo: <http://purl.obolibrary.org/obo/BFO_> .

<http://www.semanticweb.org/ahasa/ontologies/2023/3/untitled-ontology-67/tim's_sense_data_of_giacomo's_secret_diary>
	rdf:type owl:NamedIndividual , <http://purl.obolibrary.org/obo/BFO_0000141> ;
	<http://purl.obolibrary.org/obo/BFO_0000110> <http://www.semanticweb.org/ahasa/ontologies/2023/3/untitled-ontology-67/giacomo's_secret_diary> ;
	rdfs:comment "This is intended to be an instance that contradicts the ontology" ;
	rdfs:label "tim's sense data of giacomo's secret diary"@en .



<http://www.semanticweb.org/ahasa/ontologies/2023/3/untitled-ontology-67/confused_function> 
	rdf:type owl:NamedIndividual , <http://purl.obolibrary.org/obo/BFO_0000031> , <http://purl.obolibrary.org/obo/BFO_0000034> ;
	rdfs:comment "This is intended to be an instance that is invalid according to the BFO SHACL schema" ;
	rdfs:label "confused function"@en .
	
```

Validation result:
```turtle
[
	a sh:ValidationResult ;
	sh:resultSeverity sh:Violation ;
	sh:sourceConstraintComponent sh:NotConstraintComponent ;
	sh:sourceShape <https://astrea.linkeddata.es/shapes#19d465f2d26e8847b2b90b9b5fba5820> ;
	sh:focusNode <http://www.semanticweb.org/ahasa/ontologies/2023/3/untitled-ontology-67/confused_function> ;
	sh:value <http://www.semanticweb.org/ahasa/ontologies/2023/3/untitled-ontology-67/confused_function> ;
	sh:resultMessage "Value does have shape <https://astrea.linkeddata.es/shapes#a11fbe3d6d78e84e71aca851054d46da>" ;
] .
```