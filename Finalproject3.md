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
  simultaneous_with
  (b)  Transitive 
causally_influences
  (c)  Symmetric
  aligned_with
  (d)  Functional 
  ends_with
  (e)  Symmetric and Reflexive
  Overlaps
```

2. In BFO and RO identify at least one object property for each of a-e that _should not have the listed property, but which does_; argue for your case, using examples. Note: It will be easiest to view the object properties in BFO and RO using Protege.
```
  (a)  Irreflexive
  The property 'has role modelling' should not itself hasve the property 'has role modelling' because to have a role in modelling is to actually model, and the relation 'has role modelling' itself does not model but merely describes that is going on. (Thisd depends on what we mean by model. If we mean pictoral model, then my answer is correct)
  (b)  Transitive 
'is aligned with' is considered an obscelete property that should not be transitive. Just becasuse A might be aligned with B does not mean that all things that are aligned with A migt not be aligned with B, if we are talking about 3D objects.
  (c)  Asymmetric
  As Jaron has pointed out, 'has role in modeling' should not have the asymmetric property listed because it may in fact be symmetric in some instances.
  (d)  Functional 
  'has characteristic of' should not be functional because its definition implies that the entity that it is describing can only haver one characteristic, one functional characteristic. 
  (e)  Inverse Functional
  Similarly, 'has characteristic of' should not be counted as  inverse functional because it is too restrictive, we cannot define objects that have multiple characteristics and functional relations.
```

3. Model the following natural language expressions using terms from BFO and RO; you are welcome to introduce new terms where needed:  
```
  (a) Sally has an arm Tuesday but does not have an arm Wednesday. 
  “Sally participates in having at least one arm on Tuesday precedes Sally participates in having at most one arm on Wednesday”
  (b) Every liver has some cell as part at all times it exists.
  "Liver has_part_at_all_times some Cell"
  (c) John was a child, then an adult, then a senior. 
  John is an instance_of object
childhood is an instance_of occurrent.
adulthood is an instance_of occurrent.
seniorhood is an instance_of occurrent.
“John participates in childhood precedes John participates in adulthood which precedes John participates in seniorhood.”
  (d) Goofus and Gallant are married at each point in a three year span. 
  Goofus is an instance_of object
Gallant is an instance_of object
Marriage is an instance_of occurrent
“Three years span 1” is an instance_of one-dimensional temporal region.
Notice that the original phrase doesn’t say anything about Goofus and Gallant being married to each other, and we won’t represent such a fact.
T1 is an instance_of zero-dimensional temporal region.
If zero-dimensional temporal region t1 is part_of the one-dimensional temporal region “three years span 1”, then Goofus participates in marriage at t1 and Galland participates in marriage at t1.

```

4. Using the language of First-Order Logic, represent the following natural language expressions; you are welcome to introduce new terms where needed: 
```
  (a) Sally has an arm Tuesday but does not have an arm Wednesday. 
 ∃x (Tx ∧ ∃y (Hsy∧Ay)) ∧ ∃x (Wx ∧ ~∃y(Hsy∧Ay))
  T: Tuesday
  H: has
  A: arm
  W: Wednesday
  s: Sally

  (b) Every liver has some cell as part at all times it exists.
    ∀x∃y(Lx→Cy∧Pyx)
  L: liver
  C: cell
  P: part of

  (c) John was a child, then an adult, then a senior.
  j = John
E (x, y) = being earlier than
C (x, t) = being a child at t
A (x, t) = being an adult at t
S (x, t) = being a senior at t
∃t1∃t2∃t3 (C (j, t1) ∧ A (J, t2) ∧ S(J, t3) ∧ E (t1, t2) ∧ E (t2, t3))
 
  (d) Goofus and Gallant have been married for three years; for each day of that span, it is true to assert they are married. 
  we are not modeling that Goofus and Gallant are married to each other.
M(x, t) = being married at t
Y(t) = belongs to 3 year span 1
g1 = Goofus
g2 = Gallant
D(t) = t is a day
∀t(D(t) ∧ Y(t)→(M(g1,t) ∧ M(g2,t)))

```

5. Using BFO and RO, model the following scenario: the content of an rdf file is represented in two serializations - one in Turtle, one in XML - which are sent from one computer to two distinct computers on the same network.  

– RDF File Content, Turtle and XML are all generically dependent continuants. RDF File Content has_model in Turtle and XML. And they are all carried by Computer.
– Computer 1 enables the process of Data Transmission, which ends_with another process, Data Reception, which has computers 2 and 3 as participants. So this part is intended to show that there is some data (Turtle and XML) which are sent from Computers 1 to Computer 2 and 3.
– Finally, computers 1, 2, and 3 are all parts_of network I, which is instance_of Object Aggregate.) 


6. Using Protege, place these in the BFO hierarchy where you think they fit best:
```
  (a) Bach's Well-Tempered Clavier
  Generically dependent continuant 
  (b) Chair of the UB Philosophy Department
  Role
  (c) SARS-CoV-2
  Object/Material entity
  (d) Mexico City
  Site or 2D/3D spatial region
  (e) The trunk of a minivan
  Site
  (f) Occupation
  Role
  (g) Ocean
  Site
  (h) Lake
  Site
```

7. True or False; explain your answers:
```
  (a) An instance of Material Entity can have an instance of Immaterial Entity as part.
  True. Smith’s textbook: “Immaterial entities listed under 1. (boundaries and sites) are in some cases continuant parts of their material.” (108)
  (b) An instance of Immaterial Entity can have an instance of Material Entity as part.
  False, contradiction in terms
  (c) An organization may have another organization as part.
  True. For example, a political committee can have a subcommittee as a part. 

  (d) An organization may have no members as part. 
  True. If the debate club is viewed as a role,  the debate club could lose all its members while still being recognized by the school. It would be false if the debate club is viewed as an object aggregate because as an OA is the sum of its parts, by virtue of losing its members, it loses its necessary parts to being an OA.

  (e) Any site is partially bounded by some instance of Material Entity.
  False. You can identify  a specified space and it could still be surrounded by space without touching any material entity.


  (f) A book placed under the leg of a wobbly table has acquired a new function. 
False. The elucidation excludes this by saying that the function is due to the physical make-up of the object. Since nothing about the make-up changed, the book did not gain any new functions. If the book has the function of supporting the table, this is a function it has always had, even if it wasn’t intended to support the table.

  (g) A glass vase cushioned with packing material for all time, has the disposition to break. 
  True. Dispositions are in virtue of the bearer’s physical make-up, not its environment.
  (h) Spacetime is a class in BFO.
  False. This is covered by spatiotemporal region.

  (i) The continuant fiat boundary class of BFO is closed, meaning, there are no subclasses beyond those identified presently in BFO. 
  False. "Continuant fiat boundary doesn't have a closure axiom because the subclasses don't necessarily exhaust all possibilities. An example would be the mereological sum of two-dimensional continuant fiat boundary and a one dimensional continuant fiat boundary that doesn't overlap it" (from the BFO file in Protege). 

```

8. Model the following scenario in BFO, introducing whatever terms are needed to do so: John runs for 3 hours, startin slowly, speeding up during the middle, then ending the run at a slower pace.  
Karl, Giacomo and Ali’s revised answer:

 This is a graph based on Mermaid, representing the following relations:

– John (as an Object) participates_in John’s running (as a process), and John has_characteristic_at_t1 John’s average speed 1, and John has_characteristic_at_t2 John’s average speed 2, and John has_characteristic_at_t3 John’s average speed 3. All of these speeds are instances of Quality. 

(Note: A line with two nodes in Mermaid is to represent a triple [subject, predicate, object], so I don’t know how to use Mermaid to express an ordered set of 4 elements like “John [1] has_characteristic [2] John’s average speed 1 [3] at t1 [4]”. At present what I can do is to insert the temporal parameter into the predicate “has_characteristic”.)

–  John’s running includes 3 temporal parts: John’s beginning stage, John’s middle stage, and John’s final stage, each of which is a process. Besides, John’s beginning stage precedes John’s middle stage which precedes John’s final stage.

– John’s running occurs_in this 3-hour, which is instance_of one-dimensional temporal region. This 3-hour also includes 3 temporal parts: t1, t2, and t3, each of which is also instance_of one-dimensional temporal region. Besides, t1 precedes t2, and t2 precedes t3. Moreover, John’s beginning stage occurs_in t1, John’s middle stage occurs_in t2, and John’s final stage occurs_in t3.

– Change in John’s speed: John's average speed 1 is decreased_in_magnitude_relative_to John's average speed 2 (that is, speed 1＜speed 2), and John's average speed 2 is increased_in_magnitude_relative_to John's average speed 3 (that is, speed 2＞speed 3). Moreover, John's Middle Stage has_part John's accelerating, and John's Final Stage has_part John's decelerating. John’s accelerating and his decelerating are both instances of process.

9. The Pellet reasoner in Protege can be used in an incremental reasoning strategy. ELI5 when and why one should use Pellet for incremental reasoning. 
ELI5: Imagine you are playing with some building blocks to build a tower. Every time you add a block to the tower, you don't need to start building the tower from the beginning. You just need to add the new block on top of the tower.
In the same way, when we use Pellet to reason about an ontology, we don't need to start reasoning from the beginning every time we add new information to the ontology. Instead, Pellet remembers what it has already figured out and uses that knowledge to figure out what the new information means. This is kind of like adding a new block to the tower without starting from the beginning. Thus, Pellet is especially important for large, complex ontologies where re-computing all the results every time new information is added would take a long time. 


10. Protege reasoners will not allow you to combine certain properties, e.g. reflexivity and transitivity. If you attempt to assert such pairs of the same object property, then run the reasoner, nothing will happen. If you combine such properties while a reasoner is running, then ask to synchronize the reasoner, an error will be thrown. Provide a table or series of tables illustrating which pairs of properties cannot be combined in Protege, either because nothing happens when the reasoenr is run or because an error is thrown when synchronizing a reasoner after making such changes. Review the github docs on [creating tables in markdown](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/organizing-information-with-tables).



| Pairwise  | Functional | InverseFunctional| Transitive  | Symmetric | Asymmetric  | Reflexive | Irreflexive  |
| ------------- | ------------- |
| Functional  | Empty  | Yes  | No  | Yes  | Yes  | Yes  | Yes  |
| InverseFunctional  | Yes  | Empty  | No  | Yes  | Yes  | Yes  | Yes  |
| Transitive  | No  | No  | Empty  | Yes  | No  | Yes  | No  |
| Symmetric  | Yes  | Yes  | Yes  | Empty  | No  | Yes  | Yes  |
| Asymmetric  | Yes  | Yes  | No  | No  | Empty  | No  | No  | Yes  |
| Reflexive  | Yes  | Yes  | Yes  | Yes  | No  | Empty  |  No  |
| Irreflexive  | Yes  | Yes  | No  | Yes  | Yes  | No  | Empty  |

