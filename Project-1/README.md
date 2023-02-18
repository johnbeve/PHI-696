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
  
  (a) (¬A→B)∨((A∧¬C)→B) 
  (b) (A→B)∧(A→¬B)
  (c) (A→(B∨C))∨(C→¬A) 
  (d) ((A→B)∧C)∨(A∧D) 
  
  Answer:
  
  (a) is a tautology. 
  
|  A |  B   |   C   |	((¬A → B) ∨ ((A ∧ ¬C) → B)) |
| -- | ---  | ---   | ------------------------------|
|  F |  F   | 	F   |	T                           |
|  F |	F   | 	T   |   T
|  F |	T   |	F   |	T
|  F |	T   |	T   |	T
|  T |	F   |	F   |	T
|  T |	F   |	T   |	T
|  T |	T   |	F   |	T
|  T |	T   |	T   |	T

 (b) is contingent.
 
| A  |	B   |	((A → B) ∧ (A → ¬B)) |
|--- | ---  | -----------------------|
| F  |	F   |	T                    |
| F  |	T   |	T
| T  |	F   |	F
| T  |	T   |	F
 
 (c) is a tautology
 
| A  |	B   |	C   |	((A → (B ∨ C)) ∨ (C → ¬A)) |
| -- | ---  | ----  | ---------------------------- |
| F  |	F   |	F   |   T
| F  |	F   |	T   |	T
| F  |	T   |	F   |	T
| F  |	T   |	T   |	T
| T  |  F   |	F   |	T
| T  |	F   |	T   |	T
| T  |	T   |	F   |	T
| T  |	T   |	T   |	T

 (d) is contigent.
 
| A  |	B   |	C   |	D   |	(((A → B) ∧ C) ∨ (A ∧ D)) |
| -- | ---- | ----- | ----- | ----------------------------|
| F  |	F   |	F   |	F   |	F
| F  |	F   |	F   |	T   |	F
| F  |	F   |	T   |	F   |	T
| F  |	F   |	T   |	T   |	T
| F  |	T   |   F   |	F   |	F
| F  |	T   |	F   |	T   |	F
| F  |	T   |	T   |	F   |	T
| F  |	T   |	T   |	T   |	T
| T  |	F   |	F   |	F   |	F
| T  |	F   |	F   |	T   |	T
| T  |	F   |	T   |	F   |	F
| T  |	F   |	T   |	T   |	T
| T  |	T   |	F   |	F   |	F
| T  |	T   |	F   |	T   |	T
| T  |	T   |	T   |	F   |	T
| T  |	T   |	T   |	T   |	T


	
2. A _literal_ is an atomic formula or the negation of an atomic formula. We say a formula is in _conjunctive normal form_ (CNF) if it is the conjunction of the disjunction of literals. Find propositional logic formulas in CNF equivalent to each of the following:
  
  (a) (A→B)→C
  (b) (A→(B∨C))∨(C→¬A)
  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 
  
  Answer:
  
  (a) CNF: (A∨C)∧(C∨(¬B))
  
  (b) CNF: C v ¬C
  Since (b) is a tautology, its CNF form can be any formula of the form pv¬p. 
  
  (c) CNF: C v ¬C
  (c) is a tautology.
  
3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  
  (a)  B(x,y) ≡ ∃u(P(u,x)∧P(u,y))∧¬F(x)∧¬(x=y)∧¬(u=x)

  
  (b)  A(x,y) cannot be defined in this vocabulary because an aunt and her nephew may not have a blood relation and there is no marriage relation available in the vocabulary. 
  
  
  (c)  C(x,y) ≡ ∃w∃u∃z(P(w,z)∧P(w,u)∧P(z,x)∧P(u,y)∧¬(z=u))∧¬(x=y))v∃k∃m∃n∃g(P(k,m)∧P(k,n)∧P(m,x)∧P(n,g)∧P(g,y)∧¬(m=n)∧¬(n=x)∧¬(g=x)∧¬(n=y)∧¬(m=g)∧¬(y=x))
  
  
  (d)  O(x) ≡ ∃u(P(u,x)∧∀y(P(u,y)→x=y))
    
 
  (e)  T(x) ≡ ∃u∃y∃z(¬(y=z)∧¬(x=y)∧¬(x=z)∧P(u,x)∧P(u,y)∧P(u,z)∧¬F(y)∧¬F(z))∧∀w(P(u,w)∧¬F(w)→ w=x ∨ w=y ∨ w=z)
  

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```
  (a)  B that says that x is a brother of y

  Answer: 
  
  The formula cannot be defined in ALC, because the defination needs a inverse role name. 

  (b)  A that says that x is an aunt of y
  
  Answer: 
  The formula cannot be defined in ALC, because the defination needs an inverse role name. 
  
  (c)  C that says that x and y are cousins
  
  Answer: 
  The formula cannot be defined in ALC, because the defination needs number restrictions. 
  
  
  (d)  O that says that x is an only child  
  
  Answer:
  
  The formula cannot be defined in ALC, because the defination needs number restrictions and an inverse role name.
  
  (e)  T that says that x has exactly two brothers
  
  Answer: 
  
  The formula cannot be defined in ALC, because the defination needs number restrictions and inverse role names.

5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 

Answer: 

There is no formula to choose from Q4, because ALC is not expressive enough. 

6. Explain the difference - using natural language - between the first-order prefixes:
  
  (a) ∃x∀y and ∀x∃y
  Answer: the former means that there exists a x that for all y such that, while the latter means that for all x there exists a y such that.
  
  (b) ∃x∀y∃z and ∀x∃y∀z 
  Answer: the former means that there exists a x that for all y there exists a z such that, while the latter means that for all x there exists a y that for all z such that. 
  
  (c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
  Answer: the former means that for all x, there exists a y that for all z, there exists a w such that, while the latter means that there exists a x that for all y, there exists a z that for all w such that.
  
	
7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:

∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))

Answer: 

The following graph models the second sentence but not the first sentence:
Verticles: a, b, c
Edges: ab, ac, aa (loop)

See attached picture: image 0.

	
8. Using an online tableau proof generator - such as the one found here `https://www.umsu.de/trees/` - provide tree proofs of the following entailments, which are known as the De Morgan's laws:
  (a) ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
  Tree proof:
  ¬∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
  ¬∀y(¬(Pa ∧ Qa) → (¬Pa ∨ ¬Qa))      (1)
  ¬(¬(Pa ∧ Qa) → (¬Pa ∨ ¬Qa)).       (2)
         ¬(Pa ∧ Qa)                  (3)
         ¬(¬Pa ∨ ¬Qa)                (3)
            ¬¬Pa                     (5)
            ¬¬Qa                     (5)
             Qa                      (7)
             Pa                      (6)
  
  ¬Pa (4)              ¬Qa (4)
   x                   x
             
  (b) ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
  Tree proof:
  
   ¬∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))  
   ¬∀y(¬(Pa ∨ Qa) → (¬Pa ∧ ¬Qa))     (1)
    ¬(¬(Pa ∨ Qa) → (¬Pa ∧ ¬Qa))      (2)
           ¬(Pa ∨ Qa)                (3)
           ¬(¬Pa ∧ ¬Qa)              (3)
	       ¬Pa                   (4)
               ¬Qa                   (4)

¬¬Pa (5)                ¬¬Qa (5)  
  Pa (8)                  Qa (9)
  x                       x
  
  (c) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  Tree proof:
  ¬∀x∀y((¬Px ∨ ¬Qx) →  ¬(Px ∧ Qx))
   ¬∀y(¬(Pa ∨ Qa) →  ¬(Pa ∧ Qa))     (1)
    ¬(¬(Pa ∨ Qa) →  ¬(Pa ∧ Qa))      (2)
           ¬Pa ∨  ¬Qa               (3)
           ¬¬(Pa ∧ Qa)              (3)
	    Pa ∧ Qa                 (5)
	       Pa                   (6)
               Qa                   (6)

  ¬Pa (4)                 ¬Qa (4)  
  x                        x
   
  
  (d) ∀x∀y(¬(Px ∨ Qx) → ¬(Px ∧ Qx))
 Tree proof: same as (c)
 
	
9. Using a natural deduction proof generator - such as the one found here `https://proofs.openlogicproject.org/` - provide natural deduction proofs for each of De Morgan's laws. 


  first step: ∀x((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
   
 1. ¬Pa ∨ ¬Qa          premise
|2. ¬¬(Pa ∧ Qa)        assumption
|3. Pa ∧ Qa            ¬E2
|4. Pa                ∧E3
|5. Qa                ∧E3
|6. ⊥                ⊥I 1,4,5
 7. ¬¬¬(Pa ∧ Qa)      ¬I 2-6
 8. ¬(Pa ∧ Qa)        VE 1-7
 9. ∀x(¬Px ∨ ¬Qx) → ¬(Px ∧ Qx) →I1-8
 


  Second step: ∀x ( ¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
 
 1.  ¬(Pa ∧ Qa)               premise
|2.  ¬(¬Pa ∨ ¬Qa)             assumption
| |3.  ¬Pa                   assumption 
| |4.  ¬Pa ∨ ¬Qa              ∨I3
| |5. ⊥                    ⊥I2,4
|6. Pa                      ⊥I3-5
| |7. ¬Qa                    assmuption
| |8. ¬Pa ∨ ¬Qa               ∨I7
| |9. ⊥                    ⊥I2,8
|10. Qa                     ⊥I 7-9
|11. Pa ∧ Qa                 ∧I6,10
|12. ⊥                     ⊥I1,11
13. ¬¬(¬Pa ∨ ¬Qa)             ⊥I2-12         
14. ¬Pa ∨ ¬Qa                 ¬E13
15.  ¬(Pa ^ Qa)→( ¬Pa V ¬Qa)  →I1-14
16. ∀x( ¬(Px ∧ Qx)→( ¬Px v ¬Qx)  ∀I 16


Third step:  ¬(p v q) → ¬p  ∧ ¬q

See the attachment: image 3.

Fourth step:  ¬p ∧ ¬q → ¬(p v q)

see the attachment: image 4.


10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 

For (a), the natural deduction proof applies mutiple deductive rules including disjunction elimination or double negation elimination (DNE), while the Tree proof only uses indirect derivation. That is a tree proof just focuses on finding possible logical contradictions among negated subformulas of the target formula.


