# Project 3

Your third project will require you to answer each of the 10 questions below.  You will be expected to open a pull request with your initial answers by the second class meeting, giving you one week to work on these problems. You and your peers will then have one week to work together to refine your respective initial answers, so they are ready for final submission. Once your pull requests have been reviewed and merged to the development branch, I will review them, then merge to the master branch. 

```
For any question involving the use of Protege, please be sure to import Basic Formal Ontology (https://raw.githubusercontent.com/BFO-ontology/BFO/v2019-08-26/bfo_classes_only.owl) and the Relations Ontology (https://raw.githubusercontent.com/oborel/obo-relations/master/ro.owl)
```

1. In BFO and RO identify at least one object property for each of a-e that _should have the listed property, but which does not_; argue for your case, using examples. 
```
  (a)  Reflexive
  (b)  Transitive 
  (c)  Symmetric
  (d)  Functional 
  (e)  Symmetric and Reflexive
```



**(a)  Reflexive**

The object property, “overlaps”, should have the reflexive characteristic listed.

It’s definition states: x overlaps y if and only if there exists some z such that x has part z and z part of y.

Reflexivity is the characteristic that expresses the relation that an entity be related to itself. 

The object property “overlaps” should have reflexive as a listed characteristic since an object shares itself (and parts of itself) with itself. 

<img width="1031" alt="P31A" src="https://user-images.githubusercontent.com/123851163/223026735-973ca57d-9091-42d0-a639-52f568e77e6b.png">



**(b)  Transitive**

The object property, “existence ends with”, should have the transitive characteristic listed. 

It’s definition states: “x existence ends with y if and only if the time point at which x ends is equivalent to the time point at which y ends. Formally: x existence ends with y iff ω(x) = ω(y).” 

That is, if any entity x ends at the equivalent time point of any other entity y, then they share the same object property, “existence ends with”.

Thus, any entity x that ends at a shared equivalent time point with entity y, and entity y ends at a shared equivalent time point with entity z, then entity x will share an end equivalent time point with entity z. If entity x shares the same object property, i.e. existence ends with, with entity z, then the relation must be transitive. 

Therefore, the object property “existence ends with” should have transitive as a listed characteristic. 

<img width="1031" alt="P31B" src="https://user-images.githubusercontent.com/123851163/222936215-5455cf17-c6f4-4d46-b22b-52e5d15f4374.png">



**(c)  Symmetric**

The object property, “partially overlaps”, should have the symmetric characteristic listed. 

It’s definition states: “x partially overlaps y iff there exists some z such that z is part of x and z is part of y, and it is also the case that neither x is part of y or y is part of x”.

A symmetric characteristic is a relation such that given any elements a and b of set G, if a ~ b, then b ~ a. Another way to think of symmetry is that the property has itself as an inverse, so if individual a is related to individual b then individual a must also be related to individual y along the same property.

In this case, the “partially overlaps” symmetric relation is found in z. z is congruent with z and its inverse is z. Thus, z is a symmetrical relation, although x is neither a part of y, nor is y a part of x. 

Therefore, the object property “partially overlaps” should have symmetric as a listed characteristic. 

 <img width="1033" alt="P31C" src="https://user-images.githubusercontent.com/123851163/222936242-3ec80825-ca0c-4ba0-baa0-9c044b3da926.png">



**(d)  Functional**

The object property, “has target end location”, should have the functional characteristic listed. 

It’s definition states: “This relationship holds between p and l when p is a transport or localization process in which the outcome is to move some cargo c from a an initial location to some destination l.”

The functional property relation means that for any given individual, the property can have at most one value. In other words, there can be at most one out going relationship along the property for that individual. This means that a functional object property has a multiplicity 0..1 attached to it. For example,the functional property hasHusband shows that the person, in a monogamous universe, can have at most one husband.

In the case of the object property “has target end location”, there is at most one specified end location in which the outcome is to move some cargo c from a an initial location to some destination l. The end location is univocal, that is, only has one possible meaning. Thus, the object property relation “has target end location” is functional. 

Therefore, the object property “has target end location” should have functional as a listed characteristic.

<img width="1030" alt="P31D" src="https://user-images.githubusercontent.com/123851163/222936263-b264f4a2-f479-4955-b105-0143657c452b.png">

 

**(e)  Symmetric and Reflexive**

The object property, “simultaneous with”, should have the symmetric and reflexive characteristic listed. 

It’s definition states: t1 simultaneous_with t2 iff:=  t1 before_or_simultaneous_with t2  and not (t1 before t2).

It’s reflexive, since any time must be simultaneous with itself. And it’s symmetric, since, if t1 is simultaneous with t2, then t2 must be simultaneous with t1.

Therefore, the object property “simultaneous with” should have symmetric and reflexive as a listed characteristic.

<img width="1030" alt="P31E" src="https://user-images.githubusercontent.com/123851163/223026767-b87679fc-a2b8-48c4-b7a5-db6bb72b7e28.png">



2. In BFO and RO identify at least one object property for each of a-e that _should not have the listed property, but which does_; argue for your case, using examples. 
```
  (a)  Irreflexive
  (b)  Transitive 
  (c)  Asymmetric
  (d)  Functional 
  (e)  Inverse Functional
```



**(a)  Irreflexive**

The object property, “has role in modeling”, should not have the irreflexive property listed.

It’s definition states: “A relation between a biological, experimental, or computational artifact and an entity it is used to study, in virtue of its replicating or approximating features of the studied entity.” 

Imagine a machine that is designed to model aspects of itself. It can be used to study itself, in virtue of its ability to reflect aspects of itself. However, an irreflexive property relation is one such that an entity cannot relate to itself.
 
Thus, although the object property, “has role in modeling”, has the irreflexive property listed, it should not. 

<img width="1030" alt="P32C" src="https://user-images.githubusercontent.com/123851163/222936322-e9e38139-5fb5-4823-abb3-9c7e78a24c42.png">



**(b)  Transitive**

The object property, “aligned with”, should not have the transitive property listed.

For this object property, there is no definition expressed. Instead, there is an editor’s note that states: “May be obsoleted, see https://github.com/oborel/obo-relations/issues/260”. If you follow this link, you will see four collaborators deliberate on whether to make this term obsolete. It was cited that “aligned with” was used to define at least one widely used relation, “fasciculates with”. Upon searching this object property, it is now a subproperty of “overlaps”. Subsequently, on October 15th, 2020, nlharris added the obsolete label to the term.

Due to the fact that there lacks a definition and “aligned with” is insufficient to establish that it holds a transitive characteristic, the transitive characteristic should be unlisted. 

Transitivity means that if individual x is related to individual y, and individual y is related to individual z, then individual x will be related to individual z. In other words, a single “hop” is implied over a chain of two along a given property if that property is transitive. 

Based on its label, one cannot infer that “aligned with” necessitates a transitive relation between x and z. For example, x may be aligned with y, y may be aligned with z, but x may not be aligned with z. It would be said that x is aligned with y (i.e. shares a border), but x is not aligned with z. 

Imagine two lines of blocks that intersect at block B. Call one row 'Vertical' and the other 'Horizontal'. A is a block in Vertical, but not Horizontal. C is a block in Horizontal, but not Vertical. And B is in both Vertical and Horizontal. A is aligned with B, since they're in the same row, and B is aligned with C for the same reason, but A is not aligned with B.

Moreover, aligned with could also mean an overlapping relation, rather than sharing a border. This further problematizes the vagueness of the term. 

Thus, because (1) there is no clear definition, (2) the label, “aligned with”, is ambiguous, and (3) pragmatically speaking, the term has been rendered obsolete, I recommend that the transitive characteristic be unlisted. It is not clear that “aligned with” is transitive. For the reasons cited above with examples, both intransitive bordering relations and overlapping relationships can be inferred by its label and yet, the object property is not clear whether it means to represent both kinds of relations. 

<img width="1035" alt="P32B" src="https://user-images.githubusercontent.com/123851163/222936312-cd2578ed-ef6a-404a-8f71-571865d9f038.png">



**(c)  Asymmetric**

The object property, “has role in modeling”, should not have the asymmetric property listed.

It’s definition states: “A relation between a biological, experimental, or computational artifact and an entity it is used to study, in virtue of its replicating or approximating features of the studied entity.” 

In BFO, an artifact is defined as: “something that is deliberately designed (or, in certain borderline cases, selected) by human beings to address a particular purpose” (3).
Barry Smith elucidates on this further: “While not all representational artifacts are ontologies, all ontologies are representational artifacts, and thus everything that holds of representational artifacts in general holds also of ontologies” (3). 

Conceptually, the import of this is that if artifact x has a role in modeling entity y, artifact x’s relation between entity y is subject to the same BFO domain rules as everything else. That is, if the declared characteristic of an artifact x is universally declared to be asymmetric to an entity y, then it follows that there are no such cases where the relationship between artifact x and entity y is symmetric. Its plausible that artifact x’s possible relations to entity y may in some cases be asymmetric (e.g. healthy cell line [artifact] → inducing disease [entity]), in others they may be symmetric (e.g. diseased model organism [artifact] → same diseased model organism over time [entity]), and further still, it might best to remain agnostic in such relations, leaving the characteristics neither asymmetric or symmetric, for garnering preferred inference modeling conditions for particularized ends. 

In order to have a wide ranging and flexible “has role in modeling” object property to classify possible relations between an artifact x and entity y, I argue that it is more advantageous and preferable to unlist the asymmetric characteristic so that possible symmetry relations and relations where it is best to remain agnostic on symmetry/asymmetry assertions may be represented in artifact to entity modeling relations. This is both an appeal to pragmatic and philosophical reasons. Unless all relations between artifact x and entity y are asymmetric, they should not be listed as such. By doing so, other non-asymmetric modeling relations cannot adequately be represented.

Thus, although the “has role in modeling” object property has the asymmetric characteristic listed (likely for pragmatic purposes specific to modeling ontologies with distinct ends), I argue that it would be better to dispense with it if one’s aim is to represent a wider domain of possible symmetric/asymmetric relations between artifacts with specific modeling roles and entities. Moreover, a more robust and comprehensive ontology would be representable as a result of unlisting the asymmetric characteristic. 

<img width="1030" alt="P32C" src="https://user-images.githubusercontent.com/123851163/222936322-e9e38139-5fb5-4823-abb3-9c7e78a24c42.png">



**(d)  Functional**

The object property, “characteristic of”, should not have the functional property listed.

It’s definition states: “a relation between a specifically dependent continuant (the characteristic) and any other entity(the bearer), in which the characteristic depends on the bearer for its existence.”

The functional property relation means that for any given individual, the property can have at most one value. In other words, there can be at most one out going relationship along the property for that individual. This means that a functional object property has a multiplicity 0..1 attached to it. For example, it might be said that the continuant red is “characteristic of” Washington Red Delicious Apples. Or put in another way, this red color is a characteristic of this Washington Red Delicious Apple. 

However, it is not the case that a given characteristic necessarily corresponds with at most one value, univocally. It could very well be the case that the red characteristic of Washington Red Delicious Apples might also have another corresponding value in a red colored car of the same hue. This means that correspondence between a characteristic and a bearer is not necessarily functional, i.e. has a binary value between 0 and 1 at most. 

A characteristic can have a one to one relationship to a bearer, a one to many relationship, a many to many relationship, or a many to one relationship. 

What could be the explanation of why this object property was set to having the functional characteristic? Upon further analysis, one can find a note in the ontology:

“Note that this relation was previously called "inheres in", but was changed to be called "characteristic of" because BFO2 uses "inheres in" in a more restricted fashion. This relation differs from BFO2:inheres_in in two respects: (1) it does not impose a range constraint, and thus it allows qualities of processes, as well as of information entities, whereas BFO2 restricts inheres_in to only apply to independent continuants (2) it is declared functional, i.e. something can only be a characteristic of one thing.”

(2) states: “it is declared, i.e. something can only be a characteristic of one thing.” What one might infer from this declaration is that this was done for pragmatic purposes in order to elicit preferred inference relations without having to deal with the burden of unwanted inferences to irrelevant elements. So for example, by declaring a functional constraint on “characteristic of” the ontologist could make pragmatic use of a delimited ontology that always garners a one to one relation, rather than a one to many, and so on. As a result, if the reasoner is run the functional constraint set will restrict the domain to one to one functional relations only. Thereby granting the conditions for a more specific, restricted ontology.
However, I must make a case for unlisting the functional characteristic. If I was an ontologist seeking to construct a knowledge base outside of a delimited domain of one to one functional relationships and wanted to represent the class of all red things, then I ought to unlist the functional characteristic so that the object property relation “characteristic of” could represent and infer a one to many relationship, which is not functional by definition, i.e. 0..1..X.

Thus, although the “characteristic of” object property has the functional characteristic listed likely for pragmatic purposes, I argue that it would be better to dispense with it if one’s aim is to represent relations that are one to many, many to one, or many to many. 

<img width="1032" alt="P32D" src="https://user-images.githubusercontent.com/123851163/222936331-15219ce7-c549-46e1-b0ea-fa095dae3a74.png">



**(e)  Inverse Functional**

The object property, “has characteristic”, should not have the inverse functional property listed.

It’s definition is the inverse of “characteristic of” (from [d]). The “characteristic of” object property’s definition is: “a relation between a specifically dependent continuant (the characteristic) and any other entity(the bearer), in which the characteristic depends on the bearer for its existence.”

This answer relies on what was said in (d), but is its inversion. 

Like the functional characteristic, the inverse functional property relation means that for any given individual, the property can have at most one value. In other words, there can be at most one out going relationship along the property for that individual. This means that an inverse functional object property has a multiplicity 0..1 attached to it. For example, it might be said that apples “has characteristic” color red. Or put in another way, this apple has this characteristic color red.

However, it is not the case that a given bearer necessarily corresponds with at most one characteristic value, univocally. It could very well be the case that a car might also have another corresponding value in a color red of the same hue. This means that correspondence between a characteristic and a bearer is not necessarily functional, i.e. has a binary value between 0 and 1 at most. 

A bearer can have a one to one relationship to a characteristic, a one to many relationship, a many to many relationship, or a many to one relationship.

As discussed in (d), it is inferred that as “characteristic of” was declared functional likely for pragmatic purposes, its inverse, “has characteristic”, follows the same constraints for the same reasons. Thus, the reason for which why I would like to make the case that the object property “has characteristic” should be unlisted are based on the same premises argued for in (d). That is, if I was an ontologist seeking to construct a knowledge base outside of a delimited domain of one to one functional relationships and wanted to represent the class of all bearers that have the characteristic color red, then I ought to unlist the inverse functional characteristic so that the object property relation “has characteristic” could represent and infer a many to one relationship or one to many relationship, which is not functional by definition, i.e. X…1 or 0..1..X.

Thus, although the “has characteristic” object property has the inverse functional characteristic listed likely for pragmatic purposes, I argue that it would be better to dispense with it if one’s aim is to represent relations that are many to one, one to many, or many to many. 

<img width="1032" alt="P32E" src="https://user-images.githubusercontent.com/123851163/222936345-25a7f173-2123-4069-8a6d-5fefaeaee69f.png">



3. Model the following natural language expressions using terms from BFO and RO; you are welcome to introduce new terms where needed:  
```
  (a) Sally has an arm Tuesday but does not have an arm Wednesday. 
  (b) Every liver has some cell as part at all times it exists.
  (c) John was a child, then an adult, then a senior. 
  (d) Goofus and Gallant are married at each point in a three year span. 
```

**(a) Sally has an arm Tuesday but does not have an arm Wednesday.**

Sally is instance_of object

Tuesday is instance_of one-dimensional temporal region 

Wednesday is an instance of one-dimensional temporal region 

Arm is an instance of fiat object part

“Sally participates in having at least one arm on Tuesday” is an instance of occurrent 

“Sally participates in having no arms on Wednesday” is an instance of occurrent

“Sally participates in having at most one arm on Wednesday” is an instance of occurrent

Due to the vagueness of the statement above, we have narrowed the possible answers to the following two cases:

“Sally participates in having at least one arm on Tuesday precedes Sally participates in having no arms on Wednesday”

“Sally participates in having at least one arm on Tuesday precedes Sally participates in having at most one arm on Wednesday”


**(b) Every liver has some cell as part at all times it exists.**

Search liver here: https://ontobee.org

We already have cell in the ontology.

Liver is a class in Uberon (UBERON_0002107), which is a subclass of material entity. 
https://ontobee.org/ontology/UBERON?iri=http://purl.obolibrary.org/obo/UBERON_0002107

Argument according to authority BS for the object property has_part_at_all_times: https://youtu.be/fkkWkTIxrNQ

Liver has_part_at_all_times Cell


**(c) John was a child, then an adult, then a senior.**

John is an instance_of object

childhood is an instance_of occurrent.

adulthood is an instance_of occurrent.

seniorhood is an instance_of occurrent.

“John participates in childhood precedes John participates in adulthood which precedes John participates in seniorhood.”


**(d) Goofus and Gallant are married at each point in a three year span.**

Goofus is an instance_of object.

Gallant is an instance_of object.

Marriage is an instance_of occurent.

T1 is an instance_of zero-dimensional temporal region.

“Three years span 1” is an instance_of one-dimensional temporal region.

Notice that the original phrase doesn’t say anything about Goofus and Gallant being married to each other, and we won’t represent such a fact.

If zero-dimensional temporal region t1 is part_of the one-dimensional temporal region “three years span 1”, then Goofus participates in marriage at t1 and Galland participates in marriage at t1.



4. Using the language of First-Order Logic, represent the following natural language expressions; you are welcome to introduce new terms where needed: 
```
  (a) Sally has an arm Tuesday but does not have an arm Wednesday. 
  (b) Every liver has some cell as part at all times it exists.
  (c) John was a child, then an adult, then a senior. 
  (d) Goofus and Gallant have been married for three years; for each day of that span, it is true to assert they are married. 
```

**(a) Sally has an arm Tuesday but does not have an arm Wednesday.**
 
  T: Tuesday
  
  H: has
  
  A: arm
  
  W: Wednesday
  
  s: Sally

**∃x (Tx ∧ ∃y (Hsy∧Ay)) ∧ ∃x (Wx ∧ ~∃y(Hsy∧Ay))**


**(b) Every liver has some cell as part at all times it exists.**  
  
  L: liver
  
  C: cell
  
  P: part of

**∀x∃y(Lx→Cy∧Pyx)**


**(c) John was a child, then an adult, then a senior.**

j = John

E xy = being earlier than

C (x, t) = being a child at t

A (x, t) = being an adult at t

S (x, t) = being a senior at t

**∃t1∃t2∃t3 (C (j, t1) ∧ A (J, t2) ∧ S(J, t3) ∧ E (t1, t2) ∧ E (t1, t3))**


**(d) Goofus and Gallant have been married for three years; for each day of that span, it is true to assert they are married.**

Again, notice we are not modeling that Goofus and Gallant are married to each other.

M(x, t) = being married at t

Y(t) = belongs to 3 year span 1

g1 = Goofus

g2 = Gallant

D(t) = t is a day

**∀t(D(t) ∧ Y(t)→(M(g1,t) ∧ M(g2,t)))**



5. Using BFO and RO, model the following scenario: the content of an rdf file is represented in two serializations - one in Turtle, one in XML - which are sent from one computer to two distinct computers on the same network.   

**The following model graph is based on Mermaid and represents the following key relations:**

– RDF File Content, Turtle and XML are all generically dependent continuants. RDF File Content has_model in Turtle and XML. And they are all carried by Computer.

– Computer 1 enables the process of Data Transmission, which ends_with another process, Data Reception, which has computers 2 and 3 as participants. So this part is intended to show that there is some data (Turtle and XML) which are sent from Computers 1 and 2 to Computer 3.

– Finally, computers 1, 2, and 3 are all parts_of network I, which is instance_of Object Aggregate.)

<img width="626" alt="P35" src="https://user-images.githubusercontent.com/123851163/223025071-52289c92-820e-4113-a32f-3c53db03c5db.png">



6. Using Protege, place these in the BFO hierarchy where you think they fit best:
```
  (a) Bach's Well-Tempered Clavier
  (b) Chair of the UB Philosophy Department
  (c) SARS-CoV-2
  (d) Mexico City
  (e) The trunk of a minivan
  (f) Occupation
  (g) Ocean
  (h) Lake
```

(a) Three possible answers: Generically dependent continuant (e.g. the music composition), object (e.g. music sheet), or process (occurrent, e.g. playing the song)

(b) Role

(c) Object/Material entity (e.g. virus) or disposition (e.g. disease symptoms)

(d) Site or 2D/3D spatial region (e.g. map or mapping)

(e) Site or fiat object part

(f) Role

(g) Site or 2D/3D spatial region

(h) Site, or 2D/3D spatial region



7. True or False; explain your answers:
```
  (a) An instance of Material Entity can have an instance of Immaterial Entity as part.
  (b) An instance of Immaterial Entity can have an instance of Material Entity as part.
  (c) An organization may have another organization as part.
  (d) An organization may have no members as part. 
  (e) Any site is partially bounded by some instance of Material Entity.
  (f) A book placed under the leg of a wobbly table has acquired a new function. 
  (g) A glass vase cushioned with packing tape for all time, has the disposition to break. 
  (h) Spacetime is a class in BFO.
  (i) The continuant fiat boundary class of BFO is closed, meaning, there are no subclasses beyond those identified presently in BFO. 
```

(a) True. Smith’s textbook: “Immaterial entities listed under 1. (boundaries and sites) are in some cases continuant parts of their material” (108).

(b) False. An instance of immaterial entity cannot have an instance of material entity as part. Though in (a) a material entity can have an instance of immaterial entity as part, its inverse is asymmetric and therefore cannot. 

(c) True. For example, a political committee can have a subcommittee as a part. 

(d) Two answers: If the debate club is viewed as a role, on this account, the answer would be **true** as the debate club could lose all its members while still being recognized by the school. If the debate club is viewed as an object aggregate, on this account, the asnswer would be **false** because as an object aggregate is the sum of its parts, by virtue of losing its members, it loses its necessary parts to being an object aggregate.

(e) False. You can identify a specified space and it could still be surrounded by space without touching any material entity.

(f) False. The elucidation excludes this by saying that the function is due to the physical make-up of the object. Since nothing about the make-up changed, the book did not gain any new functions. If the book has the function of supporting the table, this is a function it has always had, even if it wasn’t intended to support the table.

(g) True. Dispositions are in virtue of the bearer’s physical make-up, not its environment.

(h) False. This is covered by spatiotemporal region.

(i) False. "Continuant fiat boundary doesn't have a closure axiom because the subclasses don't necessarily exhaust all possibilities. An example would be the mereological sum of two-dimensional continuant fiat boundary and a one dimensional continuant fiat boundary that doesn't overlap it" (from the BFO file in Protege). 



8. Model the following scenario in BFO, introducing whatever terms are needed to do so: John runs for 3 hours, startin slowly, speeding up during the middle, then ending the run at a slower pace.  

**The following model graph is based on Mermaid and represents the following key relations:**

– John (as an Object) participates_in John’s running (as a process), and John has_characteristic_at_t1 John’s average speed 1, and John has_characteristic_at_t2 John’s average speed 2, and John has_characteristic_at_t3 John’s average speed 3. All of these speeds are instances of Quality. 

(Note: A line with two nodes in Mermaid is to represent a triple [subject, predicate, object], so I don’t know how to use Mermaid to express an ordered set of 4 elements like “John [1] has_characteristic [2] John’s average speed 1 [3] at t1 [4]”. At present what I can do is to insert the temporal parameter into the predicate “has_characteristic”.)

–  John’s running includes 3 temporal parts: John’s beginning stage, John’s middle stage, and John’s final stage, each of which is a process. Besides, John’s beginning stage precedes John’s middle stage which precedes John’s final stage.

– John’s running occurs_in this 3-hour, which is instance_of one-dimensional temporal region. This 3-hour also includes 3 temporal parts: t1, t2, and t3, each of which is also instance_of one-dimensional temporal region. Besides, t1 precedes t2, and t2 precedes t3. Moreover, John’s beginning stage occurs_in t1, John’s middle stage occurs_in t2, and John’s final stage occurs_in t3.

– Change in John’s speed: John's average speed 1 is decreased_in_magnitude_relative_to John's average speed 2 (that is, speed 1＜speed 2), and John's average speed 2 is increased_in_magnitude_relative_to John's average speed 3 (that is, speed 2＞speed 3). Moreover, John's Middle Stage has_part John's accelerating, and John's Final Stage has_part John's decelerating. John’s accelerating and his decelerating are both instances of process.

<img width="1419" alt="P38" src="https://user-images.githubusercontent.com/123851163/223915598-fc6ba9c5-33f2-4e91-97b2-752708c6c09a.png">



9. The Pellet reasoner in Protege can be used in an incremental reasoning strategy. ELI5 when and why one should use Pellet for incremental reasoning. 

**EL15:**

Do you remember the last time we talked, we learned about how description logic, the finite model property, and tree model property are ways of teaching computers about the world using words and rules? Well there is another way that we can use description logic to help a computer understand the world better, the Pellet reasoner and its use of incremental reasoning! 

The Pellet reasoner in Protégé is like a very smart helper that can help computers understand things better and faster. If we want to create a big puzzle of things that belong to a bunch of different categories, the Pellet reasoner can help us figure out where to put each piece in the puzzle! 

Incremental reasoning is another fancy term that means that we don’t have to solve the whole puzzle at once! Instead, we can add pieces to the puzzle one by one, and the Pellet reasoner will help us figure out where each piece goes. This is like building a puzzle step by step, and asking the Pellet reasoner to help us each time we add a new piece. The Pellet reasoner was taught to do this step by step puzzle building so that it can do it naturally on its own and learn something new each step of the way. As it builds the puzzle, it learns and doesn’t have to go backward to remind itself of what it had already built—it has a super powered brain giving it amazing learning and memory abilities! Isn’t that amazing?! This means that the Pellet reasoner can save a lot of time and energy by not having to go back and relearn parts of the puzzle it had helped with. 

We should use the Pellet reasoner for incremental reasoning when we have a big puzzle with lots of pieces that belong to different categories, and we want to make sure that each piece is in the right place. Sometimes, we might not be sure where a piece belongs, and that’s where the Pellet reasoner can really help computers and us out! 

So, just like how a smart helper can help us build a big puzzle step by step, the Pellet reasoner can help computers and us figure out where each piece goes in our big puzzle of things that belong to different categories. 



10. Protege reasoners will not allow you to combine certain properties, e.g. reflexivity and transitivity. If you attempt to assert such pairs of the same object property, then run the reasoner, nothing will happen. If you combine such properties while a reasoner is running, then ask to synchronize the reasoner, an error will be thrown. Provide a table or series of tables illustrating which pairs of properties cannot be combined in Protege, either because nothing happens when the reasoenr is run or because an error is thrown when synchronizing a reasoner after making such changes. Review the github docs on [creating tables in markdown](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/organizing-information-with-tables).
 
 |   **Pairwise**  | **Functional** | **InverseFun** | **Transitive** | **Symmetric** | **Asymmetric** | **Reflexive** | **Irreflexive** |
|:-----------:|:----------:|:----------:|:----------:|:---------:|:----------:|:---------:|:-----------:|
|  **Functional** |   N/A  |     YES    |     NO     |    YES    |     YES    |    YES    |     YES     |
|  **InverseFun** |     YES    |   N/A  |     NO     |    YES    |     YES    |    YES    |     YES     |
|  **Transitive** |     NO     |     NO     |   N/A  |    YES    |     NO     |    YES    |      NO     |
|  **Symmetric**  |     YES    |     YES    |     YES    |  N/A  |     NO     |    YES    |     YES     |
|  **Asymmetric** |     YES    |     YES    |     NO     |     NO    |   N/A  |     NO    |     YES     |
|  **Reflexive**  |     YES    |     YES    |     YES    |    YES    |     NO     |  N/A  |      NO     |
| **Irreflexive** |     YES    |     YES    |     NO     |    YES    |     YES    |     NO    |   N/A   |
 

In the above table, there are 21 different sorts of possibilities in total. We use "Yes" to represent a case where a pair of object property characteristics can be combined, and "No" to represent a case where a pair of object property characteristics cannot be combined.

As a result, we found that there are 7 sorts of cases where a pair of object property characteristics cannot be combined: 

(1) The following 3 pairs cannot be combined because of a logical contradiction: 
 
Asymmetric & Reflexive, Asymmetric & Symmetric, and Reflexive-Irreflexive.
 
(2) The following 4 pairs cannot be combined because of a more subtle factor. That is, an assertion of transitivity leads to a result that the target object property becomes non-simple (see Baader's book: section 8.1, page 211), so it is beyond the capacity limit of the reasoner:
 
Transitive & Functional, Transitive & Inverse Functional, Transitive & Asymmetric, and Transitive & Irreflexive. 

