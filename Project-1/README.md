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
  A	B	C	((¬A → B) ∨ ((A ∧ ¬C) → B))
F	F	F		  T
F	F	T		  T
F	T	F		  T
F	T	T		  T
T	F	F		  T
T	F	T		  T
T	T	F		  T
T	T	T		  T

It is a Tautology.
   
  (b) (A→B)∧(A→¬B)
  
  A	B	((A → B) ∧ (A → ¬B))
F	F		 T
F	T		 T
T	F		 F
T	T		 F
It is Contigent. 
  
  
  (c) (A→(B∨C))∨(C→¬A) 
  
  A	B	C	((A → (B ∨ C)) ∨ (C → ¬A))
F	F	F		       T
F	F	T		       T
F	T	F		       T
F	T	T		       T
T	F	F		       T
T	F	T		       T
T	T	F		       T
T	T	T		       T
It is a Tautology.
  
  (d) ((A→B)∧C)∨(A∧D) 
  
  A	B	C	D	(((A → B) ∧ C) ∨ (A ∧ D))
F	F	F	F		       F
F	F	F	T		       F
F	F	T	F		       T
F	F	T	T		       T
F	T	F	F		       F
F	T	F	T		       F
F	T	T	F		       T
F	T	T	T		       T
T	F	F	F		       F
T	F	F	T		       T
T	F	T	F		       F
T	F	T	T		       T
T	T	F	F		       F
T	T	F	T		       T
T	T	T	F		       T
T	T	T	T		       T
It is Contignet.
```
	
2. A _literal_ is an atomic formula or the negation of an atomic formula. We say a formula is in _conjunctive normal form_ (CNF) if it is the conjunction of the disjunction of literals. Find propositional logic formulas in CNF equivalent to each of the following:
  ```
  (a) (A→B)→C
  
  (A ∨ C) ∧ (¬B ∨ C)
  
  (b) (A→(B∨C))∨(C→¬A)
  
  This is a tautology, so no CNF form is possible. p∨~p
  
  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 
  
  This is a tautology, so no CNF form is possible. p∨~p
```

3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```
  (a)  B(x,y) that says that x is a brother of y
  	∃x∃y∃z(P(z,y)∧P(z,x)∧¬Fx∧x≠y∧x≠z∧z≠y)
  (b)  A(x,y) that says that x is an aunt of y
  	∃w∃x∃y∃z(P(z,y)∧P(w,z)∧P(w,x)∧Fx∧x≠y∧x≠z∧x≠w∧w≠y∧w≠z∧y≠z)
  (c)  C(x,y) that says that x and y are cousins 
  	∃v∃w∃x∃y∃z(P(v,w)∧P(v,z)∧P(w,x)∧P(z,y)∧x≠v∧x≠y∧x≠z∧x≠w∧w≠y∧w≠z∧w≠v∧y≠z∧y≠v∧v≠z)
  (d)  O(x) that says that x is an only child
  	∃x∃y∀z((P(y,z)∧P(y,x)→z=x)∧y≠z∧y≠x)
  (e)  T(x) that says that x has exactly two brothers 
  	∃v∃w∃x∃y(P(v,x)∧P(v,w)∧¬Fw∧P(v,y)∧¬Fy∧∀z((P(v,z)∧¬Fz)→((z=x)∨(z=w)∨(z=y)))∧v≠w∧v≠x∧v≠y∧v≠z)
```

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```
  (a)  B that says that x is a brother of y
  
  B = M∩∃parent_of¯.(≥2∃parent_of)
  
  or
  
  p2 (parent of at least 2) = ≥2 ∃parent_of
  B = M ⊓ ∃p2¯
  
  (b)  A that says that x is an aunt of y
  
  A = ~M ⊓ ∃parent_of¯.(∃parent_of.(∃parent_of))
  I'm not sure how to say the aunt is the child of someone who is the parent of someone else besides the aunt.
  
  or
  
  A = ¬M ⊓ (∃p2¯.(∃p2.(∃parent_of)))
  This has the same problem where it doesn't make clear that it's the aunt's sibling that has the child.
  
  (c)  C that says that x and y are cousins 
  
  I could say they're children of people, but I don't know how to say they're the children of different people
  
  or
  
  gp2 (Grandparent with at least two children which each have children) ≡ ≥2parentof.(∃parentof)
  
  C = gp2¯
  But this doesn't make clear that these 2 are cousins as opposed to siblings. Either that, or it's only talking about a single person, rather than 2 cousins.
  
  (d)  O that says that x is an only child
  
   O = ∃parent_of¯.(≤1∃parent_of ⊓ ≥1∃parent_of)
   
   or
   
   O ≡ ¬∃p2¯
   I'm not a fan of this, since it's also true of rocks.
  
  (e)  T that says that x has exactly two brothers 
  
  T = ∃parent_of¯.(≥3∃parent_of ⊓ ≥2∃parent_of.Male ⊓ ≤2∃parent_of.Male)
  This doesn't quite work, since it says there's no more than 2 brothers out of the three, not that the one sibling I'm talking about has exactly 2 brothers.
  
  or
  
  p3 (parent of at least 3) = ≥3∃parent_of
  T = ∃p3¯.(≥2∃parent_of.Male ⊓ ≤2∃parent_of.Male)
  This proposal has the same problem as the previous one.
  
```

5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 
```
Tex = {Brother = M∩∃parent_of¯.(≥2∃parent_of)			(Tex.1)
	Aunt = ~M∩∃parent_of¯.(∃parent_of.(∃parent_of))		(Tex.2)
	Brother ⊆ Male,						(Tex.3)
	Aunt ⊆ ~Male}						(Tex.4)

Aex = {Billy: Brother ⊓ Male		(Aex.1)
	Bob: Brother ⊓ Male		(Aex.2)
	Mary: Aunt			(Aex.3)
	(Alex, Billy): parent_of	(Aex.4)
	(Alex, Bob): parent_of}		(Aex.5)
	
ΔI = {w, x, y, z},
Billy = w
Bob = x
Mary = y
Alex = z
Male = {w, x}
Brother = {w, x}
Aunt = {y}
Parent_of = {(z,w), (z,x)}
```

6. Explain the difference - using natural language - between the first-order prefixes:
  ```
  (a) ∃x∀y and ∀x∃y
  
  ∃x∀y means "there is an x such that, for all y...", while ∀x∃y means "for all x, there is a y such that...". For instance, if I wanted to say that there is one particular thing that everything loves, I would write: "∃x∀yL(y,x)", but if I wanted to say that everything loves something without implying they all love the same thing, I would write: "∀x∃yL(x,y)". 
  
  (b) ∃x∀y∃z and ∀x∃y∀z 
  
  ∃x∀y∃z means "there is an x such that, for all y, there is a z such that..." while ∀x∃y∀z means "for all x, there is a y such that, for all z..."
  
  (c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
  
  ∀x∃y∀z∃w means "for all x, there is a y such that, for all z, there is a w such that...", while ∃x∀y∃z∀w means "there is an x such that, for all y, there is a z such that, for all w..."
  
```
	
7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:
```
∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))


	0------> 1
       ^ |      | ^
       |_|      |_|
       
       -I'm not sure how to draw a graph in this program. I'm trying to show object 0 being in a relation with itself and with 1, but 1 only being in the relation with itself.
       U: {0, 1}
       R: {(0,0), (0,1), (1,1)}
	-This fits with the second statement, since there is an object that Rs everything (0), there is an object that Rs something (both 0 and 1), and it's true that everything Rs something (both 0 and 1 do, and they're the only objects)
	-This does not fit with the first statement, since it's not true that everything Rs everything "R(x,z)" (1 does not).
       
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
  10.¬Pa(4) 11.¬Qa(4)
      x         x

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
   x               x

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
   x                x
    
  (d) ∀x∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
  
  	1.¬∀x∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
	2.¬∀y((¬Pa ∧ ¬Qa) → ¬(Pa ∨ Qa))(1)
	3.¬((¬Pa ∧ ¬Qa) → ¬(Pa ∨ Qa))(2)
	4.¬Pa ∧ ¬Qa(3)
	5.¬¬(Pa ∨ Qa)(3)
	6.Pa ∨ Qa(5)
	7.¬Pa(4)
	8.¬Qa(4)
9.Pa(6)		10.Qa(6)
  x                x
   
```
	
9. Using a natural deduction proof generator - such as the one found here `https://proofs.openlogicproject.org/` - provide natural deduction proofs for each of De Morgan's laws. 
```

(a)
1. Show: ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
2. |	Show: ∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))    |
3. |	|	Show: ¬(Px ∧ Qx) → (¬Px ∨ ¬Qx)|
4. |	|	|¬(Px ∧ Qx)		    |||			Assumption CD
5. |	|	|	Show: (¬Px ∨ ¬Qx)   |||
6. |	|	|	|~(¬Px ∨ ¬Qx)	   ||||			Assumption ID
7. |	|	|	|	Show: Px   ||||				
8. |	|	|	|	|~Px	  |||||			Assumption ID
9. |	|	|	|	|~Px V ~Qx|||||			8, Addition
10.|	|	|	|	|_________|||||			6, 9, ID
11.|	|	|	|	Show: Qx   ||||
12.|	|	|	|	|~Qx	  |||||			Assumption ID
13.|	|	|	|	|~Px V ~Qx|||||			12, Addition
14.|	|	|	|	|_________|||||			6, 13, ID
15.|	|	|	|	Px ∧ Qx	   ||||			7, 11, Adjunction
16.|    |       |       |__________________||||                 4, 15, ID
17.|	|	|___________________________|||		        5, CD
18.|    |____________________________________||			3, UD
19.|__________________________________________|			2, UD

****Note, I'm not including the boxes in future derivations, since they're so tedious to make in this program

(b)
1. Show: ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
2.	Show: ∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
3. 		Show: ¬(Px ∨ Qx) → (¬Px ∧ ¬Qx)
4. 		¬(Px ∨ Qx)					Assumption CD
5.			Show: (¬Px ∧ ¬Qx)
6.			~(¬Px ∧ ¬Qx)				Assumption ID
7.				Show: ~Px
8.				Px				Assumption ID, Double Negation
9.				Px V Qx				8, Addition
10.								4, 9 ID
11. 				Show: ~Qx
12.				Qx				Assumption ID, Double Negation
13.				Px V Qx				12, Addition
14.								4, 13, ID
15.				~Px ∧ ¬Qx			7, 11, Addition
16.								15, Direct Derivation
17. 								5, CD
18.								3, UD
19.								2, UD

(c)
1. Show: ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
2. 	Show: ∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
3. 		Show: (¬Px ∨ ¬Qx) → ¬(Px ∧ Qx)
4. 		(¬Px ∨ ¬Qx)					Assumption CD
5. 			Show: ¬(Px ∧ Qx)
6. 			(Px ∧ Qx)				Assumption ID, Double Negation
7. 			Px					6, Simplification
8.			~~Px					7, Double Negation
9.			~Qx					4, 8, MTP
10.			Qx					6, Simplification
11.								9, 10, ID
12. 								5, CD
13. 								3, UD
14.								2, UD

(d)
1. Show: ∀x∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
2. 	Show: ∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
3. 		Show: (¬Px ∧ ¬Qx) → ¬(Px ∨ Qx)
4.		(¬Px ∧ ¬Qx)					Assumption CD
5.		~Px						4, Simplification
6.		~Qx						4, Simplification
7.			Show: ¬(Px ∨ Qx)
8.			(Px ∨ Qx)				Assumption ID, Double Negation
9.			Qx					5, 8, MTP
10.								6, 9, ID
11.								7, CD
12.								3, UD
13.								2, UD

```

10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 
```

For natural deduction proofs, I mostly proved DM by showing that certain assumptions lead to contradictions. For example, to show (a), we need to show that ¬(Px ∧ Qx) → (¬Px ∨ ¬Qx). Do do this, I need to derive (¬Px ∨ ¬Qx) from ¬(Px ∧ Qx). Instead of doing this directly, I assumed that (¬Px ∨ ¬Qx) is false and showed how this leads to a contradiction. The other proofs followed this same form, except for (b). For that one, I was able to show (¬Px ∧ ¬Qx) directly with a mixed derivation, rather than by indirect derivation.

By contrast, the parsing trees appear to start off by assuming the falsity of the DeMorgan theorems, which I did not do with the natural deduction proofs. Notably, it looks like the parsing trees either used DM in the proofs, or used something very similar to it. For instance, in (a), on line 5, it uses what looks like DM. I intentionally avoided DM in my proofs, since that would be assuming what I'm trying to prove. 

```
