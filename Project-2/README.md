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
  PP ≡ P ⊓ ¬P¯
  
  (b)  iPP that says that y is a proper part of x
 
  Answer:
  iPP ≡ (P ⊓ ¬P¯)¯
  
  (c)  iP that says that y has x as part 
  
  Answer:
  iP ≡ P¯
  
  (d)  O that says that x overlaps y
  
  Answer:
  O ≡ ∃P¯.(∃P)
  
  (e)  D that says that x and y are disjoint 
  
  Answer:
  D ≡ ¬O

2. Use your axioms from question 1 as the basis of an ALCI T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 

Answer: 

A mode I of K = (T#1, A#1) as follow,

TBox: 
T#1 = {C ≡ Fly ⊔ ¬ Fly,
PP ≡ P ⊓ ¬P¯,
iPP ≡ (P ⊓ ¬P¯)¯,
iP ≡ P¯,
O ≡ ∃P¯.(∃P),
D ≡ ¬O
}

ΔI = {Aquatic animals, Seagull, Cats, Fish, Mammal, Whales}

Individual names assignments:
Aquatic animals = a,
Seagull = b,
Cats = c,
Fish = f,
Mammal = m,
Whales = w.

Concept assignments:
Fly = {b},
¬ Fly = {a, c, f, m, w},
Animal = {a, b, c, f, m, w}.

Role relation assignments: 
P: {(a,a), (b,b), c,c), (m,m), (w,w), (f,f), (f,a), (m,a), (c,m), (w, m)}
PP: {(f,a), (m,a), (c,m), (w, m)}
iPP: {(a, f), (a, m), (m, c), (m, w)}
iP: {(a,a), (b,b), c,c), (m,m), (w,w), (f,f), (a, f), (a, m), (m,c), (m,w)}
O: {(a, m), (m,a)}
D: {(a, b),(b,a) (a, c), (c,a), (b, c), (c, b), (b, f), (f, b), (b, m), (m, b), (b, w), (w, b), (c, f), (f, c), (c, w), (w, c), (f, m), 
(m, f), (f, w,, (w,f)}


ABox:
A#1 = { 
Fly: b,
PP(w, a),
PP(w, m),
PP(f, a),
iP (m, w),
iPP (m, c),
O (a, m),
D(f,m),
D(b, c),
D(a, b)
}


3. Translate the following first-order logic axioms into ALCI: 

(a) ∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))

Answer: ∃R.(∀R.T) ⊓ ∀R.T

(b) ∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))

Answer: ∃R¯.(∃R.(∃R¯))

(c) ∀y(R(x, y) → ∃x(R(y, x) ∧ ∀y(R(x, y) → A(y))))

Answer: ∀R.∃R.∀R.A

(d) (∀y)(R(x, y) → A(y)) ∧ (∃y)(R(x, y) ∧ B(y))

Answer: (∀R.A) ⊓ (∃R.B)


4. Provide an interpretation I<sub>1</sub> for ALC and an interpretation I<sub>2</sub> for ALCN - each distinct from any interpretation covered in class so far - and construct a bisimulation that demonstrates ALCN is more expressive than ALC. Use the [mermaid syntax](https://github.com/mermaid-js/mermaid) of markdown to provide a graphical representation of your work. Feel free to use the [mermaid live editor](https://mermaid.live/) when diagramming. 

---
I<sub>1</sub>
---
```mermaid
---
title: Classification of Vertebrates
---
graph TB
  A([Vertebrates])--sub_class-->B([Warm-blooded])
  A--sub_class-->C([Cold-blooded])  
```
---
I<sub>2</sub> 
---
```mermaid
---
title: Classification of Invertebrates
---
graph TB
   A([Invertebrates])--sub_class-->B([Porifera])
   A--sub_class-->C([Cnidaria])
   A--sub_class-->D([Arthropoda])
   A--sub_class-->E([Annelida])
   A--sub_class-->F([Mollusca])
```

ΔI1 = {Vertebrates, Warm-blooded, Cold-blooded}

Vertebrates = V
Warm-blooded = WB
Cold-blooded = CB

Role Assignments:
s = {(V, WB), (V, CB)}


ΔI2 = {Invertebrates, Porifera, Cnidaria, Arthropoda, Annelida, Mollusca}

Named IndividualsI:
Invertebrates = INV
Porifera = PO
Cnidaria = CN
Arthropoda = AR
Annelida = AN
Mollusca = MO

Role Assignments:
s2 = {(INV, PO), (INV, CN), (INV, AR), (INV, AR), (INV, AN), (INV,MO)}

Bisimulation:

ρ = {(V, INV), (WB, PO), (CB, CN),(WB, AR), (CB, AN), (CB, MO)}

So V is bisimilar to INV. But we can distinguish them in ALCN by defining the role t2 as
≥5 ∃t2.⊤
in I2
___


5. Provide an interpretation I<sub>1</sub> for ALC and an interpretation I<sub>2</sub> for ALCN - each distinct from any interpretation covered in class so far - and construct a bisimulation that _does not_ demonstrate ALCN is more expressive than ALC. Use the [mermaid syntax](https://github.com/mermaid-js/mermaid) of markdown to provide a graphical representation of your work. Feel free to use the [mermaid live editor](https://mermaid.live/) when diagramming. 

---
I<sub>1</sub>
---
```mermaid
---
title: Classification of Animals
---
graph TB
  A([Animal])--sub_kingdom-->B([Vertebrates])
  A--sub_kingdom-->C([Invertebrates])
  
```
---
I<sub>2</sub> 
---
```mermaid
---
title: Classification of Plants
---
graph TB
    A([Plant])--sub-kingdom-->B([Cryptogams])
    A--sub-kingdom-->C([phanerogams])   
```
ΔI1 = {Animals, Vertebrates, Invertebrates}

Role Assignments:
s = {(Animals, Vertebrates), (Animals, Invertebrates)}

ΔI2 = {Plants, Cryptogams, Phanerograms}

Role Assignments:
s2 = {(Plants, Cryptogams),  (Plants, Phanerograms)}

Bisimulation:

ρ = {(Animals, Plants), (Vertebrates, Cryptogams), (Invertebrates, Phanerograms)}

So Animals is bisimilar to Plants.


6. Explain the difference - using natural language - between the description logic expressions:
 
  (a) ∃r.C and ∀r.C
  
  Answer: ∃r.C means that all x has a r-filler y which belongs to C, while ∀r.C means that all r-fillers ys of all x belong to C.
  
  (b) ∃r-.C and ∀r-.C
  
  Answer: ∃r-.C means that there is a thing y r-related to all xs, and this thing belongs to C,
  
  while ∀r.C means that if there is a thing r-related to all xs, then this thing belongs to C.
  
  (c) <=nr and <=nr.C
  
  Answer: <=nr means that role r connects all the xs to no more than n elements.
 
  while <=nr.C means that role r connects all the xs to no more than n elements, and they belong to C.
  
  (d) ∃r-.C and ∃r-.{a} 
  
  Answer: ∃r-.C means that for all xs, there is at least a thing y, which is r-inverse related to it, and which belongs to C,
  
  while ∃r-.{a} means that for all xs, there is element a, which is r-inverse related to it.


7. There is a delightfully helpful subreddit called "ELI5" which stands for something like "explain it like I'm 5" where users post conceptually challenging questions and other users attempt to provide explanations in simple, jargon-free, terms that presumably a 5 year-old could understand. Using this as a model, explain the _finite model property_. Be sure to provide a simple example and explain when the property might be important, and when it is not so important. 

Ansewr: 
Bob loves playing games, and he hopes there is a game that can be played with different results forever. 
One day, his father gives him a game, called Color-card: there are a number of color cards in a box. Each card has a different color, but it is full colored on one side, while on the other side it is a blank sheet with the colored dot. Once a time, the player chooses any number of cards from the box, and then use any number of cards he chose to make combinations. For example, the first time, Bob chooses five color cards from the box, red, yellow, blue, green, brown, then he uses three cards, and put them in such a order: 1, red (front side), 2, blue (back side), 3, green (back side). That is one combination. The player continues playing until there is a combination that repeats. If the player cannot continue playing, he/she fails. 
However, if the player fails at one time, he/she can choose more or/and different cards, then play the next time. The player wins if the cards he chooses can allow him to play forever. 
Unfortunately, Bob cannot win the game, because no matter how many cards he chooses (the number of cards is not limitless), and how hard he tries, he cannot continue playing without a repeated combination occurs.  
We say that the Color-card game has finite model property. 
Finite model property is important because it can be used to design a decidable algorithm for the satisfiability of its concepts. 

8. Following up on the preceding , explain the _tree model property_. Be sure to provide a simple example and explain when the property might be important, and when it is not so important. 

At another day, Bob's father gives him a different game, called Dot-and-Line. 
There is a big board, a number of tacks and thread. The games can be played with two people. When it is your turn, the other player choose a number of tacks and tacks them on the board - he/she can choose any place to locate a tack. Then you use thread to connect the tacks (any one tack needs to be connected to at least one other tack) - have all tacks to be connected. The connection is such that from one tack to any other tack through the thread, there is only one way to go. If the other player finds there is more than two ways between any two tacks in your work, you lose. If you does not lose, then it is the other player's turn. You two play in turn until one loses. 
We say that the Dot-and-Line game has the tree model property. 
The tree model property is important to tableau-based algorithms for the consistency check of knowledge base and applied ontology. Most of applied ontologies, especially those BFO-based ones, have this property, allowing that their consistency can be checked by tableau reasonings.

9. Open the Protege editor and create object properties for each of the role names that you constructed in question 1. You should have at least 6 object properties. Assert in the editor that P is a sub-property of O, that P is transitive, and that O is symmetric. Next, add individuals - a, b, c - to the file and assert that c is part of a and that c overlaps b. Running the reasoner should reveal - highlighted in yellow if you select the individual c - that c overlaps a. Using the discussion in the selections from chapter 4 of the Baader, et. al. text as a guide, explain how the tableau algorithm is generating this inference. Also, provide a screenshot of the results of your reasoner run with c highlighted. 

Answer: 

The tableau method uses the concept/concepts from a Knowledge Base (KB). In the Protege, the KB is the assertions made about individuals and classes. It has the tree model property: each node in the tree represents a possible interpretation, and the branches represent the different ways in which the interpretation can be extended. It then expands the assertions by using different rules. 
What we are doing to create individuals and classes in the Protege editor is basically constructing a set of possible interpretations where all the possible inferences from T-box are drawn, as well as all the possible concept memberships are tried.
As a result, the reasoner will notice the logical relations between the concepts we asserted for individuals through Protege. It will see that c is a part of a, and since parthood is subsumed by overlap, it will apply the subsumption rule explained at page 84 in Baader et al. This will add a new fact, that c overlaps a. 

![picture 1](Q9.png)

10. Following up on your work in question 9, adjust/add/remove/etc. object properties and individuals in your Protege file so that when you run a reasoner in Protege, you return the following consequences: 
```
  (a) a is a proper part of b and disjoint from e
  (b) a overlaps c
  (c) a is part of b, b is part of f, and a is part of f
  (e) There are no parts between a and g in common
```
Provide a screenshot of your results here. 

![picture 2](Q10.png)

