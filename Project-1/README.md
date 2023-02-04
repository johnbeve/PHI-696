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
  
  The calculator says it's already in CNF, though it doesn't look that way to me. I used a different calculator, and it said a CNF version of this does not exist.
  
  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 
  
  The calculator says this one is also already in CNF, but it also doesn't look that way. And the other calculator also said one does not exist.
```

3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```
  (a)  B(x,y) that says that x is a brother of y
  	∃x∃y∃z(P(z,y)∧P(z,x)∧¬Fx)
  (b)  A(x,y) that says that x is an aunt of y
  	∃w∃x∃y∃z(P(z,y)∧P(w,z)∧P(w,x)∧Fx)
  (c)  C(x,y) that says that x and y are cousins 
  	∃v∃w∃x∃y∃z(P(v,w)∧P(v,z)∧P(w,x)∧P(z,y))
  (d)  O(x) that says that x is an only child
  	∃x∃y∀z(P(y,z)→z=x)
  (e)  T(x) that says that x has exactly two brothers 
  	∃v∃w∃x∃y∀z(P(v,x)∧P(v,w)∧¬Fw∧P(v,y)∧¬Fy∧∀z((P(v,z)∧¬Fz)→((z=x)∨(z=w)∨(z=y))))
```

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```
  (a)  B that says that x is a brother of y
  
  ΔI = {x, y, z},
  parent_of = {(z,x), (z,y)},
  Male = {x}.
  
  (b)  A that says that x is an aunt of y
  
  ΔI = {w, x, y, z},
  parent_of = {(w,x), (w,z), (z,y)},
  ~Male = {x}.
  
  (c)  C that says that x and y are cousins 
  
  ΔI = {v, w, x, y, z},
  parent_of = {(v,w), (v,z), (w,x), (z,y)}.
  
  (d)  O that says that x is an only child
  
   I'm not sure of a way to do this. I could say that x is a child of y, but in this system that wouldn't mean it's false of anything else.
  
  (e)  T that says that x has exactly two brothers 
  
  I'm not sure of a way to say this either for the same reason as before. I can say two things are x's brother, but this wouldn't say there's only two brothers
  
```

5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 
```
Tex = {Brother ⊆ Male,		(Tex.1)
	Aunt ⊆ ~Male}		(Tex.2)

Aex = {Billy: Brother ∩ Male		(Aex.1)
	Bob: Brother ∩ Male		(Aex.2)
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
   
  (d) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  
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
   
```
	
9. Using a natural deduction proof generator - such as the one found here `https://proofs.openlogicproject.org/` - provide natural deduction proofs for each of De Morgan's laws. 

10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 

