This file contains 14 level 7 katas, 11 level 6 katas, 7 level 5 katas, and 1 level 4 kata,
for a total of 100 points.
I have privileged low level katas for a number of reasons. First of all, I am myself a beginner in
SPARQL, and I felt more comfortable in devising easier exercises, solutions and descriptions.
Secondly, in the perspective of building a set of exercises to kickstart people into using
SPARQL, I feel that providing a large range of basic exercises to train on is a good place
to start. Incidentally, I believe this is a potential weakness for some of the languages in
Codewars.

For the exercises I have written down a set of simplistic "toy" rdf schemas, usually employing
an example.org URI. In order to make this file more readable, I will now list the schemas
and will then refer to them in the exercises as the "people schema", "border schema", etc.
Nevertheless, when we upload them to Codewars, I believe that the rdf schemas should be entirely
written down for each exercise.

Incidentally, OpenAI/ Chatgpt was used to help with a lot of these questions. I believe it
might be interesting to provide an explanation of how that was done for the purposes of 
explaining the relation between AI and SPARQL. I will write a report on that in the next days. 


Traveler schema:

ex:travelers a rdfs:Class . 
ex:has_name a rdf:Property; 
             rdfs:domain ex:Traveler ;
             rdfs:range xsd:string . 
ex:has_country a rdf:Property; 
                rdfs:domain ex:Traveler ;
                rdfs:range xsd:string .
ex:has_id a rdf:Property ;
          rdfs:domain ex:Traveler ;
          rdfs:range xsd:string .

Trips schema:


ex2:Trip a rdfs:Class .

ex2:has_traveler a rdf:Property ;
                 rdfs:domain ex2:Trip ;
                 rdfs:range ex:travelers .

ex2:has_country a rdf:Property ;
                rdfs:domain ex2:Trip ;
                rdfs:range xsd:string .

Products schema:
@prefix ex: <http://example.org/products/> .

ex:Product rdf:type rdfs:Class .
 ex:id rdf:type rdf:Property ;
     rdfs:domain ex:Product ;
     rdfs:range xsd:string .

ex:has_name rdf:type rdf:Property ;
           rdfs:domain ex:Product ;
           rdfs:range xsd:string .

ex:has_isbn rdf:type rdf:Property ;
           rdfs:domain ex:Product ;
           rdfs:range xsd:string .

ex:has_price rdf:type rdf:Property ;
            rdfs:domain ex:Product ;
            rdfs:range xsd:decimal .

ex:belongs_to rdf:type rdf:Property ;
             rdfs:domain ex:Product ;
             rdfs:range ex2:Company .

ex:has_company_id rdf:type rdf:Property ;
                  rdfs:domain ex:Product ;
                  rdfs:range xsd:string .

ex:has_company_name rdf:type rdf:Property ;
                    rdfs:domain ex:Product ;
                    rdfs:range xsd:string .

Company schema:

@prefix ex2: <http://example.org/companies/> .


ex2:Company rdf:type rdfs:Class .
ex2:id rdf:type rdf:Property ;
      rdfs:domain ex2:Company ;
      rdfs:range xsd:string .

ex2:has_name rdf:type rdf:Property ;
            rdfs:domain ex2:Company ;
            rdfs:range xsd:string .

People schema:

@prefix people: <http://example.org/people#>.

people: a rdfs:Class;
          rdfs:label "Person"; 
          rdfs:subClassOf owl:Thing. 

people:id a owl:DatatypeProperty;
            rdfs:comment "The unique identifier of a person."; 
            rdfs:domain people:Person; 
            rdfs:range xsd:integer. 

people:name a owl:DatatypeProperty; 
            rdfs:label "Name";
            rdfs:comment "The name of a person."; 
            rdfs:domain people:Person;
            rdfs:range xsd:string. 

people:age a owl:DatatypeProperty; 
             rdfs:comment "The age of a person."; 
             rdfs:domain people:Person; 
             rdfs:range xsd:integer.

Card store schema:

@prefix ex: <http://example.com/> . 
ex:Department rdf:type rdfs:Class ;
              rdfs:label "Department" . 

ex:Sale rdf:type rdfs:Class ;
        rdfs:label "Sale" . 

ex:hasDepartment rdf:type rdf:Property ;
                 rdfs:domain ex:Sale ; 
                 rdfs:range ex:Department ;

ex:departmentId rdf:type rdf:Property ;
                rdfs:domain ex:Sale ; 
                rdfs:range xsd:int ; 

ex:name rdf:type rdf:Property ; 
        rdfs:domain ex:Department, ex:Sale ; 
        rdfs:range xsd:string ;  

ex:price rdf:type rdf:Property ; 
         rdfs:domain ex:Sale ; 
         rdfs:range xsd:float ; 

ex:cardName rdf:type rdf:Property ; 
            rdfs:domain ex:Sale ;
            rdfs:range xsd:string ; 

ex:cardNumber rdf:type rdf:Property ; 
              rdfs:domain ex:Sale ;
              rdfs:range xsd:string ; 

ex:transactionDate rdf:type rdf:Property ;
                     rdfs:domain ex:Sale ; 
                     rdfs:range xsd:date ; 

Modified-dbpedia schema:

@prefix dbpedia: <http://dbpedia.org/resource/> 
@prefix dbpprop: <http://dbpedia.org/property/> 
dbpedia:continent rdf:type rdfs:Class
                  rdfs:label "A continent"; 
                  rdfs:subClassOf owl:Thing.

dbpedia:country rdf:type rdfs:Class
                  rdfs:label "A country"; 
                  rdfs:subClassOf owl:Thing.

dbpprop:has_continent a rdf:Property;
                       rdfs:domain  dbpedia:country;
                       rdfs:range dbpedia:continent.

dbpprop:has_capital a rdf:Property;
                      rdfs:domain  dbpedia:country;
                      rdfs:range dbpedia:capital.

dbpprop:has_name a rdf:Property;
                      rdfs:domain dbpedia:resource;
                      rdfs:range xsd:string.

Events schema:

@prefix ex: <http://example.org/> . 

ex:Event rdf:type rdfs:Class ;
            rdfs:label "Event" . 

ex:createdAt rdf:type rdf:Property ;
                    rdfs:domain ex:Event ; 
                    rdfs:range xsd:dateTime ; 
                    rdfs:label "Created At" . 

ex:description rdf:type rdf:Property ;  
                      rdfs:domain ex:Event ; 
                      rdfs:range xsd:string ; 
                      rdfs:label "Description" .

Bookshop schema:

@prefix dc: <http://purl.org/dc/elements/1.1/>
@prefix ex: <http://example.org/>


ex:Book a rdfs:Class .
ex:author a rdf:Property ;
          rdfs:domain ex:Book ;
          rdfs:range xsd:string .

ex:copies_sold a rdf:Property ;
          rdfs:domain ex:Book ;
          rdfs:range xsd:integer .

dc:title a rdf:Property ;
          rdfs:domain ex:Book ;
          rdfs:range xsd:string .

Book review schema:

ex:Review rdf:type rdfs:Class ;
  rdfs:label "Review" .

ex:genre rdf:type rdf:Property ;
  rdfs:label "Genre" ;
  rdfs:range ex:Genre .

ex:publisher rdf:type rdf:Property ;
  rdfs:label "Publisher" ;
  rdfs:range ex:Publisher .

ex:reviewer rdf:type rdf:Property ;
  rdfs:label "Reviewer" ;
  rdfs:range ex:Person .

ex:rating rdf:type rdf:Property ;
  rdfs:label "Rating" ;
  rdfs:range xsd:integer .

ex:Person rdf:type rdfs:class ;
  rdfs:label "Person”.

Person schema:

@prefix ex: <http://example.org/> .

ex:Person a rdfs:Class .

ex:hasPrefix a rdf:Property ; 
               rdfs:domain ex:Person ; 
               rdfs:range xsd:string .
ex:hasFirstName a rdf:Property ; 
                rdfs:domain ex:Person ; 
                rdfs:range xsd:string .
ex:hasLastName a rdf:Property ; 
               rdfs:domain ex:Person ; 
               rdfs:range xsd:string .
ex:hasSuffix a rdf:Property ; 
             rdfs:domain ex:Person ; 
             rdfs:range xsd:string .

Rental schema:

@prefix xsd: <http://www.w3.org/2001/XMLSchema#>
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
@prefix payment: <http://example.org/payment#> 
@prefix staff: <http://example.org/staff#>
@prefix customer: <http://example.org/customer#>
@prefix rental: <http://example.org/rental#>

payment:Payment rdf:type rdfs:Class.

staff:Staff rdf:type rdfs:Class.

customer:Customer rdf:type rdfs:Class.

rental:Rental rdf:type rdfs:Class.

payment:madeBy rdf:type rdf:Property;
  rdfs:domain payment:Payment;
  rdfs:range staff:Staff.

payment:belongsTo rdf:type rdf:Property;
  rdfs:domain payment:Payment;
  rdfs:range rental:Rental.

payment:paidBy rdf:type rdf:Property;
  rdfs:domain payment:Payment;
  rdfs:range customer:Customer.

staff:id rdf:type rdf:Property;
  rdfs:domain staff:Staff;
  rdfs:range xsd:integer.

rental:id rdf:type rdf:Property;
  rdfs:domain rental:Rental;
  rdfs:range xsd:integer.

customer:id rdf:type rdf:Property;
  rdfs:domain customer:Customer;
  rdfs:range xsd:integer.

payment:amount rdf:type rdf:Property;
  rdfs:domain payment:Payment;
  rdfs:range xsd:decimal.

payment:payment_date rdf:type rdf:Property;
  rdfs:domain payment:Payment;
  rdfs:range xsd:dateTime.

Sales schema:

@prefix ex: <http://example.com/> .

ex:Product rdf:type rdfs:Class .
ex:Sale rdf:type rdfs:Class .
ex:SalesDetail rdf:type rdfs:Class .

ex:id rdf:type rdf:Property ;
     rdfs:domain ex:Product, ex:Sale, ex:SalesDetail ;
     rdfs:range xsd:int .

ex:name rdf:type rdf:Property ;
       rdfs:domain ex:Product ;
       rdfs:range xsd:string .

ex:price rdf:type rdf:Property ;
        rdfs:domain ex:Product ;
        rdfs:range xsd:decimal .

ex:date rdf:type rdf:Property ;
       rdfs:domain ex:Sale ;
       rdfs:range xsd:date .

ex:sale_id rdf:type rdf:Property ;
          rdfs:domain ex:SalesDetail ;
          rdfs:range xsd:int .

ex:product_id rdf:type rdf:Property ;
             rdfs:domain ex:SalesDetail ;
             rdfs:range xsd:int .

ex:count rdf:type rdf:Property ;
        rdfs:domain ex:SalesDetail ;
        rdfs:range xsd:int .
        
---------------------------------------------------------------------------------------------

Here are the exercies. Apologies in advance for the ones where I may have forgotten to specify
the schema we are querying.

Description Level 7:

This was originally a level 8 kata, but for our purposes should be at least a level 7:

Taken from “On the Canadian Border (SQL for Beginners #2)”, a SQL exercise on Codewars from https://www.codewars.com/users/MaikelNabil  

Description: 

You are a border guard sitting on the Canadian border. You were given a list of travelers who have arrived at your gate today. You know that American, Mexican, and Canadian citizens don't need visas, so they can just continue their trips. You don't need to check their passports for visas! You only need to check the passports of citizens of all other countries!

Select names, and countries of origin of all the travelers, excluding anyone from Canada, Mexico, or The US.

Starting info for the traveler graph:

ex:travelers a rdfs:Class . 
ex:has_name a rdf:Property; 
             rdfs:domain ex:Traveler ;
             rdfs:range xsd:string . 
ex:has_country a rdf:Property; 
                rdfs:domain ex:Traveler ;
                rdfs:range xsd:string .
ex:has_id a rdf:Property ;
          rdfs:domain ex:Traveler ;
          rdfs:range xsd:string .


NOTE: The United States is written as 'USA' in the table.



Reference solution:

@prefix ex: <http://example.org/travelers/> 
SELECT DISTINCT ?name ?country 
WHERE { 
?traveler ex:has_name ?name ; 
          ex:has_country ?country . 
FILTER (?country != "USA" && ?country != "Mexico" && ?country != "Canada") 
}


Level 8 version:

You are a border guard sitting on the Canadian border. You were given a list of travelers who have arrived at your gate today.

Select countries of origin of all the travelers, without repeating them.

Traveler graph


Reference solution:

prefix ex: <http://example.org/travelers/> 
SELECT DISTINCT ?country 
WHERE { 
?traveler ex:has_country ?country .
}

Description level 6:

Take the previous country schema. You are now asked to retrieve the name of the visitor that has gone to most countries, and the number of countries they have visited. Results should be offered in two columns called ?travelername and ?numCountries

Reference solution:

@prefix ex: <http://example.com/travel#>
@prefix ex2: <http://example.com/trip#>

SELECT ?travelerName (COUNT(DISTINCT ?country) AS ?numCountries) WHERE {
  ?traveler a ex:Traveler ;
             ex:has_name ?travelerName .
  ?trip a ex2:Trip ;
        ex2:has_country ?country ;
        ex2:has_traveler ?traveler .
} GROUP BY ?travelerName
  ORDER BY DESC(?numCountries)
  LIMIT 1



Description level 6:

Take now the previous schema and consider another schema called trips,  whose purpose is to store information about the trips that people crossing the border have taken.

Notice that ex2:has_country and ex:has_country are different properties, and they mean different things. 
You are now asked to retrieve a list of all the travelers’ names, alongside with a list of how many trips they have taken and to which country. You need to build a result table that has a ?name variable, a ?country variable and a ?numTrips variable that sorts out how many times each traveler went to a country. Also, you want to have a column for ?id

Reference solution:
 SELECT ?id ?name ?country (COUNT(?trip) AS ?numTrips)
WHERE {
  ?trip ex2:has_traveler ?traveler ;
        ex2:has_country ?country .
  ?traveler ex:has_id ?id ;
            ex:has_name ?name .
}
GROUP BY ?id ?name ?country

Description level 7
Take the previous schema, with both ex1 and ex2. You are now asked to retrieve a list of all the traveler names and places they travelled to. The result should be stored in two columns called ?travelerName and ?tripCountry. Also make sure that the result doesn’t have repeated entries.

Reference solution:

@prefix ex: <http://example.org/travelers#>
@prefix ex2: <http://example.org/trips#>

SELECT DISTINCT ?travelerName ?tripCountry
WHERE {
  ?traveler ex:has_name ?travelerName ;
            ex:has_country ?travelerCountry .
  ?trip ex2:has_traveler ?traveler ;
        ex2:has_country ?tripCountry .
}


Description Level 7

Starting from the traveler schema, you are now asked to retrieve the five countries that
have had the higher number of visitors, and order them in descending order. The result 
should be stored in two columns, ?country and ?numVisits.

Reference solution: 

@prefix ex: <http://example.com/travel#>
@prefix ex2: <http://example.com/trip#>

SELECT ?country (COUNT(?traveler) AS ?numVisits) WHERE {
  ?trip a ex2:Trip ;
        ex2:has_country ?country .
  ?traveler a ex:Traveler ;
             ex2:has_traveler ?trip .
} GROUP BY ?country
  ORDER BY DESC(?numVisits)
  LIMIT 5


Description Level 6

Take the previous schema. You are now tasked with retrieving a list of the people who 
have visited the same country (at least) twice in the same year. You just need to sort your results in a 
single column called ?traveler.

Reference solution:

?SELECT ?traveler
WHERE {
  ?trip1 a ex2:Trip ;
         ex2:has_traveler ?traveler ;
         ex2:has_country ?country .
         ex2:has_year ?year .
  ?trip2 a ex2:Trip ;
         ex2:has_traveler ?traveler ;
         ex2:has_country ?country .
         ex2:has_year ?year .
  FILTER (?trip1 != ?trip2)
}
GROUP BY ?traveler


Description Level 7

Level 7 kata called [SQL Basics: Simple JOIN] (https://www.codewars.com/kata/5802e32dd8c944e562000020)   from   [jhoffner](https://www.codewars.com/users/jhoffner)

For this challenge you need to create a simple SELECT statement that will return all columns from the ex:Product class, and join to the ex2:Company table so that you can return the company name. The result will then need to show the following data:

?id ?name ?isbn ?companyId ?price ?companyName 


The rdf schema you are querying is the product and the company schema.



Reference solution:

@prefix ex: <http://example.org/products/>
@prefix ex2: <http://example.org/companies/> 
SELECT ?id ?name ?isbn ?companyId ?price ?companyName 
WHERE {   
?product ex:id ?id ;          
               ex:has_name ?name ;           
               ex:has_isbn ?isbn ;           
               ex:has_company_id ?companyId ;            
               ex:has_price ?price ;            
               ex:has_company_name ?companyName .     
?company ex2:id ?companyId ;           
         ex2:has_name ?companyName . 
}


Description level 7 

Against the same rdf graph as before, you are now asked to retrieve the average price of products for each company. The resulting query should then have columns ?companyName and ?averagePrice

Reference solution:

@prefix ex: <http://example.org/products/>
@prefix ex2: <http://example.org/companies/>

SELECT ?companyName (AVG(?price) AS ?avgPrice)
WHERE {
  ?product ex:has_price ?price ;
           ex:belongs_to ?company .
  ?company ex2:has_name ?companyName .
}
GROUP BY ?companyName


Description (Level 5)

Take the products and companies graphs. You are now asked to retrieve the companies that 
sell products that match a certain pattern in their name. In this case, their name must
start with “Product".You also need to count how many of these 
products are sold by each company, and also retrieve only companies that sell at least 2 of
compatible matching products. Finally, order the result (which should have a column called 
?companyName and one called ?productCount) by descending order.

Reference solution:

@prefix ex: <http://example.org/products/>
@prefix ex2: <http://example.org/companies/>

SELECT ?companyName (COUNT(?product) AS ?productCount)
WHERE {
  ?product ex:has_price ?price ;
           ex:belongs_to ?company ;
           ex:has_name ?productName .
  ?company ex2:has_name ?companyName .
  FILTER regex(?productName, "^Product")
}
GROUP BY ?companyName
HAVING (COUNT(?product) > 1)
ORDER BY DESC(?productCount)


Description Level 6:

Starting from the previous schema, you are asked to retrieve the name of all the departments that sell a product that has the ISBN “12345”. You are then asked to calculate the sum of all the revenue made by each company.

Reference solution:

@prefix ex: <http://example.org/products/>
@prefix ex2: <http://example.org/companies/>

SELECT ?companyName (SUM(?price) AS ?revenue)
WHERE {
  ?product ex:has_isbn "1234567890" ;
           ex:belongs_to ?company ;
           ex:has_price ?price .
  ?company ex2:has_name ?companyName ;
           ex2:id ?companyId .
}
GROUP BY ?companyName

Description level 7:

Source: Level 8 Simple MAX/MIN from matt c (https://www.codewars.com/kata/581113dce10b531b1d0000bd)

For this challenge you need to create a simple MIN / MAX statement that will return the
Minimum and Maximum ages out of all the people.
You are querying the people schema.

Reference solution:

@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>. 
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#>. 
@prefix xsd: <http://www.w3.org/2001/XMLSchema#>.
@prefix people: <http://example.org/people#>.
SELECT (MIN(?age) AS ?age_min) (MAX(?age) AS ?age_max) 
WHERE { 
?person people:age ?age . 
}


Description level 7: 

Starting from the people schema, you are asked to retrieve a list of all the people who
are older than 30 years old and whose first name is “John”. Notice that you don’t want to 
accidentally include people whose last name is something like “Johnson”.

Reference solution:

@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#>
@prefix xsd: <http://www.w3.org/2001/XMLSchema#>
@prefix people: <http://example.org/people#>

SELECT ?person ?name ?age ?address ?city
WHERE {
  ?person rdf:type people:Person .
  ?person people:name ?name .
  ?person people:age ?age .
  FILTER (?age > 30)
  FILTER (strstarts(?name, "John"))

Description Level 7:

Take the people schema, and add a property

people:address a owl:ObjectProperty; 
                 rdfs:label "Address";
                 rdfs:domain people:Person; 
                 rdfs:range xds:string. 

You are now asked to retrieve the list of all the people who do not have a stable address, i.e. people for whom we didn’t store a specific address.

@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#>
@prefix xsd: <http://www.w3.org/2001/XMLSchema#>
@prefix people: <http://example.org/people#>

SELECT ?person ?name ?age
WHERE {
  ?person rdf:type people:Person .
  ?person people:name ?name .
  ?person people:age ?age .
  FILTER NOT EXISTS {
    ?person people:address ?address .
  }
}

Description level 5:

Take the people schema and add a property


people:city a owl:DatatypeProperty; 
              rdfs:label "The city where a person lives or has lived in"; 
              rdfs:domain people:Person; 
              rdfs:range xsd:string. 

You are now asked to retrieve the list of all the people. In addition to that,
there is a specific kind of people who have lived in at least two cities. 
You are asked to produce a column of strings called ?cities which is a list of all of the 
cities where these people have lived. Remember that the name of a city could appear twice, 
and we do not want to count duplicates.
Notice that you still should also get names for all the other people too in a column called 
?name, as well as a column called ?age. Finally, notice that we are only interested in 
individuals who are older than 18.

Reference solution:

SELECT ?name ?age (GROUP_CONCAT(DISTINCT ?city; SEPARATOR=",") as ?cities)
WHERE {
  ?person rdf:type people:Person ;
          people:name ?name ;
          people:age ?age .
  OPTIONAL {
    ?person people:address ?address .
    ?person people:city ?city .
  }
  FILTER (?age >= 18)
}
GROUP BY ?name ?age
HAVING (COUNT(DISTINCT ?city) >= 2)
ORDER BY ?name

Description: I am trying to make a level 5 with some math I don’t know anything about:

You are asked to retrieve from the people schema as before the people whose age equals the
median of the dataset. You are using the people schema.

Reference solution:

@prefix people: <http://example.org/people#> 
SELECT DISTINCT ?person 
WHERE { 
{ 
SELECT 
(AVG(?age) AS ?median) 
WHERE {
?person people:age ?age .
} 
GROUP BY ?person 
ORDER BY ?median
LIMIT 2
OFFSET 1 
} 
?person people:age ?age .
FILTER (?age = ?median)
}

(Limit 2 is used to take the two bigger medians, Order By is used to have the bigger 
as second, offset is used to skip the first result)


Original source is Level 8 simple DISTINCT from matt c  https://www.codewars.com/kata/58111670e10b53be31000108/train/sql

Description (Level 8)

From the previous rdf schema (no need to copy it here, I don’t want to clog the Google Doc), select all the distinct ages recorded in the data. 

Reference solution: 

SELECT DISTINCT ?age 
WHERE  { 
?person people:age ?age . 
}


Taken from Level 7 Simple GROUP BY from matt c
https://www.codewars.com/kata/58111f4ee10b5301a7000175/train/sql

Description (Level 7 version of the previous)

From the people rdf schema, select all the distinct ages recorded in the data, alongside with how many people have them

Reference solution:

SELECT DISTINCT ?age (COUNT(?person) AS ?num_people) 
WHERE { 
?person people:age ?age .
} 
GROUP BY ?age


Description Level 6

Taken from Level 6 simple EXISTS from matt c
https://www.codewars.com/kata/58113a64e10b53ec36000293/train/sql

For this challenge you need to create a SELECT statement that will contain data about 
departments that had a sale with a price over 98.00 dollars. This SELECT statement will have 
to use an EXISTS to achieve the task.

You are using the card store schema.

Reference solution:

@prefix ex: <http://example.com/>

SELECT ?name ?id
WHERE {
  ?dept a ex:Department ;
        ex:name ?name ;
        ex:departmentId ?id .
  FILTER EXISTS {
    ?sale a ex:Sale ;
          ex:hasDepartment ?dept ;
          ex:price ?price .
    FILTER (?price >= 98.0)
  }
}


Level 6 Description:

Source is level 6 kata simple JOIN and RANK from matt.c 
https://www.codewars.com/kata/58094559c47d323ebd000035/solutions

Add to the card store schema the property


ex:people_id a owl:ObjectProperty ;
          rdfs:comment "The ID of the person associated with the sale." ;
              rdfs:domain ex:Sale ;
              rdfs:range xsd:integer ;
              
This property refers to the :people RDF schema we have seen in previous exercise. Again, no need to copy it on the Google Doc. Now, retrieve a list of all the people and rank them on the basis of how much they spend as recorded by the Sale resource. Notice that you need to use the RANK function.

Reference solution

@prefix ex: <http://example.org/> 
@prefix people: <http://example.org/people#>.
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> 
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> 
SELECT ?id ?name 
(COUNT(?sale) AS ?sale_count)
(RANK() OVER(ORDER BY DESC(COUNT(?sale))) AS ?sale_rank) 
WHERE { 
?person rdf:type people:Person ; 
             people:id ?id ; 
             people:name ?name . 
?sale rdf:type ex:Sale ; 
      ex:people_id ?id . 
} 
GROUP BY ?id ?name 
ORDER BY DESC(?sale_count)


Description level 6:

Start from the card store schema. You are now requested to find where people have been 
shopping, i.e. in which department. List the persons by id. 

Reference Solution:

SELECT ?name ?id
WHERE { 
?person rdf:type people:Person ; 
             people:id ?id ; 
?sale rdf:type ex:Sale ; 
      ex:people_id ?id . 
      ex:departmentID ?dept_id
?department ex:name ?name
}


Description Level 7: 

Taken from level 7 kata Countries capitals for trivia night from MaikeINabil 
https://www.codewars.com/kata/5e5f09dc0a17be0023920f6f

Your friends told you that if you keep coding on your computer, you are going to hurt your
eyes. They suggested that you go with them to trivia night at the local club.

Once you arrive at the club, you realize the true motive behind your friends' invitation. 
They know that you are a computer nerd, and they want you to query the `countries` RDF schema and get the answers to the trivia questions.

The first question: from the African countries that start with the character E, get the 
names of their capitals ordered alphabetically.
In order to do so, you go to dbpedia and decide to make SPARQL queries to answer questions.

-   You should only give the names of the capitals. Any additional information is just noise
-   If you get more than 3, you will be kicked out, for being too smart

You are querying the modified-dbpedia schema.


Reference Solution:

@prefix dbpedia: <http://dbpedia.org/resource/> 
@prefix dbpprop: <http://dbpedia.org/property/> 
SELECT ?capital 
WHERE { 
?country dbpprop:has_continent dbpedia:Africa> ;
         dbpprop:capital ?capital. 
         dbprop:has_name ?countryname
FILTER(STRSTARTS(?countryname, "E")) 
} 
ORDER BY ?capital 
LIMIT 3


Level 6 description:

Starting from the modified-dbpedia schema you are now requested to give all the countries in Europe that have a capital whose name starts with “R”.

Reference solution:

@prefix dbpedia: <http://dbpedia.org/resource/> 
@prefix dbpprop: <http://dbpedia.org/property/> 
SELECT ?country
WHERE { 
?country dbpprop:has_continent dbpedia:Europe> ;
         dbpprop:capital ?capital. 
?capital dbprop:has_name ?capitalname
FILTER(STRSTARTS(?capitalname, "R")) 
} 


Description level 5:
Level 5 kata from jhoffner GROUP BY day, 
https://www.codewars.com/kata/5811597e9d278beb04000038/train/sql

There is an `events` RDF graph used to track different key activities taken on a website.
For this task you need to:

-   find the entries whose `name` equals `"trained"`
-   group them by the `day` the activity happened (the date part of the `created_at` 
timestamp) and their `description`'s
-   the 2 aforementioned fields should be returned together with the number of grouped
entries in a column called `count`
-   the result should also be sorted by `day`

You are querying the events table

Reference solution:

SELECT ?day ?description (COUNT(* ) AS ?count)
WHERE {
  ?event rdf:type ex:Event ;
         ex:createdAt ?created_at ;
         ex:description ?description .
  FILTER (CONTAINS(lcase(str(?description)), "trained"))
  # Extract the day from the date
  BIND(day(?created_at) AS ?day)
}
GROUP BY ?day ?description

Level 7 description:
Level 7 kata from MaikeINabil Best-selling books
https://www.codewars.com/kata/591127cbe8b9fb05bd00004b/train/sql

You work at a bookstore. It's the end of the month, and you need to find out the 5 bestselling books at your store. Use a select statement to list names, authors, and number of copies sold of the 5 books which were sold most.

You are using the bookshop schema.

Reference solution:

@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
@prefix ex: <http://example.org/>
@prefix dc: <http://purl.org/dc/elements/1.1/>

SELECT ?name ?author ?copies_sold 
WHERE {
  ?book rdf:type ex:Book ;
            dc:title ?name ;
            ex:author ?author ;
            ex:copies_sold ?copies_sold .
}
ORDER BY DESC(?copies_sold) 
LIMIT 5


Description Level 7:

Using the same book schema as before, find the five authors that have sold the least copies, 
so that your boss can decide whether they need to stop selling books from these authors.


Reference solution:

@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
@prefix ex: <http://example.org/>
@prefix dc: <http://purl.org/dc/elements/1.1/>

SELECT ?author (SUM(?copies_sold) AS ?total_copies_sold)
WHERE {
  ?book rdf:type ex:Book ;
        ex:author ?author ;
        ex:copies_sold ?copies_sold .
}
GROUP BY ?author
ORDER BY ASC(?total_copies_sold) 
LIMIT 5

Level 6 Description:

Let’s now say that to the book schema we add the book review schema.
Knowing that there is a resource called ex:Mystery that is a genre, and a resource called 
ex:Acme that is a publisher, can you find the books that have received a grade higher than 4,
of genre Mistery, and published by Acme?

Reference solution:

@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
@prefix ex: <http://example.org/>
@prefix dc: <http://purl.org/dc/elements/1.1/>
@prefix foaf: <http://xmlns.com/foaf/0.1/>

SELECT ?book ?title ?author ?publisher ?genre ?person
WHERE {
  ?book rdf:type ex:Book ;
        dc:title ?title ;
        ex:author ?author ;
        ex:publisher ?publisher ;
        ex:genre ?genre .
  
  ?person rdf:type foaf:Person ;
  
  ?review rdf:type ex:Review ;
          ex:book ?book ;
          ex:reviewer ?person ;
          ex:rating ?rating .
  
  FILTER(?rating >= 4 && ?genre = ex:Mystery && ?publisher = ex:Acme)
}


Level 5 Description: 

Level 6 kata from matt c, NULL handling, 
https://www.codewars.com/kata/5811315e04adbbdb5000050e/solutions

You are using the card shop schema. For this challenge you need to create a SELECT statement,
this statement must have NULL handling, using COALESCE and NULLIF.

If name is an empty string, you must replace with '[product name not found]'.

If card_name is an empty string, you must replace with '[card name not found]'.

If no price is specified (i.e. price is NULL), or if the price is 50 or less, you must
discard the row.

You are asked to retrieve ?id ?name ?price ?card_name ?card_number ?transaction_date and 
consider that name, cardname and cardnumber could be blank.

Reference solution:

SELECT ?id ?name ?price ?card_name ?card_number ?transaction_date 
WHERE { 
  ?s ex:id ?id ; 
     ex:price ?price ; 
     ex:transactionDate ?transaction_date . 
  OPTIONAL { ?s ex:name ?name } 
  OPTIONAL { ?s ex:cardName ?card_name } 
  OPTIONAL { ?s ex:cardNumber ?card_number } 
  FILTER (?price > 50) 
  BIND(COALESCE(NULLIF(?name, ''), '[product name not found]') AS ?name) 
  


Description Level 5 

Take the card shop schema. You are requested to find the department name of the departments 
that have had at least five sale that were worth more than 50. You also want to make sure 
that the department in question has in total sales for less than 500. Finally, you want to
make sure that the sales are checked for 2022 only.

Reference solution:

@prefix ex: <http://example.com/>

SELECT ?department_name (COUNT(?s) AS ?num_sales) (SUM(?price) AS ?total_sales) 
WHERE {
  ?s ex:id ?id ; 
     ex:price ?price ; 
     ex:transaction_date ?transaction_date ; 
     ex:sold_by ?department . 
  OPTIONAL { ?s ex:name ?name } 
  OPTIONAL { ?s ex:card_name ?card_name } 
  OPTIONAL { ?s ex:card_number ?card_number } 
  ?department ex:name ?department_name . 
  FILTER (YEAR(?transaction_date) = 2022 && ?price > 50) 
}
GROUP BY ?department_name
HAVING (COUNT(?s) > 5 && SUM(?price) > 500)
ORDER BY DESC(?total_sales)



Description level 6:

Take the people and card shop schema.

Add a property 

ex:madeBy rdf:type rdf:Property ;
          rdfs:domain ex:Sale ;
          rdfs:range ex:Person ;
    rdfs:label "Indicates that a person customer has bought a certain product" .

You are now asked to write a query that finds dates, name of the buyer and price of 
transactions made after October 10 2022.

Reference Solution:

SELECT ?name ?transaction_date ?price
WHERE {
  ?s ex:id ?id ;
     ex:price ?price ;
     ex:transactionDate ?transaction_date ;
     ex:madeBy ?p .
  ?p people:name ?name ;
  FILTER (?price > 50 && ?transaction_date > "2022-10-03"^^xsd:date)
}


Description Level 7:
Taken from level 7 kata from PG1 Concatenating columns https://www.codewars.com/kata/59440034e94fae05b2000073/train/sql

Your task is to use a select statement to return a single string containing the full title of the person, i.e. containing their prefix, first and last name, and suffix.

You are using the person schema (NB person schema is not the people schema).

Reference solution:

@prefix ex: <http://example.org/>
SELECT CONCAT(?prefix, ' ', ?first, ' ', ?last, ' ', ?suffix) AS ?title
WHERE { 
  ?person ex:hasPrefix ?prefix ; 
          ex:hasFirstName ?first ; 
          ex:hasLastName ?last ; 
          ex:hasSuffix ?suffix . 
}


Description Level 6

Take now the person schema, as well as the card store schema and the property 

ex:madeBy rdf:type rdf:Property ;
          rdfs:domain ex:Sale ;
          rdfs:range ex:Person ;

You are now asked to store in a single string the prefix and last name of all the customers who have made a purchase on February 21 2023. Also retrieve the department name, and group the result by it. Call the string column “title”.

Reference solution:

SELECT CONCAT(?prefix, ' ', ?last) AS ?title ?name 
WHERE {
  ?s ex:name ?name ;
     ex:transactionDate ?transaction_date ;
     ex:madeBy ?p .
  ?p ex:hasPrefix ?prefix;
     ex:hasLastname ?last .
  FILTER (?transaction_date = "2022-02-21"^^xsd:date)
GROUP BY ?name
}


Description level 4:
Taken from kata level 6 from [pmatseykanets](https://www.codewars.com/users/pmatseykanets) , conditional count, https://www.codewars.com/kata/5816a3ecf54413a113000074/solutions

Start from rental table.

Now, imagine that there are two employees, called Jon and Mike, and that you want to compare the number and total amounts of payments made in Mike's and Jon's stores broken down by months.
The result needs to use the following columns:
?month ?total_count  ?total_amount ?mike_count ?mikeAmount ?jon_count ?jon_amount
Where 
month - number of the month (1 - January, 2 - February, etc.)
total_count - total number of payments
total_amount - total payment amount
mike_count - total number of payments accepted by Mike (staff_id = 1)
mike_amount - total amount of payments accepted by Mike (staff_id = 1)
jon_count - total number of payments accepted by Jon (staff_id = 2)
jon_amount - total amount of payments accepted by Jon (staff_id = 2)

There is no need to worry about years, data comes from the same year only.

Reference solution:

@prefix xsd: <http://www.w3.org/2001/XMLSchema#>
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
@prefix payment: <http://example.org/payment#> 
@prefix staff: <http://example.org/staff#>  

SELECT ?month (COUNT(* ) AS ?total_count) (SUM(?amount) AS ?total_amount)      
       (COUNT(?mike) AS ?mike_count) (SUM(?mikeAmount) AS ?mike_amount)       
       (COUNT(?jon) AS ?jon_count) (SUM(?jonAmount) AS ?jon_amount) 
WHERE {   
    ?payment rdf:type payment:Payment ;            
             payment:payment_date ?date ;            
             payment:amount ?amount ;            
             payment:madeBy ?staff .   
    BIND(MONTH(?date) AS ?month)     
    OPTIONAL {    
        ?staff rdf:type staff:Staff ;          
               staff:id 1 .    
        BIND(IF(BOUND(?staff), ?payment, NULL) AS ?mike)     
        BIND(IF(BOUND(?mike), ?amount, NULL) AS ?mikeAmount)   
    }     
    OPTIONAL {  
        ?staff rdf:type staff:Staff ;           
               staff:id 2 .     
        BIND(IF(BOUND(?staff), ?payment, NULL) AS ?jon)    
        BIND(IF(BOUND(?jon), ?amount, NULL) AS ?jonAmount)   
    } 
} 
GROUP BY ?month 
ORDER BY ?month


Description Level 7 6:
kata level 6 from matt c, simple HAVING, https://www.codewars.com/kata/58164ddf890632ce00000220/train/sql

Take the people schema. You are requested to check for how many people have the same age 
and return the groups with 10 or more people who have that age. You need to return two 
columns, onefor age and one for total_people having that age.


@prefix : <http://example.org/people#> 
SELECT ?age (COUNT(?id) AS ?total_people) 
WHERE { 
?person people:age ?age ;
        people:id ?id . 
} 
GROUP BY ?age 
HAVING (COUNT(?id) > 9)


Description Level 5:
Level 6 kata from FArrekkusu, Analyzing the sales by product and date, https://www.codewars.com/kata/5dac87a0abe9f1001f39e36d/solutions

Take the sales schema.

You are asked to calculate the total revenue for each day, month, year, and product.

Notes
The sales table stores only the dates for which any data has been recorded - the information about individual sales (what was sold, and when) is stored in the sales_details table instead.
The sales_details table stores totals per product per date.
Order the result by the product_name, year, month, day columns
We're interested only in the product-specific data, so you shouldn't return the total revenue from all sales.

Reference solution:

@prefix ex: <http://example.com/>
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> 

SELECT ?product_name (xsd:int(?year) as ?year) (xsd:int(?month) as ?month) (xsd:int(?day) as ?day) (SUM(?price * ?count) as ?total) 
WHERE { 
  ?sd ex:sale_id ?sale_id ; 
      ex:product_id ?product_id ; 
      ex:price ?price ; 
      ex:count ?count .
  ?s ex:id ?sale_id ; 
     ex:date ?date . 
  ?p ex:id ?product_id ; 
     ex:name ?product_name . 
  BIND(year(?date) as ?year) 
  BIND(month(?date) as ?month) 
  BIND(day(?date) as ?day)
} 
GROUP BY ?product_name ROLLUP (?year ?month ?day)
ORDER BY ?product_name ?year ?month ?day
