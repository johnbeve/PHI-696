# Project 2

Your second project will require you to answer each of the 10 questions below.  You will be expected to open a pull request with your initial answers by the second class meeting, giving you one week to work on these problems. You and your peers will then have one week to work together to refine your respective initial answers, so they are ready for final submission. Once your pull requests have been reviewed and merged to the development branch, I will review them, then merge to the master branch. 

```
Tip #1: Carefully study the Baader, et. al. selections assigned on bisimulation; it is deceptively subtle, and quite powerful. 
Tip #2: Google is still your friend. So is stackexchange...
Tip #3: Work together to solve these problems, even for initial submissions and when you do, document this in github. 
Tip #4: Work together as a team. 
```

1. Let V be a vocabulary of ALCI consisting of a role name "P". Interpret part_of as "x is a part of y". Using this role name, define the following formulas in this language:
```
  (a)  PP that says that x is a proper part of y
  PP ≡ P ⊓ ¬P¯
  
  (b)  iPP that says that y is a proper part of x
  iPP ≡ PP¯ =>
  iPP ≡ (P ⊓ ¬P¯)¯

  iPP ≡ ¬P ⊓ P¯

  (c)  iP that says that x has y as part 
  iP ≡ P¯
  
  (d)  O that says that x overlaps y
  O ≡ ∃P¯.(∃P)
  O ≡ ∃iP.(∃P.⊤)
  
  (e)  D that says that x and y are disjoint 
  D ≡ ¬O
  
```

2. Use your axioms from question 1 as the basis of an ALCI T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 

3. Translate the following first-order logic axioms into ALCI: 
```
(a) ∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
∃R.(∀R.(∀R¯))

(b) ∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))
∃R¯.(∃R.⊤) ⊓ ∃R.⊤

(c) ∀y(R(x, y) → ∃x(R(y, x) ∧ ∀y(R(x, y) → A(y))))
∀R.∃R.∀R.A
Is this well formed?  Does it matter?

(d) (∀y)(R(x, y) → A(y)) ∧ (∃y)(R(x, y) ∧ B(y))
(∀R.A) ⊓ (∃R.B)
Same questions as above: Is this well formed?  Does it matter?


```
4. Provide an interpretation I<sub>1</sub> for ALC and an interpretation I<sub>2</sub> for ALCN - each distinct from any interpretation covered in class so far - and construct a bisimulation that demonstrates ALCN is more expressive than ALC. Use the [mermaid syntax](https://github.com/mermaid-js/mermaid) of markdown to provide a graphical representation of your work. Feel free to use the [mermaid live editor](https://mermaid.live/) when diagramming. 

5. Provide an interpretation I<sub>1</sub> for ALC and an interpretation I<sub>2</sub> for ALCN - each distinct from any interpretation covered in class so far - and construct a bisimulation that _does not_ demonstrate ALCN is more expressive than ALC. Use the [mermaid syntax](https://github.com/mermaid-js/mermaid) of markdown to provide a graphical representation of your work. Feel free to use the [mermaid live editor](https://mermaid.live/) when diagramming. 


6. Explain the difference - using natural language - between the description logic expressions:
  ```
  (a) ∃r.C and ∀r.C
 ∃r.C = all x has a r-filler y instantiating C
 ∀r.C = all r-fillers ys of all x instantiate C
 
  (b) ∃r-.C and ∀r-.C
   ∃r-.C = all xs are r-inverse-related to y and falls under concept C
   ∀r-.C = all xs are r-inverse-related to all ys and this thing falls under concept C
   
  (c) <=nr and <=nr.C
  <=nr = role r connects all the xs to no more than n elements
  <=nr.C = role r connects all the xs to no more than n elements, and they fall under concept C
  
  (d) ∃r-.C and ∃r-.{a} 
  ∃r-.C = for all xs, there is at least a thing y, which is r-related to it, and which falls under concept C
  ∃r-.{a} = for all xs, there is element a, which is r-related to it
```

7. There is a delightfully helpful subreddit called "ELI5" which stands for something like "explain it like I'm 5" where users post conceptually challenging questions and other users attempt to provide explanations in simple, jargon-free, terms that presumably a 5 year-old could understand. Using this as a model, explain the _finite model property_. Be sure to provide a simple example and explain when the property might be important, and when it is not so important. 

Definition 3.10. The interpretation I is a model of a concept C with respect to a TBox T if I is a model of T such that CI = ∅. We call this model finite if ΔI is finite. (Baader, 57)

In this scenario, I am the five-year-old that needs someone to explain this concept to.  The answered proposed on the collaborative google doc are extremely helpful.  I don't see a need to try to do it better in this case.  Jeiming's answer:

Bob loves playing games, and he hopes there is a game that can be played with different results forever. 
One day, his father gives him a game, called Color-card: there are a number of color cards in a box. Each card has a different color, but it is fully colored on one side, while on the other side it is a blank sheet with the colored dot. Once a time, the player chooses any number of cards from the box, and then uses any number of cards he chooses to make combinations. For example, the first time, Bob chooses five color cards from the box, red, yellow, blue, green, brown, then he uses three cards, and put them in such a order: 1, red (front side), 2, blue (back side), 3, green (back side). That is one combination. The player continues playing until there is a combination that repeats. If the player cannot continue playing, he fails. However, if the player fails at one time, he can choose more or/and different cards, then play the next time. The player wins if the cards he chooses can allow him to play forever. 
Unfortunately, Bob cannot win the game, because no matter how many cards he chooses (the number of cards is not limitless), and how hard he tries, he cannot continue playing without a repeated combination occurring.  
We say that the Color-card game has finite model property. 
Finite model property is important because it can be used to design a decidable algorithm for the satisfiability of its concepts. 



8. Following up on the preceding , explain the _tree model property_. Be sure to provide a simple example and explain when the property might be important, and when it is not so important. 

Basically, a tree model is a model whose graph representation is a tree." (Baader, 63)
A tree model is a graphical representation that takes the form of a tree, i.e. contains nodes which branch out and connect to another node.  The nodes, formally called 

"ALC has the tree model property, i.e., if T is an ALC TBox and C an ALC concept such that C is satisfiable with respect to T , then C has a tree model with respect to T." (Baader, 65)



Concept: represent sets of elements and can be viewed as unary predicates (Baader, 11)
- Concepts are built from concept names (i.e. Person, Course) and role names (i.e. teaches, studies) (Baader, 11)
- The set a concept represents is called its extension (Baader, 11)

A concept is a representation of things, i.e. a set of elemenets, and can be viewed as single properties of the things.  Concepts contain two elements: 1) concept names (names which label the "thing," i.e. "teacher" or "student"), and 2) concept roles (binary relations which conjoin the things, or the concept names).  An extension of a concept is the set of names and roles that the concept represents. 

The TBox, or terminological box: "The TBox represents knowledge about the structure of the domain (similar to a database schema)" (Baader, 1)
Examples: What is a teacher?  What is a student?  What is a course? 
The TBox, or terminological box, details the information of knowedge about what is contained by the domain, or the scope and structure, of by a concept and its extension. For example, who is a teacher, who is a student, and similar concept names fill out the TBox.  This is used to provide information about the structure, which is composed though defining each concept name within a particular concept.

Unpacked/Thorough Definition of tree model property:
ALC has the tree model property, ie.e., if T is an ALC TBox (terminology box which describes/represents the strucutre of the domain) and C is an ALC concept (represents a set of elements that can be viewed as unary predicates, composed of concept names and role names) such that C is satisfiable with respect to T, then C has a tree model with respect to T.

"Note that, in case the model we start with has a cycle, the tree constructed in the proof is an infinite tree, i.e., it has infinitely many nodes.
Although ALC has the finite model property and the tree model property, it does not have the finite tree model property. In fact, it is easy to see that the concept A does not have a finite tree model with respect to the TBox {A ∃r.A}" (Baader, 66)

Additions to the tree model property:
"Finally, the tree model property proved in the last section of this chapter implies that ALC cannot enforce cyclic role relationships." (Baader, 55)
"It should also be noted that, in our definition of a tree model, we do not consider edge labels." (Baader, 66)

Infinite trees:
"Finally, let us point out that the tree model property can also be used to show decidability of satisfiability of concepts with respect to TBoxes in ALC, using the so-called automata-based approach. The automata used in this approach are automata working on infinite trees." (Baader, 66)



9. Open the Protege editor and create object properties for each of the role names that you constructed in question 1. You should have at least 6 object properties. Assert in the editor that P is a sub-property of O, that P is transitive, and that O is symmetric. Next, add individuals - a, b, c - to the file and assert that c is part of a and that c overlaps b. Running the reasoner should reveal - highlighted in yellow if you select the individual c - that c overlaps a. Using the discussion in the selections from chapter 4 of the Baader, et. al. text as a guide, explain how the tableau algorithm is generating this inference. Also, provide a screenshot of the results of your reasoner run with c highlighted. 

10. Following up on your work in question 9, adjust/add/remove/etc. object properties and individuals in your Protege file so that when you run a reasoner in Protege, you return the following consequences: 
```
  (a) a is a proper part of b and disjoint from e
  (b) a overlaps c
  (c) a is part of b, b is part of f, and a is part of f
  (e) There are no parts between a and g in common
```
Provide a screenshot of your results here. 
