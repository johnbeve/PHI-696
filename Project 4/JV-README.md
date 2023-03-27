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

** Jonathan's Kata's for SPARQL **

Comment: I've attempted 20 problems.

**Problem 1.**

Setup prompt
- The following catalog contains camera products, according to their product name (ontocam:productName), model number (ontocam:modelValue), manufacturer (ontocam:manufacturer) and release date (ontocam:releaseDate).
- Find all camera products manufactured by Canon, displaying their name, model number, release date.

```
PREFIX ontocam: <https://aperturescience.org/onto/>

SELECT ?deviceLabel ?productName ?modelValue ?manufacturer ?releaseDate
WHERE {
      ?device ontocam:manufactured_by ontocam:Canon .
}
```
- Difficulty level: KATA-8
- Running total points? 0


**Problem 2.**

Setup prompt
- List all of the people who have been president in the United States of America. The ontology does not have a 'president' class but rather a 'PresidentRole' that the individual bears. Be careful to stipulate that the role has presidential authority in the United States.
- Who has been a president of the USA at some time?

```
PREFIX obo: <http://purl.obolibrary.org/obo/ro.owl>
PREFIX ontopol: <https://politicalontology.org/schema/ontopol.ttl>

SELECT ?subject
WHERE {
      ?subject obo:has_role ?PresidentialRole
      ?PresidentialRole ontopol:authority_in ontopol:United_States.
    }
```
- Difficulty level: KATA-7
- Running total points? (0 + 2) = 2


**Problem 3.**

Setup prompt
- A local militia group wants to rally potential troops for a coup and has access to the state of Oregon registry to look up demographic information. They only want to find males age 16 and older.
- Find all males’ 16 years or older, and their mailing addresses.

```
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
PREFIX ontopol: <https://politicalontology.org/schema/ontopol.ttl>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

SELECT ?subject ?mbox
WHERE {
      ?subject foaf:birthday ?birthDate .
      ?subject foaf:gender “male” .
      ?subject foaf:mbox ?mbox .
      FILTER (?birthdate < "2007-03-27T00:00:00+05:30"^^xsd:dateTime)
}
```
- Difficulty level: KATA-7
- Running total points? (0 + 2 + 2) = 4

**Problem 4.**

Setup prompt
- You’re an IT administrator working with a printer support maintenance contractor to update and replace parts for covered assets such as the Brother brand printers on site. You want to prioritize those printers that are on the network and display a warning status, especially for “low” toner.
- Get all printers on the network that have model made by Brother and which have a warning status on “high”, optional: get their toner level status

```
PREFIX itdev: <https://www.rando.org/ontology/>
 
SELECT ?printerDevice ?warningStatus
WHERE {
      ?printer itdev:manufactured_by itdev:Brother .
      ?printer itdev:device_status ?warningStatus .
      ?warningStatus itdev:severity_level “High” .
      OPTIONAL SELECT { ?warningStatus itdev:toner_value “Low” .}
}
```
- Difficulty level: KATA-6
- Running total points? (0 + 2 + 2 + 3) = 7

**Problem 5.**

Setup prompt
- A customer is searching for shelving and wants to filter results in a catalog online, with specific functionality and material type and within a price range.
- Get the USD price for all shelves that are not two-shelf, that cost less than $150 USD, and are made out of wood rather than wire frame.

```
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>
PREFIX bfo: <http://purl.obolibrary.org/obo/bfo.owl>
PREFIX homedev: <http://homeandgarden.com/ontology/>

SELECT ?shelves ?salePriceValueUSD
WHERE {
  ?shelves bfo:instance_of homedev:Shelf ;
           ro:bearer_of ?function ;
           ro:composed_primarily_ of ?material ;
           homedev:has_sale_price ?salePriceValueUSD .
  FILTER (?function != homedev:twoShelf && 
          ?salePriceValueUSD < 150 && 
          ?material = homedev:woodMaterial && 
          ?material != homedev:metalwireMaterial)
}

```
- Difficulty level: KATA-5
- Running total points? (0 + 2 + 2 + 3 + 5) = 12
