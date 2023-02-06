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
  (b) (A→B)∧(A→¬B)
Contingent (see image)
  (c) (A→(B∨C))∨(C→¬A) 
Tautology (see image)
  (d) ((A→B)∧C)∨(A∧D) 
Contingent (see image)
  ```
	
2. A _literal_ is an atomic formula or the negation of an atomic formula. We say a formula is in _conjunctive normal form_ (CNF) if it is the conjunction of the disjunction of literals. Find propositional logic formulas in CNF equivalent to each of the following:
  ```
  (a) (A→B)→C
  ¬(¬A∨B)∨C
  (A∧¬B)∨C
  (A∨C)∧(¬B∨C)
  (b) (A→(B∨C))∨(C→¬A)
  (¬A∨(B∨C))∨(¬C∨¬A)
  ¬A∨B
  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 
  (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 
  Not exactly sure how to apply the distributive rule here. 
  ```
  
3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  
  ```
  (a)  B(x,y) that says that x is a brother of y  
  B(x,y) := ∃z.(P(zx) ∧ P(zy)) ∧ ¬F(x)
  (b)  A(x,y) that says that x is an aunt of y  
  A(x,y) := ∃z.P(zy) ∧ ∃w.(P(wz) ∧ P(wx)) ∧ F(x)
  (c)  C(x,y) that says that x and y are cousins   
  C(x,y) := ∃z.P(zy) ∧ ∃w.P(wx) ∧ ∃u.(P(uz) ∧ P(uw))
  (d)  O(x) that says that x is an only child  
  O(x) := ∃y.P(yx) ∧ ¬∃z.(∃w.P(wz) ∧ (w=y))
  (e)  T(x) that says that x has exactly two brothers 
  T(x) := ∃y∃z∃w.(P(yx) ∧ P(yz) ∧ P(yw)) ∧ (P(yq) → ((q=x) ∨ (q=z) ∨ (q=w)))

  ```

4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
  ```
  ⊔ ⊓ ⊧ ⊭ ⊦ ⊬ ⊏ ⊐ ⊑ ⊒ ≡ ¬
  parent_of
  m
  To be honest I do not know how to solve most of these without introducing some concept like "person". 
  We definitely want to put some condition after the existential restriction, but I am not able to specify such restriction with the given concepts.


  (a)  B that says that x is a brother of y
  B ≡ m ⊓ ∃parentof.(and some conditions saying that the parentof-filler is the subject of the definition)
  (b)  A that says that x is an aunt of y
  A ≡ ¬m ⊓ ∃parentof.(∃parentof.)
  (c)  C that says that x and y are cousins
  (d)  O that says that x is an only child  
  (e)  T that says that x has exactly two brothers 
  ```


5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 


This requires 4 to be done first




6. Explain the difference - using natural language - between the first-order prefixes:
  ```
  (a) ∃x∀y and ∀x∃y
  The first formula reads "there is a x, such that all ys". Any relation coming afterwards will be a relation between this one x and all other elements in the domain.
  The second formula reads "for all xs, there is a y". Any relation coming afterwards will relate at least one element y to all elements x in the domain.
  (b) ∃x∀y∃z and ∀x∃y∀z 
  The first formula reads "there is an x, for all y, such that there is a z". Any relation coming afterwards will relate one element x of the domain to all elements y of the domain which also are related to at least one element z.
  The second formula reads "for all xs, there is a y, for all zs". Any relation coming afterwards will relate all the element x of the domain to at least an element y in the domain, which in turn is related to all elements z in the domain. 
  (c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
  The first formula reads "for all xs, there is a y, for all zs, there is a w."
  Any relation coming afterwards will relate all elements x in the domain with at least an element y, which in turn relates to all the elements z in the domain, which in turn are each related to at least one element w.
``The second formula reads "there is an x, for all ys, there is a z, such that all ws".
  Any relation coming afterwards will relate one element x in the domain with all elements y, which are each related to an element y, which in turn relate to all the elements w in the domain.

7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:
```
∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))
```
 {(a,b)(b,a)(a,a)} 
 The second statement is true in this model. There is an x that relates every y (a, related to a and b) There is an x that relates to a z (where a is x and b is z), all ys (a and b) are related to some z (a is related to a and b, b is related to a)
 The first statement is not true. It is not true that all xs (a and b) are related to all zs (b is not related to a)
A graph is provided in the attached file.

8. Using an online tableau proof generator - such as the one found here `https://www.umsu.de/trees/` - provide tree proofs of the following entailments, which are known as the De Morgan's laws:
  ```
See attached images.

  (a) ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
  (b) ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
  (c) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
  (d) ∀x∀y((¬Px ∧ ¬Qx) → ¬(Px ∨ Qx))
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