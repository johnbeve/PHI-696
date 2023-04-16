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

1) Write a query that returns all object properties in dbpedia. 

Reference solution:
select ?p

where{
?s ?p ?o
}

2) Write a SPARQL quiery that retrieves the name, birthplace, birth date, genre, latitude, longitude, label, and abstract of actors born after 1950, along with information about their birthplaces.

Hint:
This question uses four query forms:

Triple patterns to retrieve the actor's name and birthplace, as well as the birth date of each actor.
A property path to retrieve the genres of the movies each actor appeared in.
A set of triple patterns to retrieve the coordinates, label, and abstract of each birthplace.
Filter expressions to restrict the birth date to after 1950 and the birthplace label to English.

The query also uses a combination of operators and functions, including:

The LANGMATCHES function to match English-language labels.
The STRDT function to convert the birth date string to a date datatype for comparison.
The ORDER BY clause to sort the results by actor name.
Triple patterns to retrieve the actor's name and birthplace, as well as the birth date of each actor.
A property path to retrieve the genres of the movies each actor appeared in.
A set of triple patterns to retrieve the coordinates, label, and abstract of each birthplace.
Filter expressions to restrict the birth date to after 1950 and the birthplace label to English.

The query also uses a combination of operators and functions, including:

The LANGMATCHES function to match English-language labels.
The STRDT function to convert the birth date string to a date datatype for comparison.
The ORDER BY clause to sort the results by actor name.

Reference solution:
PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
PREFIX geo: <http://www.w3.org/2003/01/geo/wgs84_pos#>

SELECT DISTINCT ?actor ?actorName ?birthPlace ?birthDate ?genre ?latitude ?longitude ?label ?abstract
WHERE {
  # Query 1: Retrieve actors and their birthplaces
  ?actor a dbo:Actor ;
         foaf:name ?actorName ;
         dbo:birthPlace ?birthPlace .
  
  # Query 2: Retrieve the birth date of each actor
  ?actor dbo:birthDate ?birthDate .
  
  # Query 3: Retrieve the genres of the movies each actor appeared in
  ?actor dbo:starring ?movie .
  ?movie dbo:genre ?genre .
  
  # Query 4: Retrieve the coordinates, label, and abstract of each birthplace
  ?birthPlace geo:lat ?latitude ;
              geo:long ?longitude ;
              rdfs:label ?label ;
              dbo:abstract ?abstract .
  
  # Filter actors born after 1950
  FILTER(STRDT(?birthDate, xsd:date) > "1950-01-01"^^xsd:date)
  
  # Filter birthplaces with a label in English
  FILTER(LANGMATCHES(LANG(?label), "en"))
  
} ORDER BY ?actorName






