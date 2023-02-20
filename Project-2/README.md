# Project 2

Your second project will require you to answer each of the 10 questions below.  You will be expected to open a pull request with your initial answers by the second class meeting, giving you one week to work on these problems. You and your peers will then have one week to work together to refine your respective initial answers, so they are ready for final submission. Once your pull requests have been reviewed and merged to the development branch, I will review them, then merge to the master branch. 

```
Tip #1: Carefully study the Baader, et. al. selections assigned on bisimulation; it is deceptively subtle, and quite powerful. 
Tip #2: Google is still your friend. So is stackexchange...
Tip #3: Work together to solve these problems, even for initial submissions and when you do, document this in github. 
Tip #4: Work together as a team. 
```

1. Let V be a vocabulary of ALCI consisting of a role name "P". Interpret part_of as "x is a part of y". Using this role name, define the following formulas in this language:

  (a)  PP that says that x is a proper part of y
  
  Answer:
  PP ≡ ∃part_of.C ⊓ ¬( ∀part_of.C ⊓ ∀part_of.¬C)
  PP ≡ P ⊓ ¬P¯
  
  (b)  iPP that says that y is a proper part of x
 
  Answer:
  iPP ≡ ∃part_of¯.C ⊓ ¬ (∀part_of.C ⊓ ∀part_of.¬C)
  iPP ≡ (P ⊓ ¬P¯)¯
  
  (c)  iP that says that y has x as part 
  
  Answer:
  iP ≡  ¬∃part_of¯.C
  iP ≡ P¯
  
  (d)  O that says that x overlaps y
  
  Answer:
  O ≡ ¬∀part_of.C ⊓ ¬∀part_of.¬C ⊔ (∀part_of.C ⊓ ∀part_of.¬C)
  O ≡ ∃P¯.(∃P)
  
  (e)  D that says that x and y are disjoint 
  
  Answer:
  D ≡ ∀part_of.¬C ⊓ ¬(∀part_of.C ⊓ ∀part_of.¬C)
  D ≡ ¬O

2. Use your axioms from question 1 as the basis of an ALCI T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 

Answer: 

A mode I of K = (T#1, A#1) as follow,

ΔI = {Chairs, Stools, Animals, Tigers, Cats, Birds, Peacocks},
Chairs = cr,
Stools = s,
Animals = a,
Tigers = t,
Cats = ct,
Birds = b,
Peacocks = p

TBox: 
T#1 = {C ≡ C_colored ⊔ ¬C_colored,
PP ≡ ∃part_of.C ⊓ ¬( ∀part_of.C ⊓ ∀part_of.¬C),
iPP ≡ ∃part_of¯.C ⊓ ¬ (∀part_of.C ⊓ ∀part_of.¬C),
iP ≡  ¬∃part_of¯.C,
O ≡ ¬∀part_of.C ⊓ ¬∀part_of.¬C ⊔ (∀part_of.C ⊓ ∀part_of.¬C),
D ≡ ∀part_of.¬C ⊓ ¬(∀part_of.C ⊓ ∀part_of.¬C)}

ABox:
A#1 = { cr: C_colored,
p:C_colored,
s: ¬C_colored,
a: ¬C_colored,
t: ¬C_colored,
ct: ¬C_colored,
b: ¬C_colored,
P(t, ct),
P(ct, a),
pp(t, ct),
O (cr, s),
D (cr, b),
iPP (a, t)}


3. Translate the following first-order logic axioms into ALCI: 

(a) ∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))

Answer: ∃r.(∀r.C ∧ ∀r¯.C)

(b) ∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))

Answer: ∃r.(∃r.C ∧ ∀r¯.C)

(c) ∀y(R(x, y) → ∃x(R(y, x) ∧ ∀y(R(x, y) → A(y))))

Answer: ∃r.(∃r.C ∧ ∀r¯.C)

(d) (∀y)(R(x, y) → A(y)) ∧ (∃y)(R(x, y) ∧ B(y))


4. Provide an interpretation I<sub>1</sub> for ALC and an interpretation I<sub>2</sub> for ALCN - each distinct from any interpretation covered in class so far - and construct a bisimulation that demonstrates ALCN is more expressive than ALC. Use the [mermaid syntax](https://github.com/mermaid-js/mermaid) of markdown to provide a graphical representation of your work. Feel free to use the [mermaid live editor](https://mermaid.live/) when diagramming. 

---
I<sub>1</sub>
---
```mermaid
graph TB
  A([animal])-->B([mammal])
  P([plant])-->Q([Has_seeds])
  B-->C([Cat])
  Q-->R([Needle_leaves])
  C-->D([Tiger])
  R-->S([Conifers])  
  
```
---
I<sub>2</sub> 
---
```mermaid
stateDiagram-v2
    state if_state <<choice>>
    [*] --> IsPositive
    IsPositive --> if_state
    if_state --> False: if n < 2
    if_state --> True : if n >= 2
```

5. Provide an interpretation I<sub>1</sub> for ALC and an interpretation I<sub>2</sub> for ALCN - each distinct from any interpretation covered in class so far - and construct a bisimulation that _does not_ demonstrate ALCN is more expressive than ALC. Use the [mermaid syntax](https://github.com/mermaid-js/mermaid) of markdown to provide a graphical representation of your work. Feel free to use the [mermaid live editor](https://mermaid.live/) when diagramming. 

---
I<sub>1</sub>
---
```mermaid
graph TB
  A([animal])-->B([mammal])
  P([plant])-->Q([Has_seeds])
  B-->C([Cat])
  Q-->R([Needle_leaves])
  C-->D([Tiger])
  R-->S([Conifers])  
  
```
---
I<sub>2</sub> 
---
```mermaid
---
title: Animal example
---
classDiagram
    note "From Duck till Zebra"
    Animal <|-- Duck
    note for Duck "can fly\ncan swim\ncan dive\ncan help in debugging"
    Animal <|-- Fish
    Animal <|-- Zebra
    Animal : +int age
    Animal : +String gender
    Animal: +isMammal()
    Animal: +mate()
    class Duck{
        +String beakColor
        +swim()
        +quack()
    }
    class Fish{
        -int sizeInFeet
        -canEat()
    }
    class Zebra{
        +bool is_wild
        +run()
    }
```


6. Explain the difference - using natural language - between the description logic expressions:
 
  (a) ∃r.C and ∀r.C
  
  Answer: ∃r.C means that there exists a r-filler which is an element that belongs to C, while ∀r.C means that all r-fillers are Cs.
  
  (b) ∃r-.C and ∀r-.C
  
  Answer: ∃r-.C means that there exists a inverse r-filler which an element that belongs to C, while ∀r.C means that all inverse r-fillers are Cs.
  
  (c) <=nr and <=nr.C
  
  Answer: <=nr means that there are no more than n r-fillers, while <=nr.C means that there are no more than n r-fillers in C.
  
  (d) ∃r-.C and ∃r-.{a} 
  
  Answer: ∃r-.C means that there are no more than n inverse r-fillers, while <=nr.C means that there are no more than n inverse r-fillers in C.


7. There is a delightfully helpful subreddit called "ELI5" which stands for something like "explain it like I'm 5" where users post conceptually challenging questions and other users attempt to provide explanations in simple, jargon-free, terms that presumably a 5 year-old could understand. Using this as a model, explain the _finite model property_. Be sure to provide a simple example and explain when the property might be important, and when it is not so important. 

Ansewr: color, plastic, metal


8. Following up on the preceding , explain the _tree model property_. Be sure to provide a simple example and explain when the property might be important, and when it is not so important. 



9. Open the Protege editor and create object properties for each of the role names that you constructed in question 1. You should have at least 6 object properties. Assert in the editor that P is a sub-property of O, that P is transitive, and that O is symmetric. Next, add individuals - a, b, c - to the file and assert that c is part of a and that c overlaps b. Running the reasoner should reveal - highlighted in yellow if you select the individual c - that c overlaps a. Using the discussion in the selections from chapter 4 of the Baader, et. al. text as a guide, explain how the tableau algorithm is generating this inference. Also, provide a screenshot of the results of your reasoner run with c highlighted. 

10. Following up on your work in question 9, adjust/add/remove/etc. object properties and individuals in your Protege file so that when you run a reasoner in Protege, you return the following consequences: 
```
  (a) a is a proper part of b and disjoint from e
  (b) a overlaps c
  (c) a is part of b, b is part of f, and a is part of f
  (e) There are no parts between a and g in common
```
Provide a screenshot of your results here. 



