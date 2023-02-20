# Project 2

Your second project will require you to answer each of the 10 questions below.  You will be expected to open a pull request with your initial answers by the second class meeting, giving you one week to work on these problems. You and your peers will then have one week to work together to refine your respective initial answers, so they are ready for final submission. Once your pull requests have been reviewed and merged to the development branch, I will review them, then merge to the master branch. 

```
Tip #1: Carefully study the Baader, et. al. selections assigned on bisimulation; it is deceptively subtle, and quite powerful. 
Tip #2: Google is still your friend. So is stackexchange...
Tip #3: Work together to solve these problems, even for initial submissions and when you do, document this in github. 
Tip #4: Work together as a team. 
```
Symbols: ∀ ∃ ⊔ ⊓ ⊧ ⊭ ⊦ ⊬ ⊏ ⊐ ⊑ ⊒ ≡ ¬ → ∨ ∧ ¯

1. Let V be a vocabulary of ALCI consisting of a role name "P". Interpret part_of as "x is a part of y". Using this role name, define the following formulas in this language:

**(a)  PP that says that x is a proper part of y**  

In mereology, x is a proper part of y when x is a part of y and y is not a part of x (they are not the same entity).

We then need to translate this sentence into DL: PPxy = Pxy ^ ~Pyx

(x,y): PP=(x,y): P ⊓ ¬P¯

**PP ≡ P ⊓ ¬P¯**

This reads something like: a proper part between x and y exists iff x is part of y and it is not the case that the inverse parthood relation (whole) holds between x and y.
  
**(b)  iPP that says that y is a proper part of x**  

This question is asking us to write out the inverse of PP. We have established PP in (a).

**iPP ≡ PP¯ =>
  iPP ≡ (P ⊓ ¬P¯)¯**

**iPP ≡ ¬P ⊓ P¯**

These two are equivalent.
  
**(c)  iP that says that y has x as part**  

**iP ≡ P¯**

**(d)  O that says that x overlaps y**

In mereology, x overlaps y iff x and y have a part which is the same (they have a thing in common). Even if the part is just x or y. 

We need to translate this sentence into DL: Oxy = ∃z.(Pzx ^ Pzy)

**O ≡ ∃P¯.(∃P)
  O ≡ ∃iP.(∃P.T)**

**(e)  D that says that x and y are disjoint**

**D ≡ ¬O**

2. Use your axioms from question 1 as the basis of an ALCI T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a _model_ of K. This may be graphical or symbolic or both. 

3. Translate the following first-order logic axioms into ALCI: 

**(a) ∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))**

**∃R.(∀R.T) ⊓ ∀R.T**

Remember ∀x∃y(R(x,y)∧Cy) is translated into ∃R.C. So we don’t need to deal with the first quantifier ∀x in translating the formula (a). Now we have only two variables in our translation: ∃y and ∀z.

“∃R.(∀R.T)” is to deal with y, meaning that x has a R-successor y (which is “∀x∃yR(x,y)” says), and y can have any R-successor (which is “∀x∀zR(y,z)” says).

 “∀R.T“ is to deal with z, just meaning that x can have any R-successor (which is “∀x∀zR(x,z)” says).

**(b) ∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))**

Given that DL has an implicit universal quantifier at the beginning, here we decided to start from y as the subject of the formula, which is universally quantified. Given y is fixed, then we should do some work such that x and z are successors of y, whatever relation is between them. 

But we know x in R(x,y) is a predecessor but not successor of y, so we want to inverse this part to R¯(y, x). In this way, we get what we want: x is a R¯-successor of y.

R(x,y) = R¯(y,x)

∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))=>
∃x∀y∃z(R¯(y,x) ∧ R(x,z) ∧ R(y,z))  

**∃R¯.(∃R.⊤) ⊓ ∃R.⊤**

“∃R¯.(∃R.⊤)” is to deal with x and its relation to y
“∃R.⊤” is to deal with z and its relation to y

**(c) ∀y(R(x, y) → ∃x(R(y, x) ∧ ∀y(R(x, y) → A(y))))**

**∀R.∃R.∀R.A**

The inner variable “y” is closed under the outermost quantifier “∀” has to be calculated, this variable falls outside its scope. The DL translation falls in the same order with the closed variable “y” at the front.

**(d) (∀y)(R(x, y) → A(y)) ∧ (∃y)(R(x, y) ∧ B(y))**

**(∀R.A) ⊓ (∃R.B)**

Each appearance of variable “y” is closed inside the scope of a different quantifier. For this reason, it does not fall inside the scope of the other quantifier.

4. Provide an interpretation I<sub>1</sub> for ALC and an interpretation I<sub>2</sub> for ALCN - each distinct from any interpretation covered in class so far - and construct a bisimulation that demonstrates ALCN is more expressive than ALC. Use the [mermaid syntax](https://github.com/mermaid-js/mermaid) of markdown to provide a graphical representation of your work. Feel free to use the [mermaid live editor](https://mermaid.live/) when diagramming. 

P = Professor

P ⊓ ∃R.T (ALC interpretation cannot distinguish between numbers of successors)

P ⊓ ≥ 2R.T(ALCN Interpretation)
P ⊓ ≥ 3R.T(ALCN Interpretation)

ΔI1 = {Dr. Beverley, PHI 697, PHI 329, Tuesday Workshop}

Named IndividualsI:
Dr. BeverleyI = B
PHI 697I = 697
PHI 329I = 329
Tuesday WorkshopI = W

Role Assignments:
t = {(B, 697), (B, 329), (B, W)}


ΔI2 = {Dr. Beverley, PHI 697, PHI 329}

Named IndividualsI:
Dr. BeverleyI2 = B2
PHI2 697I = 697-2
PHI 329I = 329-2

Role Assignments:
t2 = {(B2, 697-2),  (B, 329-2)}

Bisimulation:

ρ = {(B, B2), (697, 697-2), (329, 329-2)}

So B is bisimilar to B2. But we can distinguish them in ALCN by defining the role t as
≥2 ∃t.⊤
in I1
≥1 ∃t2.⊤
in I2

[![](https://mermaid.ink/img/pako:eNqNkDELgkAYhv_K8S0Z6KBCoUND2NIUJDR0DR_eVyd6npxnIdp_74KGaKje6R2eB17eEQotCFI41_pWSDSW5RlvmEsWHrdaNmxNVzL1cGJBsGKTJSwkdRPbhN5OlotkOf8Pj554HCV_4rGX99QJHNhBm6qTunXiS42-q7PPZb_4t2nggyKjsBTuk_Hpc7CSFHFIXRVoKg68uTsOe6v3Q1NAak1PPvStQEtZiReDCtIz1h3dH3_hcFQ?type=png)](https://mermaid.live/edit#pako:eNqNkDELgkAYhv_K8S0Z6KBCoUND2NIUJDR0DR_eVyd6npxnIdp_74KGaKje6R2eB17eEQotCFI41_pWSDSW5RlvmEsWHrdaNmxNVzL1cGJBsGKTJSwkdRPbhN5OlotkOf8Pj554HCV_4rGX99QJHNhBm6qTunXiS42-q7PPZb_4t2nggyKjsBTuk_Hpc7CSFHFIXRVoKg68uTsOe6v3Q1NAak1PPvStQEtZiReDCtIz1h3dH3_hcFQ)

5. Provide an interpretation I<sub>1</sub> for ALC and an interpretation I<sub>2</sub> for ALCN - each distinct from any interpretation covered in class so far - and construct a bisimulation that _does not_ demonstrate ALCN is more expressive than ALC. Use the [mermaid syntax](https://github.com/mermaid-js/mermaid) of markdown to provide a graphical representation of your work. Feel free to use the [mermaid live editor](https://mermaid.live/) when diagramming. 

These graphical representations do not demonstrate that ALCN is more expressive than ALC.

[![](https://mermaid.ink/img/pako:eNqNjzELwjAQhf9KuEWFOrSC0g4OUhcnQTfjcCSnKTaJxFQpbf-7KXUQB_VNx_F9PF4DwkqCDE6lfQiFzrN9zg0LyePDxirDVnQnV9ZHNp0uWesJhaJby9bxeKuKebqY_IcnPT5L0gHn5mUl363RZ8sv_q0GItDkNBYy7Gt6n4NXpIlDFk6J7sKBmy5wWHm7q42AzLuKIqiuEj3lBZ4d6uHZPQFU2F5C?type=png)](https://mermaid.live/edit#pako:eNqNjzELwjAQhf9KuEWFOrSC0g4OUhcnQTfjcCSnKTaJxFQpbf-7KXUQB_VNx_F9PF4DwkqCDE6lfQiFzrN9zg0LyePDxirDVnQnV9ZHNp0uWesJhaJby9bxeKuKebqY_IcnPT5L0gHn5mUl363RZ8sv_q0GItDkNBYy7Gt6n4NXpIlDFk6J7sKBmy5wWHm7q42AzLuKIqiuEj3lBZ4d6uHZPQFU2F5C)

Named IndividualsI:
Dr. BeverleyI = B
PHI 697I = 697
PHI 329I = 329
Tuesday WorkshopI = W

Role Assignments:
t = {(B, 697), (B, 329), (B, W)}


ΔI2 = {Dr. Beverley, PHI 697, PHI 329}

Named IndividualsI:
Dr. BeverleyI2 = B2
PHI2 697I = 697-2
PHI 329I = 329-2

Role Assignments:
t2 = {(B2, 697-2),  (B, 329-2)}

Bisimulation:

ρ = {(B, B2), (697, 697-2), (329, 329-2)}

So B is bisimilar to B2. But we can distinguish them in ALCN by defining the role m as
≥2 ∃t.⊤
in I1
≥1 ∃t2.⊤
in I2



6. Explain the difference - using natural language - between the description logic expressions:
  ```
  (a) ∃r.C and ∀r.C
  (b) ∃r-.C and ∀r-.C
  (c) <=nr and <=nr.C
  (d) ∃r-.C and ∃r-.{a} 
```
**(a) ∃r.C and ∀r.C**  

  The first one reads: there is a thing r-related to all xs, and this thing falls under concept C
  The second one reads: if there is a thing r-related to all xs, this thing falls under concept C
  
**(b) ∃r-.C and ∀r-.C**  

  The first one reads: there is a thing r-related to all xs, and this thing falls under the reverse of concept C
  The second one reads: if there is a thing r-related to all xs, this thing falls under the reverse of concept C
  
**(c) <=nr and <=nr.C**  

  The first one reads: role r connects all the xs to no more than n elements.
  The second one reads: role r connects all the xs to no more than n elements, and they fall under concept C.
  
**(d) ∃r-.C and ∃r-.{a}**  

  The first one reads: for all xs, there is at least a thing y, which is C-reverse related to it, and which falls under concept C.
  The second one reads: for all xs, there is element a, which is C-reverse related to it.

7. There is a delightfully helpful subreddit called "ELI5" which stands for something like "explain it like I'm 5" where users post conceptually challenging questions and other users attempt to provide explanations in simple, jargon-free, terms that presumably a 5 year-old could understand. Using this as a model, explain the _finite model property_. Be sure to provide a simple example and explain when the property might be important, and when it is not so important. 

**EL15** (I will come back to this and revise!)

The finite model property means that if you want to prove something in a game or puzzle, you don't have to use too many toys or blocks, just a few of them will be enough. This makes it easier to solve the game or puzzle and saves time.

Imagine you have a game with two toy animals, a cat and a dog. The rules of the game are that the cat is always hungry, and the dog is always friendly. You want to prove that if the cat is hungry, then the dog is not hungry.

One way to prove this would be to use all the possible combinations of hunger and friendliness for the cat and the dog, which would require an infinite number of possibilities. Infinite is the biggest number ever that never ends! It goes on forever! But because the game has the finite model proper

**Finite Model Property** (Full explanation)

The finite model property is a property of a logical system or a formal language that means that every sentence that is true in all models of the system or language is also logically equivalent to a sentence that is true in some finite model of the system or language.

In other words, a logical system or formal language has the finite model property if every true sentence can be proved using only a finite number of objects or elements, rather than requiring an infinite number of objects. This is a desirable property for logical systems or formal languages, as it allows for more effective and efficient reasoning and proof methods.

The finite model property is closely related to other concepts in logic and computer science, such as decidability and computability. Many important logical systems, such as first-order logic, have the finite model property, while others, such as second-order logic, do not.

**Simplified**

The finite model property means that if something is true in a logical system or language, it can be shown to be true using only a finite number of objects or elements, instead of needing an infinite number. This makes reasoning and proving things more efficient and effective.

8. Following up on the preceding , explain the _tree model property_. Be sure to provide a simple example and explain when the property might be important, and when it is not so important.

**EL15** (I will come back to this and revise!)

Imagine you have a toy with lots of buttons and levers. When you press a button or pull a lever, the toy changes in some way. The finite tree model is like a picture of all the different ways the toy can change.

Each picture shows the toy in a different state, with some buttons and levers pressed and others not pressed. The lines between the pictures show how the toy changes when you press a button or pull a lever.

By looking at all the pictures together, you can see all the different ways the toy can change, and how it changes from one state to another. This can help you understand how the toy works and how to use it.

In the same way, the finite tree model helps people understand how programs and processes work by showing all the different ways they can change and how they change from one state to another.

An example:Imagine you're playing a game where you have to guess a number between 1 and 10. The game will tell you if your guess is too high or too low, and you have to keep guessinguntil you get the right answer.

We can represent this game as a finite tree model. The starting point is when you make your first guess, which is like the "root" of the tree. Depending on whether your guess is too high or too low, the tree branches off into two different paths.

If your guess is too high, you go down one path where you make a lower guess. If your guess is too low, you go down the other path where you make a higher guess. 

This branching continues until you finally guess the right number, which is like reaching a "leaf" node in the tree.

By using the finite tree model to represent the guessing game, we can see all the different possible paths that the game can take, and how the game progresses from one guess to the next.

In the same way, the finite tree model helps people understand how programs and processes work by showing all the different ways they can change and how they change from one state to another.


9. Open the Protege editor and create object properties for each of the role names that you constructed in question 1. You should have at least 6 object properties. Assert in the editor that P is a sub-property of O, that P is transitive, and that O is symmetric. Next, add individuals - a, b, c - to the file and assert that c is part of a and that c overlaps b. Running the reasoner should reveal - highlighted in yellow if you select the individual c - that c overlaps a. Using the discussion in the selections from chapter 4 of the Baader, et. al. text as a guide, explain how the tableau algorithm is generating this inference. Also, provide a screenshot of the results of your reasoner run with c highlighted. 

**For some reason, there is a bug on the most recent Protege version for MacOs users, which is not allowing me to open the application. I am still working on this one, but I should have it completed over the next week!**

10. Following up on your work in question 9, adjust/add/remove/etc. object properties and individuals in your Protege file so that when you run a reasoner in Protege, you return the following consequences: 
```
  (a) a is a proper part of b and disjoint from e
  (b) a overlaps c
  (c) a is part of b, b is part of f, and a is part of f
  (e) There are no parts between a and g in common
```
Provide a screenshot of your results here.

**For some reason, there is a bug on the most recent Protege version for MacOs users, which is not allowing me to open the application. I am still working on this one, but I should have it completed over the next week!**
