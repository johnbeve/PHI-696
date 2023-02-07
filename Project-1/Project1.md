# Question 1
1. Provide the truth tables for each of the following propositional logic formulas. State whether each is a tautology, a contradiction, or contingent:
```
  (a) (¬A→B)∨((A∧¬C)→B) 
  (b) (A→B)∧(A→¬B)
  (c) (A→(B∨C))∨(C→¬A) 
  (d) ((A→B)∧C)∨(A∧D) 
```

## Answers
(a) `(¬A→B)∨((A∧¬C)→B)` is a tautology
| A | B | C | (¬A→B) | ((A∧¬C)→B) | (¬A→B) ∨ ((A∧¬C)→B) |
| - | - | - | ------ | ---------- | -------------------- |
| T | T | T | T      | T          | T                    |
| T | F | T | T      | T          | T                    |
| F | T | T | T      | T          | T                    |
| F | F | T | F      | T          | T                    |
| T | T | F | T      | T          | T                    |
| T | F | F | T      | F          | T                    |
| F | T | F | T      | T          | T                    |
| F | F | F | F      | T          | T                    |

* (A∧¬C)→B <==> ¬(A∧¬C)∨B <==> (¬A∨C)∨B


(b) `(A→B)∧(A→¬B)` is contingently true
| A | B | (A→B) | (A→¬B) | (A→B) ∧ (A→¬B) |
| - | - | ----- | ------ | -------------- |
| T | T | T     | F      | F              |
| T | F | F     | T      | F              |
| F | T | T     | T      | T              |
| F | F | T     | T      | T              |


(c) `(A→(B∨C))∨(C→¬A)` is a tautology
| A | B | C | (A→(B∨C)) | (C→¬A) | (A→(B∨C)) ∨ (C→¬A) |
| - | - | - | --------- | ------ | ------------------ |
| T | T | T | T         | F      | T                  |
| T | F | T | T         | F      | T                  |
| F | T | T | T         | T      | T                  |
| F | F | T | T         | T      | T                  |
| T | T | F | T         | T      | T                  |
| T | F | F | F         | T      | T                  |
| F | T | F | T         | T      | T                  |
| F | F | F | T         | T      | T                  |


(d) `((A→B)∧C)∨(A∧D)` is contingently true (2<sup>4</sup> booleans is 16 possibilities)
| A | B | C | D | (A→(B∧C)) | (A∧D) | ((A→B)∧C) ∨ (A∧D) |
| - | - | - | - | ---------- | ---- | ------------------ |
| T | T | T | T | T          | T    | T                  |
| T | F | T | T | F          | T    | T                  |
| F | T | T | T | T          | F    | T                  |
| F | F | T | T | T          | F    | T                  |
| T | T | F | T | F          | T    | T                  |
| T | F | F | T | F          | T    | T                  |
| F | T | F | T | F          | F    | F                  |
| F | F | F | T | F          | F    | F                  |
| T | T | T | F | T          | F    | T                  |
| T | F | T | F | F          | F    | F                  |
| F | T | T | F | T          | F    | T                  |
| F | F | T | F | T          | F    | T                  |
| T | T | F | F | F          | F    | F                  |
| T | F | F | F | F          | F    | F                  |
| F | T | F | F | F          | F    | F                  |
| F | F | F | F | F          | F    | F                  |



---
# Question 2
2. A _literal_ is an atomic formula or the negation of an atomic formula. We say a formula is in _conjunctive normal form_ (CNF) if it is the conjunction of the disjunction of literals. Find propositional logic formulas in CNF equivalent to each of the following:
```
  (a) (A→B)→C
  (b) (A→(B∨C))∨(C→¬A)
  (c) (¬A∧¬B∧C)∨(¬A∧¬C)∨(B∧C)∨A 
```

## Answers
(a) `(A→B)→C`
```
(¬A ∨ B) → C           [→ to ∨]
¬(¬A ∨ B) ∨ C          [→ to ∨]
(A ∧ ¬B) ∨ C           [DeMorgan]
(A ∨ C) ∧ (¬B ∨ C)     [Distribute ∨]

```

(b) `(A→(B∨C))∨(C→¬A)`
```
(¬A ∨ (B ∨ C)) ∨ (¬C ∨ ¬A)     [→ to ∨]
```

(c) `(¬A ∧ ¬B ∧ C) ∨ (¬A ∧ ¬C) ∨ (B ∧ C) ∨ A`
```
(¬A ∧ ¬B ∧ C) ∨ (¬A ∧ ¬C) ∨ (B ∨ A) ∧ (A ∨ C)      [Distribute ∨]
```

---
# Question 3
3. Let V be the vocabulary of first-order logic consisting of a binary relation P and a unary relation F. Interpret P(x,y) as “x is a parent of y” and F(x) as “x is female.” Where possible define the following formulas in this vocabulary; where not possible, explain why: 
```
  (a)  B(x,y) that says that x is a brother of y
  (b)  A(x,y) that says that x is an aunt of y
  (c)  C(x,y) that says that x and y are cousins 
  (d)  O(x) that says that x is an only child
  (e)  T(x) that says that x has exactly two brothers 
```

## Answers:
```
x is brother of y
B(x,y) = ∃x∃y∃p( P(p,x) ∧ P(p,y) ∧ ¬F(x) )

x is aunt of y
A(x,y) = ∃y∃p∃g∃x( P(p,y) ∧ P(g,p) ∧ P(g,x) ∧ F(x) )

x is cousin of y
C(x,y) = ∃x∃p∃g∃u∃y( P(p,x) ∧ P(g,p) ∧ P(g,u) ∧ P(u,y) )

x is an only child
O(x) = ∃x∃p( P(p,x) ∧ ∀y( P(p,y) → y=x ) )

x has exactly two brothers
T(x) = ∃x∃y∃w∃p(
                  P(p, x) 
                  ∧ P(p,y) ∧ ¬F(y)
                  ∧ P(p,w) ∧ ¬F(w) 
                  ∧ ∀b( P(p,b) → b=y ∨ b=w )
                )
```

---
# Question 4
4. Let V be a vocabulary of the attribute (concept) language with complements (ALC) consisting of a role name "parent_of" and a concept name "Male". Interpret parent_of as "x is a parent of y" and M as "x is male". Where possible define the following formulas in this vocabulary; where not possible, explain why: 
```
  (a)  B that says that x is a brother of y
  (b)  A that says that x is an aunt of y
  (c)  C that says that x and y are cousins 
  (d)  O that says that x is an only child
  (e)  T that says that x has exactly two brothers 
```


---
# Question 5
5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 

---
# Question 6
6. Explain the difference - using natural language - between the first-order prefixes:
```
(a) ∃x∀y and ∀x∃y
(b) ∃x∀y∃z and ∀x∃y∀z 
(c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
```


---
# Question 7
7. Show that the following sentences are not equivalent by exhibiting a graph that models one but not both of these sentences:
```
∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))
```

---
# Question 8
8. Using an online tableau proof generator - such as the one found here `https://www.umsu.de/trees/` - provide tree proofs of the following entailments, which are known as the De Morgan's laws:
```
(a) ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
(b) ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
(c) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
(d) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
```
	

---
# Question 9
9. Using a natural deduction proof generator - such as the one found here `https://proofs.openlogicproject.org/` - provide natural deduction proofs for each of De Morgan's laws. 


---
# Question 10
10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 
