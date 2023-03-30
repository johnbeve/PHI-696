**The SPARQL Library of Buffalo**

[Codewars](https://www.codewars.com/dashboard) is a website designed to facilitate algorithmic training for various programming languages. Users supply problem statements and others provide coding solutions to those problems. For example, you might find a problem for Python such as: 

```
Define a function that returns the length of a given string. 
```

With a solution like: 

```
def length_of_string(s):
	return len(s)
```
	
Codewars is not limited to traditional programming languages like Python, but also facilitates training for languages like SQL. As you have learned, SQL and SPARQL are both query languages, but what might surprise you is that there is currently no option for training SPARQL in Codewars. This project will go some way to remedy that. 

For this project, you will be tasked with constructing SPARQL problems for the codewars site. 

```
Note #1: Completion of this task will not require you to actually have your SPARQL problems successfully posted to codewars. Adding problems to codewars takes more time than we have for this project. Additionally, you are only allowed to add propose problems to codewars if you have a certain amount of experience (specifically, you need 300 of what they call 'honor points', which is acquired by solving problems). At some point, assuming you permit it, I will post your problems to codewars (giving you credit of course). 
Note #2: The potential for this project to directly impact the ontology community is clear. SPARQL can be challenging, and there are few opportunities for drill practice like this. 
Note #3: You will not be required to learn a programming language, though you will likely need to expand your comfort with computer science jargon; if you hit a wall, ask your peers for help; if the wall persists, ask me. 
Note #4: Codewars provides a guidebook - https://docs.codewars.com/authoring/tutorials/create-first-kata/ - for creating problems; I strongly encourage you to read it, since the standard provided there is how I will be evaluating success. 
```
**Assignment Details**

Problems on Codewars are ranked in terms of difficulty. The lowest "kata" - 8 - indicates a rather easy problem, while the highest kata - 1 - indicates a very challenging problem. 

For our purposes, harder kata will be worth more points than easier kata, and you are required to submit enough kata to acquire 100 points according to the following point system: 

  |   **kata**    |  **points**   |
  | ------------- | ------------- |
  |       1       |      35       |
  |       2       |      25       |
  |       3       |      20       |
  |       4       |      10       |
  |       5       |       5       |
  |       6       |       3       |
  |       7       |       2       |
  |       8       |       0       |

You're probably thinking, "why would I submit a level 8 kata if they're not worth any points?" Great question. Because everyone had to submit at least one level 8 kata. Otherwise, you're permitted to submit kata in any distribution you choose. For example, you might submit 2 problems for kata one (70 points), one for kata 3 (20 points), one for kata 4 (10 points), and one for kata 8 (0 points but required). 

It is your responsibility and the responsibility of your peers reviewing your submission in PR to determine whether your submission is ranked appropriately. In the event that consensus is reached that your kata is ranked inappropriately, you must work with your peers to revise the submission so that it is either more or less challenging, accordingly. You are not permitted to submit new problems with different strengths after PRs are open, but must instead revise your PRs. So, think hard about how challenging your submission is. 

There is one other option for those desiring a different sort of challenge. If you provide alongside your SPARQL submission a translation of the same problem into SQL, complete with documentations, solution, etc. then you may receive half points extra at that kata level (rounded up). For example, if you submit a SPARQL problem that is kata rank 1 and also submit a SQL version of that same problem, you  will receive 35+18=53 points. 



___
**Kata Level 8—Who Invented the Buffalo Wing?**

Description (and problem):
There is a dispute about which restaurant invented the Buffalo wing in Buffalo, New York. Using a SPARQL query, retrieve the name of the restaurant who is credited for being the home of the first Buffalo wing. 

Hint: Inventor is not the category name that you should construct your SPARQL query with if using dbpedia.org. That is, dbo:inventor will not retrieve the right result. 

Reference Solution (and answer):

```
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX dbp: <http://dbpedia.org/property/>

SELECT ?creator
WHERE {
  dbr:Buffalo_wing dbp:creator
 ?creator . 
}
```

Answer:

"The Anchor Bar restaurant. Buffalo New York."@en

https://dbpedia.org/sparql?default-graph-uri=http%3A%2F%2Fdbpedia.org&query=PREFIX+dbo%3A+%3Chttp%3A%2F%2Fdbpedia.org%2Fontology%2F%3E%0D%0A%0D%0ASELECT+%3Fcreator%0D%0AWHERE+%7B%0D%0A++%3Chttp%3A%2F%2Fdbpedia.org%2Fresource%2FBuffalo_wing%3E+dbp%3Acreator%0D%0A+%3Fcreator+.%0D%0A%7D%0D%0A&format=text%2Fhtml&timeout=10000&signal_void=on&signal_unconnected=on



___
**Kata Level 7—There Exists Only Buffalo Wings or Nah?**

**Description:**

Another dispute arises between friends while eating Buffalo wings. One Buffalo wing lover proclaimed, “There is only one chicken wing in the world, BUFFALO WINGS!” A friend exclaimed, “Have you ever heard of Nashville Hot Fried Chicken?!”, while yet another said, “What about the other KFC,  Korean Fried Chicken?!” To settle this dispute, you as the burgeoning SPARQL queryist will create a SPARQL query to (1) determine whether it is true or false that there are multiple kinds of ways to cook chicken wings than merely Buffalo wings and (2) if it is true that there are differently cooked chicken wings, retrieve a list of those chicken wings. 

Hint: You must use both the ASK and SELECT query forms and your ASK request must result in “true”.

**Reference Solution:**

```
PREFIX ex: <http://example.org/food/>
PREFIX ex: <http://example.org/chickenWing/>
PREFIX ex: <http://example.org/cookingMethod/>

ASK {
  ?chickenWing ex:food ;
               ex:type ex:chickenWing ;
               ex:cookingMethod ?cookingMethod .
  {
    SELECT DISTINCT ?cookingMethod  
    WHERE {
      ?chickenWing ex:cookingMethod ?cookingMethod .
    }
  }
  HAVING (COUNT(DISTINCT ?cookingMethod) > 1)
}
```



___
Kata Level 6--  
