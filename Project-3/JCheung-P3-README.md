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
  (a)  Reflexive 

The object property, “immediate transformation of”, should have the reflexive characteristic listed.

It’s definition states: “x immediate transformation of y iff x immediately succeeds y temporally at a time boundary t, and all of the matter present in x at t is present in y at t, and all the matter in y at t is present in x at t”.

Reflexivity is the characteristic that expresses the relation that an entity be related to itself. Although, x and y constitute the same matter and it can be implied that x and y do not share the same identity at a particular time t, the “immediate transformation of” relation is reflexive because it relates back to the same matter that constitutes both x and y.

Therefore, the object property “immediate transformation of” should have reflexive as a listed characteristic.

 

  (b)  Transitive 

The object property, “existence ends with”, should have the transitive characteristic listed. 

It’s definition states: “x existence ends with y if and only if the time point at which x ends is equivalent to the time point at which y ends. Formally: x existence ends with y iff ω(x) = ω(y).” 

That is, if any entity x ends at the equivalent time point of any other entity y, then they share the same object property, “existence ends with”.

Thus, any entity x that ends at a shared equivalent time point with entity y, and entity y ends at a shared equivalent time point with entity z, then entity x will share an end equivalent time point with entity z. If entity x shares the same object property, i.e. existence ends with, with entity z, then the relation must be transitive. 

Therefore, the object property “existence ends with” should have transitive as a listed characteristic. 

 

  (c)  Symmetric

The object property, “partially overlaps”, should have the symmetric characteristic listed. 

It’s definition states: “x partially overlaps y iff there exists some z such that z is part of x and z is part of y, and it is also the case that neither x is part of y or y is part of x”.

A symmetric characteristic is a relation such that given any elements a and b of set G, if a~b, then b~a. Another way to think of symmetry is that the property has itself as an inverse, so if individual a is related to individual b then individual a must also be related to individual y along the same property.

In this case, the “partially overlaps” symmetric relation is found in z. z is congruent with z and its inverse is z. Thus, z is a symmetrical relation, although x is neither a part of y, nor is y a part of x. 

Therefore, the object property “partially overlaps” should have symmetric as a listed characteristic. 

 

  (d)  Functional 

The object property, “has target end location”, should have the functional characteristic listed. 

It’s definition states: “This relationship holds between p and l when p is a transport or localization process in which the outcome is to move some cargo c from a an initial location to some destination l.”

The functional property relation means that for any given individual, the property can have at most one value. In other words, there can be at most one out going relationship along the property for that individual. This means that a functional object property has a multiplicity 0..1 attached to it. For example,the functional property hasHusband shows that the person, in a monogamous universe, can have at most one husband.

In the case of the object property “has target end location”, there is at most one specified end location in which the outcome is to move some cargo c from a an initial location to some destination l. The end location is univocal, that is, only has one possible meaning. Thus, the object property relation “has target end location” is functional. 

Therefore, the object property “has target end location” should have functional as a listed characteristic.


 

  (e)  Symmetric and Reflexive

The object property, “connects”, should have the symmetric and reflexive characteristics listed. 

It’s definition states: “c connects a if and only if there exist some b such that a and b are similar parts of the same system, and c connects b, specifically, c connects a with b. When one structure connects two others it unites some aspect of the function or role they play within the system.

That is, c connects a and b iff: 
a, b, c ∈ G {  
c=c 
a~b ⊓ b~a 
a ⊑ b
b ⊑ a
a ⊑ c  
c ⊑ a
b ⊑ c
c ⊑ b 
}

A symmetric property relation is instanced where entities share the same property of which, its inverse is itself. a, b, and c belong to the same system set G and correspond to each other. a and b are similar to one another and both correspond to c as the connective. c is symmetric because its inverse is itself. Thus, a, b, and c all possess a symmetric property relation with one another found in c, “connects”, and should have the symmetric characteristic listed.

A reflexive property relation is instanced where an entity is related or equal to itself. For an entity c to possess the “connects” object property characteristic, every entity c in a given set A must therefore be related and/or equal to itself, i.e. c=c. The object property “connects” should relate back to any entity c within a given class in identifying itself as the connective. Thus, the object property “connects” should have the reflexive characteristic listed as well. 

In sum, the object property “connects” should have both the symmetric and reflexive characteristics listed as it instances both property relations in its definition. 

 



2. In BFO and RO identify at least one object property for each of a-e that _should not have the listed property, but which does_; argue for your case, using examples. 
```
  (a)  Irreflexive
  (b)  Transitive 
  (c)  Asymmetric
  (d)  Functional 
  (e)  Inverse Functional
```
  (a)  Irreflexive

The object property, “has skeleton”, should not have the irreflexive property listed.

It’s definition states: “A relation between a segment or subdivision of an organism and the maximal subdivision of material entities that provides structural support for that segment or subdivision.”

An irreflexive property relation is one such that an entity cannot relate to itself. If the “has skeleton” irreflexive property relation were true and if in the case of an individual, Jaron, does indeed have a skeleton, it would then be said that this relation of having a skeleton could not be related back to the individual, Jaron. This, however, is false. An individual can be instanced by a “has skeleton” relation reflexively, i.e. relating back to itself. Thus, although the “has skeleton” object property has the irreflexive characteristic listed, it should not. 

 

  (b)  Transitive 

The object property, “aligned with”, should not have the transitive property listed.

For this object property, there is no definition expressed. Instead, there is an editor’s note that states: “May be obsoleted, see https://github.com/oborel/obo-relations/issues/260”. If you follow this link, you will see four collaborators deliberate on whether to make this term obsolete. It was cited that “aligned with” was used to define at least one widely used relation, “fasciculates with”. Upon searching this object property, it is now a subproperty of “overlaps”. Subsequently, on October 15th, 2020, nlharris added the obsolete label to the term.

Due to the fact that there lacks a definition and “aligned with” is insufficient to establish that it holds a transitive characteristic, the transitive characteristic should be unlisted. 

Transitivity means that if individual x is related to individual y, and individual y is related to individual z, then individual x will be related to individual z. In other words, a single “hop” is implied over a chain of two along a given property if that property is transitive. 

Based on its label, one cannot infer that “aligned with” necessitates a transitive relation between x and z. For example, x may share a border with y, y may share a border with z, but x may not share a border with z. It would be said that x is aligned with y (i.e. shares a border), but x is not aligned with z. 

Moreover, aligned with could also mean an overlapping relation, rather than sharing a border. This further problematizes the vagueness of the term. 

Thus, because (1) there is no clear definition, (2) the label, “aligned with”, is ambiguous, and (3) pragmatically speaking, the term has been rendered obsolete, I recommend that the transitive characteristic be unlisted. It is not clear that “aligned with” is transitive. For the reasons cited above with examples, both intransitive bordering relations and overlapping relationships can be inferred by its label and yet, the object property is not clear whether it means to represent both kinds of relations. 

 

  (c)  Asymmetric

The object property, “has role in modeling”, should not have the asymmetric property listed.

It’s definition states: “A relation between a biological, experimental, or computational artifact and an entity it is used to study, in virtue of its replicating or approximating features of the studied entity.” 

In BFO, an artifact is defined as: “something that is deliberately designed (or, in certain borderline cases, selected) by human beings to address a particular purpose” (3).
Barry Smith elucidates on this further: “While not all representational artifacts are ontologies, all ontologies are representational artifacts, and thus everything that holds of representational artifacts in general holds also of ontologies” (3). 

Conceptually, the import of this is that if artifact x has a role in modeling entity y, artifact x’s relation between entity y is subject to the same BFO domain rules as everything else. That is, if the declared characteristic of an artifact x is universally declared to be asymmetric to an entity y, then it follows that there are no such cases where the relationship between artifact x and entity y is symmetric. Its plausible that artifact x’s possible relations to entity y may in some cases be asymmetric (e.g. healthy cell line [artifact] → inducing disease [entity]), in others they may be symmetric (e.g. diseased model organism [artifact] → same diseased model organism over time [entity]), and further still, it might best to remain agnostic in such relations, leaving the characteristics neither asymmetric or symmetric, for garnering preferred inference modeling conditions for particularized ends. 

In order to have a wide ranging and flexible “has role in modeling” object property to classify possible relations between an artifact x and entity y, I argue that it is more advantageous and preferable to unlist the asymmetric characteristic so that possible symmetry relations and relations where it is best to remain agnostic on symmetry/asymmetry assertions may be represented in artifact to entity modeling relations. This is both an appeal to pragmatic and philosophical reasons. Unless all relations between artifact x and entity y are asymmetric, they should not be listed as such. By doing so, other non-asymmetric modeling relations cannot adequately be represented.

Thus, although the “has role in modeling” object property has the asymmetric characteristic listed (likely for pragmatic purposes specific to modeling ontologies with distinct ends), I argue that it would be better to dispense with it if one’s aim is to represent a wider domain of possible symmetric/asymmetric relations between artifacts with specific modeling roles and entities. Moreover, a more robust and comprehensive ontology would be representable as a result of unlisting the asymmetric characteristic. 

 

  (d)  Functional 

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

 

  (e)  Inverse Functional

The object property, “has characteristic”, should not have the inverse functional property listed.

It’s definition is the inverse of “characteristic of” (from [d]). The “characteristic of” object property’s definition is: “a relation between a specifically dependent continuant (the characteristic) and any other entity(the bearer), in which the characteristic depends on the bearer for its existence.”

This answer relies on what was said in (d), but is its inversion. 

Like the functional characteristic, the inverse functional property relation means that for any given individual, the property can have at most one value. In other words, there can be at most one out going relationship along the property for that individual. This means that an inverse functional object property has a multiplicity 0..1 attached to it. For example, it might be said that apples “has characteristic” color red. Or put in another way, this apple has this characteristic color red.

However, it is not the case that a given bearer necessarily corresponds with at most one characteristic value, univocally. It could very well be the case that a car might also have another corresponding value in a color red of the same hue. This means that correspondence between a characteristic and a bearer is not necessarily functional, i.e. has a binary value between 0 and 1 at most. 

A bearer can have a one to one relationship to a characteristic, a one to many relationship, a many to many relationship, or a many to one relationship.

As discussed in (d), it is inferred that as “characteristic of” was declared functional likely for pragmatic purposes, its inverse, “has characteristic”, follows the same constraints for the same reasons. Thus, the reason for which why I would like to make the case that the object property “has characteristic” should be unlisted are based on the same premises argued for in (d). That is, if I was an ontologist seeking to construct a knowledge base outside of a delimited domain of one to one functional relationships and wanted to represent the class of all bearers that have the characteristic color red, then I ought to unlist the inverse functional characteristic so that the object property relation “has characteristic” could represent and infer a many to one relationship or one to many relationship, which is not functional by definition, i.e. X…1…0 and 0..1..X.

Thus, although the “has characteristic” object property has the inverse functional characteristic listed likely for pragmatic purposes, I argue that it would be better to dispense with it if one’s aim is to represent relations that are many to one, one to many, or many to many. 

 



3. Model the following natural language expressions using terms from BFO and RO; you are welcome to introduce new terms where needed:  
```
  (a) Sally has an arm Tuesday but does not have an arm Wednesday. 
  (b) Every liver has some cell as part at all times it exists.
  (c) John was a child, then an adult, then a senior. 
  (d) Goofus and Gallant are married at each point in a three year span. 
```

4. Using the language of First-Order Logic, represent the following natural language expressions; you are welcome to introduce new terms where needed: 
```
  (a) Sally has an arm Tuesday but does not have an arm Wednesday. 
  (b) Every liver has some cell as part at all times it exists.
  (c) John was a child, then an adult, then a senior. 
  (d) Goofus and Gallant have been married for three years; for each day of that span, it is true to assert they are married. 
```

5. Using BFO and RO, model the following scenario: the content of an rdf file is represented in two serializations - one in Turtle, one in XML - which are sent from one computer to two distinct computers on the same network.   


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

8. Model the following scenario in BFO, introducing whatever terms are needed to do so: John runs for 3 hours, startin slowly, speeding up during the middle, then ending the run at a slower pace.  

9. The Pellet reasoner in Protege can be used in an incremental reasoning strategy. ELI5 when and why one should use Pellet for incremental reasoning. 

10. Protege reasoners will not allow you to combine certain properties, e.g. reflexivity and transitivity. If you attempt to assert such pairs of the same object property, then run the reasoner, nothing will happen. If you combine such properties while a reasoner is running, then ask to synchronize the reasoner, an error will be thrown. Provide a table or series of tables illustrating which pairs of properties cannot be combined in Protege, either because nothing happens when the reasoenr is run or because an error is thrown when synchronizing a reasoner after making such changes. Review the github docs on [creating tables in markdown](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/organizing-information-with-tables).
 