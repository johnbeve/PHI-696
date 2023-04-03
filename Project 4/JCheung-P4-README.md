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

**Summary of Project #4:**

**12 Kata Total (potential points accrued: 103 or 113 pts): 1 kata lvl 8, 1 kata lvl 7, 2 kata lvl 6, 3 kata lvl 5, 2 kata lvl 4, 1 kata lvl 3, 2 kata lvl 3 or lvl 2.**

```
**Outline of Project #4:**
1. Kata Level 8
2. Kata Level 7 
3. Theme: Enter the Dōjō: Master the Basics of SPARQL Series (7 kata total)
4. Theme: SPARQL for Research and Problem Solving Series (3 kata total)
```

Note #1: The reference solutions for kata #1-#9 are all given in relation to primarily chicken, with some solutions also pertaining to turkey and beef. Although the author of these SPARQL queries does indeed love chicken (especially wings) and food in general, this was done to showcase the wide range of query capacities that SPARQL offers. The author apologizes in advance if readers get either tired of or hungry reading about chicken and its many varieties.

Note #2: The Enter the Dōjō: Master the Basics of SPARQL Series was written with beginning and intermediate SPARQL users in mind. It was designed to give scaffolded kata challenges, comprehensive in scope and sequential in order, beginning from the first stage of learning SPARQL. In essence, this series was designed to be an educational experience covering the foundational basics of SPARQL, as well as some of the foundational intermediate level tools (i.e. data update and aggregrate functions). 

Note #3: The order of the kata generally ascend in level of difficuly throughout the project and was meant to be scaffolded as such. 

Note #4: The SPARQL for Research and Problem Solving Series was meant to demonstrate SPARQL's research and problem solving capacities. 

Note #5: Most of the prefixes, i.e. URIs, are example placeholder addresses. Moreover, even when actual URIs are used, most of the time, for chicken wings, and the following food related queries in general, the data sets are incomplete or lacking. As such, though the reference solutions may not have the right data sets to extract the pertinent information, the syntax of each reference solution, I take, is the primary focus. 

Thank you for taking the time to review my Project #4! My sincerest regards and best wishes. 

___
**[1] Kata Level 8 (0 pts, total pts accrued: 0pts): Who Invented the Buffalo Wing?**

**Description (and problem):**

There is a dispute about which restaurant invented the Buffalo wing in Buffalo, New York. Using a SPARQL query, retrieve the name of the restaurant who is credited for being the home of the first Buffalo wing. 

Hint: Inventor is not the category name that you should construct your SPARQL query with if using dbpedia.org. That is, dbo:inventor will not retrieve the right result. 

**Reference Solution (and answer):**

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

Another dispute arises between friends while eating Buffalo wings. One Buffalo wing lover proclaimed, “There is only one chicken wing in the world, BUFFALO WINGS!” A friend exclaimed, “Have you ever heard of Nashville Hot Fried Chicken?!”, while yet another said, “What about the other KFC,  Korean Fried Chicken?!” To settle this dispute, you as the burgeoning SPARQL queryist will create a SPARQL query to (1) determine whether it is true or false that there are multiple kinds of ways to cook chicken wings than merely Buffalo wings and (2) if it is true that there are differently cooked chicken wings, retrieve a list of those chicken wings. 

Hint: You must use both the ASK and SELECT query forms and your ASK request must result in “true”.

**Reference Solution:**

```
PREFIX ex: <http://example.org/food/>
PREFIX ex2: <http://example.org/chickenWing/>
PREFIX ex3: <http://example.org/cookingMethod/>

ASK {
  ?chickenWing ex:food ;
               ex2:type ex2:chickenWing ;
               ex3:cookingMethod ?cookingMethod .
    }
  HAVING (COUNT(DISTINCT ?cookingMethod) > 1
  }
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

**[3] Kata Level 6 (3 pts, total pts accrued: 5 pts): Enter the Dōjō—Beginner: SPARQL’s Four Query Forms (1)**

**Description:**

You are a beginning SPARQL queryist and must learn the first four basic SPARQL query forms. These four query forms will lay the foundation of your query artistry and act as “offensive” moves, i.e. action-forward tools. 

**Construct one SPARQL query that utilizes all four SPARQL query forms: SELECT, CONSTRUCT, ASK, and DESCRIBE.**

```
Hint: You may query any data set. However, the four query forms must be used on the same data set.

1. Run SELECT queries when you want to find and return all of the data that matches certain patterns.
2. Run CONSTRUCT queries when you want to create or transform data based on the existing data.
3. Run ASK queries when you want to know whether a certain pattern exists in the data. ASK queries return only "true" or "false" to indicate whether a solution exists.
4. Run DESCRIBE queries when you want to view the RDF graph that describes a particular resource.

(1-4 Cited from Cambridge Semantics: https://docs.cambridgesemantics.com/anzograph/v2.5/userdoc/sparql-queries.htm)
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

**[4] Kata Level 6 (3 pts, total pts accrued: 8 pts): Enter the Dōjō—Beginner: SPARQL’s Four Query Clauses (2)**

**Description:**

If you completed the first stage of Enter the Dōjō, well done! You are well on your way to becoming proficient in the SPARQL foundational basics. Let us continue our training. 

You are a beginning SPARQL queryist and must now learn the four basic SPARQL query clauses. These four query clauses will lay the foundation of your query artistry and act as “defensive” moves, i.e. action-delimiting tools. 

**Construct one SPARQL query that utilizes all four SPARQL query clauses: the PREFIX, result, FROM, and WHERE clauses. Note: within the range of capacity of the WHERE clause, there are seven additional conditional clauses that you may use. However, for our purposes, as we are beginning SPARQL queryists, use FILTER and UNION in this query also.**

```
Hint: You may query any data set. However, the four query clauses and the two additional FILTER and UNION clauses must be used on the same data set.

1. The optional PREFIX clause declares the abbreviations that you want to use to reference URIs in the query.
2. The required result clause specifies the type of query and defines the data that the query should return (identified in the SELECT section)
3. The optional FROM clause defines the data sets or graphs to query.
4. The required WHERE clause defines the data that the query operates against.
5. FILTER applies boolean conditions or tests to constrain results and filter out values that do not meet the specified conditions.
6. UNION includes results from either of two graph patterns. Solutions to both sides of the union are included in the results.

(1-6 Cited from Cambridge Semantics: https://docs.cambridgesemantics.com/anzograph/v2.5/userdoc/sparql-queries.htm)
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

**[5] Kata Level 5 (5 pts, total pts accrued: 13 pts): Enter the Dōjō—Beginner: SPARQL’s Seven WHERE Condition Clauses (3)**

**Description:**

If you completed the second stage of Enter the Dōjō, good work! You are on your way to becoming proficient in the SPARQL query foundational basics! Let us continue our training.

You are a beginning SPARQL queryist who has learned the four “offensive”, i.e. action-forward, query forms and the four “defensive”, i.e. action-delimiting query clauses. However, the WHERE query clause itself has seven different condition clauses that can delimit a query.

**Here is the challenge: Construct a query with the seven WHERE condition clauses: BIND, FILTER, MINUS, OPTIONAL, SERVICE, UNION, and VALUES.**

These are essentially seven “defensive” moves, i.e. delimiting conditions, for your query. 

To be a true master SPARQL queryist, you must be creative. Think innovatively in using all seven WHERE condition clauses in one query.

```
Hint: You may query any data set, but the data set(s) must be related to the aims of the overall query. 

1. BIND: Assigns the results of an expression to a new variable.
2. FILTER: Applies boolean conditions or tests to constrain results and filter out values that do not meet the specified conditions.
3. MINUS: Subtracts matches from the result based on the evaluation of the pattern that you specify.
4. OPTIONAL: Tries to match a graph pattern but does not fail to return results if the optional match fails.
5. SERVICE: Queries remote data at a SPARQL endpoint.
6. UNION: Includes results from either of two graph patterns. Solutions to both sides of the union are included in the results.
7. VALUES: Enables users to include data in a graph pattern to filter results on more specific requirements. The data is joined with the results of the query evaluation.

(1-7 Cited from Cambridge Semantics: https://docs.cambridgesemantics.com/anzograph/v2.5/userdoc/where.htm)
```

**Reference Solution:**

```
PREFIX ex: < http://example.org/ontology/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>

SELECT ?chickenPart
WHERE {
  {
    SELECT ?chickenCuisine
    WHERE {
      ?chickenCuisine a ex:ChickenDish.
    }
    SERVICE <https://query.wikidata.org/sparql> {
      ?chickenCuisine wdt:P31/wdt:P279* wd:Q27994917.
      ?chickenCuisine rdfs:label ?label.
      FILTER(lang(?label) = "en").
    }
  }
  OPTIONAL {
    ?chickenCuisine dbp:mainIngredient ?ingredient.
    ?ingredient rdfs:label ?ingredientLabel.
    FILTER(lang(?ingredientLabel) = "en").
    {
      MINUS {
        ?ingredient wdt:P279 wd:Q873716.
      }
      MINUS {
        ?ingredient wdt:P279 wd:Q104664167.
      }
    }
    FILTER(?ingredientLabel IN ("chicken wings", "chicken thighs", "chicken legs", "chicken feet")).
    BIND(IF(?ingredientLabel IN ("chicken legs", "chicken feet"), "chickenLegsAndFeet", ?ingredientLabel) AS ?chickenPart).
  }
  VALUES ?chickenPart { "chicken skin" }
  {
    ?chickenCuisine dbp:mainIngredient ?ingredient.
    ?ingredient rdfs:label ?ingredientLabel.
    FILTER(lang(?ingredientLabel) = "en").
    FILTER(?ingredientLabel IN ("chicken wings", "chicken thighs", "chicken legs", "chicken feet")).
    BIND(IF(?ingredientLabel IN ("chicken legs", "chicken feet"), "chickenLegsAndFeet", ?ingredientLabel) AS ?chickenPart).
  } UNION {
    VALUES ?chickenPart { "chicken wings", "chicken thighs", "chicken legs", "chicken feet", "chickenLegsAndFeet" }
  }
}

**Explanation of the query:**

This query attempts to query for a selection of varying chicken cuisine styles as outline below:

1.	The first part of the query selects all chicken cuisine styles from example.org by querying for all instances of the ex:ChickenDish class.
2.	The SERVICE clause is used to query Wikidata for the subclass of "chicken cuisine" (Q27994917) that each selected chicken cuisine style belongs to, as well as its English label.
3.	The OPTIONAL clause is used to query for all ingredients used in each chicken cuisine style. The MINUS clause is used to remove chicken head and chicken gizzard from the results.
4.	The FILTER clause is used to select only the chicken parts that we are interested in (chicken wings, chicken thighs, chicken legs, and chicken feet). If the ingredient label is one of these parts, it is bound to the variable ?chickenPart.
5.	The BIND clause is used to create a new variable ?chickenPart that represents both chicken legs and chicken feet. This is done because later in the query, we will be using a UNION clause to combine all the chicken parts into a single result set, and we want to treat chicken legs and chicken feet as a single category.
6.	The VALUES clause is used to add a new value to the ?chickenPart variable: "chicken skin".
7.	Finally, the UNION clause is used to combine all the chicken parts into a single result set. 
```



___
**[6] Kata Level 5 (5 pts, total pts accrued: 18 pts): Enter the Dōjō—Beginner: SPARQL’s Solution Modifiers Part 1 (4)**

**Description:**

If you completed the third stage of the Enter the Dōjō series, fantastic! You are now ready to begin training with solution modifiers! Let's train!

You are a beginning SPARQL queryist who has learned the four “offensive”, i.e. action-forward, query forms and the four “defensive”, i.e. action-delimiting query clauses, along with the seven WHERE query condition clauses. 

Now we must add optional solution modifiers to our query tool box. Solution modifiers help restrict, group, sort, and further refine query results. They are “techniques” that allow us to execute our solution with specificity. There are five general solution modifiers: ORDER BY, OFFSET, LIMIT, GROUP BY, and HAVING (we will only focus on the first three for this kata). 

**For this challenge, construct a query that queries multiple kinds or parts of an entity from at least two data sets. UNION the queried information and then CONSTRUCT a new graph. Then use the following solution modifiers ORDER BY, OFFSET, and LIMIT in an instrumental way to achieve your aims.** 

To be a true master SPARQL queryist, you must be creative. Think about how solution modifiers can refine your solution to enhance the aims of your query.

```
Hint: You may query any data set, but the data set(s) must be related to the aims of the overall query. 

1. ORDER BY: This modifier sorts the result set in a particular order. It sorts query solutions on the value of one or more variables.
2. OFFSET: Using this modifier in conjunction with LIMIT and ORDER BY returns a slice of a sorted solution set, for example, for paging.
3. LIMIT: This modifier restricts the results to return a certain number of solutions.

(1-3 Cited from Cambridge Semantics: https://docs.cambridgesemantics.com/anzograph/v2.5/userdoc/sparql-queries.htm)
```

**Reference Solution:**

```
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dbpedia: <http://dbpedia.org/resource/>

CONSTRUCT {
  ?food rdf:type ?type .
}
WHERE {
  {
    SELECT DISTINCT ?food ?type
    WHERE {
      <http://dbpedia.org/resource/Chicken_wings> rdf:type ?type .
      ?food rdf:type ?type .
    }
    ORDER BY ?type
    LIMIT 10 OFFSET 0
  }
  UNION
  {
    SELECT DISTINCT ?food ?type
    WHERE {
      <http://dbpedia.org/resource/Turkey_wings> rdf:type ?type .
      ?food rdf:type ?type .
    }
    ORDER BY ?type
    LIMIT 10 OFFSET 0
  }
  ?food rdf:type ?type .
  FILTER (regex(str(?type), "http://dbpedia.org/ontology/Food"))
}
OFFSET 10

**Explanation of the query:**
This query first selects all the different types of chicken wing cuisines from a unique URI and limits the result to 10 items. Then it selects all the different kinds of turkey wing cuisines from a different URI and limits the result to 10 items as well. The results from both data sets are combined using the UNION operator.

Next, a CONSTRUCT clause is used to create a new graph that contains all the food items and their corresponding types. The results are ordered by type, putting the chicken wings first and then the turkey wings second. Ordering by type allows for analysis of each to be streamlined. Finally, the results are offset by 10 on each page for printing purposes.
```



___
**[7] Kata Level 5 (5 pts, total pts accrued: 23 pts): Enter the Dōjō—Beginner: SPARQL’s Solution Modifiers Part 2 (5)**

**Description:**

If you completed the fourth stage of the Enter the Dōjō series, excellent! You will soon be ready to move on to intermediate SPARQL forms! Now, we must continue to Part 2 of learning our solution modifiers techniques.

You are a beginning SPARQL queryist who has learned the four “offensive”, i.e. action-forward, query forms, the four “defensive”, i.e. action-delimiting query clauses, along with the seven WHERE query condition clauses, and the first three solution modifiers from part 1: ORDER BY, OFFSET, and LIMIT.

Now we must add further optional solution modifiers to our query tool box. As we learned, solution modifiers help restrict, group, sort, and further refine query results. They are “techniques” that allow us to execute our solution with specificity. There are five general solution modifiers: ORDER BY, OFFSET, LIMIT, GROUP BY, and HAVING (we will only focus on the latter two for this exercise). 

**For this challenge, write a query that queries at least two data sets. UNION the queried information and then CONSTRUCT a new graph. However, for this exercise you must use the solution modifiers GROUP BY and HAVING to create 10 novel groups. Use these forms, functions, and solution modifiers instrumentally to achieve a clear and established aim.**

To be a true master SPARQL queryist, you must be creative. Think about how the GROUP BY and HAVING solution modifiers can refine your solution to enhance the aims of your query. 

```
Hint: You may query any data sets, but the data sets must be related to the aims of the overall query. Also, consider using FILTER, REGEX, and/or GROUP_CONCAT to help pick out the groups that you want so that you can perform the GROUP BY and HAVING solution modifier. 

1. GROUP BY: This modifier is used with aggregate functions and specifies the key variables to use to partition the solutions into groups. 
2. HAVING: This modifier is used with aggregate functions and further filters the results after applying the aggregates.

(1-2 Cited from Cambridge Semantics: https://docs.cambridgesemantics.com/anzograph/v2.5/userdoc/sparql-queries.htm)
```

**Reference Solution:**

```
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dbpedia: <http://dbpedia.org/resource/>
PREFIX dbo: <http://dbpedia.org/ontology/>

CONSTRUCT {
  ?dish rdf:type ?type .
}
WHERE {
  {
    SELECT DISTINCT ?dish ?type
    WHERE {
      <http://dbpedia.org/resource/Category:Chicken_dishes> dbo:ingredient/(dbo:name) ?ingredient .
      ?dish dbo:ingredient/(dbo:name) ?ingredient ;
            rdf:type ?type .
      FILTER(?ingredient IN ("chicken wings", "chicken breasts", "chicken thighs", "chicken legs", "chicken feet", "chicken head"))
    }
    LIMIT 10 OFFSET 10
  }
  UNION
  {
    SELECT DISTINCT ?dish ?type
    WHERE {
      <http://dbpedia.org/resource/Category:Turkey_dishes> dbo:ingredient/(dbo:name) ?ingredient .
      ?dish dbo:ingredient/(dbo:name) ?ingredient ;
            rdf:type ?type .
      FILTER(?ingredient IN ("turkey wings", "turkey breasts", "turkey thighs", "turkey legs", "turkey feet", “turkey head”))
    }
    LIMIT 10 OFFSET 10
  }
  ?dish rdf:type ?type .
  FILTER (regex(str(?type), "http://dbpedia.org/ontology/Food"))
}
GROUP BY ?dish ?type
HAVING (
  regex(GROUP_CONCAT(DISTINCT ?ingredient; separator=","), "chicken head") 
    || !regex(GROUP_CONCAT(DISTINCT ?ingredient; separator=","), "chicken head")
) ORDER BY ?type

**Explanation of the query:**

This query first selects all the different types of chicken dish cuisines from a unique URI, and all the different kinds of turkey wing cuisines from a different URI. The results from both data sets are then combined using the UNION operator, and a CONSTRUCT clause is used to create a new graph that contains all the dish items and their corresponding types. The results are then grouped by dish and type.
The solution modifier HAVING is used to group "chicken head" separately, as follows:

HAVING (
 regex(GROUP_CONCAT(DISTINCT ?ingredient; separator=","), "chicken head") 
    || !regex(GROUP_CONCAT(DISTINCT ?ingredient; separator=","), "chicken head")
)

This code checks whether the ingredient "chicken head" is present in the list of ingredients using a regular expression. If it is, the dish is grouped separately. Otherwise, it is grouped with the other chicken dishes.
```



___
**[8] Kata Level 4 (10 pts, total pts accrued: 33 pts): Enter the Dōjō—Intermediate: SPARQL’s Data Update Functions (6)** 

**Description:**

If you successfully passed the Enter the Dōjō—Beginner levels of the series, congratulations young SPARQL query artist, you are now an intermediate player! 

You are an intermediate SPARQL queryist who has at least learned the foundational four “offensive”, i.e. action-forward, query forms, the four “defensive”, i.e. action-delimiting query clauses, along with the seven WHERE query condition clauses, and the five solution modifier “techniques” to refine solutions. 

**As SPARQL queryists retrieve, organize, refine, and edit data for their own respective purposes, a master SPARQL queryist must learn the seven data update functions: CLEAR, COPY, CREATE, DELETE, and DELETE DATA, DROP, INSERT and INSERT DATA, and LOAD.**

**For this challenge, write a query that retrieves at least three separate graphs and uses the seven data update functions in a novel way with real-world purchase (i.e. it must be a realistic project in using the seven data update functions).** 

```
Hint: You may query any data sets, but the data sets must be related to the aims of the overall query.

1. CLEAR: Deletes all of the triples in a graph without deleting the graph.
2. COPY: Copies graph data from the database to disk. 
3. CREATE: Creates a new empty graph.
4. DELETE and DELETE DATA: Deletes the specified graph or triple patterns or specific triples from the database.
5. DROP: Deletes a graph and all of its triples.
6. INSERT and INSERT DATA: Inserts the specified graph or triple patterns or specific triples to the database.
7. LOAD: Loads data to the database from a file or files that are on the AnzoGraph DB file system.

(1-7 Cited from Cambridge Semantics: https://docs.cambridgesemantics.com/anzograph/v2.5/userdoc/system-update.htm#DELETE)
```

**Reference Solution:**

```
PREFIX ex: <http://example.com/chickenwingsales/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

# Retrieve the data of annual chicken wing sales in all cities named Buffalo in the United States in 2022
SELECT ?city ?sales
WHERE {
  ?s ex:city ?city ;
     ex:sales ?sales ;
     ex:year "2022"^^xsd:integer .
  FILTER regex(?city, "^Buffalo,.*United States$")
}

# COPY the retrieved data from the database to the disk
COPY <file:///path/to/file.rdf>
WHERE {
  # The above SPARQL query goes here
}

# DROP the retrieved data
DROP { ?s ?p ?o }
WHERE {
  # The above SPARQL query goes here
}

# CREATE a new graph
CREATE GRAPH <http://example.com/newgraph>

# Retrieve the annual chicken wing sales of Buffalo, NY in 2002 and INSERT the data into the new graph
INSERT DATA {
  GRAPH <http://example.com/newgraph> {
    ex:BuffaloNY2002 ex:city "Buffalo, NY, United States" ;
                     ex:sales <INSERT 2002 SALES HERE> ;
                     ex:year "2002"^^xsd:integer .
  }
}

# Retrieve the annual chicken wing sales of Buffalo, NY in 2012 and INSERT the data into the new graph
INSERT DATA {
  GRAPH <http://example.com/newgraph> {
    ex:BuffaloNY2012 ex:city "Buffalo, NY, United States" ;
                     ex:sales <INSERT 2012 SALES HERE> ;
                     ex:year "2012"^^xsd:integer .
  }
}

# Retrieve the annual chicken wing sales of Buffalo, NY in 2022 and INSERT the data into the new graph
INSERT DATA {
  GRAPH <http://example.com/newgraph> {
    ex:BuffaloNY2022 ex:city "Buffalo, NY, United States" ;
                     ex:sales <INSERT 2022 SALES HERE> ;
                     ex:year "2022"^^xsd:integer .
  }
}

# COPY the new graph with the inserted annual chicken wing sales data from 2002, 2012, and 2022 to the disk
COPY <file:///path/to/file.rdf>
FROM <http://example.com/newgraph>

# CLEAR the data on the new graph
CLEAR GRAPH <http://example.com/newgraph>

# DELETE the data on the new graph
DELETE {
  GRAPH <http://example.com/newgraph> {
    ?s ?p ?o
  }
}
WHERE {
  GRAPH <http://example.com/newgraph> {
    ?s ?p ?o
  }
}

# LOAD the data of annual chicken wing sales in all cities named Buffalo in the United States in 2022 into the new graph
LOAD <file:///path/to/file.rdf>
INTO GRAPH <http://example.com/newgraph>

# LOAD the new graph with the inserted annual chicken wing sales data from 2002, 2012, and 2022
LOAD <file:///path/to/file.rdf>
INTO GRAPH <http://example.com/newgraph>

**Explanation of the query:**

The query represents a situation in which a SPARQL queryist first retrieves information to compare annual chicken wing sales in 2022 from all cities named Buffalo in the United States. Then the query goes on to focus specifically on annual chicken wing sales across three decades: 2002, 2012, and 2022. It creates a new graph and inserts the annual chicken wing sales from each decade into the new graph. The query saves the newly created graph on the disk so that the SPARQL queryist can compare the first generated graph to the second newly created graph.

```



___
**[9] Kata Level 4 (10 pts, total pts accrued: 43 pts): Enter the Dōjō—Intermediate: SPARQL’s Aggregate Functions (6)**

**Description:**

You are an intermediate SPARQL queryist with knowledge of the foundational query forms, clauses, and solution modifiers.
To push your training to the next level, we must learn the special powers of SPAQRL “queryistry”, SPARQL quantitative functions. Let us begin first with harnessing the powers of aggregate functions. 

Aggregate functions allow for analysis of quantified data.

**For this challenge, you are hired by a client from the food industry that has one primary research question: What is better for the United States economy, chicken or beef?** 

**Make a case by writing a query using at least 10 aggregate functions at least once for either chicken or beef as being better for the United States economy.** 

```
Hint: You may query any data sets, but the data sets must be related to the aims of the overall query.

1. AVG: Calculates the average (arithmetic mean) value for a group of numbers.
2. CHOOSE_BY_MAX: Returns the value from a group that corresponds to the maximum value from another group.
3. CHOOSE_BY_MIN: Returns the value from a group that corresponds to the minimum value from another group.
4. COUNT: Counts the number of values that exist for a group.
5. GROUP_CONCAT: Concatenates a group of strings into a single string.
6. MAX: Returns the maximum value from a group of values.
7. MEDIAN: Returns the median number out of a group of numbers.
8. MIN: Returns the minimum value from a group of values.
9. MODE: Returns the mode (the value that occurs most frequently) from a group of values.
10. MODE_PERCENT: Calculates the percentage of values in a group that belong to the mode.
11. SAMPLE: Returns an arbitrary value from the specified group of values.
12. SUM: Calculates the sum of the numbers within a group.
13. VAR: Calculates the unbiased (sample) variance of a group of numbers.
14. VARP: Calculates the biased (population) variance of a group of numbers.


(1-14 Cited from Cambridge Semantics: https://docs.cambridgesemantics.com/anzograph/v2.5/userdoc/system-aggregate.htm#AVG)
```

**Reference Solution:**

```
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX us-gov: <http://example.com/us-gov/>
PREFIX product: <http://example.com/product/>

SELECT 
  (SUM(?chickenSales) AS ?totalChickenSales)
  (SUM(?beefSales) AS ?totalBeefSales)
  (AVG(?chickenSales) AS ?avgChickenSales)
  (AVG(?beefSales) AS ?avgBeefSales)
  (MAX(?chickenSales) AS ?maxChickenSales)
  (MAX(?beefSales) AS ?maxBeefSales)
  (MIN(?chickenSales) AS ?minChickenSales)
  (MIN(?beefSales) AS ?minBeefSales)
  (COUNT(?chickenProduct) AS ?numChickenSales)
  (COUNT(?beefProduct) AS ?numBeefSales)
  (MAX(?chickenPrice) AS ?maxChickenPrice)
  (MAX(?beefPrice) AS ?maxBeefPrice)
  (AVG(?chickenPrice) AS ?medianChickenPrice)
  (AVG(?beefPrice) AS ?medianBeefPrice)
  (MIN(?chickenPrice) AS ?minChickenPrice)
  (MIN(?beefPrice) AS ?minBeefPrice)
  (MODE(?chickenSales) AS ?chickenSalesMode)
  (MODE(?beefSales) AS ?beefSalesMode)
  (MODE_PERCENT(?chickenSales) AS ?chickenSalesModePercent)
  (MODE_PERCENT(?beefSales) AS ?beefSalesModePercent)
  (SAMPLE(?chickenProduct) AS ?sampleChickenProduct)
  (SAMPLE(?beefProduct) AS ?sampleBeefProduct)
  (VAR(?chickenSales) AS ?unbiasedChickenSalesVar)
  (VAR(?beefSales) AS ?unbiasedBeefSalesVar)
  (VAR_POPULATION(?chickenSales) AS ?biasedChickenSalesVar)
  (VAR_POPULATION(?beefSales) AS ?biasedBeefSalesVar)

WHERE {
  ?chickenProduct rdf:type product:Chicken ;
                  product:sales ?chickenSales ;
                  product:price ?chickenPrice ;
                  product:country us-gov:United_States ;
                  product:dateSold ?chickenDate .
  FILTER(YEAR(?chickenDate) >= 2012 && YEAR(?chickenDate) <= 2022)
  
  ?beefProduct rdf:type product:Beef ;
               product:sales ?beefSales ;
               product:price ?beefPrice ;
               product:country us-gov:United_States ;
               product:dateSold ?beefDate .
  FILTER(YEAR(?beefDate) >= 2012 && YEAR(?beefDate) <= 2022)
}

**Explanation of the query:**

The query represents one direction that a queryist can choose to go in order to make a case about whether chicken or beef is better for the U.S. economy. The range of data chosen was a ten year period, 2012-2022, which would give the most recent sales data to inform one’s proposal. Another alternative is to include in the query restaurant sales that are explicitly chicken and beef based restaurants or to mark out available data from restaurants that show revenue from chicken and beef dishes specifically. 

```



___

**I will now transition away from creating Enter the Dōjō: Master the Basics of SPARQL Series material. There are still many functions to cover, but I would like to focus on using SPARQL to research and problem solve.**

___

**Theme: SPARQL for Research and Problem Solving**

___ 

**[10] Kata Level 3 (20 pts, total pts accrued: 63 pts): SPARQL for Research and Problem Solving—Which is the gloomier city: Seattle or Buffalo?** 

**Description:**

It has been often often reported that Seattle is the United States’ gloomiest city based off of annual reports of having the highest amount of overcast days and highest amount of reported cases of depression. A politician and wealthy businessman from Seattle wants to change Seattle’s reputation in the media and has recently heard of Buffalo, NY’s recent city-stopping blizzards and similar to Seattle, proclivity for having overcast days.

You are hired to make a new case for Buffalo to actually hold the “gloomiest city” title. You must first create a report that supports the claim that Seattle is regarded as the gloomiest city in the United States. Then create a second report with your new findings showing that Buffalo is actually the gloomiest city in the United States based off new markers. 


**Reference Solution:**

```
Part 1: Construct a graph (Report 1) that supports the claim that Seattle is regarded as the gloomiest city in the United States.

PREFIX : <http://example.org/data#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX geo: <http://www.w3.org/2003/01/geo/wgs84_pos#>

CONSTRUCT {
  ?statistic rdf:type :Statistic .
  ?statistic :averageOvercastDays ?avgOvercastDays .
  ?statistic :averageRainyDays ?avgRainyDays .
  ?statistic :averageDepressionCases ?avgDepressionCases .
  ?statistic :totalGloomiestCityYears ?totalGloomiestYears .
}
WHERE {
  {
    SELECT (AVG(?overcastDays) AS ?avgOvercastDays)
    WHERE {
      ?year :hasLocation :Seattle ;
            :hasYear ?yearValue ;
            :totalOvercastDays ?overcastDays .
      FILTER (?yearValue >= 1972 && ?yearValue <= 2022)
    }
  }
  UNION
  {
    SELECT (AVG(?rainyDays) AS ?avgRainyDays)
    WHERE {
      ?year :hasLocation :Seattle ;
            :hasYear ?yearValue ;
            :totalRainyDays ?rainyDays .
      FILTER (?yearValue >= 1972 && ?yearValue <= 2022)
    }
  }
  UNION
  {
    SELECT (AVG(?depressionCases) AS ?avgDepressionCases)
    WHERE {
      ?year :hasLocation :Seattle ;
            :hasYear ?yearValue ;
            :totalDepressionCases ?depressionCases .
      FILTER (?yearValue >= 1972 && ?yearValue <= 2022)
    }
  }
  UNION
  {
    SELECT (COUNT(?gloomiestYear) AS ?totalGloomiestYears)
    WHERE {
      ?gloomiestYear :hasLocation :Seattle ;
                     :hasYear ?yearValue ;
                     :isGloomiestCity true .
      FILTER (?yearValue >= 1972 && ?yearValue <= 2022)
    }
  }
  BIND (IRI(CONCAT("http://example.org/data#statistic-", STRUUID())) AS ?statistic)
}
# COPY the retrieved data from the database to the disk
COPY <file:///path/to/file.rdf>
WHERE {
  # The above SPARQL query goes here
}
# DROP the retrieved data
DROP { ?s ?p ?o }
WHERE {
  # The above SPARQL query goes here
}


Part 2: Construct a second graph (Report 2) with new findings showing that Buffalo is actually the gloomiest city in the United States based off new markers.

PREFIX : <http://example.org/data#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX geo: <http://www.w3.org/2003/01/geo/wgs84_pos#>

CONSTRUCT {
  ?city1 :averageOvercastDays ?avgOvercastDays1 .
  ?city2 :averageOvercastDays ?avgOvercastDays2 .
  ?city1 :averageRainyDays ?avgRainyDays1 .
  ?city2 :averageRainyDays ?avgRainyDays2 .
  ?city1 :averageDepressionCases ?avgDepressionCases1 .
  ?city2 :averageDepressionCases ?avgDepressionCases2 .
  ?city1 :averageSnowfall ?avgSnowfall1 .
  ?city2 :averageSnowfall ?avgSnowfall2 .
  ?city1 :averageTemperature ?avgTemperature1 .
  ?city2 :averageTemperature ?avgTemperature2 .
  ?city1 :averageUnemploymentRate ?avgUnemploymentRate1 .
  ?city2 :averageUnemploymentRate ?avgUnemploymentRate2 .
  ?city1 :averageHappinessIndex ?avgHappinessIndex1 .
  ?city2 :averageHappinessIndex ?avgHappinessIndex2 .
}
WHERE {
  {
    SELECT ?city1 (AVG(?overcastDays1) AS ?avgOvercastDays1) ?city2 (AVG(?overcastDays2) AS ?avgOvercastDays2) WHERE {
      {
        SELECT ?city1 ?year (SUM(?overcastDays) AS ?overcastDays1) WHERE {
          ?city1 rdfs:label "Seattle, Washington" .
          ?city1 :hasWeatherData ?weatherData1 .
          ?weatherData1 :overcastDays ?overcastDays .
          ?weatherData1 :year ?year .
          FILTER (1972 <= ?year && ?year <= 2022)
        } GROUP BY ?city1 ?year
      }
      {
        SELECT ?city2 ?year (SUM(?overcastDays) AS ?overcastDays2) WHERE {
          ?city2 rdfs:label "Buffalo, New York" .
          ?city2 :hasWeatherData ?weatherData2 .
          ?weatherData2 :overcastDays ?overcastDays .
          ?weatherData2 :year ?year .
          FILTER (1972 <= ?year && ?year <= 2022)
        } GROUP BY ?city2 ?year
      }
    } GROUP BY ?city1 ?city2
  }
  UNION
  {
    SELECT ?city1 (AVG(?rainyDays1) AS ?avgRainyDays1) ?city2 (AVG(?rainyDays2) AS ?avgRainyDays2) WHERE {
      {
        SELECT ?city1 ?year (SUM(?rainyDays) AS ?rainyDays1) WHERE {
          ?city1 rdfs:label "Seattle, Washington" .
          ?city1 :hasWeatherData ?weatherData1 .
          ?weatherData1 :rainyDays ?rainyDays .
          ?weatherData1 :year ?year .
                   FILTER (1972 <= ?year && ?year <= 2022)
        } GROUP BY ?city1 ?year
      }
      {
        SELECT ?city2 ?year (SUM(?rainyDays) AS ?rainyDays2) WHERE {
          ?city2 rdfs:label "Buffalo, New York" .
          ?city2 :hasWeatherData ?weatherData2 .
          ?weatherData2 :rainyDays ?rainyDays .
          ?weatherData2 :year ?year .
          FILTER (1972 <= ?year && ?year <= 2022)
        } GROUP BY ?city2 ?year
      }
    } GROUP BY ?city1 ?city2
  }
  UNION
  {
    SELECT ?city1 (AVG(?depressionCases1) AS ?avgDepressionCases1) ?city2 (AVG(?depressionCases2) AS ?avgDepressionCases2) WHERE {
      {
        SELECT ?city1 ?year (SUM(?depressionCases) AS ?depressionCases1) WHERE {
          ?city1 rdfs:label "Seattle, Washington" .
          ?city1 :hasHealthData ?healthData1 .
          ?healthData1 :depressionCases ?depressionCases .
          ?healthData1 :year ?year .
          FILTER (1972 <= ?year && ?year <= 2022)
        } GROUP BY ?city1 ?year
      }
      {
        SELECT ?city2 ?year (SUM(?depressionCases) AS ?depressionCases2) WHERE {
          ?city2 rdfs:label "Buffalo, New York" .
          ?city2 :hasHealthData ?healthData2 .
          ?healthData2 :depressionCases ?depressionCases .
          ?healthData2 :year ?year .
          FILTER (1972 <= ?year && ?year <= 2022)
        } GROUP BY ?city2 ?year
      }
    } GROUP BY ?city1 ?city2
  }
  UNION
  {
    SELECT ?city1 (AVG(?snowfall1) AS ?avgSnowfall1) ?city2 (AVG(?snowfall2) AS ?avgSnowfall2) WHERE {
      {
        SELECT ?city1 ?year (SUM(?snowfall) AS ?snowfall1) WHERE {
          ?city1 rdfs:label "Seattle, Washington" .
          ?city1 :hasWeatherData ?weatherData1 .
          ?weatherData1 :snowfall ?snowfall .
          ?weatherData1 :year ?year .
          FILTER (1972 <= ?year && ?year <= 2022)
        } GROUP BY ?city1 ?year
      }
      {
        SELECT ?city2 ?year (SUM(?snowfall) AS ?snowfall2) WHERE {
          ?city2 rdfs:label "Buffalo, New York" .
          ?city2 :hasWeatherData ?weatherData2 .
          ?weatherData2 :snowfall ?snowfall .
          ?weatherData2 :year ?year .
          FILTER (1972 <= ?year && ?year <= 2022)
        } GROUP BY ?city2 ?year
      }
    } GROUP BY ?city1 ?city2
  }
  UNION
  {
    SELECT ?city1 (AVG(?dailyAverageTemperature1) AS ?avgTemperature1) ?city2 (AVG(?dailyAverageTemperature2) AS ?avgTemperature2) WHERE {
      {
        SELECT ?city1 ?year (AVG(?dailyAverageTemperature) AS ?dailyAverageTemperature1) WHERE {
                    ?city1 rdfs:label "Seattle, Washington" .
          ?city1 :hasWeatherData ?weatherData1 .
          ?weatherData1 :dailyAverageTemperature ?dailyAverageTemperature .
          ?weatherData1 :year ?year .
          FILTER (1972 <= ?year && ?year <= 2022)
        } GROUP BY ?city1 ?year
      }
      {
        SELECT ?city2 ?year (AVG(?dailyAverageTemperature) AS ?dailyAverageTemperature2) WHERE {
          ?city2 rdfs:label "Buffalo, New York" .
          ?city2 :hasWeatherData ?weatherData2 .
          ?weatherData2 :dailyAverageTemperature ?dailyAverageTemperature .
          ?weatherData2 :year ?year .
          FILTER (1972 <= ?year && ?year <= 2022)
        } GROUP BY ?city2 ?year
      }
    } GROUP BY ?city1 ?city2
  }
  UNION
  {
    SELECT ?city1 (AVG(?unemploymentRate1) AS ?avgUnemploymentRate1) ?city2 (AVG(?unemploymentRate2) AS ?avgUnemploymentRate2) WHERE {
      {
        SELECT ?city1 ?year (AVG(?unemploymentRate) AS ?unemploymentRate1) WHERE {
          ?city1 rdfs:label "Seattle, Washington" .
          ?city1 :hasEconomicData ?economicData1 .
          ?economicData1 :unemploymentRate ?unemploymentRate .
          ?economicData1 :year ?year .
          FILTER (2012 <= ?year && ?year <= 2022)
        } GROUP BY ?city1 ?year
      }
      {
        SELECT ?city2 ?year (AVG(?unemploymentRate) AS ?unemploymentRate2) WHERE {
          ?city2 rdfs:label "Buffalo, New York" .
          ?city2 :hasEconomicData ?economicData2 .
          ?economicData2 :unemploymentRate ?unemploymentRate .
          ?economicData2 :year ?year .
          FILTER (2012 <= ?year && ?year <= 2022)
        } GROUP BY ?city2 ?year
      }
    } GROUP BY ?city1 ?city2
  }
  UNION
  {
    SELECT ?city1 (AVG(?happinessIndex1) AS ?avgHappinessIndex1) ?city2 (AVG(?happinessIndex2) AS ?avgHappinessIndex2) WHERE {
      {
        SELECT ?city1 ?year (AVG(?happinessIndex) AS ?happinessIndex1) WHERE {
          ?city1 rdfs:label "Seattle, Washington" .
          ?city1 :hasSocialData ?socialData1 .
          ?socialData1 :happinessIndex ?happinessIndex .
          ?socialData1 :year ?year .
          FILTER (2012 <= ?year && ?year <= 2022)
        } GROUP BY ?city1 ?year
      }
      {
        SELECT ?city2 ?year (AVG(?happinessIndex) AS ?happinessIndex2) WHERE {
          ?city2 rdfs:label "Buffalo, New York" .
          ?city2 :hasSocialData ?socialData2 .
          ?socialData2 :happinessIndex ?happinessIndex .
          ?socialData2 :year ?year .
          FILTER (2012 <= ?year && ?year <= 2022)
        } GROUP BY ?city2 ?year
      }
    } GROUP BY ?city1 ?city2
  }
}
# COPY the retrieved data from the database to the disk
COPY <file:///path/to/file.rdf>
WHERE {
  # The above SPARQL query goes here
}

**Explanation of the query:**

The example query represented has two parts. The URIs are example place holders, so the query is only referential. The first part creates the initial graph with evidence that may be used to support the claim that Seattle is America’s gloomiest city. 

The second part compares Seattle and Buffalo on seven different markers. Upon analysis, one could make the argument that Buffalo is more gloomy based on additional factors such as a higher annual average snowfall, lower annual average temperature, higher annual average unemployment rate, and lower annual average rating on the happiness index. 

```



___ 

**[11] Kata Level 3 or 2 (20 pts or 25 pts, total pts accrued: 83 or 88 pts): SPARQL for Research and Problem Solving—Epidemiological Studies** 

**Description:**

You have recently been hired by the Center for Disease Control and Prevention (CDC) as an epidemiologist. There has been much talk about how the United States has likely reached herd immunity. However, with recent market and housing fears arising, along with heavy skepticism and criticism from the public about the CDC's credibility, the new director of the CDC has sought to allay fears by hiring you, a new breed epidemiologist with SPARQL querying skills. 

Using your experience with SPARQL, create a query in order to conduct research to develop a report which makes a prediction and a case for when and where the next COVID-19 outbreak will be in the United States. You must query at least two different data sets and construct a novel graph as part of your report.

```
Hint: Use these CSV files which are updated each week:

US National Data: https://raw.githubusercontent.com/nytimes/covid-19-data/master/us.csv
US State Data: https://raw.githubusercontent.com/nytimes/covid-19-data/master/us-states.csv
US County Data: https://raw.githubusercontent.com/nytimes/covid-19-data/master/us-counties-recent.csv

Hint 2: SPARQL is designed to query RDF data, not CSV data.

Hint 3: Consider using SPARQL property paths to examine the patterns between properties in the data. Property paths reveal the routes between nodes in a graph.
```

**Reference Solution:**

```
Part 1: Convert the CSV data to RDF data. 

To convert the NY Times COVID-19 data CSV file to RDF, you could use a tool like the RDF Mapping Language (RML) and its implementation in the RMLMapper. Here's an example of how you could create an RML mapping file for the CSV file:

@prefix rr: <http://www.w3.org/ns/r2rml#>.
@prefix rml: <http://semweb.mmlab.be/ns/rml#>.
@prefix ql: <http://semweb.mmlab.be/ns/ql#>.
@prefix xsd: <http://www.w3.org/2001/XMLSchema#>.
@prefix nyt: <http://example.org/nytimes/covid-19-data#>.

# Define the data source
rr:DataSource
  rml:source "https://raw.githubusercontent.com/nytimes/covid-19-data/master/us.csv";
  rml:referenceFormulation ql:CSV.

# Define the logical source
rr:LogicalSource
  rr:source rr:DataSource;
  rr:iterator "us".

# Define the subject map
rr:SubjectMap
  rr:template "http://example.org/nytimes/covid-19-data/{date}/{state}/{county}";
  rr:class nyt:Observation.

# Define the predicate-object maps
rr:PredicateObjectMap
  rr:predicate nyt:date;
  rr:objectMap [ rml:reference "date"; ].
rr:PredicateObjectMap
  rr:predicate nyt:state;
  rr:objectMap [ rml:reference "state"; ].
rr:PredicateObjectMap
  rr:predicate nyt:county;
  rr:objectMap [ rml:reference "county"; ].
rr:PredicateObjectMap
  rr:predicate nyt:fips;
  rr:objectMap [ rml:reference "fips"; ].
rr:PredicateObjectMap
  rr:predicate nyt:cases;
  rr:objectMap [ rml:reference "cases"; rr:datatype xsd:integer; ].
rr:PredicateObjectMap
  rr:predicate nyt:deaths;
  rr:objectMap [ rml:reference "deaths"; rr:datatype xsd:integer; ].

This mapping file assumes that you have downloaded the us.csv file from the NY Times GitHub repository and saved it locally. It defines a logical source for the us table in the CSV file, and a subject map that generates URIs for each observation based on the date, state, and county. The predicate-object maps specify how to map each column in the CSV file to RDF predicates and objects.



Part 2: Query national data and construct new graph

PREFIX covid: <http://example.org/covid/>

CONSTRUCT {
  ?statistic covid:totalCases ?totalCasesValue ;
             covid:totalDeaths ?totalDeathsValue .
}
WHERE {
  {
    SELECT (SUM(?cases) AS ?totalCasesValue) (AVG(?cases) AS ?avgCasesValue)
           (MAX(?cases) AS ?maxCasesValue) (MIN(?cases) AS ?minCasesValue)
           (SUM(?deaths) AS ?totalDeathsValue) (AVG(?deaths) AS ?avgDeathsValue)
           (MAX(?deaths) AS ?maxDeathsValue) (MIN(?deaths) AS ?minDeathsValue)
    WHERE {
      ?record covid:date ?date ;
              covid:cases ?cases ;
              covid:deaths ?deaths .
      FILTER (?date >= "2020-01-21"^^xsd:date && ?date <= "2023-03-23"^^xsd:date)
    }
  }
  BIND (URI(CONCAT("http://example.org/covid/statistics/", STRUUID())) AS ?statistic)
}
# COPY the retrieved data from the database to the disk
COPY <file:///path/to/file.rdf1>
WHERE {
  # The above SPARQL query goes here
}



Part 3: Query indiviudal state data and construct new graph (Note: This data expresses that there are 55 states [50 states + 5 territories]).

PREFIX covid2: <http://example.org/covid/>

CONSTRUCT {
  ?state covid:totalCasesStats ?totalCasesStats ;
          covid:totalDeathsStats ?totalDeathsStats .
}
WHERE {
  {
    SELECT ?state
           (SUM(?cases) AS ?totalCasesSum) (AVG(?cases) AS ?avgCases) (MAX(?cases) AS ?maxCases) (MIN(?cases) AS ?minCases)
           (SUM(?deaths) AS ?totalDeathsSum) (AVG(?deaths) AS ?avgDeaths) (MAX(?deaths) AS ?maxDeaths) (MIN(?deaths) AS ?minDeaths)
    WHERE {
      ?record covid2:date ?date ;
              covid2:state ?state ;
              covid2:cases ?cases ;
              covid2:deaths ?deaths .
      FILTER (?date >= "2020-01-21"^^xsd:date && ?date <= "2023-03-23"^^xsd:date)
      FILTER (?state IN (
                "Alabama", "Alaska", "Arizona", "Arkansas", "California", "Colorado", "Connecticut", "Delaware", "Florida", "Georgia",
                "Hawaii", "Idaho", "Illinois", "Indiana", "Iowa", "Kansas", "Kentucky", "Louisiana", "Maine", "Maryland",
                "Massachusetts", "Michigan", "Minnesota", "Mississippi", "Missouri", "Montana", "Nebraska", "Nevada", "New Hampshire",
                "New Jersey", "New Mexico", "New York", "North Carolina", "North Dakota", "Ohio", "Oklahoma", "Oregon", "Pennsylvania",
                "Rhode Island", "South Carolina", "South Dakota", "Tennessee", "Texas", "Utah", "Vermont", "Virginia", "Washington",
                "West Virginia", "Wisconsin", "Wyoming", "American Samoa", "Guam", "Northern Mariana Islands", "Puerto Rico", "U.S. Virgin Islands"
              ))
    }
    GROUP BY ?state
  }
  BIND (URI(CONCAT("http://example.org/covid/totalCasesStats/", STRUUID())) AS ?totalCasesStats)
  BIND (URI(CONCAT("http://example.org/covid/totalDeathsStats/", STRUUID())) AS ?totalDeathsStats)
  ?totalCasesStats covid2:sum ?totalCasesSum ;
                   covid2:avg ?avgCases ;
                   covid2:max ?maxCases ;
                   covid2:min ?minCases .
  ?totalDeathsStats covid2:sum ?totalDeathsSum ;
                    covid2:avg ?avgDeaths ;
                    covid2:max ?maxDeaths ;
                    covid2:min ?minDeaths .
}
# COPY the retrieved data from the database to the disk
COPY <file:///path/to/file.rdf2>
WHERE {
  # The above SPARQL query goes here
}
# DROP the retrieved data
DROP { ?s ?p ?o }
WHERE {
  # The above SPARQL query goes here
}



Part 4: Query for sequence property path pattern (growth) on the saved US national data RDF file

# LOAD the new graph 1
LOAD <file:///path/to/file.rdf1>
INTO GRAPH <http://example.com/newgraph1>

PREFIX covid: <http://example.com/newgraph1>

SELECT ?date1 (SUM(?cases1) AS ?totalCases1) (SUM(?deaths1) AS ?totalDeaths1)
              ?date2 (SUM(?cases2) AS ?totalCases2) (SUM(?deaths2) AS ?totalDeaths2)
WHERE {
  ?record1 covid:date ?date1 ;
           covid:cases ?cases1 ;
           covid:deaths ?deaths1 ;
           covid:nextRecord ?record2 .
  ?record2 covid:date ?date2 ;
           covid:cases ?cases2 ;
           covid:deaths ?deaths2 .

  FILTER (?cases2 > ?cases1 && ?deaths2 > ?deaths1)
  FILTER (?date1 >= "2023-01-23"^^xsd:date && ?date1 <= "2023-03-22"^^xsd:date)
  FILTER (?date2 = ?date1 + "P1D"^^xsd:duration)
}
GROUP BY ?date1 ?date2
ORDER BY ?date1



Part 5: Query for Sequence Property Path Pattern (Growth) on the Saved US State Data RDF File

# LOAD the new graph 2
LOAD <file:///path/to/file.rdf2>
INTO GRAPH <http://example.com/newgraph2>

PREFIX covid: <http://example.com/newgraph2>

CONSTRUCT {
  ?record1 covid:state ?state ;
           covid:date ?date1 ;
           covid:cases ?cases1 ;
           covid:deaths ?deaths1 ;
           covid:nextRecord ?record2 .
  ?record2 covid:date ?date2 ;
           covid:cases ?cases2 ;
           covid:deaths ?deaths2 .
}
WHERE {
  ?record1 covid:date ?date1 ;
           covid:state ?state ;
           covid:cases ?cases1 ;
           covid:deaths ?deaths1 ;
           covid:nextRecord ?record2 .
  ?record2 covid:date ?date2 ;
           covid:cases ?cases2 ;
           covid:deaths ?deaths2 .
           
  FILTER (?cases2 > ?cases1 && ?deaths2 > ?deaths1)
  FILTER (?state IN (
            "Alabama", "Alaska", "Arizona", "Arkansas", "California", "Colorado", "Connecticut", "Delaware", "Florida", "Georgia",
            "Hawaii", "Idaho", "Illinois", "Indiana", "Iowa", "Kansas", "Kentucky", "Louisiana", "Maine", "Maryland",
            "Massachusetts", "Michigan", "Minnesota", "Mississippi", "Missouri", "Montana", "Nebraska", "Nevada", "New Hampshire",
            "New Jersey", "New Mexico", "New York", "North Carolina", "North Dakota", "Ohio", "Oklahoma", "Oregon", "Pennsylvania",
            "Rhode Island", "South Carolina", "South Dakota", "Tennessee", "Texas", "Utah", "Vermont", "Virginia", "Washington",
            "West Virginia", "Wisconsin", "Wyoming", "American Samoa", "Guam", "Northern Mariana Islands", "Puerto Rico", "U.S. Virgin Islands"
          ))
  FILTER (?date1 >= "2023-01-23"^^xsd:date && ?date1 <= "2023-03-22"^^xsd:date)
  FILTER (?date2 = ?date1 + "P1D"^^xsd:duration)
}



Part 6: Combine the two newly constructed graphs, perform a final comparative sequence property path pattern analysis, and filter the states where there is positive patterned growth to identify and predict where the next possible COVID-19 surge can occur.

PREFIX covid: <http://example.com/newgraph1>
PREFIX covid: <http://example.com/newgraph2>

CONSTRUCT {
  ?record1 covid:state ?state ;
           covid:date ?date1 ;
           covid:cases ?cases1 ;
           covid:deaths ?deaths1 ;
           covid:nextRecord ?record2 .
  ?record2 covid:date ?date2 ;
           covid:cases ?cases2 ;
           covid:deaths ?deaths2 .
}
WHERE {
  {
    GRAPH <http://example.com/newgraph1> {
      ?record1 covid:date ?date1 ;
               covid:state ?state ;
               covid:cases ?cases1 ;
               covid:deaths ?deaths1 ;
               covid:nextRecord ?record2 .
    }
  } UNION {
    GRAPH <http://example.com/newgraph2> {
      ?record1 covid:date ?date1 ;
               covid:state ?state ;
               covid:cases ?cases1 ;
               covid:deaths ?deaths1 ;
               covid:nextRecord ?record2 .
    }
  }
  ?record2 covid:date ?date2 ;
           covid:cases ?cases2 ;
           covid:deaths ?deaths2 .

  FILTER (?cases2 > ?cases1 && ?deaths2 > ?deaths1)
  FILTER (?date1 >= "2023-01-23"^^xsd:date && ?date1 <= "2023-03-22"^^xsd:date)
  FILTER (?date2 = ?date1 + "P1D"^^xsd:duration)
}

**Explanation of the query:**

The example query represented has six parts. The URIs are example place holders, so the query is only referential. However, the CSV links are real. 

This is a multi-faceted and challenging exercise, which can use further property path pattern analysis to make a case for when and where the next possible COVID-19 surge will be, more than I did here (e.g. AlternativePath or OneOrMorePath). I demonstrated the sequence path analysis and compared the results between the US as a whole and 55 individual states and on each day between the dates 2023-01-23 and 2023-03-22. 

```



___ 

**[12] Kata Level 3 or 2 (20 pts or 25 pts, total pts accrued: 103 or 113 pts): SPARQL for Research and Problem Solving—Generating Novel Map Models in Crisis** 

**Description:**

World War III has been raging for three long years now. Over half of the United States has been topographically demolished by the tragedies of war--weapons of mass destruction, environmental terrorism, and famine. Major metropolitan cities have been razed, mountain ranges leveled, bodies of water either destroyed and/or rendered as ecological biohazards. Yet, the indomitable spirit of the US and its citizens continue to burn aflame to fight the good fight and to labor towards securing a world of freedom, justice, equality, and peace. 

Since WWIII started, Ashburn in Loudoun County, Virginia, the home of the majority of servers that supported the internet, was targeted and largely destroyed by the U.S.'s enemies. As such, much of the internet's capacities have been down. Moreover, the servers of Google and Apple have also largely been destroyed and therefore, their respective applications have mostly become defunct. Specifically, Google search and Google Maps, along with Apple Maps, no longer work. 

The U.S. military had recently sent out a mandatory draft for all cartographers and engineers that know the SPARQL querying language. Most drawn maps that existed prior to the start of WWIII are now obsolete because of the destruction that had occurred over the past three years. The land is now largely indistinguishable and the loss of reliable internet has paralyzed communication systems and internet reliant navigation. 

However, there is hope! All U.S. satelites are intact and undamaged. As such, devices that utilize GPS still work. Furthermore, there still exists some servers that allow for some parts of the internet to function. Specifically, the worlds largest and most comprehensive URI, http://example.org/ontology/, is still up and functioning. 

**Your mission is this: You must use SPARQL to design a novel model map of the United States and its 50 states that can be used by military and government personnel to navigate this country by air and land. This map model cannot rely on topographical visuals or features. Retrieve the pertinent information needed to creatively solve this navigation crisis.**

Best of luck, soldier! 

Hint 1: GPS

Hint 2: Property paths, haversine, and path algorithms

**Reference Solution:**

```
Part 1: Create a query that retreives latitude and longitude coordinates outlining the shape and border of the United States as a whole. 

PREFIX ont: <http://example.org/ontology/>
PREFIX geo: <http://example.org/geo/>

CONSTRUCT {
  ?borderNode geo:lat ?lat ;
              geo:long ?long ;
              geo:border ?border ;
              geo:country "United States" .
}
WHERE {
  {
    SELECT ?border (SAMPLE(?latitude) AS ?lat) (SAMPLE(?longitude) AS ?long) (COUNT(?coordinate) AS ?number)
    WHERE {
      ?coordinate geo:lat ?latitude ;
                  geo:long ?longitude ;
                  geo:border ?border ;
                  geo:country "United States" .
    
      VALUES ?border { "west" "north" "east" "south" }
    }
    GROUP BY ?border
    HAVING (COUNT(?coordinate) >= 50)
  }

  BIND (IRI(CONCAT("http://example.org/border/", ?border)) AS ?borderNode)
}
# COPY the retrieved data from the database to the disk
COPY <file:///path/to/file.rdf1>
WHERE {
  # The above SPARQL query goes here
}
# DROP the retrieved data
DROP { ?s ?p ?o }
WHERE {
  # The above SPARQL query goes here
}

This query first retrieves 50 latitude and longitude coordinates for each border (west, north, east, and south), and then uses the CONSTRUCT clause to create a new graph with the information. The BIND statement is used to create a new IRI for each border node in the constructed graph.



Part 2: Create a query that retreives latitude and longitude coordinates outlining the shape and border of all 50 US states and the US's five territories (for this exercise, we will call them states), as well as retrieving the latitude and longitude midpoint coordinates of each.

PREFIX ont: <http://example.org/ontology/>
PREFIX geo: <http://example.org/geo/>

CONSTRUCT {
  ?borderNode geo:lat ?lat ;
              geo:long ?long ;
              geo:border ?border ;
              geo:state ?state ;
              geo:country "United States" .

  ?midpointNode geo:lat ?midpointLat ;
                geo:long ?midpointLong ;
                geo:state ?state ;
                geo:country "United States" .
}
WHERE {
  {
    SELECT ?state ?border (SAMPLE(?latitude) AS ?lat) (SAMPLE(?longitude) AS ?long) (COUNT(?coordinate) AS ?number)
    WHERE {
      ?coordinate geo:lat ?latitude ;
                  geo:long ?longitude ;
                  geo:border ?border ;
                  geo:state ?state ;
                  geo:country "United States" .
      
      VALUES ?border { "west" "north" "east" "south" }
      VALUES ?state {
        "Alabama" "Alaska" "Arizona" "Arkansas" "California" "Colorado" "Connecticut" "Delaware" "Florida" "Georgia"
        "Hawaii" "Idaho" "Illinois" "Indiana" "Iowa" "Kansas" "Kentucky" "Louisiana" "Maine" "Maryland"
        "Massachusetts" "Michigan" "Minnesota" "Mississippi" "Missouri" "Montana" "Nebraska" "Nevada" "New Hampshire" "New Jersey"
        "New Mexico" "New York" "North Carolina" "North Dakota" "Ohio" "Oklahoma" "Oregon" "Pennsylvania" "Rhode Island" "South Carolina"
        "South Dakota" "Tennessee" "Texas" "Utah" "Vermont" "Virginia" "Washington" "West Virginia" "Wisconsin" "Wyoming"
        "American Samoa" "Guam" "Northern Mariana Islands" "Puerto Rico" "U.S. Virgin Islands"
      }
    }
    GROUP BY ?state ?border
    HAVING (COUNT(?coordinate) >= 50)
    BIND (IRI(CONCAT("http://example.org/border/", REPLACE(STR(?state), " ", "_"), "/", ?border)) AS ?borderNode)
  }

  UNION

  {
    SELECT ?state (AVG(?latitude) AS ?midpointLat) (AVG(?longitude) AS ?midpointLong)
    WHERE {
      ?coordinate geo:lat ?latitude ;
                  geo:long ?longitude ;
                  geo:state ?state ;
                  geo:country "United States" .
      
      VALUES ?state {
        "Alabama" "Alaska" "Arizona" "Arkansas" "California" "Colorado" "Connecticut" "Delaware" "Florida" "Georgia"
        "Hawaii" "Idaho" "Illinois" "Indiana" "Iowa" "Kansas" "Kentucky" "Louisiana" "Maine" "Maryland"
        "Massachusetts" "Michigan" "Minnesota" "Mississippi" "Missouri" "Montana" "Nebraska" "Nevada" "New Hampshire" "New Jersey"
        "New Mexico" "New York" "North Carolina" "North Dakota" "Ohio" "Oklahoma" "Oregon" "Pennsylvania" "Rhode Island" "South Carolina"
        "South Dakota" "Tennessee" "Texas" "Utah" "Vermont" "Virginia" "Washington" "West Virginia" "Wisconsin" "Wyoming"
        "American Samoa" "Guam" "Northern Mariana Islands" "Puerto Rico" "U.S. Virgin Islands"
      }
    }
    GROUP BY ?state
    BIND (IRI(CONCAT("http://example.org/midpoint/", REPLACE(STR(?state), " ", "_"))) AS ?midpointNode)
  }
}
# COPY the retrieved data from the database to the disk
COPY <file:///path/to/file.rdf2>
WHERE {
  # The above SPARQL query goes here
}



Part 3: Combine the two newly constructed graphs, perform a final comparative inverse, sequence, and matching property path pattern analysis on all border nodes for all 50 states and the 5 territories.  

# LOAD the new graph 1
LOAD <file:///path/to/file.rdf1>
INTO GRAPH <http://example.com/newgraph1>

PREFIX ont: <http://example.org/ontology/>
PREFIX geo: <http://example.org/geo/>
PREFIX ex1: <http://example.com/newgraph1>
PREFIX ex2: <http://example.com/newgraph2>

CONSTRUCT {
  ?usBorderNode geo:matchedStateBorder ?stateBorderNode .
}
WHERE {
  GRAPH ex1:newgraph1 {
    ?usBorderNode geo:lat ?usLat ;
                  geo:long ?usLong ;
                  geo:border ?usBorder .
  }
  GRAPH ex2:newgraph2 {
    ?stateBorderNode geo:lat ?stateLat ;
                     geo:long ?stateLong ;
                     geo:border ?stateBorder ;
                     geo:state ?state .
  }

  VALUES ?state {
    "Alabama" "Alaska" "Arizona" "Arkansas" "California" "Colorado" "Connecticut" "Delaware" "Florida" "Georgia"
    "Hawaii" "Idaho" "Illinois" "Indiana" "Iowa" "Kansas" "Kentucky" "Louisiana" "Maine" "Maryland"
    "Massachusetts" "Michigan" "Minnesota" "Mississippi" "Missouri" "Montana" "Nebraska" "Nevada" "New Hampshire" "New Jersey"
    "New Mexico" "New York" "North Carolina" "North Dakota" "Ohio" "Oklahoma" "Oregon" "Pennsylvania" "Rhode Island" "South Carolina"
    "South Dakota" "Tennessee" "Texas" "Utah" "Vermont" "Virginia" "Washington" "West Virginia" "Wisconsin" "Wyoming"
    "American Samoa" "Guam" "Northern Mariana Islands" "Puerto Rico" "U.S. Virgin Islands"
  }

  FILTER (?usBorder = ?stateBorder)
  FILTER (?usLat = ?stateLat && ?usLong = ?stateLong)
}
# COPY the retrieved data from the database to the disk
COPY <file:///path/to/file.rdf3>
WHERE {
  # The above SPARQL query goes here
}
# DROP the retrieved data
DROP { ?s ?p ?o }
WHERE {
  # The above SPARQL query goes here
}


Part 4: Determine the haversine distance between each latitude and longitude coordinate border note to determine the kilometers between each node. Save the new constructed graph to disk.

# LOAD the new graph 3
LOAD <file:///path/to/file.rdf3>
INTO GRAPH <http://example.com/newgraph3>

PREFIX ont: <http://example.org/ontology/>
PREFIX geo: <http://example.org/geo/>
PREFIX ex3: <http://example.com/newgraph3>

CONSTRUCT {
  ?borderNodeA geo:haversineDistanceTo ?borderNodeB ;
               geo:distanceValue ?haversineDistance .
}
WHERE {
  GRAPH ex3:newgraph3 {
    ?borderNodeA geo:lat ?latA ;
                 geo:long ?longA ;
                 geo:border ?borderA ;
                 geo:state ?state .
    ?borderNodeB geo:lat ?latB ;
                 geo:long ?longB ;
                 geo:border ?borderB ;
                 geo:state ?state .
  }

  VALUES ?state {
    "Alabama" "Alaska" "Arizona" "Arkansas" "California" "Colorado" "Connecticut" "Delaware" "Florida" "Georgia"
    "Hawaii" "Idaho" "Illinois" "Indiana" "Iowa" "Kansas" "Kentucky" "Louisiana" "Maine" "Maryland"
    "Massachusetts" "Michigan" "Minnesota" "Mississippi" "Missouri" "Montana" "Nebraska" "Nevada" "New Hampshire" "New Jersey"
    "New Mexico" "New York" "North Carolina" "North Dakota" "Ohio" "Oklahoma" "Oregon" "Pennsylvania" "Rhode Island" "South Carolina"
    "South Dakota" "Tennessee" "Texas" "Utah" "Vermont" "Virginia" "Washington" "West Virginia" "Wisconsin" "Wyoming"
    "American Samoa" "Guam" "Northern Mariana Islands" "Puerto Rico" "U.S. Virgin Islands"
  }

  FILTER (?borderNodeA != ?borderNodeB)

  BIND (HAVERSINE_DIST(?latA, ?longA, ?latB, ?longB) AS ?haversineDistance)
}
# COPY the retrieved data from the database to the disk
COPY <file:///path/to/file.rdf4>
WHERE {
  # The above SPARQL query goes here
}



Part 5: Use the GPS signal of your device to identify exact latitude and longitude coordinates. Then, in order to to calculate travel in relation to the border nodes and midpoint nodes, utilize the all paths or shortest path algorithm to help calculate estimated navigation time and distance. 

# LOAD the new graph 4
LOAD <file:///path/to/file.rdf4>
INTO GRAPH <http://example.com/newgraph4>

All Paths: The All Paths algorithm finds all of the paths that exist between a source node and destination node in a graph (cited from Cambridge Semantics: https://docs.cambridgesemantics.com/anzograph/v2.5/userdoc/all-paths.htm).

Shortest Path: The Shortest Path algorithm finds the shortest path from a source node to the other reachable nodes in a graph (cited from Cambridge Semantics: https://docs.cambridgesemantics.com/anzograph/v2.5/userdoc/shortest-path.htm)

**Explanation of the query:**

This query attempts to identify 50 latitude and longitude border nodes for the west, north, east, and south sides of the United States border as a whole each and for the west, north, east, and south borders of each of the 50 U.S. states and its 5 territories. It attempts a property path inverse, sequence, and matching pattern analsyis between all border nodes. It then uses the All Paths and Shortest Path algorithm, alongside GPS to find a traveller's immediate geolocation, i.e. latitude and longitude coordinates, to calculate an estimated time and distance to a specified destination. Moreover, the Haversine distance, which finds the kilometers between two border nodes are another measuring capability that a traveller may use when navigating the U.S. with this novel model map. 

```




