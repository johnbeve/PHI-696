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
  (a) (¬A→B)∨((A∧¬C)→B) (Is a tautology)
  	A	B	C	((¬A → B) ∨ ((A ∧ ¬C) → B))
	F	F	F	T
	F	F	T	T
	F	T	F	T
	F	T	T	T
	T	F	F	T
	T	F	T	T
	T	T	F	T
	T	T	T	T
	
	
  (b) (A→B)∧(A→¬B) (Is contingent)
  	A	B	((A → B) ∧ (A → ¬B))
	F	F	T
	F	T	T
	T	F	F
	T	T	F
	
  (c) (A→(B∨C))∨(C→¬A) (Is a tautology)
  	A	B	C	((A → (B ∨ C)) ∨ (C → ¬A))
	F	F	F	T
	F	F	T	T
	F	T	F	T
	F	T	T	T
	T	F	F	T
	T	F	T	T
	T	T	F	T
	T	T	T	T
	
  (d) ((A→B)∧C)∨(A∧D) 
  	B	C	D	(((A → B) ∧ C) ∨ (A ∧ D))
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
  	(A∨¬A) is  equivalent because tautologies are equivalent.
  
  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 
  	(A∨¬A) is  equivalent because tautologies are equivalent.
  ```
  
3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  
  ```
  (a)  B(x,y) that says that x is a brother of y  
  	B(x,y)↔∃x∃y(~Fx & ∀z(P(z,x)⟷P(z,y) & ∃wP(w,x)) & x≠y) , but only if we accept that to be male is equivalent to the negation of being female, and if we 
discount half-siblings as siblings. 
  
  (b)  A(x,y) that says that x is an aunt of y  
  	A(x,y)↔(∃x∃y(Fx & (∃zP(z,y) & ∃w(P(w,z) & P(w,x)))) & ∀w(P(w,z)↔P(w,x)) & x≠z) , if we (again) discount half-siblings as siblings.
  	
  (c)  C(x,y) that says that x and y are cousins   
  	C(x,y)↔∃x∃y∃v∃w∃z((((P(v,w) & P(v,z)) & P(w,x)) & P(z,y)) & ∀v(P(v,w)↔P(v,z)) & z≠w ) , if we (once more) discount half-siblings as siblings.
	
  (d)  O(x) that says that x is an only child  
  	O(x)↔∃x∀y∀z((P(y,x)&P(y,z))→x=z) , though this one seems to count half-siblings as siblings.
  	
  (e)  T(x) that says that x has exactly two brothers 
  	T(x)  ↔∃x∃y∃z((B(y,x)&B(z,x)& y≠z) &∀w(B(w,x)→(w=y∨w=z)))
  	
  ```

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```
  (a)  B that says that x is a brother of y
  (b)  A that says that x is an aunt of y
  (c)  C that says that x and y are cousins
  (d)  O that says that x is an only child  
  (e)  T that says that x has exactly two brothers 
  ```


5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 

6. Explain the difference - using natural language - between the first-order prefixes:
  ```
  (a) ∃x∀y and ∀x∃y
	‘∃x∀y’ is equivalent to ‘There is an x for all y…’ while 
        ‘∀x∃y’ is equivalent to ‘For all x, there is a y…’ 

           That is, The former means that there is at least one y to which all xs have some sort of relation (to be specified after the prefix), while the latter means that every x has a(n unspecified) relation to some y, which does not have to be the same y for every x (though it certainly could be, depending upon how the relation is specified).
	   
  (b) ∃x∀y∃z and ∀x∃y∀z 
  	'∃x∀y∃z' is equivalent to 'There exists an x for all y such that there exists a z such that...'
	'∀x∃y∀z' is equivalent to 'For all x there exists a y for all z such that...'
		
		That is, the former means that there is at least one x to which all things y bear some sort of relation, which is in a relation to another existing thing, z and the latter means that all xs have some relation (yet to be specified) to some class (min 1) of existing thing(s), related also to all things z. 
  
  
  (c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
  	'∀x∃y∀z∃w' is equivalent to 'For all x there exists a y such that for all z there exists a w such that...'
	'∃x∀y∃z∀w' is equivalent to 'There exists an x for all y such that there exists a z for all w such that...'
		
		That is, the former means that all xs bear some relation to at least one y which bear(s) a relation to all zs which bear a relation to some w.
		The latter means that some thing (x) is related to all y in 
  
```
	
7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:
```
∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))

	U: {0, 1, 2}
	R: {(0,2), (1,0), (1,1), (1,2), (2,2)}

In this model, the first sentence is false while the second sentence is true. 

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
  
  (b) ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx)
  
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
		9.Pa(6)		10.Qa(6)
		x		x
```
	
9. Using a natural deduction proof generator - such as the one found here `https://proofs.openlogicproject.org/` - provide natural deduction proofs for each of De Morgan's laws. 
```
(a) ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))

			1. Show ∀x(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
			2. 	Show (¬(Pa ∧ Qa) → (¬Pa ∨ ¬Qa))		
			3. 		¬(Pa ∧ Qa)			Assumption for CD
			4. 		Show (¬Pa ∨ ¬Qa)
			5.			¬(¬Pa ∨ ¬Qa)		Assumption for ID
			6. 			Show Pa 		
			7. 				¬Pa		Assumption for ID 
			8. 				¬Pa ∨ ¬Qa	7, DI
			9.				!		5,7 ID	
			10.			Show Qa	
			11.				¬Qa		Assumption for ID
			12.				¬Pa ∨ ¬Qa	11, DI
			13.				!		5, 12 ID
			14.			Pa ∧ Qa			6, 10 ADJ
			15.			!			3, 14 ID
			16.						3,4 CD
			17.						2, UD
			
(b) ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))

			1. Show ∀x(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
			2. 	Show (¬(Pa ∨ Qa) → (¬Pa ∧ ¬Qa))
			3. 		¬(Pa ∨ Qa)			Assumption for CD
			4. 		Show (¬Pa ∧ ¬Qa)
			5.			¬(¬Pa ∧ ¬Qa)		Assumption for ID 
			6. 			Show ¬Pa			
			7.				¬¬Pa		Assumption for ID
			8. 				Pa 		7 DN
			9.				Pa ∨ Qa		8 DI
			10.				!		3, 9 ID
			11.			Show ¬Qa		
			12.				¬¬Qa		Assumption for ID
			13. 				Qa		12 DN
			14.				Pa ∨ Qa		13 DI
			15.				!		3, 14 ID
			16.			¬Pa ∧ ¬Qa		6, 11 ADJ
			17. 			!			5, 16 ID
			18.						3, 4 CD
			19.						2, UD
			
(c) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
			1. Show ∀x((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
			2. 	Show 
(d) ∀x∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
			1. Show ∀x∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
			2. 

```
10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 
 
