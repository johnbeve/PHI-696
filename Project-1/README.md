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
 
A B C ¬A→B (A∧¬C)→B (¬A→B)∨((A∧¬C)→B)
T T T   T     T           T
T F T   T     T           T
T T F   T     T           T
F T T   T     T           T
F T F   T     T           T
F F T   F     T           T
T F F   T     T           T              
F F F   F     T           T

- If I am doing this right, this is a tautology.
  
  ```(b) (A→B)∧(A→¬B)
  
 - (A→B)∧(A→¬B) means if 'A' then 'B' and if 'A' then 'not-B' are true at the same time.
  
A B ¬A ¬B (A→B) (A→¬B) (A→B)∧(A→¬B)
T T  F  F   T     F         F
T F  F  T   F     T         F
F T  T  F   T     T         T
F F  T  T   T     T         T

- If I am doing this right, this is a contingent.
  
  ```(c) (A→(B∨C))∨(C→¬A) 
  
 - (A→(B∨C)) means if 'A', then either 'B', 'C', or both.
 - (C→¬A) means if 'C', then 'not A'.
 - (A→(B∨C))∨(C→¬A) means either one or both of the above statements are true.
 
A B C  A→(B∨C) (C→¬A) (A→(B∨C))∨(C→¬A)
T T T     T       F            T
T F T     T       F            T   
T T F     T       F            T
F T T     T       T            T
F T F     T       T            T
F F T     T       T            T
T F F     F       T            T
F F F     T       T            T

- If I am doing this right, this is a tautology.
 
 
  ```(d) ((A→B)∧C)∨(A∧D)
  
A B C D ((A→B)∧C)(A∧D) ((A→B)∧C)∨(A∧D)
F F F F	    F.     F.          F                      
F F F T	    F.     F.          F
F F T F	    F.     T.          T
F F T T	    T      F           T
F T F F	    F.     F.          F
F T F T	    F.     F.          F
F T T F	    T      T.          T
F T T T	    T.     F.          T
T F F F	    F.     F.          F     
T F F T	    T.     T.          T
T F T F	    F.     F.          F
T F T T	    F.     T.          T
T T F F	    F.     F.          F
T T F T	    F.     T.          T
T T T F	    T.     F.          T
T T T T     T.     T.          T
  
  - If I am correct, this is a contingent.

	
2. A _literal_ is an atomic formula or the negation of an atomic formula. We say a formula is in _conjunctive normal form_ (CNF) if it is the conjunction of the disjunction of literals. Find propositional logic formulas in CNF equivalent to each of the following:
  ```(a) (A→B)→C
- I am going to try and use DeMorgan's laws here:
A→B ≡ ¬A∨B
(A→B)→C ≡ ¬(¬A∨B)∨C
¬(¬A∨B)∨C ≡ (A∧¬B)∨C
(A∧¬B)∨C ≡ (C∨A)∧(C∨¬B)


  (b) (A→(B∨C))∨(C→¬A)
  
A→(B∨C) ≡ ¬Av(B∨C)
C→¬A ≡ ¬C∨¬A
(A→(B∨C))∨(C→¬A) ≡ (¬Av(B∨C))v(¬C∨¬A)
...
- Ali: ((¬AvB)v(¬AvC))v(¬C∨¬A)
- Karl, Sydney, Ali: This is a tautology. Any tautology written in CNF will yield the same result and works as a conversion.




  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 
 1. This formula contains no conditionals or biconditionals.
 2. This formula contains no double negations, or negations outside parentheses.
 
 3. I don't know how to use DeMorgan's distributive laws to put this formula in CNF from here on.  


3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 

  ```(a)  B(x,y) that says that x is a brother of y
  
   ∀B(x,y)∃P(z,y)∧P(z,x)∧(x≠y≠z)∧F(¬x)
  
  (b)  A(x,y) that says that x is an aunt of y
  
    - All aunts A(x) are female F(x)
  ...
  - There exists a parent relationship between g and children x and z. x does not equal z and is female. z is a parent to y.
  ...
   ∀A(x,y)∃P(g,x)∧P(g,z)∧∀F(x)∧P(z,y)∧(x≠y≠z≠g)

  (c)  C(x,y) that says that x and y are cousins 

There exists a parent relationship between z and children u and w. u does not equal w. w is a parent to x. u is a parent to y. x does not equal y.
 ...
 ∀C(x,y)∃P(z,u)∧P(z,w)∧P(w,x)∧P(u,y)∧(x≠y≠u≠w≠z)
 
  (d)  O(x) that says that x is an only child
  
  There exists at least one relation between parent z and child x, where for all cases of a third child y, x is equal to y.
 ...
   ∀O(x)∃P(z,x)∧(x≠z)∀P(z,y)∧(x=y)
  
  (e)  T(x) that says that x has exactly two brothers 
  
  For all cases x, with brothers y and z, it is only the case that a fourth child would be either x, y, or z. none of them equal each other, and neither y nor z are female. 
 ...
 ∀T(x)∃P(g,x)∧P(g,y)∧P(g,z)∧(x≠y≠z≠g)∀P(g,w)((w=y)∨(w=z))
 

```

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```(a)  B that says that x is a brother of y

 B ≡ ⊓M  ∀  parent_of ⊓ parent_of
  
  (b)  A that says that x is an aunt of y
  
  A ≡ ¬M 
  
  (c)  C that says that x and y are cousins 
  
  (d)  O that says that x is an only child

0 := ∃parent_of.0

  (e)  T that says that x has exactly two brothers 

T := ∃parent_of.2⊓∀M

```

5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 

Domain (???) {x, y, Male, parent_of}
Concepts: Male
Role: Parent_Of


6. Explain the difference - using natural language - between the first-order prefixes:
  ```(a) ∃x∀y and ∀x∃y

- The first prefix ∃x∀y has the existence of x contain all instances 'y' , whereas the second prefix ∀x∃y means for all cases 'x' there exists 'y'. The first prefix guarantees itself in all instances 'y', but the second prefix only holds in at least one, but not all, cases of 'y'.
  
  (b) ∃x∀y∃z and ∀x∃y∀z 
  
 - ∃x∀y∃z states the existence of 'x' contains all cases of 'y' bearing the existence of 'z'. ∀x∃y∀z means in all cases 'x' there exists 'y' which contains all cases of 'z'.
 
 (c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
 - ∀x∃y∀z∃w states that for all 'x' there exists 'y' such that all instances 'z' contain the existence of 'w'. ∃x∀y∃z∀w states the existence of 'x' with all cases 'y' there also exists 'z' for all cases 'w'.
 
```
	
7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:
```
∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))

- This statement is saying that for all cases x there exists at least one case y containing all cases of z, with x being related to y, x being related to z, and y being related to z by virtue of R



∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))

- This statement means there exists at least one x containing all cases y with the existence of at least one z, where x is related to y, x is related to z, and y is related to z by virtue of R

```
	
8. Using an online tableau proof generator - such as the one found here `https://www.umsu.de/trees/` - provide tree proofs of the following entailments, which are known as the De Morgan's laws:
  ```(a) ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
 ![proof](https://user-images.githubusercontent.com/119642653/216776523-b77a92b1-7f0f-4c67-859f-432f3eed674b.png)

  (b) ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
 ![proof (1)](https://user-images.githubusercontent.com/119642653/216776576-4dc43fa9-14ce-456e-8b14-b3c368378015.png)
  
  (c) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
 ![proof (2)](https://user-images.githubusercontent.com/119642653/216776622-f5655fff-7687-4618-9d42-9efac487e9f2.png)
 
  (d) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
 ![proof (3)](https://user-images.githubusercontent.com/119642653/216776659-68375ce8-5e5d-4d32-ba2b-689c609e4430.png)

```	
9. Using a natural deduction proof generator - such as the one found here `https://proofs.openlogicproject.org/` - provide natural deduction proofs for each of De Morgan's laws. 

10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 

