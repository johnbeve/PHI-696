# Project 2

Your first project will require you to answer each of the 10 questions below.  You will be expected to open a pull request with your initial answers by the second class meeting, giving you one week to work on these problems. You and your peers will then have one week to work together to refine your respective initial answers, so they are ready for final submission. Once your pull requests have been reviewed and merged to the development branch, I will review them, then merge to the master branch. 

```Tip #1: Carefully study the Baader, et. al. selections assigned on bisimulation; it is deceptively subtle, and quite powerful. 
Tip #2: Google is still your friend. So is stackexchange...
Tip #3: Work _together_ to solve these problems, even for initial submissions and when you do, document this in github. 
Tip #4: Work together _as a team_. 
```

1. Let V be a vocabulary of ALCI consisting of a role name "P". Interpret part_of as "x is a part of y". Using this role name, define the following formulas in this language:
```
  (a)  PP that says that x is a proper part of y 
- P means x is a part of y
- ~P means x is not a part of y
- P^_ means y is a part of x
  
- A proper part is like a one-sided (subsumption) relationship.
- Finn, Giacomo, Ali: PP:= ∃P.~P OR PP:= ∃(P⊓~P^_)

  (b)  iPP that says that y is a proper part of x
 - Finn, Giacomo, Ali: iPP:= PP^_
 
  (c)  iP that says that y has x as part 
iP := P^_

  (d)  O that says that x overlaps y
 - Pulled from https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1175958/: "r1 overlap r2 = [definition] for some r, r part_of r1 and r part_of r2."
0 := ∃P.P^_
 - Could ∃(P⊓P^_) also work for the above?
 
  (e)  D that says that x and y are disjoint 
D:= 0^_

``` 

2. Use your axioms from question 1 as the basis of an ALCI T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 
- These slides https://www.inf.unibz.it/~calvanese/teaching/16-17-odbs/lecture-notes/KRO-6-alc.pdf are the best
- https://www.researchgate.net/publication/326360368_Automated_noninvasive_epithelial_cell_counting_in_phase_contrast_microscopy_images_with_automated_parameter_selection/figures?lo=1 Figure 3 here helps me think about parthood for the purposes of my T box

Instances: {Hand, Severed_Hand, Handless_Darcy, Darcy_2Hands}
Concepts: {Limb, Person}
Relations: {P, PP, P¯, PP¯, 0, D}

T Box: inclusive Terms
 

A box: membership Assertions

Person: {Handless_Darcy, Darcy_2Hands}
Limb: {Hand, Severed_Hand}



3. Translate the following first-order logic axioms into ALC: 
```
(a) ∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))


(b) ∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))


(c) ∀y(R(x, y) → ∃x(R(y, x) ∧ ∀y(R(x, y) → A(y))))
- ALC does not include conditionals or biconditionals in its syntax, so first I'm going to re-express the given formula without them:
∀y(R(x, y) → ∃x(R(y, x) ∧ ∀y(R(x, y) → A(y)))) ≡ ∀y(R(x,y) ∨ ¬(∃x(R(y,x))) ∧ ∀y(R(x,y)∨ ¬A(y))


(d) (∀y)(R(x, y) → A(y)) ∧ (∃y)(R(x, y) ∧ B(y))
(∀y)(R(x, y) → A(y)) ∧ (∃y)(R(x, y) ∧ B(y)) ≡ (∀y)(R(x, y) ∨ ¬A(y)) ∧ (∃y)(R(x, y) ∧ B(y))

```
4. Provide an interpretation I<sub>1</sub> for ALC and an interpretation I<sub>2</sub> for ALCN - each distinct from any interpretation covered in class so far - and construct a bisimulation that demonstrates ALCN is more expressive than ALC. Use the [mermaid syntax](https://github.com/mermaid-js/mermaid) of markdown to provide a graphical representation of your work. 

- ALCN is a syntax identical to ALC with "...unqualified number restrictions... concepts of the form (≤nr.T) and (≥nr.T)" (Baader et. al., 63)
- So, in the textbook, once a set contains more or less than 1 relation, it can no longer be expressed in ALC.
- This looks like (≤1 r).

5. Provide an interpretation I<sub>1</sub> for ALC and an interpretation I<sub>2</sub> for ALCN - each distinct from any interpretation covered in class so far - and construct a bisimulation that _does not_ demonstrate ALCN is more expressive than ALC. Use the [mermaid syntax](https://github.com/mermaid-js/mermaid) of markdown to provide a graphical representation of your work. 

- I feel like this could be done by contrasting (bisimulating?) two solitary sets of relations.
- Looking at the third page of this pdf https://lat.inf.tu-dresden.de/teaching/ws2013-2014/DL/handout3.pdf tells me an empty relation 0 could also work here.

6. Explain the difference - using natural language - between the description logic expressions:
(a) ∃r.C and ∀r.C
- 'All x's are related to some instance of C via R' versus 'All x's are ONLY related to some instance of C via R'. 

(b) ∃r-.C and ∀r-.C
- 'C' is a concept, which in ALC is synonymous to a class, set, or type. The inverse role relation means that 'C is being r'd by all xs' ( ∃r-.C) or 'only being r'd by all xs' (∀r-.C)

(c) <=nr and <=nr.C
- '<=n' in either case is a number restriction meaning 'fewer or equal to n instances'. The first expression specifies there are fewer than or equal to n instances of relation 'r's bearers, while the second is an element of the concept C set and therefore means there are 'fewer than or equal to n instances of the relation r bearing in a member of concept C'.

(d) ∃r-.C and ∃r-.{a} 
- An inverse role is focusing on the variable that is being related to in the syntax. 'C' is a concept, which in ALC is synonymous to a class, set, or type. There could be multiple instances of C being 'r'd'. '{a}', on the other hand, is an atomic concept. It is the only one of its kind. It is also being 'r'd' by some variable, but there are no interchangeable entities just like it.
...
- After help from Karl, I now know that ∃r-.C refers to all members of some concept C being r'd by every instance of some variable. ∃r-.{a} means the individual a is being r'd by every instance of some variable.
  
```

7. There is a delightfully helpful subreddit called "ELI5" which stands for something like "explain it like I'm 5" where users post conceptually challenging questions and other users attempt to provide explanations in simple, jargon-free, terms that presumably a 5 year-old could understand. Using this as a model, explain the _finite model property_. Be sure to provide a simple example and explain when the property might be important, and when it is not so important. 
- I got help here from https://vimeo.com/65392670 and https://philosophy.stackexchange.com/questions/15525/how-is-first-order-logic-complete-but-not-decidable#:~:text=First%2Dorder%20logic%20is%20complete,or%20is%20not%20logically%20entailed. 

- Languages in logic are like special clubs, and these clubs can be used to make new clubs about whatever we're interested in. Sometimes, us logicians (logical people) want to know if something new can be part of a club or not. We can test it out by treating what we're interested in like a new member, and seeing if it gets along with the other members. If we can count the number of steps it takes before we can tell if everybody gets along or not, our club has the finite model property.

- The finite model property is important because it gives us a helpful routine that makes figuring out these clubs a lot simpler. Sometimes all we need is three members to tell us they can't handle a new member. 
- Now, sometimes we don't want to limit the members of these clubs. Then it's more about making sure there can be space for everybody, even if that takes more work. When we're thinking about clubs like this, we don't need the finite model property so much.
...
- Here are some notes from Jieming: "...it seems if we define a club member as, say being interested in xxx, then, even though there is no limit requirement to the number of club members, it can also have the finite model property."
- Here is a note from Karl: "Finite model property (FMP): Any satisfiable concept can be satisfied by a finite model... Finite model property (FMP) can be used to design a decidable algorithm for the satisfiability of its concepts."
...


8. Following up on the preceding , explain the _tree model property_. Be sure to provide a simple example and explain when the property might be important, and when it is not so important. 

- Here is a note from Jieming: "...from one end to another end, or from one point to another point, through the branches, there is one way and only one way to go. Thus, if a structure has the tree model property, it can determine whether one point in a relation falls into some specific branches, which means whether the object (represented by the point), falls into some specific concepts."
- Here is a note from Karl: "...TMP is crucial to tableau-based algorithms for the consistency check of knowledge base and applied ontology. Most of applied ontologies, especially those BFO-based ones, have TMP, allowing that their consistency can be checked by tableau reasonings."
...
- So, here is my updated explanation:
- One way logicians (logical people) think about what we're interested is by picturing it like it's the trunk of a tree. 
- A tree has lots of different branches that go in different directions. These branches _extend away_ from the trunk, but they're a part of the whole tree just like every other part is. The ends of these branches grow into more specific parts of what we want to think about. These are connected to the whole rest of the tree by the branches. 
- As the tree grows, We can add our own branches, more stuff on the ends of the branches, or even ask computers to lend a hand. Then we get to search through all the branches, collect what we're interested in like apples, and look at it all together. 

- Sometimes, though, if we tried to make a tree out of what we're looking at, it wouldn't help us that much. Then we'll find other ways of putting the parts together instead of trying to grow one. 

9. Open the Protege editor and create object properties for each of the role names that you constructed in question 1. You should have at least 6 object properties. Assert in the editor that P is a sub-property of O, that P is transitive, and that O is symmetric. Next, add individuals - a, b, c - to the file and assert that c is part of a and that c overlaps b. Running the reasoner should reveal - highlighted in yellow if you select the individual c - that c overlaps a. Using the discussion in the selections from chapter 4 of the Baader, et. al. text as a guide, explain how the tableau algorithm is generating this inference. 

- So, C must overlap A as well because C is a part of A and they both bear the broader overlap property (Many thanks to Karl for correcting me here).
- The reasoner in Protege figures this out by applying ALC "syntax expansion rules" to the given ontology knowledge base, following to the logical conclusions in order to 'complete' the A-box. In this case, it's using the subsumption rule explained on page 84 of Baader et. al.
- Many thanks to Ali and Giacomo for their explanations :-)

10. Following up on your work in question 9, adjust/add/remove/etc. object properties and individuals in your Protege file so that when you run a reasoner in Protege, you return the following consequences: 
```(a) a is a proper part of b...

...and disjoint from e
- disjunction is a symmetric object property, so a reasoner will show a is_disjoint_from e when I input that e is_disjoint_from a

  (b) a overlaps c
 - this can be reasoned out of the instructions for question 9, given that overlap is a symmetric object property.
 
  (c) a is part of b, b is part of f, and a is part of f
  
  (e) There are no parts between a and g in common
```
