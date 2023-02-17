# Project 2

Your first project will require you to answer each of the 10 questions below.  You will be expected to open a pull request with your initial answers by the second class meeting, giving you one week to work on these problems. You and your peers will then have one week to work together to refine your respective initial answers, so they are ready for final submission. Once your pull requests have been reviewed and merged to the development branch, I will review them, then merge to the master branch. 

```Tip #1: Carefully study the Baader, et. al. selections assigned on bisimulation; it is deceptively subtle, and quite powerful. 
Tip #2: Google is still your friend. So is stackexchange...
Tip #3: Work _together_ to solve these problems, even for initial submissions and when you do, document this in github. 
Tip #4: Work together _as a team_. 
```

1. Let V be a vocabulary of ALCI consisting of a role name "P". Interpret part_of as "x is a part of y". Using this role name, define the following formulas in this language:
  (a)  PP that says that x is a proper part of y
  (a) Not definable 
  
  (b) iPP that says that y is a proper part of x
  (b) Not deinable 
  
  (c) iP that says that y has x as part 
  (c) iP ≡ ∀part_of-.
   
  (d)  O that says that x overlaps y
  (d)  not definable 
  
  (e)  D that says that x and y are disjoint 
  (e)  not definable 
  
2. Use your axioms from question 1 as the basis of an ALCI T-Box. Supplement this T-box with whatever other axioms you like, as well as an A-box, so that you ultimately construct a knowledge base K = (T,A). Provide a model of K. This may be graphical or symbolic or both.

TBox:

3. Translate the following first-order logic axioms into ALCI:

(a) ∀x∃y∀z(R(x,y) ∧ R(x,z) ∧ R(y,z))
(a)

(b) ∃x∀y∃z(R(x,y) ∧ R(x,z) ∧ R(y,z))
(b)

(c) ∀y(R(x, y) → ∃x(R(y, x) ∧ ∀y(R(x, y) → A(y))))
(c)

(d) (∀y)(R(x, y) → A(y)) ∧ (∃y)(R(x, y) ∧ B(y))
(d)

4. Provide an interpretation I1 for ALC and an interpretation I2 for ALCN - each distinct from any interpretation covered in class so far - and construct a bisimulation that demonstrates ALCN is more expressive than ALC. Use the mermaid syntax of markdown to provide a graphical representation of your work. Feel free to use the mermaid live editor when diagramming.



5. Provide an interpretation I1 for ALC and an interpretation I2 for ALCN - each distinct from any interpretation covered in class so far - and construct a bisimulation that does not demonstrate ALCN is more expressive than ALC. Use the mermaid syntax of markdown to provide a graphical representation of your work. Feel free to use the mermaid live editor when diagramming.



6. Explain the difference - using natural language - between the description logic expressions:

I will make the assumption (if allowed) the Role is Biological Parent of. and C is the concept Capricorn child
I will assume {a} to be Donnie
⊔ ⊓ ⊧ ⊭ ⊦ ⊬ ⊏ ⊐ ⊑ ⊒ C ¬ ≡ ≠ ≥ ≤ ∃ ∀

(a) ∃r.C and ∀r.C

(a) ∃ParentOf.Capricorn: Things that are biological parents of Capricorns

(a) ∀ParentOf.Capricorn: All biological parents of Capricorns 

(b) ∃r-.C and ∀r-.C

(b) ∃r-.C and ∀r-.C∃ParentOf-.Capricorn: Things that are biological children of parents are Capricorns 

(b) ∀ParentOf-.ParentedCapricorn: All things that are biological children of parents are Capricorns

(c) <=nr and <=nr.C

(c) at most n Parent of

(c) at most n ParentOf.Capricorn: There is at most n of things that are parents of Capricorn children

(d) ∃r-.C and ∃r-.{a} 

(d) ∃ParentOf-.Capricorn: Things that are biological children are Capricorns

(d) ∃ParentOf-.Donnie: Things that are biological children of Donnie are Capricorns

7. There is a delightfully helpful subreddit called "ELI5" which stands for something like "explain it like I'm 5" where users post conceptually challenging questions and other users attempt to provide explanations in simple, jargon-free, terms that presumably a 5 year-old could understand. Using this as a model, explain the finite model property. Be sure to provide a simple example and explain when the property might be important, and when it is not so important.

Answer to 7. First to define some terms, Attributive (Concept) Language with Complements is what ALC stands for -- a concept is an idea or general notion. A TBox is a set of included statements that relate to some thing, which provides a limitation for that statement. Finite means it has limits and infinite means to be limitless.  A finite model property in ALC is what makes a model, which cannot be forced to have limits (or be finite), unable to be limitless (or infinite). This is to say, a concept model will have the finite model property if the concept is able to be modeled with a TBox as the TBox allows us to determine and define the size of the finite model. This is possible because not only can we define specific concepts in a TBox but we can also define the concepts that support that concept, we call these subconcepts. Consider the concept of the color green, green also contains the subconcepts of the colors blue and yellow. This is because the mixture of blue and yellow creates the color green -- this is to say, the concept green in supported by subconcepts green and yellow. Following the model a TBox for the one concept green would include the subconcepts blue and yellow adn by conrast would not include the color red, purple, or black. 

8. Following up on the preceding , explain the tree model property. Be sure to provide a simple example and explain when the property might be important, and when it is not so important.

Answer to 8. 

9. Open the Protege editor and create object properties for each of the role names that you constructed in question 1. You should have at least 6 object properties. Assert in the editor that P is a sub-property of O, that P is transitive, and that O is symmetric. Next, add individuals - a, b, c - to the file and assert that c is part of a and that c overlaps b. Running the reasoner should reveal - highlighted in yellow if you select the individual c - that c overlaps a. Using the discussion in the selections from chapter 4 of the Baader, et. al. text as a guide, explain how the tableau algorithm is generating this inference. Also, provide a screenshot of the results of your reasoner run with c highlighted.

10. Following up on your work in question 9, adjust/add/remove/etc. object properties and individuals in your Protege file so that when you run a reasoner in Protege, you return the following consequences:

  (a) a is a proper part of b and disjoint from e
  
  (b) a overlaps c
  
  (c) a is part of b, b is part of f, and a is part of f
  
  (e) There are no parts between a and g in common
  
Provide a screenshot of your results here.
