# Question 1
1. Provide the truth tables for each of the following propositional logic formulas. State whether each is a tautology, a contradiction, or contingent:
```
  (a) (¬A→B)∨((A∧¬C)→B) 
  (b) (A→B)∧(A→¬B)
  (c) (A→(B∨C))∨(C→¬A) 
  (d) ((A→B)∧C)∨(A∧D) 
```

## Answers:
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

## Answers:
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
FOL 

// x is brother of y
B(x,y) = ∃x∃y∃p( P(p,x) ∧ P(p,y) ∧ ¬F(x) )

// x is aunt of y
A(x,y) = ∃y∃p∃g∃x( P(p,y) ∧ P(g,p) ∧ P(g,x) ∧ F(x) )

// x is cousin of y
C(x,y) = ∃x∃p∃g∃u∃y( P(p,x) ∧ P(g,p) ∧ P(g,u) ∧ P(u,y) )

// x is an only child
O(x) = ∃x∃p( P(p,x) ∧ ∀y( P(p,y) → y=x ) )

// x has exactly two brothers
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

## Answers:
### $ALC$
* The description logic $AL$ conventionally consists of:
  * Top $\top$, Bottom $\bot$, Conjunction $\sqcap$, Atomic Negation $\neg A$, Value Restriction $\forall r.C$
* $AL$ extended with $C$ adds Negation (of compound concepts) $\neg C$
  * This allows a derivation of Disjunction $\sqcup$ (from Negation & Conjunction)
  * This allows a derivation of Existential Restriction $\exist r.C$ (from Negation & Value Restrction)

### DL Extensions
* None of the provided formulas are strictly definable as roles in $ALC$ in terms of the role `parent_of`
* The DL extension $H$ adds Role Inclusion Axioms $r \sqsubseteq s$, allowing us to define other roles in terms of `parent_of`
* The DL extension $I$ adds Inverse Roles $r^-$, allowing us to express the inverse of `parent_of` 

With these extensions we can define the formulas:

(a) `B that says that x is a brother of y`
  * $B ≡ M\sqcap ∃parentOf^-.(∃parentOf)$
    * "Someone is a brother of someone else iff they're a male and there's a parent of that someone who is also a parent of that someone else"
  * This relation should also be defined as irreflexive, symmetric, and transitive

(b) `A that says that x is an aunt of y`
  * $A ≡ \neg M \sqcap ∃parentOf^-.(∃parentOf.(∃parentOf))$
    * "Someone is an aunt of someone else iff they're not male and there's a parent of that someone, who is also a parent of another, who in turn is a parent of that someone else"
  * This relation should be irreflexive, asymmetric, and intransitive

(c) `C that says that x and y are cousins`
  * $C ≡ ∃parentOf^-.(∃parentOf^-.(∃parentOf.(∃parentOf))) $
    * "Someone is a cousin of someone else iff they have a parent, who has a parent, who is the parent of another, who is the parent of that someone else"
  * This relation should be irreflexive, symmetric, and intransitive (for first cousins)


The following formulas can be defined using the DL extension $N$, which adds Number Restrictions $(\leqslant n r)$ and $(\geqslant nr )$ where $n$ is a positive number:

(d) `O that says that x is an only child`
  * $O ≡ \exist parentOf^-.((\geqslant 1 parentOf) \sqcap (\leqslant 1 parentOf))$
    * "Someone is an only child iff there is a parent of them, who is a parent of at least and at most 1 (person)." 

(e) `T that says that x has exactly two brothers`
  * $T ≡ \exist parentOf^-.((\leqslant 2 parentOf) \sqcap (\geqslant 2 parentOf) \sqcap \exist parentOf.(M)) $
    * "Someone has exactly two brothers iff there's a parent of them who is the parent of exactly two males"

---
# Question 5
5. Select two formulas defined in ALC from question 4 to form the basis of a T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 


## Answers:
Knowledge Base $K = (T, A)$

### T-Box T
$ T = \left\{
	\begin{darray}{l}
	  B \equiv M\sqcap ∃parentOf^-.(∃parentOf) \\\\
    C ≡ ∃parentOf^-.(∃parentOf^-.(∃parentOf.(∃parentOf))) \\\\
    siblingOf \equiv \exist parentOf^-(\exist parentOf) \\\\
    Sibling \equiv \exist siblingOf
	\end{darray}
\right\} $

### A-Box A
$ A = \left\{
	\begin{darray}{r}
		(Tim, Ralph) : B \\
    (Ralph, Maynard) : B \\
    (Tim, Maynard) : B \\
    (Matt, Tim) : C \\
    (Jill, Tim) : siblingOf \\
    Tim : Sibling \\ 
    Ralph : Sibling
	\end{darray}
\right\} $

### Interpretation $I$
$ I \left\{
	\begin{darray}{l}
    \Delta^I = \set{t, j, r, q, m, 5, 11} \\
    Tim^I = t \\
    Jill^I = j \\
    Ralph^I = r \\
    Maynard^I = q \\
    Matt^I = m \\ 
    Extra^I = 5 \\
    CoolestGuy^I = t \\
    B^I = \set{(t, r), (r, q), (t, q)} \\
    C^I = \set{(m, t)} \\
    siblingOf^I = \set{(j, t), (t, q) } \\
    Sibling^I = \set{t, r}
	\end{darray}
\right\} $

$I_1$ is a model of $K$ because it satisfies every axiom of $T$ and every assertion of $A$. 

It's still a model even though:
* It interprets concept names not in the knowledge base, $Extra$ and $CoolestGuy$
* Extra elements are in the extension of $siblingOf$
* The same element $t$ satisfies multiple concept names, $Tim$ and $CoolestGuy$, without a Unique Name Assumption preventing this
* Axiom $Sibling \equiv \exist siblingOf$ plus the assertion that $Ralph : Sibling$ means someone is a sibling of Ralph, but no relation satisfies this. The Open World Assumption allows for incomplete knowledge about who is Ralph's sibling.

---
# Question 6
6. Explain the difference - using natural language - between the first-order prefixes:
```
(a) ∃x∀y and ∀x∃y
(b) ∃x∀y∃z and ∀x∃y∀z 
(c) ∀x∃y∀z∃w and ∃x∀y∃z∀w
```

## Answers:
(a) 
* `∃x∀y` means "There exists some x such that for all y".
* `∀x∃y` means "For all x, there exists some y".

(b)
* `∃x∀y∃z` means "There exists some x such that, for all y, there exists some z".
* `∀x∃y∀z` means "For all x, there exists some y such that for all z".

(c)
* `∀x∃y∀z∃w` means "For all x there exists some y such that for all z there exists some w".
* `∃x∀y∃z∀w` means "There exists some x such that for all y there exists some z such that for all w".


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

## Answers:

(a) ∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx)) is valid
```
        1.¬∀x∀y(¬(Px ∧ Qx) → (¬Px ∨ ¬Qx))
        2.¬∀y(¬(Pa ∧ Qa) → (¬Pa ∨ ¬Qa))     (1)
        3.¬(¬(Pa ∧ Qa) → (¬Pa ∨ ¬Qa))       (2)
        4.¬(Pa ∧ Qa)                        (3)
        5.¬(¬Pa ∨ ¬Qa)                      (3)
        6.¬¬Pa                              (5)
        7.¬¬Qa                              (5)
        8.Qa                                (7)
        9.Pa                                (6)
10.¬Pa          11.¬Qa                      (4, 4)
x               x
```

(b) ∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx)) is valid
```
        1.¬∀x∀y(¬(Px ∨ Qx) → (¬Px ∧ ¬Qx))
        2.¬∀y(¬(Pa ∨ Qa) → (¬Pa ∧ ¬Qa))       (1)
        3.¬(¬(Pa ∨ Qa) → (¬Pa ∧ ¬Qa))         (2)
        4.¬(Pa ∨ Qa)                          (3)
        5.¬(¬Pa ∧ ¬Qa)                        (3)
        6.¬Pa                                 (4)
        7.¬Qa                                 (4)
8.¬¬Pa          9.¬¬Qa                        (5,5)
10.Pa           11.Qa                         (8, 9)
x               x
```


(c) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx)) is valid
```
        1.¬∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
        2.¬∀y((¬Pa ∨ ¬Qa) → ¬(Pa ∧ Qa))         (1)
        3.¬((¬Pa ∨ ¬Qa) → ¬(Pa ∧ Qa))           (2)
        4.¬Pa ∨ ¬Qa                             (3)
        5.¬¬(Pa ∧ Qa)                           (3)
        6.Pa ∧ Qa                               (5)
        7.Pa                                    (6)
        8.Qa                                    (6)
9.¬Pa           10.¬Qa                          (4,4)
x               x
```


(d) ∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx)) is valid
```
        1.¬∀x∀y((¬Px ∨ ¬Qx) → ¬(Px ∧ Qx))
        2.¬∀y((¬Pa ∨ ¬Qa) → ¬(Pa ∧ Qa))         (1)
        3.¬((¬Pa ∨ ¬Qa) → ¬(Pa ∧ Qa))           (2)
        4.¬Pa ∨ ¬Qa                             (3)
        5.¬¬(Pa ∧ Qa)                           (3)
        6.Pa ∧ Qa                               (5)
        7.Pa                                    (6)
        8.Qa                                    (6)
9.¬Pa           10.¬Qa                          (4,4)
x               x
```

---
# Question 9
9. Using a natural deduction proof generator - such as the one found here `https://proofs.openlogicproject.org/` - provide natural deduction proofs for each of De Morgan's laws. 


---
# Question 10
10. Compare and contrast the proofs provided for (a) in your answers to questions 8 and 9. Explain the different assumptions, strategies, etc. exhibited in tree proofs vs natural deduction proofs. 
