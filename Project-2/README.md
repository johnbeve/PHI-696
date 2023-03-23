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

Taken from Josh Vonderhaar: 

ipp= ∃part_of-^~∃part-of

ip= ∃part_of-

O= ∃part_of^∃part_of-

D= ∃~part_of^∃~part-of-

(Lazarus,x): PP

(Lazarus, City)

(City, y): Ipp

(Lazarus, City): Part_of

(City, Lazarus): Part_of

Proper part: Lazarus, City

overlaps: none

Disjoint: none

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

In seeing an example for the above question (Jeiming's response), I'll give this one a go:

Baader definition of tree model property:
"ALC has the tree model property, i.e., if T is an ALC TBox and C an ALC concept such that C is satisfiable with respect to T , then C has a tree model with respect to T." (Baader, 65)

What is a concept? A representation of sets of elements and can be viewed as unary predicates (Baader, 11)
- Concepts are built from concept names (i.e. Person, Course) and role names (i.e. teaches, studies) (Baader, 11)
- The set a concept represents is called its extension (Baader, 11)

In other words ... A concept is a representation of things, i.e. a set of elemenets, and can be viewed as single properties of the things.  Concepts contain two elements: 1) concept names (names which label the "thing," i.e. "teacher" or "student"), and 2) concept roles (binary relations which conjoin the things, or the concept names).  An extension of a concept is the set of names and roles that the concept represents. 

What is a TBox? "The TBox represents knowledge about the structure of the domain (similar to a database schema)" (Baader, 1)
Examples: What is a teacher?  What is a student?  What is a course? 

In other words ... The TBox, or terminological box, details the information of knowedge about what is contained by the domain, or the scope and structure, of by a concept and its extension. For example, who is a teacher, who is a student, and similar concept names fill out the TBox.  This is used to provide information about the structure, which is composed though defining each concept name within a particular concept.

Returning now to unpack Baader's original defintion of tree model property:
ALC has the tree model property, ie.e., if T is an ALC TBox (terminology box which describes/represents the strucutre of the domain) and C is an ALC concept (represents a set of elements that can be viewed as unary predicates, composed of concept names and role names) such that C is satisfiable with respect to T, then C has a tree model with respect to T.

To explain as if you were five ...

You have a bag full of writing utensils.  In your bag, there are multiple kinds of writing utensils in this bag: markers, highlighters, crayons, mechanical pencils, and pens.  Accordingly, there are this many of each writing utensil in the bag: 10 markers, 2 highlighers, 15 crayons, 1 mechanical pencils, and 2 pens.  You would like to know exactly what writing utensils you have in Your Bag.  To see the extend of your writing utensils, you take them all out of the bag and sort them into five distinct piles, grouping accordingly: markers, highlighters, crayons, mechanical pencils, and pens. Now you are able to see the entirety of your writing utensils, or your complete set of writing utensils.

Your Bag of Writing Utensils represents the concept, C.  T, the ALC TBox, is represented by the five different kinds of writing utensils: markers, highlighters, crayons, mechanical pencils, and pens.  Delaney describes concept satisfiability in the following way:  A concept is statisfiable so long as the concept is true under some assignment of values or on some intrepretation.  In assigning names to each writing utensil, we have filled out the TBox associated with the concept of Your Bag of Writing Utensils. The concept is true under this assignment/interpretation - Your Bag of Writing Utensils is complete/satified through the assignment and organization by type of writing utensil.  

In dividing up Your Bag of Writing Utensils, we have created something of a tree model.  Representationally, this can look like your (empty) bag at the top connected by five distinct strings to five distinct piles of utensils.  In this simple model, there are five branches of Writing Utensils.

The tree model property is probably important in situations where you may find something that does not belong in Your Bag of Utensils, thus making the concept unsatisfiable (maybe?).  For example, you may find a coin in Your Bag.  This is not a writing utensil and should not belong in Your Bag, or under the concept of Your Bag of Writing Utensils. Coin is not in the domain of writing utensils. 


Additions to the tree model property:
"Finally, the tree model property proved in the last section of this chapter implies that ALC cannot enforce cyclic role relationships." (Baader, 55)
I'm not sure exactly what a cyclical role relationship looks like, but there seems to be no cyclical role connecting the kinds of writing utensils with Your Bag.  Each kind is directly related (so, not cyclically related?) to the concept.

"It should also be noted that, in our definition of a tree model, we do not consider edge labels." (Baader, 66)
I'm also not sure what an edge label is, but a google search seems to connect the idea of edge labels with the idea of cyclical role relationships, so I am assume they are connected.  If so, they are not relevant to the specifications of the example provided above (unless they are, in some way, and I'm not aware). 


9. Open the Protege editor and create object properties for each of the role names that you constructed in question 1. You should have at least 6 object properties. Assert in the editor that P is a sub-property of O, that P is transitive, and that O is symmetric. Next, add individuals - a, b, c - to the file and assert that c is part of a and that c overlaps b. Running the reasoner should reveal - highlighted in yellow if you select the individual c - that c overlaps a. Using the discussion in the selections from chapter 4 of the Baader, et. al. text as a guide, explain how the tableau algorithm is generating this inference. Also, provide a screenshot of the results of your reasoner run with c highlighted. 

![Protege](https://user-images.githubusercontent.com/123913163/226708867-68c34a98-aaa4-41aa-b518-10ed04c77ee4.jpg)

From the google doc: The tableau method starts from a Knowledge Base, i.e. the assertions we made through the Protege editor about individuals and between classes. We then build a tree. Each node in the tree represents a possible interpretation, and the branches represent the different ways in which the interpretation can be extended. It then expands the assertions by using different rules. For example the disjunction rule to check all the possible cases (see Baader from page 71 to 73) and other rules for subsumption, etc. (see Baader pag. 84). What we are doing is basically constructing a set of possible interpretations where all the possible inferences from T-box are drawn, as well as all the possible concept memberships are tried.
As a result, the reasoner will notice the logical relations between the concepts we asserted for individuals through Protege. It will see that c is a part of a, and since parthood is subsumed by overlap, it will apply the subsumption rule explained at page 84 in Baader et al. This will add a new fact, that c overlaps a. 

In other words, we input the knowledge we have (assertions?) and allow Protege to take care of the logic which gives us our answer. 

I returned to pages 71-73 in Baader to try to understand this better.  This is not mentioned in the response above, but does this describe "checking ABox consistency?"  Page 72 states "This algorithm is very simple because, when the TBox is empty, the expansion rules only need to explicate the semantics of the concepts occurring in concept assertions in A. Moreover, because these rules syntactically decompose concepts, the algorithm naturally terminates when all concepts have been fully decomposed."  I can interpret this quote according to what is stated above (from the google doc) such that logical (expansion?) rules are applied to assertions (Knowledge Base?) and run through each possible interpretation until there are no further possible outcomes (decomposed?).  This is like the Zebra problem which required us to  input the information available + relations available and then Protege (magically) provided the answer, once all information was correctly in Protege. 


10. Following up on your work in question 9, adjust/add/remove/etc. object properties and individuals in your Protege file so that when you run a reasoner in Protege, you return the following consequences: 
```
  (a) a is a proper part of b and disjoint from e
  (b) a overlaps c
  (c) a is part of b, b is part of f, and a is part of f
  (e) There are no parts between a and g in common
```
Provide a screenshot of your results here. 

![Protege again](https://user-images.githubusercontent.com/123913163/226721969-27d05294-5ff6-405e-94d0-fb12a7864c48.jpg)

