# Project 1 Assignment

Your first project will require you to answer each of the 10 questions below.  You will be expected to open a pull request with your initial answers by the second class meeting, giving you one week to work on these problems. You and your peers will then have one week to work together to refine your respective initial answers, so they are ready for final submission. Once your pull requests have been reviewed and merged to the development branch, I will review them, then merge to the master branch. 

```
Tip #1: Carefully study the Hedman selections assigned, as several of the questions are taken directly from the textbook. 
Tip #2: Google is your friend. An important skill to pick up in this class is recognizing when to think hard and when to think smart. You might find answers to some of the questions below simply by googling; you might find pieces of answers to parts of some question below, which will need to be combined; then again, you might not find any help at all because the questions are more novel than they initially appear. I encourage you to use existing resources as guidance, but be careful. My reputation for asking students tricky questions is well-earned. 
Tip #3: Work _together_ to solve these problems, even for initial submissions and when you do, document this in github. For example, you might feel like you nearly have answers to question 1, but would love another pair of eyes. You can then open a post in your local github account, and tag folks from class requesting they check out your work. 
Tip #4: The work we do is challenging; that should be assumed. You are smart enough to be here; that should also be assumed. We have neither time nor space for shaming, but all of time and space for praising. Be cognizant of how your messages might be received, and err on the side of caution. It is hard to surmise intent from text alone. For my part, I treat text only communications the way modern musicals are written: Little subtext; emotions on the sleeve. 
```

Note: The standard interpretation of the logical symbols - "∨", "∧", "→", "¬", "∀", "∃" - is assumed throughout. 
Other symbols: ⊔ ⊓ ⊧ ⊭ ⊦ ⊬ ⊏ ⊐ ⊑ ⊒ ≡


1. Provide the truth tables for each of the following propositional logic formulas. State whether each is a tautology, a contradiction, or contingent:
  ```
  (a) (¬A→B)∨((A∧¬C)→B)
Tautology (see image)
![1-a](https://user-images.githubusercontent.com/117365623/219531269-1fbc6a49-f023-402e-a7ac-661ef785cf4e.png)

   
<img width="205" alt="7" src= https://user-images.githubusercontent.com/117365623/219530920-e372b761-5f7a-4d10-b351-57d280b03044.png>




  (b) (A→B)∧(A→¬B)
Contingent (see image)

![1-b](https://user-images.githubusercontent.com/117365623/218544900-f0888a15-ab53-4016-b860-654132fe64b9.png>

(c) (A→(B∨C))∨(C→¬A) 
Tautology (see image)

![1-c](https://user-images.githubusercontent.com/117365623/218545360-8301579b-7a83-4c9e-984a-8cfa8aa0dfd1.png)

  (d) ((A→B)∧C)∨(A∧D) 
Contingent (see image)

![1-d](https://user-images.githubusercontent.com/117365623/218545382-d9b88607-891c-4c02-a755-d24eade1d933.png)

  ```
	
2. A _literal_ is an atomic formula or the negation of an atomic formula. We say a formula is in _conjunctive normal form_ (CNF) if it is the conjunction of the disjunction of literals. Find propositional logic formulas in CNF equivalent to each of the following:
  ```
  (a) (A→B)→C
  (¬A∨B)→C
  ¬(¬A∨B)∨C
  (A∧¬B)∨C
  (A∨C)∧(¬B∨C)

  (b) (A→(B∨C))∨(C→¬A)
   A∨¬A
  Since this is a tautology

  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 
  A∨¬A
  Since this is a tautology
  ```
  
3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  
  ```
  (a)  B(x,y) that says that x is a brother of y  
  B(x,y) := ∃z.(P(zx) ∧ P(zy) ∧ ¬(z=y)) ∧ ¬(z=x) ¬(x=y) ¬F(x)
  (b)  A(x,y) that says that x is an aunt of y  
  A(x,y) := ∃z∃w.(P(zy) ∧ P(wz) ∧ P(wx) ∧ ¬(z=x)) F(x)
  (c)  C(x,y) that says that x and y are cousins   
  C(x,y) := ∃u∃w∃z(P(w,z)∧P(w,u)∧P(z,x)∧P(u,y)∧¬(z=u))∧¬(x=y)
  (d)  O(x) that says that x is an only child  
  O(x) := ∃y.(P(yx) ∧ ∀z.(P(yz) → (w=y)))
  (e)  T(x) that says that x has exactly two brothers 
  T(x) := ∃u∃y∃z(¬(y=z)∧¬(x=y)∧¬(x=z)∧P(u,x)∧P(u,y)∧P(u,z)∧¬F(y)∧¬F(z))∧∀w(P(u,w)∧¬F(w)→ w=x ∨ w=y ∨ w=z)

  ```

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```
  ⊔ ⊓ ⊧ ⊭ ⊦ ⊬ ⊏ ⊐ ⊑ ⊒ ≡ ¬ ¯
  parent_of
  m

  There is an implicit universal quantifier before everything.

 
  (a)  B that says that x is a brother of y

  Per (Person) ≡ M ⊔ ¬M
  p2 (Parent of 2) ≡ ∃parentof. ≥ 2 ⊓ ¬(∃parentof. = 1) (this condition is meant to avoid that the two persons are the same, but I am not entirely sure it works or whether there are better ways to do so)
  
  B ≡ M ⊓ ∃p2¯.Per

  (b)  A that says that x is an aunt of y
  
  ∃p2¯.parentof.parentof.Per

  A ≡ ¬M ⊓ (∃p2¯. (parentof. Per ≥ 2).(parentof.Per)) ⊔ ¬parentof.Per 
  Alternative syntax:
  A ≡ ¬M ⊓ (∃p2¯.(≥ 2 parent_of. (∃parent_of. Person)) ⊔ ¬∃parent_of. Person)

  (c)  C that says that x and y are cousins

  gp2(Grandparent with at least two children which each have children) ≡ ∃parentof ≥ 2.parentof.Per

  C ≡ gp2¯.Per

  But this would only describe one of the two cousins, i.e. "being a cousin of someone" or "having a cousin".
  We cannot define "being cousins" in description logic.

  (d)  O that says that x is an only child  

  O ≡ ¬ ∃p2¯.Per

  (e)  T that says that x has exactly two brothers 

  If this syntax works, then:

  
  p3m (be a parent of exactly three male children) ≡ (≥3 parent_of. Male) ⊓ (≤3 parent_of. Male)

  p1 (be a parent of at least one child) ≡ ≥1 parent_of. Person -- the inverse of p1 is just "be a child of"!

  T ≡ ∃p3m¯.Person ⊔ (¬M ⊓ ∃p1¯. (≥2 parent_of. Male ⊓ ≤2 parent_of. Male)

 

  ```


5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 

TBox = {
B ⊑ M
B ⊑ Per
M ⊑ Per
A ⊑ ¬M
A ⊑ Per
}

ABox = { John : M
John : parentof. Chris
John: B
Chris: M
Mary : ¬M
Mary: A
Alexander : parentof. Mary
Alexander : parentof. John
}

ΔI = {John, Mary, Alexander, Chris}

Named Individuals:
JohnI = J,
MaryI = M,
AlexanderI = A,
Chris = C

Concept Assignments:
PersonI = {J, M, A, C},
MaleI = {J, A, C},
FemaleI = {M},
BrotherI = {J},
AuntI = {M}

Role Assignments:
parentofI = {(J, C), (A, J), (A, M)}


6. Explain the difference - using natural language - between the first-order prefixes:
  ```
  (a) ∃x∀y and ∀x∃y
  The first formula reads "there is a x, such that for all ys". Any relation coming afterwards will be a relation between this one x and all other elements in the domain.
  The second formula reads "for all xs, there is a y such that". Any relation coming afterwards will relate at least one element y to all elements x in the domain.
  (b) ∃x∀y∃z and ∀x∃y∀z 
  The first formula reads "there is an x, for all y, there is a z such that". Any relation coming afterwards will relate one element x of the domain to all elements y of the domain which also are related to at least one element z.
  The second formula reads "for all xs, there is a y, such that for all zs". Any relation coming afterwards will relate all the element x of the domain to at least an element y in the domain, which in turn is related to all elements z in the domain. 
  (c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
  The first formula reads "for all xs, there is a y, such that for all zs, there is a w such that"
  Any relation coming afterwards will relate all elements x in the domain with at least an element y, which in turn relates to all the elements z in the domain, which in turn are each related to at least one element w.
``The second formula reads "there is an x, such that for all ys, there is a z, such that all w".
  Any relation coming afterwards will relate one element x in the domain with all elements y, which are each related to an element y, which in turn relate to all the elements w in the domain.

7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:
```
∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))

<img width="205" alt="7" src="https://user-images.githubusercontent.com/117365623/218544552-d4b55a2f-6529-4459-a7f1-8949af713f85.png">

```
 {(a,b)(b,a)(a,a)} 
 The second statement is true in this model. There is an x that relates every y (a, related to a and b) There is an x that relates to a z (where a is x and b is z), all ys (a and b) are related to some z (a is related to a and b, b is related to a)
 The first statement is not true. It is not true that all xs (a and b) are related to all zs (b is not related to a)
A graph is provided in the attached file.

8. Using an online tableau proof generator - such as the one found here `https://www.umsu.de/trees/` - provide tree proofs of the following entailments, which are known as the De Morgan's laws:
  ```
See attached images.

  (a) ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
  
  <img width="292" alt="8-a" src="https://user-images.githubusercontent.com/117365623/218544428-355ea0a8-b36a-4be7-aadb-7f4d47c89b10.png">

  (b) ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
  
  <img width="289" alt="8-b" src="https://user-images.githubusercontent.com/117365623/218544451-7c56e309-7114-4dd8-b0ea-75b964f764c1.png">

  (c) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  
  <img width="289" alt="8-c" src="https://user-images.githubusercontent.com/117365623/218544502-17e98b99-5a7a-4692-9ca8-72e714aad700.png">

  (d) ∀x∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
  
  <img width="301" alt="8-d" src="https://user-images.githubusercontent.com/117365623/218544517-8cac0986-7773-4451-bfd5-74b6a94b3e2d.png">

```
	
9. Using a natural deduction proof generator - such as the one found here `https://proofs.openlogicproject.org/` - provide natural deduction proofs for each of De Morgan's laws. 

Using http://teachinglogic.liglab.fr/DN/index.php, since I couldn't make the other website work.

a) 
assume -(Px & Qx).
  assume -(-Px + -Qx).
    assume -Px.
      -Px + -Qx.
      F.
    therefore --Px.
    assume Qx.
      Px.
      assume -(-Px + -Qx).
        Px & Qx.
        F.
      therefore --(-Px + -Qx).
      F.
    therefore -Qx.
    -Px + -Qx.
    F.
  therefore --(-Px + -Qx).
  -Px + -Qx.
therefore -(Px & Qx) => -Px + -Qx.	

b)
assume -(Px + Qx).
  assume Px.
    Px + Qx.
    F.
  therefore -Px.
  assume Qx.
    Px + Qx.
    F.
  therefore -Qx.
  -Px & -Qx.
therefore -(Px + Qx) => -Px & -Qx.	    

c)
assume -Px + -Qx.
  assume Px & Qx.
    Px.
    Qx.
    assume -Px.
      F.
    therefore -Px => F.
    assume -Qx.
      F.
    therefore -Qx => F.
    F.
  therefore -(Px & Qx).
therefore -Px + -Qx => -(Px & Qx).

d)
assume -Px & -Qx.
  assume Px + Qx.
    assume Px.
      -Px.
      F.
    therefore Px => F.
    assume Qx.
      -Qx.
      F.
    therefore Qx => F.
    F.
  therefore -(Px + Qx).
therefore -Px & -Qx => -(Px + Qx).	    

10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 
 
The tree method starts by assuming the negation of the statement to prove. It then applies a set of rule of derivations in order to find closed branches which provide a countermodel to the negated statement and ultimately prove it wrong (thus proving the original statement).
The natural deduction method instead breaks the statement into an assumption and a consequence and then applies rules which transform the original statement into the cnosequence. In alternative, it can negate the statement and reach a contradiction, thus proving the statement true.
8a) starts by negating the statement we want to prove, then gets rid of the quantifiers, then unwraps the negation of the implication, then applie rules to break down the disjunction in line 5 and then eliminates the double negation. We are left with either Qa or Pa being true. Buth both are in contradiction with the breaking down of line 4. Hence, the negated statement is contradictory and we have proved our initial goal.
9a) starts by assuming the antecedent inside the parenthesis. Then assumes the negation of the consequent. Then goes on to prove that this is contradictory, and prove the consequent starting from the antecedent. Even if there are proofs by contradiction inside of this strategy, it remains different from the tableau method because we started by assuming one of the elements and then proved that the other element followed from it. Using the tableau method, we rather tried to negate the whole statement and proved that it brings to a contradiction by exploring each possbility. 
