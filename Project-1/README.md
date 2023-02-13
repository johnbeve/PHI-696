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
  
  ```
  (a)  B(x,y) that says that x is a brother of y  
  B(x,y) := ∃z.(P(zx) ∧ P(zy) ∧ ¬(z=y)) ∧ ¬(z=x) ¬(x=y) ¬F(x)
  (b)  A(x,y) that says that x is an aunt of y  
  A(x,y) := ∃z∃w.(P(zy) ∧ P(wz) ∧ P(wx) ∧ ¬(z=x)) F(x)
  (c)  C(x,y) that says that x and y are cousins   
  C(x,y) := ∃u∃w∃z(P(w,z)∧P(w,u)∧P(z,x)∧P(u,y)∧¬(z=u))∧¬(x=y)
  (d)  O(x) that says that x is an only child  
  O(x) := ∃y.(P(yx) ∧ ∀z.(P(yz) → (w=y)))
  (e)  T(x) that says that x has exactly two brothers 
  T(x) := ∃u∃y∃z(¬(y=z)∧¬(x=y)∧¬(x=z)∧P(u,x)∧P(u,y)∧P(u,z)∧¬F(y)∧¬F(z))∧∀w(P(u,w)∧¬F(w)→ w=x ∨ w=y ∨ w=z)

  ```

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```
  (a)  B that says that x is a brother of y

  Per (Person) ≡ M ⊔ ¬M
  p2 (Parent of 2) ≡ ∃parentof. ≥ 2 ⊓ ¬(∃parentof. = 1) (this condition is meant to avoid that the two persons are the same, but I am not entirely sure it works or whether there are better ways to do so)
  
  B ≡ M ⊓ ∃p2¯.Per

  (b)  A that says that x is an aunt of y
  
  ∃p2¯.parentof.parentof.Per

  A ≡ ¬M ⊓ (∃p2¯. (parentof. Per ≥ 2).(parentof.Per)) ⊔ ¬parentof.Per 
  
  U(uncle) ≡ M ⊓ (∃p2¯. (parentof. Per ≥ 2).(parentof.Per)) ⊔ ¬parentof.Per 

  (c)  C that says that x and y are cousins

  gp2(Grandparent with at least two children which each have children) ≡ ∃parentof ≥ 2.parentof.Per

  C ≡ gp2¯.per

  But this would only describe one of the two cousins, i.e. "being a cousin of someone" or "having a cousin".
  We cannot define "being cousins" in description logic.

  (d)  O that says that x is an only child  

  O ≡ ¬ ∃p2¯.Per

  (e)  T that says that x has exactly two brothers 

  This cannot be done without a role name for brother, we only have a concept name for it.

  ```

5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 
	
	TBox = {
B ⊑ M
B ⊑ Per
M ⊑ Per
A ⊑ ¬M
A ⊑ Per
}

ABox = { John : M
John : parentof. Chris
John: B
Chris: M
Mary : ¬M
Mary: A
Alexander : parentof. Mary
Alexander : parentof. John
}

ΔI = {John, Mary, Alexander, Chris}

Named Individuals:
JohnI = J,
MaryI = M,
AlexanderI = A,
Chris = C

Concept Assignments:
PersonI = {J, M, A, C},
MaleI = {J, A, C},
FemaleI = {M},
BrotherI = {J},
AuntI = {M}

Role Assignments:
parentofI = {(J, C), (A, J), (A, M)}
	
	

6. Explain the difference - using natural language - between the first-order prefixes:
  ```
  (a) ∃x∀y and ∀x∃y
  	** These read "There exists some X such that for all y..." and "For all x there exists some y such that..." There is no way to explain the difference beyond this because these are incomplete sentences. They are analogous to "sentence fragments" from natural language where the Subject was missing and the only verb is "is"; "Is large and blue."  **
	
  (b) ∃x∀y∃z and ∀x∃y∀z 
  	** These read "There exists some X such that for all Y and some z..." and "For all X there exists some Y such that all Z. .. " There is no way to explain the difference beyond this because these are incomplete sentences **
	
  (c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
  	** These read "For all X there exists some Y such that all Z and some W. . ." and "There exists some X for all Y such that some some Z and all W . . . " There is no way to explain the difference beyond this because these are incomplete sentences.  **
  
```
	
7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:
```
∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))

```
 {(a,b)(b,a)(a,a)} 
 The second statement is true in this model. There is an x that relates every y (a, related to a and b) There is an x that relates to a z (where a is x and b is z), all ys (a and b) are related to some z (a is related to a and b, b is related to a)
 The first statement is not true. It is not true that all xs (a and b) are related to all zs (b is not related to a)

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
a) 
assume -(Px & Qx).
  assume -(-Px + -Qx).
    assume -Px.
      -Px + -Qx.
      F.
    therefore --Px.
    assume Qx.
      Px.
      assume -(-Px + -Qx).
        Px & Qx.
        F.
      therefore --(-Px + -Qx).
      F.
    therefore -Qx.
    -Px + -Qx.
    F.
  therefore --(-Px + -Qx).
  -Px + -Qx.
therefore -(Px & Qx) => -Px + -Qx.	

b)
assume -(Px + Qx).
  assume Px.
    Px + Qx.
    F.
  therefore -Px.
  assume Qx.
    Px + Qx.
    F.
  therefore -Qx.
  -Px & -Qx.
therefore -(Px + Qx) => -Px & -Qx.	    

c)
assume -Px + -Qx.
  assume Px & Qx.
    Px.
    Qx.
    assume -Px.
      F.
    therefore -Px => F.
    assume -Qx.
      F.
    therefore -Qx => F.
    F.
  therefore -(Px & Qx).
therefore -Px + -Qx => -(Px & Qx).

d)
assume -Px & -Qx.
  assume Px + Qx.
    assume Px.
      -Px.
      F.
    therefore Px => F.
    assume Qx.
      -Qx.
      F.
    therefore Qx => F.
    F.
  therefore -(Px + Qx).
therefore -Px & -Qx => -(Px + Qx).	

10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 

The tableau proofs are more systematizable because they take the negation of each statement; this is a fixed starting point which does not require any choice between options. The natural proof method is more flexible and depends on dividing the original statement into an assumption/consequent pair; this is less easy to systematize, because the division needs to be chosen.
