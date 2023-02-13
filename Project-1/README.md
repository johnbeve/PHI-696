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

A→B ≡ ¬A∨B

(A→B)→C ≡ ¬(¬A∨B)∨C

¬(¬A∨B)∨C ≡ (A∧¬B)∨C

(A∧¬B)∨C ≡ (C∨A)∧(C∨¬B)

CNF: (C∨A)∧(C∨¬B)

  (b) (A→(B∨C))∨(C→¬A)
  
A→(B∨C) ≡ ¬Av(B∨C)

C→¬A ≡ ¬C∨¬A

(A→(B∨C))∨(C→¬A) ≡ (¬Av(B∨C))v(¬C∨¬A)

- Ali: ((¬AvB)v(¬AvC))v(¬C∨¬A)

- Karl, Sydney, Ali: This is a tautology. Any tautology written in CNF will yield the same result and works as a conversion.

  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 
  
- Plugging this statement into the Stanford Truth Table Generator shows that it is also a tautology.

- So, both (2b) and (2c) can be rewritten as a CNF formula with no terms (got this from stack exchange, https://math.stackexchange.com/questions/64473/what-is-the-conjunction-normal-form-of-a-tautology), so 'T'. I've also seen A∨¬A used as a simplification.


3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 

  ```(a)  B(x,y) that says that x is a brother of y
  
   B(x,y) ≡ ¬F(x)∧P(z,y)∧P(z,x)
  
  (b)  A(x,y) that says that x is an aunt of y
  
   A(x,y) ≡ F(x)∧P(g,x)∧P(g,z)∧P(z,y)

  (c)  C(x,y) that says that x and y are cousins 
  
 C(x,y) ≡ (z,u)∧P(z,w)∧P(w,x)∧P(u,y)
 
  (d)  O(x) that says that x is an only child
  
  O(x) ≡ P(z,x)∧P(z,y)∧(x=y)
  
  (e)  T(x) that says that x has exactly two brothers 
  
 T(x)≡ ¬F(y)¬F(z)∧P(g,x)∧P(g,y)∧P(g,z)∧P(g,w)((w=y)∨(w=z)∨(w=x))

```

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```(a)  B that says that x is a brother of y
 - Identify role bearing in concept
 - A brother is a male child with all cases of a parent relation to two individuals
 person ≡ M ⊔ ¬M
 
∀B.person
∀B.M
B ≡ ∃parentof.M ⊓ ∀parentof.person
  
  (b)  A that says that x is an aunt of y
  
 A ≡ ∃parentof.¬M ⊓
 ...
 - During some meetings in the past week I got a feel for the logic behind the answers Giacomo and Ali provided to these questions.
 - If I understood the syntax of ALC, here are some things I would like to do:
- Establish a concept of 'parent' to denote anything that bears the parent role
- That way, I could use a similar syntax to the one in question 3b. An aunt is a not-male who has a parent, and that parent has another parent as a child.
  
  (c)  C that says that x and y are cousins 
  
  - Ali and Giacomo showed me how description logic can only be used to write formulas describing either concepts or roles. Because the statement 'x and y are cousins' involves more than two concepts and a relation between them, it cannot be formulated into one sentence in FOL. 
 - With this said, ∀C.person 
 
  (d)  O that says that x is an only child
  
  (e)  T that says that x has exactly two brothers 
```

5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 

Tbox 

Abox
 B ⊑ M
 



6. Explain the difference - using natural language - between the first-order prefixes:
  ```(a) ∃x∀y and ∀x∃y

- The first prefix ∃x∀y means there exists some x related to all instances 'y' , whereas the second prefix ∀x∃y means for all cases 'x' there exists 'y'. The first prefix guarantees itself in all instances 'y', but the second prefix only holds in at least one, but not all, cases of 'y'.
  
  (b) ∃x∀y∃z and ∀x∃y∀z 
  
 - ∃x∀y∃z states the existence of 'x' relates all cases of 'y' with the existence of 'z'. ∀x∃y∀z means in all cases 'x' there exists 'y' which relates to all cases 'z'.
 
 (c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
 - ∀x∃y∀z∃w states that for all 'x' there exists 'y' such that all instances 'z' have a relation to the existence of some 'w'. ∃x∀y∃z∀w states the existence of 'x' is related to all cases 'y' where there exists 'z' with all cases of 'w'.
 
```
	
7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:
```
- https://www.geeksforgeeks.org/mathematic-logic-predicates-quantifiers/ I found a neat little table explaining quantifiers here
- http://www.jfsowa.com/peirce/ms514.htm This site is awesome!!!!
...
∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))

- For all vertices there is a vertex that is connected to all other vertices
... so (1, 0, 1)
x is related to y
x is related to z
y is related to z 
all by virtue of R

∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))

- There exists a vertex which is connected to all other vertices connected to a third vertex
... so, (0,1,0)
x is related to y
x is related to z
and y is related to z 
all by virtue of R
  
x ---> y
|->z <-|

I believe this models the second one, and not the first. I believe I'm deeply misunderstanding something though because I can't shake the feeling that the first variable in each relation is somehow the 'active' member, hence the direction of my graph's arrows. Is this true, or do relations in logic not work on this dynamic?

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
- For these problems I am combining answers from stack exchange, http://teachinglogic.liglab.fr/DN/index.php, and https://www.erpelstolz.at/gateway//prover.html 
- I was also given a lot of wonderful help by Josh, Delaney, Finn and Giacomo!

a. ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
- here's my attempt:
premise ¬(Px ∧ Qx)
 assume ¬(¬Px ∨ ¬Qx)
 therefore ¬(¬Px ∨ ¬Qx) ≡ Px ∧ Qx
assume ¬(Px ∧ Qx)
 T
 ...
 - here's a generation:
 assume ¬(Px ∧ Qx).
  assume ¬(¬Px ∨ ¬Qx).
    assume ¬Px.
     ¬Px ∨ ¬Qx.
      F.
    therefore ¬¬Px.
    assume Qx.
      Px.
      assume ¬(¬Px ∨ ¬Qx).
        Px ∧ Qx.
        F.
      therefore ¬¬(¬Px ∨ ¬Qx).
      F.
    therefore ¬Qx.
    ¬Px ∨ ¬Qx.
    F.
  therefore ¬¬(¬Px ∨ ¬Qx).
 ¬Px ∨ ¬Qx.
 ¬(Px ∧ Qx) → ¬Px ∨ ¬Qx.
 T
  
 b. ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
 - here's a generation:
 assume ¬(Px ∨ Qx).
  assume Px
    Px ∨ Qx.
    F
  therefore ¬P.
  assume Q.
    P ∨ Q.
    F
  therefore ¬Q.
  ¬P ∧ ¬Q
¬(P + Q) → ¬P ∧ ¬Q 
 T
 
 c. ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
 - I love computers! here's a generation:
 assume ¬Px ∨ ¬Qx.
  assume Px ∧ Qx.
    Px.
    Qx.
    assume ¬Px.
      F.
    assume ¬Qx.
      F.
  therefore ¬(Px ∨ Qx).
 ¬Px ∨ ¬Qx → ¬(Px ∧ Qx)
 T

d. ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
- here's a generation:
assume ¬Px ∨ ¬Qx.
  assume Px ∧ Qx.
    Px.
    Qx.
    assume ¬Px.
      F.
    therefore ¬Px → F.
    assume ¬Qx.
      F.
    therefore ¬Qx → F.
    F.
  therefore ¬(Px ∧ Qx).
¬Px ∨ ¬Qx → ¬(Px ∧ Qx).	
 T

10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 

Natural deduction proofs repeatedly negate the right-hand (concluding) contingent variable or expression to (fail to) prove a contradiction. The proof is free to use whatever rules or inferences are relevant at each stage. Tree proofs, at least via the ones I've seen via the online tableau proof generator, only appear to work off of negating the left-hand side, or the premises, of the given entailment.
