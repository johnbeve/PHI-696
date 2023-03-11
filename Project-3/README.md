# Project 3

Your third project will require you to answer each of the 10 questions below.  You will be expected to open a pull request with your initial answers by the second class meeting, giving you one week to work on these problems. You and your peers will then have one week to work together to refine your respective initial answers, so they are ready for final submission. Once your pull requests have been reviewed and merged to the development branch, I will review them, then merge to the master branch. 

```
For any question involving the use of Protege, please be sure to import:
1. Basic Formal Ontology (https://raw.githubusercontent.com/BFO-ontology/BFO/v2019-08-26/bfo_classes_only.owl)
2. The Relations Ontology (https://raw.githubusercontent.com/oborel/obo-relations/master/ro.owl)
```

1. In BFO and RO identify at least one object property for each of a-e that _should have the listed property, but which does not_; argue for your case, using examples. Note: It will be easiest to view the object properties in BFO and RO using Protege.
  
  (a)  Reflexive
  Answer: overlaps
  The definition says: x overlaps y if and only if there exists some z such that x has part z and z part of y.
  The object property “overlaps” should be reflexive, if an object has a part which is also a part of other object, the former object must has at least such a part overlaps with itself. So the object property "overlaps" is reflexive. 
  Apartment 202 and Apartment 203 share one adjoining wall. 202 overlaps 203 because they have the wall as a part of both 202 and 203. Besides, 202 also overlaps itself, since any part of 202 is also a part of itself. 

  (b)  Transitive 
  Answer: branching part of 
  The definition says: x is a branching part of y if and only if x is part of y and x is connected directly or indirectly to the main stem of y.
  "branching part of" should be transitive because if a branching_part_of b and y branching_part_of c, then, first, a part_of b, and b part_of c, and second, a is connected directly or indirectly to the main stem of b, and b is connected directly or indirectly to the main stem of c.                       Since part_of(instance level) is transitive, so is connected directly or indirectly to the main stem, a branching_part_of c. 
  
  (c)  Symmetric
  
  Answer: aligned with
  If x aligned_with y, x is at the same line with y. So, y is at the same line with x too. 
  Therefore, "aligned with" should be symmetric. 
  
  (d)  Functional 
  
  Answer: has end location  
  "has end location" should be functional, since for whatever location there can only be one end.
  
  (e)  Symmetric and Reflexive
  
  Answer: spatially coextensive with
  Since x always has the same location with x, and if x spatially coextensive with y, y spatially coextensive with x, so the property should be symmetric and reflexive.

2. In BFO and RO identify at least one object property for each of a-e that _should not have the listed property, but which does_; argue for your case, using examples. Note: It will be easiest to view the object properties in BFO and RO using Protege.

  (a)  Irreflexive
  
  Answer: has role in modeling  
  The definition says: A relation between a biological, experimental, or computational artifact and an entity it is used to study, in virtue of its replicating or approximating features of the studied entity.
   The irreflexive property relation is such that an entity having the property cannot relate to itself. However, if a machine that is designed to model aspects of itself. It can be used to study itself, in virtue of its ability to reflect aspects of itself. 
  
  (b)  Transitive 
  
  Answer: aligned with
  In BFO and RO, the property "aligned with" is transitive, which means if a is aligned with b, and b is aligned with c, then a is aligned with c. In addition, aligned with can be applied to both occurrent entities, say processes, and continuant entities, such as individuals with blood relationships.
  
  The counterexample can be the cases that involves possible worlds. For example, m is aligned with n in the actural world, and n is aligned with q in a possible world, then it may not be the case that m is aligned with q, say Many is aligned with Mike in blood relation, and Otto would be aligned with Mary in a possible world if Mary gave birth to Otto. Then Otto is not aligned with Mike. 
  
  (c)  Asymmetric
  
  Answer: has role in modeling.
  The definition: A relation between a biological, experimental, or computational artifact and an entity it is used to study, in virtue of its replicating or approximating features of the studied entity.
  If the declared characteristic of an artifact x is universally declared to be asymmetric to an entity y, then it follows that there are no such cases where the relationship between artifact x and entity y is symmetric. But it is possible that an artifact x's relation to entity y may be in some cases symmetric.  
  
  (d)  Functional
  
  Answer: characteristic of 
  The definition: a relation between a spefically dependent continaunt (the characteristic) and any other entity (the bearer), in which the characteristic depends on the bearer for its existence. The RO "characteristic of" is functional, which means, if x is characteristic of y, there is only one bearer y for any x. However, for a given individual, the property "characteristic of" can have more values. Take the Moon as an example, not only cold is characteristic of the Moon, but round is also characteristic of the Moon. 
     
  
  (e)  Inverse Functional
  
  Answer: has charcteristic 
  The definition is the inverse of “characteristic of”. This answer relies on what was said in (d), but is its inversion. 


3. Model the following natural language expressions using terms from BFO and RO; you are welcome to introduce new terms where needed:  

  (a) Sally has an arm Tuesday but does not have an arm Wednesday. 
  
    ¬ (an arm Occurrent_part_of Sally at Tuesday) ⊓ (an arm Occurrent_part_of Sally at Wednesday)
  
  (b) Every liver has some cell as part at all times it exists.
  
  ∃ cell (∀.Continuant_part_of liver)
  
  (c) John was a child, then an adult, then a senior. 
  
  (Childhood Occurrent_part_of John's life) Aligned_with (Adulthood Occurrent_part_of John's life) Aligned_with (Seniorhood Occurent_part_of John's life)
  
  (d) Goofus and Gallant are married at each point in a three year span. 
  
  ((Goofus Marriage_with Gallant during 3 years) Occurrent_part_of Goofus's life) ⊓ ((Goofus Marriage_with Gallant during 3 years) Occurrent_part_of Gallant's life) 


4. Using the language of First-Order Logic, represent the following natural language expressions; you are welcome to introduce new terms where needed: 

  (a) Sally has an arm Tuesday but does not have an arm Wednesday. 
  
    
  
  (b) Every liver has some cell as part at all times it exists.
  (c) John was a child, then an adult, then a senior. 
  (d) Goofus and Gallant have been married for three years; for each day of that span, it is true to assert they are married. 


5. Using BFO and RO, model the following scenario: the content of an rdf file is represented in two serializations - one in Turtle, one in XML - which are sent from one computer to two distinct computers on the same network.   


6. Using Protege, place these in the BFO hierarchy where you think they fit best:

  (a) Bach's Well-Tempered Clavier
  
  instance_of Object
  
  (b) Chair of the UB Philosophy Department
  
  instance_of Role
  
  (c) SARS-CoV-2
  
  instance_of Object/Creature
  
  (d) Mexico City
  
  instance_of Site
  
  (e) The trunk of a minivan
  
  Fiat_objecty_part
  
  (f) Occupation
  
  History
  
  (g) Ocean
  
  Object
  
  (h) Lake
  
  Object

7. True or False; explain your answers:

  (a) An instance of Material Entity can have an instance of Immaterial Entity as part.
  
  True. Mike's soul is continuant_part_of Mike
  
  (b) An instance of Immaterial Entity can have an instance of Material Entity as part.
  
  
  
  (c) An organization may have another organization as part.
  
  True. Constitutional law court is continuant_part_of Courts in some countries.
  
  (d) An organization may have no members as part. 
  
  True. 
  
  (e) Any site is partially bounded by some instance of Material Entity.
  
  No. Sites are bounded by other sites, which are not material entities.
  
  (f) A book placed under the leg of a wobbly table has acquired a new function. 
  
  No. Because function is subProperty of disposition, and there should be physical change involved. 
  
  (g) A glass vase cushioned with packing material for all time, has the disposition to break. 
  
  Yes. 
  
  (h) Spacetime is a class in BFO.
  
  No, if spacetime is just a reference system.
  
  (i) The continuant fiat boundary class of BFO is closed, meaning, there are no subclasses beyond those identified presently in BFO. 


8. Model the following scenario in BFO, introducing whatever terms are needed to do so: John runs for 3 hours, startin slowly, speeding up during the middle, then ending the run at a slower pace.  

9. The Pellet reasoner in Protege can be used in an incremental reasoning strategy. ELI5 when and why one should use Pellet for incremental reasoning. 

10. Protege reasoners will not allow you to combine certain properties, e.g. reflexivity and transitivity. If you attempt to assert such pairs of the same object property, then run the reasoner, nothing will happen. If you combine such properties while a reasoner is running, then ask to synchronize the reasoner, an error will be thrown. Provide a table or series of tables illustrating which pairs of properties cannot be combined in Protege, either because nothing happens when the reasoenr is run or because an error is thrown when synchronizing a reasoner after making such changes. Review the github docs on [creating tables in markdown](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/organizing-information-with-tables).
11. 
