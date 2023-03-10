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
  (b)  Transitive 
  (c)  Symmetric
  (d)  Functional 
  (e)  Symmetric and Reflexive
```

2. In BFO and RO identify at least one object property for each of a-e that _should not have the listed property, but which does_; argue for your case, using examples. Note: It will be easiest to view the object properties in BFO and RO using Protege.
```
  (a)  Irreflexive
  (b)  Transitive 
  (c)  Asymmetric
  (d)  Functional 
  (e)  Inverse Functional
```

3. Model the following natural language expressions using terms from BFO and RO; you are welcome to introduce new terms where needed:  
```
  (a) Sally has an arm Tuesday but does not have an arm Wednesday. 
  Sally participates in having at least one arm on Tuesday precedes Sally participates in having no arms on Wednesday.
  
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
  (g) A glass vase cushioned with packing material for all time, has the disposition to break. 
  (h) Spacetime is a class in BFO.
  (i) The continuant fiat boundary class of BFO is closed, meaning, there are no subclasses beyond those identified presently in BFO. 
```

8. Model the following scenario in BFO, introducing whatever terms are needed to do so: John runs for 3 hours, startin slowly, speeding up during the middle, then ending the run at a slower pace.  

9. The Pellet reasoner in Protege can be used in an incremental reasoning strategy. ELI5 when and why one should use Pellet for incremental reasoning. 

10. Protege reasoners will not allow you to combine certain properties, e.g. reflexivity and transitivity. If you attempt to assert such pairs of the same object property, then run the reasoner, nothing will happen. If you combine such properties while a reasoner is running, then ask to synchronize the reasoner, an error will be thrown. Provide a table or series of tables illustrating which pairs of properties cannot be combined in Protege, either because nothing happens when the reasoenr is run or because an error is thrown when synchronizing a reasoner after making such changes. Review the github docs on [creating tables in markdown](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/organizing-information-with-tables).
