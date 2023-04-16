# Born Free But Everywhere in SHACL #

For this project, the class will divide into two teams. Teams will be divided according to the following tasks: 
```
1. Construct and validate a SHACL scheme for Basic Formal Ontology
2. Construct five useful, general, novel SHACL patterns
``` 
I strongly encourage you leverage your understanding of description logics for both tasks; if you understand what can be expressed in OWL, then you can more easily construct SHACL constraints on expressions in OWL. 
Protege allows one to construct and test SHACL constraints. If you explore a bit, you'll be able to identify a way to visualize the constraints in a graph as you develop them as well. 


## Task 1 ##

The team pursuing task 1 will focus on constructing and validating a SHACL scheme for Basic Formal Ontology (BFO). It is not enough, however, to simply construct a SHACL file that parallels the BFO OWL file. That can be automated, as a matter of fact. Completing this task, rather, requires the construction of a SHACL file that parallels the BFO owl file but also constrains compatible knowledge graphs built on BFO to as much of the First-Order Logic representation of BFO, as possible. As you know, the FOL version of BFO expresses semantic content that cannot be expressed in BFO OWL version, since the latter uses a more restrictive language than the former. 

To validate your SHACL schema for BFO, you will need to generate a knowledge graph based on BFO with instance data added. You will then need to run your SHACL schema against this knowledge graph and generate a report absent errors or warnings. This must be done while respecting the semantics of the FOL version of BFO to the extent possible. 

This work will provide the foundation for a publication that illustrates how SHACL may be used to bridge the semantics of a data model whose implementations require expressivity restrictions. Completion of this task will thus make you eligible for co-authorship on the resulting publication. Students are encouraged, but not required, to continue building on this work as a final course project. 

You will need the following files: 

1. [BFO-FOL](https://github.com/BFO-ontology/BFO-2020/tree/master/21838-2/pdf)
2. [BFO-OWL](https://github.com/BFO-ontology/BFO-2020/blob/master/21838-2/owl/bfo-2020.owl)

You may find the following resources useful:

3. [SHACL W3C](https://www.w3.org/TR/shacl/)
4. [BFO 2.0 User Guide](https://ncorwiki.buffalo.edu/index.php/Basic_Formal_Ontology_2.0) - Link under "Background Information" 


## Task 2 ##

The team pursuing task 2 will focus on constructing 5-10 useful, general, novel SHACL constraints. 

By "useful", I mean a SHACL constraint that reflects a compelling use case. For example, in the DASH library one finds dash:AllObjects which represents the set of all objects in a data graph, and which is used in scenarios where a shape is expected to apply to any object, no matter the subject or predicate. This is a useful constraint for determining whether a graph contains no literals. 

By "general", I mean a SHACL constraint that is not restricted to a single ontology, upper-level or otherwise, but rather can be used by many ontologies with minimal adjustment, if any. 

By "novel" I mean a SHACL constraint does not currently exist. I encourage you to explore widely to determine whether your constraint exists; I will be. You should not, for example, duplicate any constraints from the SHACL W3C documentation or from the DASH library, though you are free to use such constraints as inspiration. 

This work will provide the foundation for a publication describing a new extension of the SHACL library designed for wide use in the ontology community. Completion of this task will thus make you eligible for co-authorship on the resulting publication. Students are encouraged, but not required, to continue building on this work as a final course project. 

You may find the following resources useful: 

1. [SHACL W3C](https://www.w3.org/TR/shacl/)
2. [DASH Library](https://datashapes.org/dash.html)


1.	Constraint for Asymmetry 

a.	Our constraint checks for asymmetric patterns in a graph.

b.	An example of when to use this constraint would be for tracking enrollment in courses at a university. Such that each node would represent a student of course and each relation represents the enrollment of a student in a course. Enrollment relations should only be allowed between students and courses that are in a department. If a violation of this constraint is detected it would mean that there is an enrollment relation that does not satisfy the requirement of a student enrolling in a course without the course being enrolled in a student. By changing ex:AsymmteryShape to ex:AsymmetryEnrollementShape and following our basic structure. 

c.	aRb → ~bRa (equivalent as: ~aRb ∨ ~bRa)

@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix ex: <http://example.com/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .


ex:AsymmetryShape

a sh:NodeShape ;
sh:targetClass ex:relation ;
sh:property [    
sh:path rdf:value ;    
sh:minCount 1 ;    
sh:maxCount 2 ;    
sh:datatype xsd:string ; 

] .

2.	Constraint for Symmetry 
a.	Our constraint checks for symmetry patterns in a graph.

b.	An example of when to use this constraint would be if we had an RDF graph that represented your 
connections on LinkedIn. Such that if A is connected with B then B is connected with A. Wanting to ensure this relation is symmetric we would use a SHACL constraint like this. Easily substituting SymmteryShape for ConnectionSymmteryShape and then following our model below. Our model would alert the user if there were cases of connection not going both ways.

c.	a -> b ^ b -> a

@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix ex: <http://example.com/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

ex:SymmetricRelationShape

    a sh:NodeShape ;

    sh:targetClass ex:Relation ;
    sh:property [       
 sh:path ex:hasSource ;    
 ] ;
    sh:property [        

sh:path ex:hasTarget ;        

sh:minCount 1 ;        

sh:maxCount 1 ;        

sh:message "A relation must have exactly one target"   

] ;

sh:property [        

sh:path ex:hasInverseRelation ;       

sh:minCount 0 ;        

sh:maxCount 1 ;        

sh:class ex:Relation ;        

sh:node [           

sh:property [                

sh:path ex:hasSource ;            


] ;

sh:property [                

sh:path ex:hasTarget ;                

sh:minCount 1 ;                

sh:maxCount 1 ;                

sh:message "An inverse relation must have exactly one target"            

] ;

sh:property [                

sh:path ex:hasInverseRelation ;                

sh:minCount 0 ;                

sh:maxCount 1 ;                

sh:class ex:Relation ;                

sh:node [                   

sh:property [                        

sh:path ex:hasSource ;                        

sh:equals [ 

sh:path [ 

rdf:reverseProperty ex:hasTarget 
]
 ]
] ;

sh:property [                        

sh:path ex:hasTarget ;                        

sh:equals [ 

sh:path [ 

rdf:reverseProperty ex:hasSource 

] 

]
                    ]
                ]
            ] ;

sh:property [               

sh:path ex:hasSource ;                

sh:equals [

sh:path [ 

rdf:reverseProperty ex:hasTarget 

] 

]
            ] ;

sh:property [                

sh:path ex:hasTarget ;                

sh:equals [ 

sh:path [ 

rdf:reverseProperty ex:hasSource 

] 

]

]
        ]
    ] .



3.	Constraint Symmetry with a check thing not being symmetric. 
a.	Our constraint is meant to check for symmetry in a graph and check for when things are not symetric.

b.	An example of when to use this constraint would be if we had a graph that represented followers on Twitter. Our constraint would check for cases of when A follows B than B should follow A. This constraint would indeed produce the message “The relation does not have symmetric values" when this is not the case. 
To use this constraint in this was one would start the constraint with something like 
ex:TwitterFollowersSymmetryShape and follow the general format of this constraint. 

c.	a -> b ^ b -> a

@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix ex: <http://example.com/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

ex:SymmetryShape

a sh:NodeShape ;

sh:targetclass ex:relation ;

sh:property [    

sh:path rdf:value ;    

sh:minCount 2 ;   

sh:maxCount 8 ;

sh:datatype xsd:string ;    

sh:nodeKind sh:Literal ;    

sh:message "The relation does not have symmetric values"  

] ;

sh:property [    

sh:path [ 

sh:inversePath ex:property 

] ;

sh:minCount 2 ;

sh:datatype xsd:string ;

sh:nodeKind sh:Literal ;


sh:message "The relation does not have symmetric values"

] .

Constraint for Reflexivity 
a.	Our constraint checks for reflexivity in a graph.

b.	An example of when one would use this constraint would be if we had a graph that represented published philosophers to check for when philosophers are self-referencing themselves in a novel piece. Such that when a philosopher published novel work that references that philosophers in a self-referential way this constraint would alert to the self-reference. One would change ex:ReflexivityShape to ex:PhilosopherReferenceReflexivityShape and follow the format of the constraint below. Importantly, when self-referring, the philosopher is referring to herself (rather than the body of work).  

c.	a -> a

@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix ex: <http://example.com/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .


ex:ReflexiveShape

a sh:NodeShape ;

sh:targetClass ex:relation ;

sh:property [    

sh:path rdf:value ;    

sh:minCount 1 ;    

sh:maxCount 6 ;    

sh:datatype xsd:string ; 

] .

5.	Constraint for Irreflexive 
a.	Our constraint checks for irreflexively in a graph 

b.	An example of when to use this constraint would be if you had a graph that represented a company’s organizational structure. Such that no employee should be their own manager. This constraint would ensure that is not possible. One would simply change ex:IrrelexiveShape to ex:CompanyIrrelexiveOrganizationShape and follow the formatting below. 

c.	~(a -> a)

@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix ex: <http://example.com/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

ex:IrreflexiveShape

a sh:NodeShape ;

sh:targetClass ex:relation ;

sh:property [    

sh:path rdf:value ;    

sh:minCount 1 ;    


sh:maxCount 4 ;    

sh:datatype xsd:string ; 
] .

6.	Constraint for Transitivity 
a.	Our constraint checks for transitivity in a graph.

b.	An example of when one would use this constraint would be to check a graph of clan, band, nation affiliation. Such that when one is a recognized citizen of the Cherokee Nation one is also a member of one of the 3 bands of Cherokee and a member of one of the 7 clans. This constraint would be used to check if one is a member of a clan, they are a member of a band and if you are member a band you are a member of the Nation and if you are a member of a clan, you are a member of the Nation. One would simply change ex:TransitiveShape to ex:CherokeeNationEnrollmentClanTransitiveShape.

c.	c -> b. b -> a. ؞ c -> a
  i.	a = nation
  ii.	b = band
  iii.	c = clan

@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix ex: <http://example.com/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

ex:TransitiveShape

a sh:NodeShape ;

sh:targetClass ex:relation ;

sh:property [    

sh:path rdf:value ;    

sh:minCount 1 ;    

sh:maxCount 3 ;    

sh:datatype xsd:string ; 

] .

7.	Constraint for Transitivity and Symmetry 
a.	Our constraint checks for when a graph is both transitivity and symmetry in a graph. 
b.	An example of when one would use this constraint would be to check a graph of clan, band, nation affiliation. Such that when one is a recognized citizen of the Cherokee Nation one is also a member of one of the 3 bands of Cherokee and a member of one of the 7 clans. This constraint would be used to check if one is a member of a clan they are a member of the a band and if you are a member of a band you are a member of the Nation and if you are a member of a clan you are a member of the Nation. Similarly, if you are a member of a clan you are a member of the Nation and if you are a member of the Nation you are a member of a clan.  
c.	c -> b. b -> a. ؞ c -> a
  i.	a = nation
  ii.	b = band
  iii.	c = clan
d.	a -> c. c -> a
  i.	a = nation
  ii.	c = clan 


@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix ex: <http://example.com/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

ex:TransSymmetryShape

a sh:NodeShape ;

sh:targetClass ex:relation ;
sh:property [    
sh:path ex:hasSource ;    
sh:class ex:Node  
] ;

sh:property [    
sh:path ex:hasTarget ;    
sh:class ex:Node  ] ;
sh:property [    
sh:path ex:hasValue ;    
sh:or (       [ sh:datatype xsd:string ; 
sh:in ( "same, opposite" ) 
]
[ sh:datatype xsd:boolean ]
)
 ] ;
 sh:property [    
sh:path ex:hasType ;    
sh:in ( "symmetric, transitive" )  
] .




8.	Constraint for disjoint of symmetry or asymmetry 
a.	Our constraint checks for when a graph is either symmetric or asymmetric 

b.	An example of when this constraint could be used to check a dataset of products represented as an RDF resource with various properties. This constraint will ensure a specific property (or multiple properties) is/are always present when a product is listed. To take this further, let’s say that our product type must have a review and a rating as the property, when the graph is checking the dataset it will check for symmetry of review existing and rating existing while also checking for an asymmetry such that there is a review but no rating or a rating and no review. One would change ex:symmetricalProperty to ex:hasReviewShape and then following this basic formatting!

c.	[(a -> b) ^ (b -> a)] v [(a -> b) ^ ~(b -> a)]

@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix ex: <http://example.com/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .


ex:AsymReflexShape

a sh:NodeShape ;
sh:targetClass ex:relation ;
sh:property [    
sh:path ex:hasSource ;    
sh:class ex:Node 
] ;

sh:property [    
sh:path ex:hasTarget ;    
sh:class ex:Node  
] ;

sh:property [    
sh:path ex:hasValue ;    
sh:datatype xsd:boolean ;    
sh:in ( true )  ] ;
sh:property [    
sh:path ex:hasType ;    
sh:in ( "asymmetric" )  
] .


9.	Constraint for PropertyIn for Asymmetrical or Irreflexive 
a.	Our constraint checks for when a graph has a propertyIn that is both asymmetric and irreflexive. 

b.	An example of a time when you could use this constraint would be when checking a flow chart type graph (I think they are called directed acyclic graphs). Such that in a flow chart there could be many outgoing relations with only one incoming relation. This means the ex:asymmetricalPropertySHape constraint could ensure that each arrow of the graph in directed in a consistent way. While is ex:IrreeflexivePropertyShape constraint on the other hand, could be used to ensure that there are no cycles in the graph by prohibiting self-reference. By combing these constraints with sh:or property type you can check the validity of a flow chart. 

c.	[(a -> b) ^ ~(b -> a)] v [~(a -> a)]

@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix ex: <http://example.com/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

ex:asymmetricalPropertyShape

a sh:PropertyShape ;
sh:path ex:asymmetricalProperty ;
sh:propertyConstraint [
sh:asymmetrical true ;
] .

ex:irreflexivePropertyShape
a sh:PropertyShape ;
sh:path ex:irreflexiveProperty ;
sh:propertyConstraint [
sh:irreflexive true ;
] .

ex:MyClassShape
a sh:NodeShape ;
sh:property [
sh:or ( ex:asymmetricalPropertyShape ex:irreflexivePropertyShape ) ;
] .



10.	Constraint for hasProperty
a.	An example of when this constraint might be used is in a real estate application that manages multiple properties. Such that the three associated properties rdf:value (the monetary value of a given property), ex:b (the number of bedrooms on a given property) and ex:c (the number of bathrooms on a given property). The constraint can be applied to ensure that any of the data associated with ex:property class meets these requirements, preventing incomplete or incorrect data being entered into the system. 

b.	Going to be perfectly honest. I am not sure how to translate this into symbolic logic. 

@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix ex: <http://example.com/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

ex:hasProperty
a sh:NodeShape ;
sh:targetClass ex:property ;
sh:property [    
sh:path rdf:value ;        
sh:minCount 1 ;        
sh:maxCount 8 ;      
] ;

sh:property [    
sh:path ex:b ;    
sh:minCount 1 ;    
sh:maxCount 8 ;  
] ;

sh:property [    
sh:path ex:c ;    
sh:minCount 1 ;    
sh:maxCount 8 ;  
] .
