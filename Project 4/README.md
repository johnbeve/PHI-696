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

Query 2. (Kata 4 - 10 points)

Mike learns that air companies offer mile-tickets for some lines, which can be purchased by their member accumulated mileage. In peak season, the 
"prices" of mile-tickets are much lower than the typical prices, given 100 member mileages is worth 1 dollar. Mike also learns that some credit card 
companies offer initial bonus, which typically are credit card points for people who intially apply for their credit cards and are approved. Also some 
credit cards have such a benefit that the credit card points can be transferred to mileages of some air companie, and the ratio is 1:1, which means one 
point can be transferred as one mileage. Some of the initial bonus can be more than 60,000 points (100 points is generally worth 1 dollar. So Mike thinks
that applying for a specific credit card is a way to save money to buy flight tickets. There is already an ever-updating dataset of credit cards offers 
(http://creditcardoffers.org/), so he wants to use the dataset and makes a Sparql query, called "credit card offer" to look for relevant credit card 
offers. 

Description of the offers (no more than 5 offers):
1) The credit card points can be transfer to one of UA, Delta, AA.
2) The initial bonus is more than 60,000 points.
3) The annual fee is less than 250 dollars.  
4) The spending requirement for the initial bonus is no more than 3000 dollars in the first three month of the account openning. 

``` 
PREFIX cdt: < http://creditcardoffers.org/type/ >
PREFIX cdo: < http://creditcardoffers.org/object/ >

SELECT ?cardName ?airCom ?iniPoints ?annFee ?spending 

WHERE{ 
   ?item cdt:label ?cardName;
         cdt:transfer_mile ?airCom.
	FILTER (str(?airCom)= "UA","AA","Delta")
	 cdt:initial_bonus ?iniPoints
	FILTER (?iniPoints > 60000)
	 cdt: annual_fee ?annFee
	FILTER (?annFee <= 200)
	 cdt:spending_req ?spending
	FILTER (?spending <= 3000)
}
LIMIT 5


```
Query 3. (Kata 2 -25 points)


Description: the politicians from politician families in China.

A politician P from politician family is defined as below:
1) One of P's biological parent is or was a politician; or
2) One of P's legal parent is or was a politician; or
3) One of P's spouse or ex-spouse is a politician; or
4) One of P's spouse's biological parent in law is or was a politician; or
5) One of P's spouse's legal parent is or was a politican; or
6) P is a Chinese citizen; and
7) P was born after 1949.

```

PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX wikibase: <http://wikiba.se/ontology#>

# politician from family

SELECT (COUNT (?item) AS ?numPoliticianFromFamily) (COUNT (?politician) AS ?totalPolitician)

WHERE {
  
  ?item wdt:P31 wd:Q5.          #instance of human.
  ?item wdt:P27 wd:Q148.        # a citizen of PR of China.  
  ?item wdt:P106 wd:Q82955.      # politician.
  {?item wdt:P22 ?father.       
         ?father wdt:P106 wd:Q82955.}         #item's father is a politician
  UNION {?item wdt:P25 ?mother.
               ?mother wdt:P106 wd:Q82955.}   # or item's mother is a politician
  UNION {?item wdt:P8810 ?parent.
               ?parent wdt:P106 wd:Q82955.}     #or item's one of parents(other than father and mother defined by P22 and P25).
  UNION {?item wdt:P3448 ?stepparent.
               ?stepparent wdt:P106 wd:Q82955.}.  #or item's one of stepparents is a politician. Noting that the content of P25, P8810, P3448 and P106 may overlap. 
  UNION {?item wdt:P26 ?spouse.
               ?spouse wdt:P106 wd:Q82955.}     #or item's spouse is a politician.     
  UNION {?item wdt:P26 ?spouse.
               ?spouse wdt:P22 ?sFather.
               ?sFather wdt:P106 wd:Q82955.}      #or item's spouse' father is a politician.
  UNION {?item wdt:P26 ?spouse.
               ?spouse wdt:P25 ?sMother.
               ?sMother wdt:P106 wd:Q82955.}      #or item's spouse' mothe is a politician.
  UNION {?item wdt:P26 ?spouse.
               ?spouse wdt:P8810 ?sParent.
               ?sParent wdt:P106 wd:Q82955.}      #or one of the item's spouse' parent is a politician.
  UNION {?item wdt:P26 ?spouse.
               ?spouse wdt:P3448 ?sStepparent.
               ?sStepparent wdt:P106 wd:Q82955.}. #or one of the item's spouse's stepparent is a politician. 
  
  ?item wdt:P569 ?dob.
  FILTER (?dob >= "1949-10-01"^^xsd:dateTime).   # item is borned later than Jan.1, 1949. 
  
  
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE], zh". } # Helps get the label in your language, if not, then zh language
} 


```

Query 4. (Kata 2 - 25 points)

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

```
#Law firms in the US

PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX wikibase: <http://wikiba.se/ontology#>

SELECT ?item ?itemLabel ?cityLabel ?yearFounded ?annualIncome2022 ?popurarity 
WHERE {
  ?item wdt:P31 wd:Q613142.   #item is an instance of law firm.                      
  ?item wdt:P17 wd:Q30.       #item is a US company. 
  
  FILTER (!{?item wdt:P31 wd:Q163740.} UNION {?item wdt:P31 wd:Q613142}). #exclude an institute which is both a law firm and a nonprofit orginzation.
  
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
    ?item wdt:P8687 ?popurarity #the number how many twitter followers.
    }
                
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". } # Helps get the label in your language, if not, then en language
}  

```
Then Jim creats a RDF-based remote database of US Law firms called "LF" (http://uslawfirms.org/), including the data collocted by runing the query. Since there is no data about how many lawyers in a lawfirm available in the items of the law firm, there is no such information in LF. However, through a query searching the lawyers whose employer is a lawform which is ?item in LF, and the COUNT function, the data that the number of lawyers working in the law firm can be retrieved from Wikidata (supposing that the data of lawyers in the US are completed). After that, Jim adds the data to the LF. 

The Sparql solution is displayed as below: 

```
PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX wikibase: <http://wikiba.se/ontology#>
PREFIX lf:<http://uslawfirms.org/>

SELECT ?itemLF (COUNT (?lawyer) AS ?numOfLawyers)

WHERE {
    
    lf:item lf:itemCode ?itemLF
    ?lawyer wdt:P108 ?itemLF. 
    ?lawyer wdt:P31 wd:Q5.    #?lawyer is a human. 
    }  
GROUP BY ?itemLF

INSERT {
    ?item lf: numOfLawyers ?numOfLawyers.
        WHERE{
	
	lf:item lf:numOfLawyers ?numOfLawyers
	       
	}    
    }
  
}


```

