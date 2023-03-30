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
**[1] Kata Level 8 (0 pts, total pts accrued: 0pts): Who Invented the Buffalo Wing?**

Description (and problem):

```
There is a dispute about which restaurant invented the Buffalo wing in Buffalo, New York. Using a SPARQL query, retrieve the name of the restaurant who is credited for being the home of the first Buffalo wing. 

Hint: Inventor is not the category name that you should construct your SPARQL query with if using dbpedia.org. That is, dbo:inventor will not retrieve the right result. 
```

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
**[2] Kata Level 7 (2 pts, total pts accrued: 2pts): There Exists Only Buffalo Wings or Nah?**

**Description:**

```
Another dispute arises between friends while eating Buffalo wings. One Buffalo wing lover proclaimed, “There is only one chicken wing in the world, BUFFALO WINGS!” A friend exclaimed, “Have you ever heard of Nashville Hot Fried Chicken?!”, while yet another said, “What about the other KFC,  Korean Fried Chicken?!” To settle this dispute, you as the burgeoning SPARQL queryist will create a SPARQL query to (1) determine whether it is true or false that there are multiple kinds of ways to cook chicken wings than merely Buffalo wings and (2) if it is true that there are differently cooked chicken wings, retrieve a list of those chicken wings. 

Hint: You must use both the ASK and SELECT query forms and your ASK request must result in “true”.
```

**Reference Solution:**

```
PREFIX ex: <http://example.org/food/>
PREFIX ex2: <http://example.org/chickenWing/>
PREFIX ex3: <http://example.org/cookingMethod/>

ASK {
  ?chickenWing ex:food ;
               ex2:type ex2:chickenWing ;
               ex3:cookingMethod ?cookingMethod .
  {
    SELECT DISTINCT ?cookingMethod  
    WHERE {
      ?chickenWing ex3:cookingMethod ?cookingMethod .
    }
  }
  HAVING (COUNT(DISTINCT ?cookingMethod) > 1)
}
```



___

**Theme: Enter the Dōjō: Master the Basics of SPARQL Series**
___

**[3] Kata Level 6 (3 pts, total pts accrued: 5 pts): Enter the Dōjō: SPARQL’s Four Query Forms (1)**

**Description:**

```
You are a beginning SPARQL queryist and must learn the first four basic SPARQL query forms. These four query forms will lay the foundation of your query artistry. Construct one SPARQL query that utilizes all four SPARQL query forms: SELECT, CONSTRUCT, ASK, and DESCRIBE. 

Hint: You may query any data set. However, the four query forms must be used on the same data set.

1.	Run SELECT queries when you want to find and return all of the data that matches certain patterns.
2.	Run CONSTRUCT queries when you want to create or transform data based on the existing data.
3.	Run ASK queries when you want to know whether a certain pattern exists in the data. ASK queries return only "true" or "false" to indicate whether a solution exists.
4.	Run DESCRIBE queries when you want to view the RDF graph that describes a particular resource.
```

**Reference Solution:**

```
PREFIX ex: < http://example.org/ontology/>
PREFIX ex2: < http://example.org/chicken_wing/>>

SELECT ?cuisine 
WHERE {
  ?cuisine ex:type ex2:Chicken_wings .
}

CONSTRUCT {
  ?cuisine ex:isPartOf ?region .
}

WHERE {
  ?cuisine ex:type ex2:Chicken_wings .
  ?cuisine ex:isPartOf ?region .
}

ASK {
  ?cuisine ex:type ex2:Chicken_wings .
  FILTER NOT EXISTS {
    ?cuisine ex:genre ?genre .
    FILTER (?genre != ex2:Chicken_wing)
  }
}

DESCRIBE ?cuisine ?region 
WHERE {
  ?cuisine ex:type ex2:Chicken_wings .
  ?cuisine ex:isPartOf ?region .
}

**Explanation of the query:**

This query attempts to retrieve all chicken wing cuisine styles in order to construct a new data set which relates chicken wing cuisine styles to their respective regions of origin. The following is a description of each query form and their specific functions for this query.

1.	The first SELECT query retrieves all cuisines that have the type Chicken_wings.
2.	The CONSTRUCT query constructs a new data set by adding the dbo:isPartOf property to each cuisine. This property relates each cuisine to its region.
3.	The ASK query checks whether all the retrieved cuisines have the genre Chicken_wing. If there exists a cuisine that has a genre other than Chicken_wing, the query returns false. Otherwise, it returns true.
4.	The DESCRIBE query describes the cuisines and their regions by retrieving all the properties of each cuisine and its region.
```



___

**[4] Kata Level 6 (3 pts, total pts accrued: 8 pts): Enter the Dōjō: SPARQL’s Four Query Clauses (Series 2)**

**Description:**

```
If you completed the first stage of Enter the Dōjō, well done! You are well on your way to becoming proficient in the SPARQL foundational basics. Let us continue our training. 

You are a beginning SPARQL queryist and must now learn the four basic SPARQL query clauses. These four query clauses will lay the foundation of your query artistry and act as “defensive” moves, i.e. action-delimiting tools. Construct one SPARQL query that utilizes all four SPARQL query clauses: the PREFIX, result, FROM, and WHERE clauses. Note: within the range of capacity of the WHERE clause, there are seven additional conditional clauses that you may use. However, for our purposes, as we are beginning SPARQL queryists, use FILTER and UNION in this query also. 

Hint: You may query any data set. However, the four query clauses and the two additional FILTER and UNION clauses must be used on the same data set.

1.	The optional PREFIX clause declares the abbreviations that you want to use to reference URIs in the query.
2.	The required result clause specifies the type of query and defines the data that the query should return (identified in the SELECT section)
3.	The optional FROM clause defines the data sets or graphs to query.
4.	The required WHERE clause defines the data that the query operates against.
5.	FILTER applies boolean conditions or tests to constrain results and filter out values that do not meet the specified conditions.
6.	UNION includes results from either of two graph patterns. Solutions to both sides of the union are included in the results.
(1-6 Cited from Cambridge Semantics:  https://docs.cambridgesemantics.com/anzograph/v2.2/userdoc/query-clauses.htm)
```

**Reference Solution:**

```
PREFIX ex: < http://example.org/ontology/>
PREFIX ex2: < http://example.org/chicken_wing/>

SELECT ?cuisineLabel 
FROM < http://example.org>
WHERE {
  {
    SELECT ?cuisine 
WHERE {
      ?cuisine rdf:type ex:Food .
      ?cuisine ex:type ex2:Chicken_wings .
    }
  }
  UNION
  {
    SELECT ?cuisine 
WHERE {
      ?cuisine rdf:type ex:Food .
      ?cuisine ex:type ex2:Chicken_thighs .
    }
  }
  ?cuisine rdfs:label ?cuisineLabel .
  FILTER (langMatches(lang(?cuisineLabel), "en"))
}

**Explanation of the query:**

This query attempts to retrieve all chicken wing and chicken thigh cuisine styles by utilizing the four primary query clausesThe following is a description of each query form and their specific functions for this query.

1.	The PREFIX declarations define two example prefixes as URIs.
2.	The result clauses identified on the SELECT lines retrieves the English labels of all chicken wing and chicken thigh cuisines.
3.	The FROM clause specifies the data source for the query. In this case, we're querying http://example.org.
4.	The WHERE clause specifies the conditions that the resources must satisfy. We use two sub-queries, one for chicken wing cuisines and one for chicken thigh cuisines, and then UNION the results. Each sub-query retrieves any resources that have the type ex:Food and either the ex2:Chicken_wings or ex2:Chicken_thighs type, respectively.
5.	The FILTER clause filters the results to only include the English labels.
```



___

**[5] Kata Level 5 (5 pts, total pts accrued: 13 pts): Enter the Dōjō: SPARQL’s Seven WHERE Condition Clauses (Series 3)**


