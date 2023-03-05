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
  (a) (¬A→B)∨((A∧¬C)→B) Tautology
  A	B	C	((¬A → B) ∨ ((A ∧ ¬C) → B))
F	F	F	T
F	F	T	T
F	T	F	T
F	T	T	T
T	F	F	T
T	F	T	T
T	T	F	T
T	T	T	T

  (b) (A→B)∧(A→¬B) Contingent
  A	B	((A → B) ∧ (A → ¬B))
F	F	T
F	T	T
T	F	F
T	T	F

  (c) (A→(B∨C))∨(C→¬A) Tautology
  A	B	C	((A → (B ∨ C)) ∨ (C → ¬A))
F	F	F	T
F	F	T	T
F	T	F	T
F	T	T	T
T	F	F	T
T	F	T	T
T	T	F	T
T	T	T	T
  (d) ((A→B)∧C)∨(A∧D) Contingent
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
  (a) (A→B)→C
  (A∨C)∧(¬B∨C)
  (b) (A→(B∨C))∨(C→¬A)
  Av~A
  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 
 Bv~B
  ```
  
3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  
  ```
  Note that any definitions require that V has access to the connectives and quantifiers of first-order logic, which is not specified in the prompt. I have assumed that they are available, as otherwise there is no way to define any of the formulas in the following examples. 
  
  Also note that none of the gendered examples are definable if we allow for non-binary genders and if we read male or female as terms referring to sex rather than gender. In the first case, this would mean that we cannot assume that man and women are binary opposites to which these labels apply. In the latter, case, male or female unary relations will not refer to any of the gendered terms mentioned below.
  
  (a)  B(x,y) that says that x is a brother of y
  B= ∃(x)∃(y)∃(z) (P(z,x)^P(z,y)^~F(x))
  (b)  A(x,y) that says that x is an aunt of y
  A(x,y)= ∃(x)∃(y)∃(z)∃(w) (P(z,y)^P(w,z)^P(w,x)^~P(x,y)^Fx).
  (c)  C(x,y) that says that x and y are cousins
  C(x,y): ∃(v)∃(w)∃(x)∃(y)∃(z) (P(v,x)^P(w,y)^P(z,v)^P(z,w)^~P(w,x)^~P(v,y))
  (d)  O(x) that says that x is an only child 
  O(x)= ∃(x)∃(y)(P(x,y)^~∃(z)P(x,z))
  (e)  T(x) that says that x has exactly two brothers
  T(x)= ∃(w)∃(x)∃(y)∃(z) ((P(w,x)^(P(w,y)^(P(w,z)^~F(y)^~(F(z))^~∃(v)(P(w,v))
  ```

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```
  (a)  B that says that x is a brother of y
  B= Parent_of: (zx, zy) Male^∃Parent_of.(∃parent_of>=2).
  Male: (x)
  (b)  A that says that x is an aunt of y
  A: Parent_of: (zw, zx, wy) ~Male^(∃parent_of.(∃parent_of>=1).^~∃parent_of.(>=1).)
  (c)  C that says that x and y are cousins
  C: parent_of: (zx, wy, vw, vz) ∃Parent_of.(∃parent_of>=2).^∃Parent_of.(∃parent_of>=1).^∃Parent_of.(∃parent_of>=1).
  (d)  O that says that x is an only child 
  O= parent_of (∃parent_of=1) 
  (e)  T that says that x has exactly two brothers 
  T= Parent_of: (wx,wy,wz) ∃parent_of.(∃Parent_of=3)^Male(∃Male>=2)
  Male: (y,z)
  ```


5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 
B= Male^∃Parent_of.(∃parent_of>=2).
O= parent_of (∃parent_of=1)
O^~B
B^~O
Jason: B
(Mary Ann, Jason)
(Mary Ann, Mona)
Killian: O
Amanda: Parent_of Killian
Jason: (w,B)
Mary Ann: Z
Mona: Y
Killian: (O,x)
Amanda: v
parent: (z,v)
brother: w
Only child: x
child: w,y,x
parent_of: zw,zy,vx
Male: x,w

6. Explain the difference - using natural language - between the first-order prefixes:
  ```
  (a) ∃x∀y and ∀x∃y
  The first claims that for something such that it is x, every thing such that it is Y has a certain relationship with it. The second claims that for all things such that they are X, there is some Y that has a certain relationship with it.
  (b) ∃x∀y∃z and ∀x∃y∀z 
  The first claims that for something such that it is x, everything such that it is Y has a certain relationship with X and that there is something such that it is Z has a certain relationship with all Ys and some X. The second claims that for all things such that they are X, there is something such that it is Y that has a certain relationship with it and everything such that it is Z has a certain relationship with some Y and everything such that it is X.
  (c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
  The first claims that for all things such that they are x, there is something such that is is Y in a certain relationship with it and everything that is such that it is z is in a certain relationship with all xs and some y and there is some w which is in a certain relationship with all zs and some y and all xs. In the second, it claims that there is something such that it is x where there all ys are in a certain relationship with it, and there is some z which has a certain relationship with some x and all ys and all things such that they are w are in a certain relationship with some z and all ys and some x.
```
	
7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:
```
∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
X1>Y1, X2>Z1<Y2, X2>Y2 Arrows indicate relationship R and its directionality
∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))
X1>Y1>Z1, X2>Z2
```
	
8. Using an online tableau proof generator - such as the one found here `https://www.umsu.de/trees/` - provide tree proofs of the following entailments, which are known as the De Morgan's laws:
  ```
  (a) ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
1.¬∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
2.¬∀y(¬(Pa ∧ Qa) → (¬Pa ∨ ¬Qa))(1)
3.¬(¬(Pa ∧ Qa) → (¬Pa ∨ ¬Qa))(2)
4.¬(Pa ∧ Qa)(3)
5.¬(¬Pa ∨ ¬Qa)(3)
6.¬¬Pa(5)
7.¬¬Qa(5)
8.Qa(7)
9.Pa(6)
10.¬Pa(4)	11.¬Qa(4)
x		x

  (b) ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
  1.¬∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
  2.¬∀y(¬(Pa ∨ Qa) → (¬Pa ∧ ¬Qa))(1)
  3.¬(¬(Pa ∨ Qa) → (¬Pa ∧ ¬Qa))(2)
  4.¬(Pa ∨ Qa)(3)
  5.¬(¬Pa ∧ ¬Qa)(3)
  6.¬Pa(4)
  7.¬Qa(4)
  8.¬¬Pa(5)	9.¬¬Qa(5)
  10.Pa(8)	11.Qa(9)
x		x

  (c) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  1.¬∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  2.¬∀y((¬Pa ∨ ¬Qa) → ¬(Pa ∧ Qa))(1)
  3.¬((¬Pa ∨ ¬Qa) → ¬(Pa ∧ Qa))(2)
  4.¬Pa ∨ ¬Qa(3)
  5.¬¬(Pa ∧ Qa)(3)
  6.Pa ∧ Qa(5)
  7.Pa(6)
  8.Qa(6)
  9.¬Pa(4)	10.¬Qa(4)
x		x

  (d) ∀x∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
  1.¬∀x∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
  2.¬∀y((¬Pa ∧ ¬Qa) → ¬(Pa ∨ Qa))(1)
  3.¬((¬Pa ∧ ¬Qa) → ¬(Pa ∨ Qa))(2)
  4.¬Pa ∧ ¬Qa(3)
  5.¬¬(Pa ∨ Qa)(3)
  6.Pa ∨ Qa(5)
  7.¬Pa(4)
  8.¬Qa(4)
  9.Pa(6)	10.Qa(6)
x		x



```
	
9. Using a natural deduction proof generator - such as the one found here `https://proofs.openlogicproject.org/` - provide natural deduction proofs for each of De Morgan's laws. 
(a)
1. ¬(¬Pa ∨ ¬Qa)	assumption
2. ~(Pa ^ Qa) assumption
3.   (Pa ∧ Qa)	1, ~v	
4.  ¬(Pa ∧ Qa)  2,3 contradiction
(b)	
1. ¬(¬Pa ∧ ¬Qa)	assumption
2. ~(Pa v Qa)   assumption
3. (Pa ∨ Qa)	1, ~^	
4. ¬(Pa ∨ Qa)   2,3 contradiction
(c)
1.	¬¬(Pa ∧ Qa)	assumptIon
2.      ~Pa v ~Qa       assumption
3.	Pa ∧ Qa	1	1, dne
4.		Px	2	
5.		Qx	2	
6.	¬Pa ∨ ¬Qa	4,5, 2 contradiction

(d)
1.	¬¬(Pa ∨ Qa) assumptIon
2.      ~Pa ^ ~Qa   assumption
3.	Pa ∨ Qa	1 DNE	
4.		¬Pa	2 DS	
5.		Qa	2 DS	
6.		¬Qa	2 DS	
7.		Pa	2 DS	
8.	¬Pa ∧ ¬Qa	4, 5, 6, 7, 2 Contradiction
10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 

The tree proofs tended to be longer and work through the whole of the equation down to the atomic formulas. They would begin by supposing the negation of the whole formula and working down to the contradictions in those formulas. 

In contrast the natural deductions would begin by assuming the only condition where the initial conditional would be fale, namely a situation where the first part is true while the second is false. By assuming both of these, I would find a contradiction quickly on account of breaking down the falsified second half until it contradicted the assumption of the first half.
 
