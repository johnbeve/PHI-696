# Project 1 Assignment

Your first project will require you to answer each of the 10 questions below.  You will be expected to open a pull request with your initial answers by the second class meeting, giving you one week to work on these problems. You and your peers will then have one week to work together to refine your respective initial answers, so they are ready for final submission. Once your pull requests have been reviewed and merged to the development branch, I will review them, then merge to the master branch. 

```Tip #1: Carefully study the Hedman selections assigned, as several of the questions are taken directly from the textbook. 
Tip #2: Google is your friend. An important skill to pick up in this class is recognizing when to think hard and when to think smart. You might find answers to some of the questions below simply by googling; you might find pieces of answers to parts of some question below, which will need to be combined; then again, you might not find any help at all because the questions are more novel than they initially appear. I encourage you to use existing resources as guidance, but be careful. My reputation for asking students tricky questions is well-earned. 
Tip #3: Work _together_ to solve these problems, even for initial submissions and when you do, document this in github. For example, you might feel like you nearly have answers to question 1, but would love another pair of eyes. You can then open a post in your local github account, and tag folks from class requesting they check out your work. 
Tip #4: The work we do is challenging; that should be assumed. You are smart enough to be here; that should also be assumed. We have neither time nor space for shaming, but all of time and space for praising. Be cognizant of how your messages might be received, and err on the side of caution. It is hard to surmise intent from text alone. For my part, I treat text only communications the way modern musicals are written: Little subtext; emotions on the sleeve. 
```

Note: The standard interpretation of the logical symbols - "∨", "∧", "→", "¬", "∀", "∃" - is assumed throughout. 

1. Provide the truth tables for each of the following propositional logic formulas. State whether each is a tautology, a contradiction, or contingent:
  ```(a) (¬A→B)∨((A∧¬C)→B) 
 
 - (¬A→B) means if 'not A' then B
 - (A∧¬C)→B means if A with 'not C', then B
 - So, (¬A→B)∨((A∧¬C)→B) means either one or both of them are true.
 
 A ¬A   C ¬C  B ¬B (¬A→B)∨((A∧¬C)→B) ¬(¬A→B)∨((A∧¬C)→B)
 T  F   T  F  F  T       F                  T  
 T  F   F  T  T  F       T                  F
 F  T   T  F  T  F       T                  F 
 F  T   F  T  T  F       T                  F

 - Am I doing this right?? 
 - If I am, this is a contingent.
  
  ```(b) (A→B)∧(A→¬B)
  
 - (A→B)∧(A→¬B) means if 'A' then 'B' and if 'A' then 'not-B' are true at the same time.
  
 A ¬A  B ¬B  (A→B)∧(A→¬B)
 T  F  T  F       F
 F  T  F  T       F
 T. F. F  T.      T
 F. 
 
 - If I am doing this right, this is a contingent.

  
  ```(c) (A→(B∨C))∨(C→¬A) 
  
 - (A→(B∨C)) means if 'A', then either 'B', 'C', or both.
 - (C→¬A) means if 'C', then 'not A'.
 - (A→(B∨C))∨(C→¬A) means either one or both of the above statements are true.
 - Well, both of the statements cannot be true because A∧¬A is a contradiction.
 
 A  B  C ¬A ¬B ¬C A→(B∨C) (C→¬A) (A→(B∨C))∨(C→¬A)
 
 
  
  
 
  ```(d) ((A→B)∧C)∨(A∧D)
  A B C D ¬A ¬B ¬C ¬D ((A→B)∧C)∨(A∧D)
  
  

	
2. A _literal_ is an atomic formula or the negation of an atomic formula. We say a formula is in _conjunctive normal form_ (CNF) if it is the conjunction of the disjunction of literals. Find propositional logic formulas in CNF equivalent to each of the following:
  ```(a) (A→B)→C
  (b) (A→(B∨C))∨(C→¬A)
  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 
```

3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```(a)  B(x,y) that says that x is a brother of y
  (b)  A(x,y) that says that x is an aunt of y
  (c)  C(x,y) that says that x and y are cousins 
  (d)  O(x) that says that x is an only child
  (e)  T(x) that says that x has exactly two brothers 
```

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```(a)  B that says that x is a brother of y
  (b)  A that says that x is an aunt of y
  (c)  C that says that x and y are cousins 
  (d)  O that says that x is an only child
  (e)  T that says that x has exactly two brothers 
```

5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 

6. Explain the difference - using natural language - between the first-order prefixes:
  ```(a) ∃x∀y and ∀x∃y

-  ∃x∀y means the existence at least one 'x' contains all cases of 'y'. ∀x∃y means all cases of 'x' contain the existence of at least one 'y'.
  The difference comes from potentially restricting either x or y. 
  
  
  (b) ∃x∀y∃z and ∀x∃y∀z 
  (c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
```
	
7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:
```
∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))
```
	
8. Using an online tableau proof generator - such as the one found here `https://www.umsu.de/trees/` - provide tree proofs of the following entailments, which are known as the De Morgan's laws:
  ```(a) ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
  (b) ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
  (c) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  (d) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
```
	
9. Using a natural deduction proof generator - such as the one found here `https://proofs.openlogicproject.org/` - provide natural deduction proofs for each of De Morgan's laws. 

10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 

