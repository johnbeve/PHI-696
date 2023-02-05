# Project 1 Assignment

Your first project will require you to answer each of the 10 questions below.  You will be expected to open a pull request with your initial answers by the second class meeting, giving you one week to work on these problems. You and your peers will then have one week to work together to refine your respective initial answers, so they are ready for final submission. Once your pull requests have been reviewed and merged to the development branch, I will review them, then merge to the master branch. 

```Tip #1: Carefully study the Hedman selections assigned, as several of the questions are taken directly from the textbook. 
Tip #2: Google is your friend. An important skill to pick up in this class is recognizing when to think hard and when to think smart. You might find answers to some of the questions below simply by googling; you might find pieces of answers to parts of some question below, which will need to be combined; then again, you might not find any help at all because the questions are more novel than they initially appear. I encourage you to use existing resources as guidance, but be careful. My reputation for asking students tricky questions is well-earned. 
Tip #3: Work _together_ to solve these problems, even for initial submissions and when you do, document this in github. For example, you might feel like you nearly have answers to question 1, but would love another pair of eyes. You can then open a post in your local github account, and tag folks from class requesting they check out your work. 
Tip #4: The work we do is challenging; that should be assumed. You are smart enough to be here; that should also be assumed. We have neither time nor space for shaming, but all of time and space for praising. Be cognizant of how your messages might be received, and err on the side of caution. It is hard to surmise intent from text alone. For my part, I treat text only communications the way modern musicals are written: Little subtext; emotions on the sleeve. 
```

Note: The standard interpretation of the logical symbols - "∨", "∧", "→", "¬", "∀", "∃" - is assumed throughout. 

1. Provide the truth tables for each of the following propositional logic formulas. State whether each is a tautology, a contradiction, or contingent:
  ```
 
(a) (¬A→B)∨((A∧¬C)→B) <<< **This is a Tuatology**

| A | B | C | ((¬A → B) ∨ ((A ∧ ¬C) → B)) |
|:-:|:-:|:-:|:---------------------------:|
| F | F | F | T                           |
| F | F | T | T                           |
| F | T | F | T                           |
| F | T | T | T                           |
| T | F | F | T                           |
| T | F | T | T                           |
| T | T | F | T                           |
| T | T | T | T                           |


  (b) (A→B)∧(A→¬B) <<< **This is Contingent**

| **A** | **B** | **((A → B) ∧ (A → ¬B))** |
|:-----:|:-----:|:------------------------:|
|   F   |   F   |             T            |
|   F   |   T   |             T            |
|   T   |   F   |             F            |
|   T   |   T   |             F            |


  (c) (A→(B∨C))∨(C→¬A) <<< **This is a Tuatology**

| A | B | C | ((A → (B ∨ C)) ∨ (C → ¬A)) |
|:-:|:-:|:-:|:--------------------------:|
| F | F | F | T                          |
| F | F | T | T                          |
| F | T | F | T                          |
| F | T | T | T                          |
| T | F | F | T                          |
| T | F | T | T                          |
| T | T | F | T                          |
| T | T | T | T                          |


  (d) ((A→B)∧C)∨(A∧D) <<< **This is contingent**

| A | B | C | D | (((A → B) ∧ C) ∨ (A ∧ D)) |
|:-:|:-:|:-:|:-:|:-------------------------:|
| F | F | F | F | F                         |
| F | F | F | T | F                         |
| F | F | T | F | T                         |
| F | F | T | T | T                         |
| F | T | F | F | F                         |
| F | T | F | T | F                         |
| F | T | T | F | T                         |
| F | T | T | T | T                         |
| T | F | F | F | F                         |
| T | F | F | T | T                         |
| T | F | T | F | F                         |
| T | F | T | T | T                         |
| T | T | F | F | F                         |
| T | T | F | T | T                         |
| T | T | T | F | T                         |
| T | T | T | T | T                         |


2. A _literal_ is an atomic formula or the negation of an atomic formula. We say a formula is in _conjunctive normal form_ (CNF) if it is the conjunction of the disjunction of literals. Find propositional logic formulas in CNF equivalent to each of the following:
  ```(a) (A→B)→C
 **(A∨B∨C) ∧ (A∨¬B∨C) ∧ (¬A∨¬B∨C)**
  
  (b) (A→(B∨C))∨(C→¬A)
 **No CNF form is possible, as this is a Tuatology.**
   
  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 
  **No CNF form is possible, as this is a Tuatology.**
  
3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  
  (a)  B(x,y) that says that x is a brother of y
  	**Not possible; unless "brother" is considered sex and/or gender neutral and the neutral, in which case (∃x(F(x)∧(B(x,y))))**
	
  (b)  A(x,y) that says that x is an aunt of y
  	***Possible: (∃x(F(x)∧(A(x,y))))**
	
  (c)  C(x,y) that says that x and y are cousins
  	**Possible: (∃x(C(x,y)))**
	
  (d)  O(x) that says that x is an only child 
  	**Not Possible: as (P(x,y)) is a parent relationship, and (O(x)) describes a *child_of* relationship, V does not have the relation necessary**
	
  (e)  T(x) that says that x has exactly two brothers
  	**Possible: (∃x(P(x,y)∧T(x)))**

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```
  (a)  B that says that x is a brother of y
  	**Possible: MB ≡ M∩∃B**
	
  (b)  A that says that x is an aunt of y
  	**Not Possible, unless "aunt" is considered a gender neutral term, in which case; MA ≡ M∩∃A**
	
  (c)  C that says that x and y are cousins
  	**Possible: MC ≡ M∩∃C**
	
  (d)  O that says that x is an only child  
  	**Not Possible, as nd O describes a *child_of* relationship, V does not have the relation necessary**
	
  (e)  T that says that x has exactly two brothers 
	**Possible: I have no idea how.**

5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 
	
	**There's literally no way I can do this correctly.**
	
	1) B that says that x is a brother of y
		T1 = {Brother	⊆ Entity
			X	⊆ exists.Entity
			Y	⊆ exists.Entity
		No.... this can't be right. There's an existential quantifier on page 18... the existence is... presumed? But the problem with it is that they're using "Teacher" in the example, but they don't mean it as a concept, but as a "thing"... I have no idea how to go about this with an X and a Y, which are not "things which exist".				
	
	
	2) O that says that x is an only child.
	See above. Obviously I have no idea what I'm doing.
	

6. Explain the difference - using natural language - between the first-order prefixes:
  ```
  (a) ∃x∀y and ∀x∃y
  	** These read "There exists some X such that for all y..." and "For all x there exists some y such that..." There is no way to explain the difference beyond this because there is no meaning associated with these prefixes. They are analogous to "sentence fragments" from natural language where the Subject was missing and the only verb is "is"; "Is large and blue."  **
	
  (b) ∃x∀y∃z and ∀x∃y∀z 
  	** These read "There exists some X such that for all Y and some z..." and "For all X there exists some Y such that all Z. .. " There is no way to explain the difference beyond this because there is no meaning associated with these prefixes. **
	
  (c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
  	** These read "For all X there exists some Y such that all Z and some W. . ." and "There exists some X for all Y such that some some Z and all W . . . " There is no way to explain the difference beyond this because there is no meaning associated with these prefixes. **
  
```
	
7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:
```
∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))
** I have no idea where to even begin. Do I just *make up* verticies and edges? How would I have any idea how many I needed?**

```
	
8. Using an online tableau proof generator - such as the one found here `https://www.umsu.de/trees/` - provide tree proofs of the following entailments, which are known as the De Morgan's laws:
  ```
  (a) ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
  ![proof(1)](https://user-images.githubusercontent.com/123899465/216850416-7fb691da-f18f-4164-877c-bc1064085130.png)

  (b) ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
  ![proof(2)](https://user-images.githubusercontent.com/123899465/216850442-db0062d8-5ffb-4e46-bec6-1135c47a53a8.png)

  (c) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  ![proof(3)](https://user-images.githubusercontent.com/123899465/216850473-a00e0b27-ee52-43a3-a2b8-e7060cd0abac.png)

   (d) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
    ![proof(4)](https://user-images.githubusercontent.com/123899465/216850506-16aea313-2ca2-4297-8615-668f8d5a3701.png)

```
	
9. Using a natural deduction proof generator - such as the one found here `https://proofs.openlogicproject.org/` - provide natural deduction proofs for each of De Morgan's laws.
I honestly couldn't figure out how to use the Natural Deduction Proof checker. There's nothing to see here but my utter lack of knowledge.

10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 
I couldn't begin to and this was due an hour ago.
