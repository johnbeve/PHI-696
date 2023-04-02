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

Query 1. (Kata 8)

Description (and problem):

There is a dispute about when Buffalo_Bills was founded. Using a SPARQL query, to retrieve the date when Buffalo_Bills was founded. 


Reference Solution (and answer):

PREFIX dbo: <http://dbpedia.org/ontology/>
PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX dbp: <http://dbpedia.org/property/>

SELECT ?date
WHERE {
  dbr:Buffalo_Bills dbp:founded ?date.
}


Query 2. (Kata 4)

Description:

The company H collcets legal cases and sells the relevant databases, such as case data, case briefs collections, etc. In order to be aware the target 
clients, the marketing manager Julia wants her secratory Jim to do the research of law firms in the US. She wants to establish a database of law firms
(the annual income > USD.5,000,000), including the following inforamtion:  
1) the name of the law firm.
2) the city in which the law firm or its headquarter locates.
3) the number of years since the law firm has founded.
4) the number of lawyers in the law firm.
5) the number of anual income in the last year.
6) the popularity of the law firm. 

The secratory Jim plans to use his SPARQL knowledge and Wikidata Query Service to do the research. Jim names the query "Law firms in the US."

# Law firms in the US

PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX wikibase: <http://wikiba.se/ontology#>

SELECT ?item ?itemLabel ?cityLabel (COUNT (?lawyer) AS ?numOfLawyers) ((2023  - ?yearFounded) AS ?numOfYears) ?annualIncome2022 ?popurarity 
WHERE {
  ?item wdt:P31 wd:Q613142.   #item is an instance of law firm.                      
  ?item wdt:P17 wd:Q30.       #item is a US company. 
  
  FILTER (!(?item wdt:P31 wd:Q163740.)).
  
  OPTIONAL {
    ?item wdt:P159 ?city.     #city is the law firm's headquarter location.
    }
  
  OPTIONAL {
    ?item wdt:P571 ?yearFounded. #yearFound is the year when the law firm founded.
    }
 
  OPTIONAL {
    ?item wdt:P2139 ?annualIncome2022.     #annualIncome2022 is the number of dollors of the law firm's income in 2022.
    FILTER (?annualIncome2022 > 5000000).  #only the law firms whose income is more than 5 million dollars are listed. 
    }
  
  OPTIONAL {
    ?lawyer wdt:P108 ?item.  #since there is no data about how many lawyers in a law firm, I use COUNT to count the number lawyers whose emplyor is the law firm.
    }     
  
  OPTIONAL {
    ?item wdt:P8687 ?popurarity #the number how many twitter followers.
    }
                
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". } # Helps get the label in your language, if not, then en language
}  

Query 3. (Kata 2)



