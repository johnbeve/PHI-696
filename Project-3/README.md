# Project 3

Your third project will require you to answer each of the 10 questions below.  You will be expected to open a pull request with your initial answers by the second class meeting, giving you one week to work on these problems. You and your peers will then have one week to work together to refine your respective initial answers, so they are ready for final submission. Once your pull requests have been reviewed and merged to the development branch, I will review them, then merge to the master branch. 

```
For any question involving the use of Protege, please be sure to import:
1. Basic Formal Ontology (https://raw.githubusercontent.com/BFO-ontology/BFO/v2019-08-26/bfo_classes_only.owl)
2. The Relations Ontology (https://raw.githubusercontent.com/oborel/obo-relations/master/ro.owl)
```

1. In BFO and RO identify at least one object property for each of a-e that _should have the listed property, but which does not_; argue for your case, using examples. Note: It will be easiest to view the object properties in BFO and RO using Protege.
  
  (a)  Reflexive
  Answer: spatially coextensive with
  the property means that x spatially_coextensive_with y if and only if x and y have the same location. So the property should be reflexive.
  
  
  (b)  Transitive 
  
  Answer: connecting branch of
  
  (c)  Symmetric
  
  Answer: spatially coextensive with
  In BFO and RO, the property means that x spatially_coextensive_with y if and only if x and y have the same location. x have the same location with y, so the property should be symmetric.
 
  part of
  Because x is also part_of x, so part of is symmetric. 
  
  
  (d)  Functional 
  
  Answer: function of
  Since function of is subProperty of characteristic of , and the RO characteristic of is functional, functional of should be functional. For example, Mike's heart' beating is function of Mike's heart. 
  
  (e)  Symmetric and Reflexive
  
  Answer: spatially coextensive with
  Since x always has the same location with x, and if x spatially coextensive with y, y spatially coextensive with x, so the property should be symmetric and reflexive.

2. In BFO and RO identify at least one object property for each of a-e that _should not have the listed property, but which does_; argue for your case, using examples. Note: It will be easiest to view the object properties in BFO and RO using Protege.

  (a)  Irreflexive
  
  Answer: partially overlaps
  
  (b)  Transitive 
  
  Answer: aligned with
  In BFO and RO, the property "aligned with" is transitive, which means if a is aligned with b, and b is aligned with c, then a is aligned with c. In addition, aligned with can be applied to both occurrent entities, say processes, and continuant entities, such as individuals with blood relationships.
  
  The counterexample can be the cases that involves different possible worlds. For example, m is aligned with n in the actural world, and n is aligned with q in a possible world, then it may not be the case that m is aligned with q, say Many is aligned with Mike in blood relation, and Otto would be aligned with Mary in a possible world if Mary gave birth to Otto. Then Otto is not aligned with Mike. 
  
  
  (c)  Asymmetric
  
  
  
  
  (d)  Functional
  
  Answer: characteristic of 
  The definition is the relation between a spefically dependent continaunt (the characteristic) and any other entity (the bearer), in which the characteristic depends on the bearer for its existence. The RO characteristic is functional, which means, if x is characteristic of y, there is only one bearer y for any x. 
  
  However, the RO should not be functional because 
   
  
  
  (e)  Inverse Functional
  

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
```
  (a) An instance of Material Entity can have an instance of Immaterial Entity as part.
  (b) An instance of Immaterial Entity can have an instance of Material Entity as part.
  (c) An organization may have another organization as part.
  (d) An organization may have no members as part. 
  (e) Any site is partially bounded by some instance of Material Entity.
  (f) A book placed under the leg of a wobbly table has acquired a new function. 
  (g) A glass vase cushioned with packing material for all time, has the disposition to break. 
  (h) Spacetime is a class in BFO.
  (i) The continuant fiat boundary class of BFO is closed, meaning, there are no subclasses beyond those identified presently in BFO. 
```

8. Model the following scenario in BFO, introducing whatever terms are needed to do so: John runs for 3 hours, startin slowly, speeding up during the middle, then ending the run at a slower pace.  

9. The Pellet reasoner in Protege can be used in an incremental reasoning strategy. ELI5 when and why one should use Pellet for incremental reasoning. 

10. Protege reasoners will not allow you to combine certain properties, e.g. reflexivity and transitivity. If you attempt to assert such pairs of the same object property, then run the reasoner, nothing will happen. If you combine such properties while a reasoner is running, then ask to synchronize the reasoner, an error will be thrown. Provide a table or series of tables illustrating which pairs of properties cannot be combined in Protege, either because nothing happens when the reasoenr is run or because an error is thrown when synchronizing a reasoner after making such changes. Review the github docs on [creating tables in markdown](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/organizing-information-with-tables).
