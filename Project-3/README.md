# Project 3


Your third project will require you to answer each of the 10 questions below.  You will be expected to open a pull request with your initial answers by the second class meeting, giving you one week to work on these problems. You and your peers will then have one week to work together to refine your respective initial answers, so they are ready for final submission. Once your pull requests have been reviewed and merged to the development branch, I will review them, then merge to the master branch. 


```
For any question involving the use of Protege, please be sure to import:
1. Basic Formal Ontology (https://raw.githubusercontent.com/BFO-ontology/BFO/v2019-08-26/bfo_classes_only.owl)
2. The Relations Ontology (https://raw.githubusercontent.com/oborel/obo-relations/master/ro.owl)
```

1. In BFO and RO identify at least one object property for each of a-e that _should have the listed property, but which does not_; argue for your case, using examples. Note: It will be easiest to view the object properties in BFO and RO using Protege. 
```
  (a)  Reflexive
  Object property: has_quality
  I think this object property could be reflexive.  Protege states that "a relation between an independent continuant (the bearer) and a quality, in which the quality specifically depends on the bearer for its existence."  If "is the same height as" is a reflexive relation (as presented in David Braun's Modal Logic textbook), this seems consistent with the definition provided in Protege.  Consider, for example, the quality "is 5'8" tall."  This is a reflexive relation - if Katie has_quality 5'8" tall, i.e. Katie is 5'8", she bears this relation to herself (and all others who are 5'8" tall, but this is not required).  If there is no entity (or person, or instance, maybe?) that has the quality of being 5'8" tall, this relation/quality 1) does not exist and 2) is not reflexive. 
  
 Alternative (per Josh's comments): 
 Object property: overlaps_with 
  The object property, “overlaps”, should have the reflexive characteristic listed.  It’s definition states: x overlaps y if and only if there exists some z such that   x has part z and z part of y.  Reflexivity is the characteristic that expresses the relation that an entity be related to itself. The object property “overlaps”     
  should have reflexive as a listed characteristic since an object shares itself (and parts of itself) with itself. 
  
  (b)  Transitive 
  Object property: derives from
  Because this object property defines a relation in which a "significant" portion of the original entity is inherited by the entity that begins to exist as the original goes out of existence, this is (maybe) a transitive relation.  For example, if Cell B is derived from Cell A (the original cell), Cell B inherits a significant portion of Cell A. Later, when Cell C is derived from Cell B, Cell C inherits a significant portion of Cell B (which includes a significant portion of Cell A by definition).  Therefore, Cell C contains a significant portion (or at least some portion at this point of derivation) of Cell A, making this relation transitive.  If it is not the case that Cell C contains at least some portion of Cell A (the original Cell), then this relation is not transitive.
  
  (c)  Symmetric
  Object Property: correlated with
  If A is correlated with B then B must also be correlated with A, therefore the relation is symmetric.  Braun's Modal Logic textbook provides "married to" as an example of a symmetric relation, which seems to function similarly to the object propery "correlated_with," although maybe not perfectly (depending on the strength of the "statistical dependence" correlating the entities (as defined in Protege)).
  
  (d)  Functional 
  Object property: has primary input (or has primary output)
  A relation is functional when there is at most one out going relationship along the property for an individual (http://protegeproject.github.io/protege/views/object-property-characteristics/).  If an input (or output) is primary, it is unique in the sense that there can only be one.  If this is true, it could be a functional relation, as there is at most one out going relationship.  I'm not sure if I've misinterpreted the definition of a functional relation.
  
  (e)  Symmetric and Reflexive
  Object property: simultaneous with
  We could say that an event is simultaneous with itself (reflexive) and simultaneous with an second event that occurs at the same exact time (symmetric).  For example, the event of me driving home on Monday afternoon is simultaneous with itself and with the event of Bagel Jays closing - both events occur at 4pm.  I'm not sure how one might argue that an event cannot be temporally simultaneous with itself, so this should work. 
  
  
```

2. In BFO and RO identify at least one object property for each of a-e that _should not have the listed property, but which does_; argue for your case, using examples. Note: It will be easiest to view the object properties in BFO and RO using Protege.
```
  (a)  Irreflexive
  Object property: has member
  This object property is defined by "a mereological relation between a collection and an item" in Protege.  If we allow a collection to include one or more things (such that one thing may be referred to as a "collection"), this property should be reflexive as all individuals can be related to itself.
  
  (b)  Transitive 
  Object propery: has branching part
  I don't think "has branching part" should be transitive mostly because the inverse, "branching part of," is not transitive in Protege.  In any case, it doesn't seem to me that if A has branching part B and B has branching part C, then A has branching part C.  The C branch belongs to the B branch. but not the A branch. 
  
  (c)  Asymmetric
  Object property: has role in modeling
  The only two object properties that I can find that are marked Asymmetric are "has skeleton" and "has role in modeling." It's really difficult to argue that "has       skeleton" is not an asymmetric property, but I did learn (from ChatGPT) that horseshoe crabs and armadillos (allegedly) have endoskeletons and exoskeletons.  This     could roughly be interpreted as the skeleton we traditionally think of, the endoskeleton, has its own skeleton, the exoskeleton, which seems slightly symmetric.  If   that's acceptable, "has skeleton" isn't an asymmetric property. 
  The other object property, "has role in modeling," is defined in Protege by: “A relation between a biological, experimental, or computational artifact and an entity   it is used to study, in virtue of its replicating or approximating features of the studied entity.”  It's difficult to see how this is not an asymmetric relation       given the words "replication" and "approximating."  However, if we extend the word "model" to include things themselves, or, in other words, objects that are not       replicated, this could work.  The definition of model in this case would have to be interpreted more broadly (think "fashion model," where nothing is replicated but   some thing or object is being modeled). 

  
  (d)  Functional 
Object property: characteristic of 
The definition of “characteristic of” in Protege states: “a relation between a specifically dependent continuant (the characteristic) and any other entity (the bearer), in which the characteristic depends on the bearer for its existence.”
This object property seems very cagey as a functional relation, which I’m sure is 1) helpful and 2) intentional in the ontology.  However, the definition of a functional relation includes that: “if multiple individuals are specified as values for the property then these values will be inferred to denote the same object” (http://protegeproject.github.io/protege/views/object-property-characteristics/).  This bothers me for the property of “characteristic of.”
If it is possible for a thing to be “characteristic of” multiple objects, will this be even more problematic?  The definition of the object property in Protege may eliminate this concern. But this seems too restrictive or reductionary for a concept like “characteristic of.”  It is characteristic of myself (and many others) to enjoy rum, but this relation should not then designate each rum-enjoyer as the same object.  

  (e)  Inverse Functional
  Object property: has characteristic
  The only Inverse Functional object property in Protege is "has characteristic," the inverse property of "characteristic of."  My reasoning for not marking "has charactertistic" as Inverse Functional is therefore similar to my reasoning above for "characteristic of." Part of the definition of Inverse Functional includes: "In other words, there can be at most one incoming relationship along the property for that individual. Note that, if multiple individuals are specified as incoming values for the property then these values will be inferred to denote the same object" (http://protegeproject.github.io/protege/views/object-property-characteristics/).  My problem is with how restrictive this relation is when combined with the definition of the object property "has characteristic."
 
```

3. Model the following natural language expressions using terms from BFO and RO; you are welcome to introduce new terms where needed:  
```
Tuesday is instance_of one-dimensional temporal region
Wednesday is an instance of one-dimensional temporal region
Arm is an instance of fiat object part

  (a) Sally has an arm Tuesday but does not have an arm Wednesday. 
  Sally participates in having_at_least_one_arm on Tuesday precedes Sally participates in having_no_arms on Wednesday.
  
  (b) Every liver has some cell as part at all times it exists.
  Liver has_part_at_all_times some Cell
  
  (c) John was a child, then an adult, then a senior. 
  John participates in childhood precedes John participates in adulthood which precedes John participates in seniorhood.
  
  (d) Goofus and Gallant are married at each point in a three year span. 
  Goofus spouse_of Gallant at t1
  
```

4. Using the language of First-Order Logic, represent the following natural language expressions; you are welcome to introduce new terms where needed: 

⊔ ⊓ ⊧ ⊭ ⊦ ⊬ ⊏ ⊐ ⊑ ⊒ C ¬ ≡ ≠ ≥ ≤ ∃ ∀ ∧ →
```
  (a) Sally has an arm Tuesday but does not have an arm Wednesday. 
  ∃x (Tx ∧ ∃y (Hsy∧Ay)) ∧ ∃x (Wx ∧ ~∃y(Hsy∧Ay))
  
  Where:   
  T: Tuesday
  H: has
  A: arm
  W: Wednesday
  s: Sally

  
  (b) Every liver has some cell as part at all times it exists.
   ∀x∃y(Lx→Cy∧Pyx)
   
  Where:
  L: liver
  C: cell
  P: part of
  
  (c) John was a child, then an adult, then a senior. 
  ∃t1∃t2∃t3 (C (j, t1) ∧ A (J, t2) ∧ S(J, t3) ∧ E (t1, t2) ∧ E (t2, t3))
  
  Where:
  j = John
  E (x, y) = being earlier than
  C (x, t) = being a child at t
  A (x, t) = being an adult at t
  S (x, t) = being a senior at t

  (d) Goofus and Gallant have been married for three years; for each day of that span, it is true to assert they are married. 
  ∀t(D(t) ∧ Y(t)→(M(g1,t) ∧ M(g2,t)))
  
  Where:
  M(x, t) = being married at t
  Y(t) = belongs to 3 year span 1
  g1 = Goofus
  g2 = Gallant
  D(t) = t is a day
  
  Something I am curious about in this question (but am not sure how to represent) is how to incorporate that Goofus and Gallant have been married for three years to   each other.  It seems that "married" can be an instance or a relation to me.  Does "married" need to be represented by a relation to say that Goofus and Gallant are married to each other?

```

5. Using BFO and RO, model the following scenario: the content of an rdf file is represented in two serializations - one in Turtle, one in XML - which are sent from one computer to two distinct computers on the same network.  


![PXL_20230310_200733169 MP](https://user-images.githubusercontent.com/123913163/224419366-526d0357-ae37-4561-aa6a-d87cabc230e1.jpg)


There seems to be something missing in this graph such that the Turtle and XML are not connected to computer 1, computer 2, and computer 3.  To understand this problem, I drew out the mermaid graph attached on the shared Google Doc (attached). Although it does not appear in the drawing, there should be two arrows drawn to computer 1 from both Turtle serialization and XML serialization labeled "output of."  Additionally, there should be two arrows drawn to computers 2 and 3 from both serializations labeled "receives."


6. Using Protege, place these in the BFO hierarchy where you think they fit best:
```
  (a) Bach's Well-Tempered Clavier
      Generically dependent continuant (e.g.  the music composition), object (e.g. music sheet), or process (occurrent, e.g. playing the song)
      
  (b) Chair of the UB Philosophy Department
      Role
      
  (c) SARS-CoV-2
      Object/Material entity (e.g. virus) or disposition (e.g. disease symptoms)
      
  (d) Mexico City
      Site or 2D/3D spatial region (e.g. map or mapping) or Instance
      
  (e) The trunk of a minivan
      Site or fiat object part
      
  (f) Occupation
      Role
      
  (g) Ocean
      Site or 2D/3D spatial region
      
  (h) Lake
      Site or 2D/3D spatial region
  
```

7. True or False; explain your answers:
```
  (a) An instance of Material Entity can have an instance of Immaterial Entity as part.
      True. Smith’s textbook: “Immaterial entities listed under 1. (boundaries and sites) are in some cases continuant parts of their material.” (108)
      
      
  (b) An instance of Immaterial Entity can have an instance of Material Entity as part.
       False.  An entity that is essentially immaterial can find no material ground, but stands in relation to material entities (in BFO).  This is interesting because an example used (as an immaterial entity) is the boundary of Wales.  This feels "grounded" (materially) to me, but maybe that is just the character of the relation between the immaterial and material?
      
  (c) An organization may have another organization as part.
      True. For example, a political committee can have a subcommittee as a part. 
      
  (d) An organization may have no members as part. 
      True. If the debate club is viewed as a role,  the debate club could lose all its members while still being recognized by the school. It would be false if the         debate club is viewed as an object aggregate because as an OA is the sum of its parts, by virtue of losing its members, it loses its necessary parts to being an       OA.
     
      
  (e) Any site is partially bounded by some instance of Material Entity.
      False. You can identify  a specified space and it could still be surrounded by space without touching any material entity.
      
  (f) A book placed under the leg of a wobbly table has acquired a new function. 
    False. The elucidation excludes this by saying that the function is due to the physical make-up of the object. Since nothing about the make-up changed, the book       did not gain any new functions. If the book has the function of supporting the table, this is a function it has always had, even if it wasn’t intended to support       the table.
     
  (g) A glass vase cushioned with packing material for all time, has the disposition to break. 
      True. Dispositions are in virtue of the bearer’s physical make-up, not its environment.
      
  (h) Spacetime is a class in BFO.
      False. This is covered by spatiotemporal region.
      
  (i) The continuant fiat boundary class of BFO is closed, meaning, there are no subclasses beyond those identified presently in BFO. 
      False. "Continuant fiat boundary doesn't have a closure axiom because the subclasses don't necessarily exhaust all possibilities. An example would be the        
      mereological sum of two-dimensional continuant fiat boundary and a one dimensional continuant fiat boundary that doesn't overlap it" (from the BFO file in 
      Protege). 
```

8. Model the following scenario in BFO, introducing whatever terms are needed to do so: John runs for 3 hours, startin slowly, speeding up during the middle, then ending the run at a slower pace.  

![image](https://user-images.githubusercontent.com/123913163/229375516-d4740d9c-3668-4721-9eb5-2ab4f16377b6.png)

9. The Pellet reasoner in Protege can be used in an incremental reasoning strategy. ELI5 when and why one should use Pellet for incremental reasoning. 

Imagine you are playing with some building blocks to build a tower. Every time you add a block to the tower, you don't need to start building the tower from the beginning. You just need to add the new block on top of the tower.
In the same way, when we use Pellet to reason about an ontology, we don't need to start reasoning from the beginning every time we add new information to the ontology. Instead, Pellet remembers what it has already figured out and uses that knowledge to figure out what the new information means. This is kind of like adding a new block to the tower without starting from the beginning. Thus, Pellet is especially important for large, complex ontologies where re-computing all the results every time new information is added would take a long time. 

Per Josh's suggestion, I'd like to mention why we may not want to use the Pellet reasoner.  My concern is that by building from an unchanging foundation, there may be inconsistencies or errors "baked in" the Ontology.  Or, alternatively, perhaps the "end" of the Ontology will have abstracted too far away from the "beginning."


10. Protege reasoners will not allow you to combine certain properties, e.g. reflexivity and transitivity. If you attempt to assert such pairs of the same object property, then run the reasoner, nothing will happen. If you combine such properties while a reasoner is running, then ask to synchronize the reasoner, an error will be thrown. Provide a table or series of tables illustrating which pairs of properties cannot be combined in Protege, either because nothing happens when the reasoenr is run or because an error is thrown when synchronizing a reasoner after making such changes. Review the github docs on [creating tables in markdown](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/organizing-information-with-tables).

![image](https://user-images.githubusercontent.com/123913163/229375744-acb2a5bb-ecb7-4d88-84b0-b2e6df116737.png)

Where:

"Yes" indicates a case where a pair of object property characteristics can be combined, and 
"No" indicates a case where a pair of object property characteristics cannot be combined.


