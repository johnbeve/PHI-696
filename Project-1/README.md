# Project 1 Assignment

Your first project will require you to answer each of the 10 questions below.  You will be expected to open a pull request with your initial answers by the second class meeting, giving you one week to work on these problems. You and your peers will then have one week to work together to refine your respective initial answers, so they are ready for final submission. Once your pull requests have been reviewed and merged to the development branch, I will review them, then merge to the master branch. 

```
Tip #1: Carefully study the Hedman selections assigned, as several of the questions are taken directly from the textbook. 
Tip #2: Google is your friend. An important skill to pick up in this class is recognizing when to think hard and when to think smart. You might find answers to some of the questions below simply by googling; you might find pieces of answers to parts of some question below, which will need to be combined; then again, you might not find any help at all because the questions are more novel than they initially appear. I encourage you to use existing resources as guidance, but be careful. My reputation for asking students tricky questions is well-earned. 
Tip #3: Work _together_ to solve these problems, even for initial submissions and when you do, document this in github. For example, you might feel like you nearly have answers to question 1, but would love another pair of eyes. You can then open a post in your local github account, and tag folks from class requesting they check out your work. 
Tip #4: The work we do is challenging; that should be assumed. You are smart enough to be here; that should also be assumed. We have neither time nor space for shaming, but all of time and space for praising. Be cognizant of how your messages might be received, and err on the side of caution. It is hard to surmise intent from text alone. For my part, I treat text only communications the way modern musicals are written: Little subtext; emotions on the sleeve. 
```

Note: The standard interpretation of the logical symbols - "∨", "∧", "→", "¬", "∀", "∃" - is assumed throughout. 

1. Provide the truth tables for each of the following propositional logic formulas. State whether each is a tautology, a contradiction, or contingent:
  ```
  (a) (¬A→B)∨((A∧¬C)→B), Tautology
  A	B	C	((¬A → B) ∨ ((A ∧ ¬C) → B))
F	F	F	T
F	F	T	T
F	T	F	T
F	T	T	T
T	F	F	T
T	F	T	T
T	T	F	T
T	T	T	T

  (b) (A→B)∧(A→¬B), Contingent
  A	B	((A → B) ∧ (A → ¬B))
F	F	T
F	T	T
T	F	F
T	T	F

  (c) (A→(B∨C))∨(C→¬A), Tautology
  A	B	C	((A → (B ∨ C)) ∨ (C → ¬A))
F	F	F	T
F	F	T	T
F	T	F	T
F	T	T	T
T	F	F	T
T	F	T	T
T	T	F	T
T	T	T	T

  (d) ((A→B)∧C)∨(A∧D), Contingent
  A	B	C	D	(((A → B) ∧ C) ∨ (A ∧ D))
F	F	F	F	F
F	F	F	T	F
F	F	T	F	T
F	F	T	T	T
F	T	F	F	F
F	T	F	T	F
F	T	T	F	T
F	T	T	T	T
T	F	F	F	F
T	F	F	T	T
T	F	T	F	F
T	F	T	T	T
T	T	F	F	F
T	T	F	T	T
T	T	T	F	T
T	T	T	T	T
  ```
	
2. A _literal_ is an atomic formula or the negation of an atomic formula. We say a formula is in _conjunctive normal form_ (CNF) if it is the conjunction of the disjunction of literals. Find propositional logic formulas in CNF equivalent to each of the following:
  ```
  (a) (A→B)→C, CNF: (A∨C)∧(¬B∨C)
  (1) ¬(A→B)∨C
  (2) ¬(¬A→B)∨C
  (3) ¬(A→ ¬B)∨C
  (4) (A∨C)∧ (¬B∨C)
  
  (b) (A→(B∨C))∨(C→¬A), CNF: B ∨ ¬B (tautology)
  
  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A, CNF: B ∨ ¬B (tautology) 
  ```
  
3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  
  ```
  (a)  B(x,y) that says that x is a brother of y  
  
   B(x,y) <--> ∃x∃y∃z((Pzx ∧ Pzy) ∧ x ≠ y ∧ ~Fx)
  
  (b)  A(x,y) that says that x is an aunt of y  
  
  A(x,y) <--> ∃x∃y∃z((Fx ∧ Pzy ∧ ∃w(Pwx ∧ Pwz ∧ x ≠ z))
  
  (c)  C(x,y) that says that x and y are cousins
  
  C(x,y) <--> ∃x∃y∃z∃w∃r(Pzx ∧ Pwy ∧ Prz ∧ Prw ∧ z ≠ w ∧ x ≠ y)
  
  (d)  O(x) that says that x is an only child  
  
  O(x) <--> ∃x∃y∀z(Pyx ∧ (Pyz --> z = x))
  
  (e)  T(x) that says that x has exactly two brothers 
  
  T(x) <--> ∃x∃y∃z∃w∀r(Pyx ∧ Pyz ∧ Pyw ∧ z ≠ w ∧ w ≠ x ∧ x ≠ z ∧ (Pyr --> (r = x V r = w V r = z))) 
  
  ```

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```
  (a)  B that says that x is a brother of y
  
  B = M ∩ brother_of.Person
  
  (b)  A that says that x is an aunt of y
  (c)  C that says that x and y are cousins
  (d)  O that says that x is an only child  
  (e)  T that says that x has exactly two brothers 
  ```


5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 

6. Explain the difference - using natural language - between the first-order prefixes:
  ```
  (a) ∃x∀y and ∀x∃y
  
  ∀x∃y - For all x there exists some y 
  ∃x∀y - There exists an x for all y 
  
  (b) ∃x∀y∃z and ∀x∃y∀z 
  
  ∃x∀y∃z - 
  ∀x∃y∀z - 
  
  
  (c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
```
	
7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:
```
∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))
```
	
8. Using an online tableau proof generator - such as the one found here `https://www.umsu.de/trees/` - provide tree proofs of the following entailments, which are known as the De Morgan's laws:
  ```
  (a) ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
  
 (1) ¬∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
 (2) ¬∀y(¬(Pa ∧ Qa) → (¬Pa ∨ ¬Qa))
 (3) ¬(¬(Pa ∧ Qa) → (¬Pa ∨ ¬Qa))
 (4)¬(Pa ∧ Qa)
 (5)¬(¬Pa ∨ ¬Qa)
 (6).¬¬Pa
 (7)¬¬Qa
 (8)Qa
 (9) Pa
 (10) ¬Pa	(11) ¬Qa
        x	       x
 
  (b) ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
  
  (1) ¬∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
  (2) ¬∀y(¬(Pa ∧ Qa) → (¬Pa ∨ ¬Qa))
  (3) ¬(¬(Pa ∧ Qa) → (¬Pa ∨ ¬Qa))
  (4) ¬(Pa ∧ Qa)
  (5) ¬(¬Pa ∨ ¬Qa)
  (6) ¬¬Pa
  (7) ¬¬Qa
  (8) Qa
  (9) Pa
  (10) ¬Pa	(11) ¬Qa
        x	      x
  
  (c) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  
  (1) ¬∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  (2) ¬∀y((¬Pa ∨ ¬Qa) → ¬(Pa ∧ Qa))
  (3) ¬((¬Pa ∨ ¬Qa) → ¬(Pa ∧ Qa))
  (4) ¬Pa ∨ ¬Qa
  (5) ¬¬(Pa ∧ Qa)
  (6) Pa ∧ Qa
  (7) Pa
  (8) Qa
  (9) ¬Pa	(10) ¬Qa
     x		     x
  
  (d) ∀x∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
  
 (1) ¬∀x∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
 (2) ¬∀y((¬Pa ∧ ¬Qa) → ¬(Pa ∨ Qa))
 (3) ¬((¬Pa ∧ ¬Qa) → ¬(Pa ∨ Qa))
 (4) ¬Pa ∧ ¬Qa
 (5) ¬¬(Pa ∨ Qa)
 (6) Pa ∨ Qa
 (7) ¬Pa
 (8) ¬Qa
 (9) Pa		(10) Qa
     x		     x
  
```
	
9. Using a natural deduction proof generator - such as the one found here `https://proofs.openlogicproject.org/` - provide natural deduction proofs for each of De Morgan's laws. 

¬∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
(1) ¬(Px ∧ Qx)		assumption
(2) ¬(¬Px ∨ ¬Qx)	assumption
(3) (Px ∧ Qx)		2, negated disjunction
(4) ¬(Px ∧ Qx)		1,3 contradiction

∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
(1) ¬(Px ∨ Qx)		assumption
(2) (¬Px ∧ ¬Qx)		assumption
(3) (Px ∨ Qx)		2, negated conjunction
(4) ¬(Px ∨ Qx)		1,3 contradiction

∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
(1) (¬Px ∨ ¬Qx)		assumption
(2) ¬¬(Px ∧ Qx)		assumption
(3) (Px ∧ Qx)		2, double negation
(4) Px			3, conjunction
(5) Qx			3, conjunction
(6) (¬Px ∨ ¬Qx)		4,5,6 contradiction

∀x∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
(1) (¬Px ∧ ¬Qx)		assumption
(2) ¬¬(Px ∨ Qx)		assumption
(3) (Px ∨ Qx)		2, double negation
(4) ¬Px			1, conjunction
(5) ¬Qx			1, conjunction
(6) Px			3, disjunction
(7) ¬Qx			3, disjunction
(8) ¬Px			3, disjunction
(9) Qx			3, disjunction
(10) (¬Px ∧ ¬Qx)	6,7,8,9 contradiction


10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 

Both proofs seek contradictions.  In step 3 in the proof for 8a, it seems ¬((¬Pa ∧ ¬Qa) → ¬(Pa ∨ Qa)) is negated (to arrive at steps 4 and 5), but I don't know.  The proof for 9a is much shorter and simply negates the consequent.  
 
