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
  (b) (A→B)∧(A→¬B)
  (c) (A→(B∨C))∨(C→¬A) 
  (d) ((A→B)∧C)∨(A∧D) 

A	B	C	((¬A → B) ∨ ((A ∧ ¬C) → B))
F	F	F		  T
F	F	T		  T
F	T	F		  T
F	T	T		  T
T	F	F		  T
T	F	T		  T
T	T	F		  T
T	T	T		  T
(a) is a tautology.



A	B	((A → B) ∧ (A → ¬B))
F	F	T
F	T	T
T	F	F
T	T	F
(b)is contingent

 A	B	C	((A → (B ∨ C)) ∨ (C → ¬A))
F	F	F	T
F	F	T	T
F	T	F	T
F	T	T	T
T	F	F	T
T	F	T	T
T	T	F	T
T	T	T	T
 (c) is a tautology
 
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
(d) is contignet

2. A _literal_ is an atomic formula or the negation of an atomic formula. We say a formula is in _conjunctive normal form_ (CNF) if it is the conjunction of the disjunction of literals. Find propositional logic formulas in CNF equivalent to each of the following:

  ```(a) (A→B)→C
  (b) (A→(B∨C))∨(C→¬A)
  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 

``` (a) (A ∨ C) ∧ (¬B ∨ C)
(b) B ∨ ¬B -- Tautology 
(c) B ∨ ¬B -- Tautology 

3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 

  ```(a)  B(x,y) that says that x is a brother of y
  (b)  A(x,y) that says that x is an aunt of y
  (c)  C(x,y) that says that x and y are cousins 
  (d)  O(x) that says that x is an only child
  (e)  T(x) that says that x has exactly two brothers 
  
    ⊔ ⊓ ⊧ ⊭ ⊦ ⊬ ⊏ ⊐ ⊑ ⊒ C ¬ ≡ ≠ ≥ ≤ ∀ ∃

```(a) ∀x∀y∀z(P(z,x) ∧ P(z,y) ∧ ¬Fx → z≠y ∧ x≠y ∧ z≠x) - For all cases of x and for all cases of y and for all cases of z if z is the parent of x and z is the parent of y and x is not male then z is not identical with y and x is not is not identical with y and z is not identical with x.

(b) ∀v∀w∀x∀y∀z(((P(z,y)∧P(w,z)∧P(w,x)∧Fx) → z≠y∧x≠y∧w≠x∧w≠z∧y≠w) v ((P(z,y)∧(P(w,z)∧(P(v,x)∧Fx)→ z≠y∧ x≠y∧ w≠v ∧ x≠v ∧ y≠v)) - For all cases of v and all cases of w and all cases of x and all cases of y and all cases of z if z is the parent of y and w is parent of z and w is the parent of x and x is female then z is not indetical with y and x is not identical with y and w is not identical with x and w is not identical with z and y is not indetical with w OR z is the parent of y and w is the parent of z and v is the parent of x and x if female then z is not identical with y and x is not identical with y and w is not identical with v and x is not identical with v and y is not identical with v
(woof, I hope that captures it)

(c) ∀v∀w∀x∀y∀z(P(v,w)∧P(v,z)∧P(w,x)∧P(z,y)  → v≠w  ∧ v≠x ∧ v≠y ∧ v≠z ∧ w≠x ∧ w≠y ∧ w≠z ∧ x≠y ∧ x≠z ∧ y≠z) - For all cases of v and all cases of w and all cases of x and all cases of y and all cases of z if v is a parent of w and v is a parent of z and w is a parent of x and z is a parent of y then v is not identical to w and v is not identical to x and v is not identical to y and v is not identical to z and w is not identical to x and w is not identical to y and w is not identical to z and x is not identical to y and x is not identical to z and y is not identical to z (This only counts for first cousins as definitions including 2nd, 3rd, 4th, and so on introducing a nearly infinite amount of cousins and clauses to match) 

(d) ∃x∃y∀z(P(y,z)→z=x) - There is some x and some y such that for all z if y is the parent of z then z and x are identical ( I think this works because it is exactly one)

(e) ∃v∃w∃x∃y∀z(P(v,x)∧P(v,w)∧¬Fw∧P(v,y)∧¬Fy∧∀z((P(v,z)∧¬Fz)→((z=x)∨(z=w)∨(z=y)))) - There is some v and some w and some x and some y such that for all z if v is the parent of x and v is the parent of w and w is not female and v is the parent of y and y is not female and for all instances of z v is a parent of z and z is not female then z is identical with w or z is identical with w or z is identical with y ( I think this works because it is exactly two brother)

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```(a)  B that says that x is a brother of y
  (b)  A that says that x is an aunt of y
  (c)  C that says that x and y are cousins 
  (d)  O that says that x is an only child
  (e)  T that says that x has exactly two brothers 
```
⊔ ⊓ ⊧ ⊭ ⊦ ⊬ ⊏ ⊐ ⊑ ⊒ C ¬ ≡ ≠ ≥ ≤

(a) Not possible to define using ALC -- not expressive enough
(b) Not possible to define using ALC -- not expressive enough
(c) Not possible to define using ALC -- not expressive enough
(d) Not possible to define using ALC -- not expressive enough
(e) Not possible to define using ALC -- not expressive enough

5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both.

No usable formulas due to the inability to express anything in question #4

6. Explain the difference - using natural language - between the first-order prefixes:
 ```(a) ∃x∀y and ∀x∃y
  (b) ∃x∀y∃z and ∀x∃y∀z 
  (c) ∀x∃y∀z∃w and ∃x∀y∃z∀w

```(a) ∃x∀y says something like there is some x such that for all y
(a) ∀x∃y says for all x there is some y 
(b) ∃x∀y∃z says there is some x such that for all y there is some z such that 
(b) ∀x∃y∀z says for all x there is come y such that for all x
(c) ∀x∃y∀z∃w says for all x there is some y such that for all z there is some w
(c) ∃x∀y∃z∀w says there is some x such that for all y there exists some z such that for all w

7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:
```
∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))

``` Here is my diagram of the universe: [label](file:///Universe.pub)
U: {0,1}
R: {(0,0), (0,1), (1,1)} 
	
8. Using an online tableau proof generator - such as the one found here `https://www.umsu.de/trees/` - provide tree proofs of the following entailments, which are known as the De Morgan's laws:

  ````(a) ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
  (b) ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
  (c) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  (d) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  
  ⊔ ⊓ ⊧ ⊭ ⊦ ⊬ ⊏ ⊐ ⊑ ⊒ C ¬ ≡ ≠ ≥ ≤ ∀ ∃
  
(a)∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
¬∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
∃x¬∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))  (1)
¬∀y(¬(Pw ∧ Qw) → (¬Pw ∨ ¬Qw))    (2)
∃y¬(¬(Pw ∧ Qw) → (¬Pw ∨ ¬Qw))    (3)
¬(¬(Pw ∧ Qw) → (¬Pw ∨ ¬Qw))      (4)
         ¬(Pw ∧ Qw)              (4)
        ¬(¬Pw ∨ ¬Qw)             (4)
	  ¬¬Pw                   (7)
	  ¬¬Qw                   (7)
	    Qw                   (9)
	    Pw                   (8)
  ¬Pw(b)             ¬Qw(b)
  x                     x
  
 (b)∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
 ¬∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
 ∃x¬∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))   (1)
 ¬∀y((¬(Pw ∨ Qw) → (¬Pw ∧ ¬Qw))    (2)
 ∃y¬((¬(Pw ∨ Qw) → (¬Pw ∧ ¬Qw))    (3)
  ¬((¬(Pw ∨ Qw) → (¬Pw ∧ ¬Qw))     (4)
           ¬(Pw ∨ Qw)              (5)
           ¬(¬Pw ∧ ¬Qw)            (5)
               ¬Pw                 (b)
	       ¬Qw                 (b)
  ¬¬Pw                     ¬¬Qw    (7)
    x                        x


  (c) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  ¬∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  ∃x¬∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))     (1)
  ¬∀y((¬Pw ∨ ¬Qw) → ¬(Pw ∧ Qw))       (2)
  ∃y¬((¬Pw ∨ ¬Qw) → ¬(Pw ∧ Qw))       (3)
  ¬((¬Pw ∨ ¬Qw) → ¬(Pw ∧ Qw))         (4)
            ¬Pw ∨ ¬Qw                 (5)
	    ¬¬(Pw ∧ Qw)               (5)
	      Pw ∧ Qw                 (7)
	        Pw                    (8)
		Qw                    (8)
       ¬Pw (6)              ¬Qw (6)
       x                     x
       
(d) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
¬∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
 ∃x¬∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))    (1)
 ¬∀y((¬Pw ∨ ¬Qw) → ¬(Pw ∧ Qw))      (2)
 ∃y¬((¬Pw ∨ ¬Qw) → ¬(Pw ∧ Qw))      (3)
  ¬((¬Pw ∨ ¬Qw) → ¬(Pw ∧ Qw))       (4)
         ¬Pw ∨ ¬Qw                  (5)
	 ¬¬(Pw ∧ Qw)                (5)
	      ¬Pw		    (6)
	      ¬Qw 		    (6)
  Pw (8)		Qw (8)
   x                    x
  
9. Using a natural deduction proof generator - such as the one found here `https://proofs.openlogicproject.org/` - provide natural deduction proofs for each of De Morgan's laws. 

(a)
1. Show: ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
2. 	Show: ∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))    
3. 		Show: ¬(Px ∧ Qx) → (¬Px ∨ ¬Qx)
4. 		¬(Px ∧ Qx)		    			Ass CD
5. 			Show: (¬Px ∨ ¬Qx)   
6. 			~(¬Px ∨ ¬Qx)	   			Ass ID
7. 				Show: Px   				
8. 				~Px	  			        Ass ID
9. 				~Px V ~Qx			      8, Add
10.								            6, 9, ID
11.				Show: Qx   
12.				~Qx	  			        Ass ID
13.				~Px V ~Qx			      12, Add
14.								            6, 13, ID
15.				Px ∧ Qx	   			    7, 11, Adj
16.						                4, 15, ID
17.							              5, CD
18.								            3, UD
19.							              2, UD

(b)
1. Show: ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
2.	Show: ∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
3. 		Show: ¬(Px ∨ Qx) → (¬Px ∧ ¬Qx)
4. 		¬(Px ∨ Qx)					            Ass CD
5.			Show: (¬Px ∧ ¬Qx)
6.			~(¬Px ∧ ¬Qx)			           	Ass ID
7.				Show: ~Px
8.				Px				                  Ass ID, DN
9.				Px V Qx				              8, Add
10.								                    4, 9 ID
11. 				Show: ~Qx
12.				      Qx				            Ass ID, DN
13.			        	Px V Qx				      12, Add
14.								                    4, 13, ID
15.			         ~Px ∧ ¬Qx  	    		7, 11, Add
16.								                    15, DD
17. 							                  	5, CD
18.							                     	3, UD
19.								                    2, UD
(c)   
1. Show: ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
2. 	Show: ∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
3. 		Show: (¬Px ∨ ¬Qx) → ¬(Px ∧ Qx)
4. 		(¬Px ∨ ¬Qx)					              Ass CD
5. 			Show: ¬(Px ∧ Qx)
6. 			(Px ∧ Qx)				                Ass ID, DN
7. 			Px					                    6, S
8.			~~Px					                  7, DN
9.			~Qx					                    4, 8, MTP
10.			Qx				                    	6, S
11.								                      9, 10, ID
12. 								                    5, CD
13. 							                    	3, UD
14.								                      2, UD
(d)
1. Show: ∀x∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
2. 	Show: ∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
3. 		Show: (¬Px ∧ ¬Qx) → ¬(Px ∨ Qx)
4.		(¬Px ∧ ¬Qx)					              Ass CD
5.		~Px						                    4, S
6.		~Qx					                     	4, S
7.			Show: ¬(Px ∨ Qx)
8.			(Px ∨ Qx)				               Ass ID, DN
9.			Qx					                   5, 8, MTP
10.								                     6, 9, ID
11.								                     7, CD
12.								                     3, UD
13.							                       2, UD

Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 

Well firsty and perhaps most notably the tree proof software provides no annotations (justifications?) for the how each line is derived from the line before it. I personally like having the annotations as it shows clearly how to move from one step to the next. Further, the tree proofs look like they start by universally instainting whereas in the natural deduction proofs you can go several route but the easiest with Universal Quantifiers is usually a universal derivation. I myself am prone to doing indirect derivations. This is because if it can be derived you can always(?) find a contradiction. Obviously, I still assumed inderictly once all of the unviersal were removed from the situation to complete the derivations. 
