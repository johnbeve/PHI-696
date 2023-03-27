**The SPARQL Library of Buffalo**

[Codewars](https://www.codewars.com/dashboard) is a website designed to facilitate algorithmic training for various programming languages. Users supply problem statements and others provide coding solutions to those problems. For example, you might find a problem for Python such as: 

** Jonathan's Kata's for SPARQL **

Comment: I've attempted almost 30 problems.
 - Kata-8's x 1 = 0
 - Kata-7's x 10 = 20
 - Kata-6's x 10 = 30
 - Kata-5's x 6 = 30
 - Kata-4's x 2 = 20

My problems are given in the following format: "Problem [Kata level]-[instance]"

**Problem 8-1.**
- The following catalog contains camera products, according to their product name (ontocam:productName), model number (ontocam:modelValue), manufacturer (ontocam:manufacturer) and release date (ontocam:releaseDate).
- Find all camera products manufactured by Canon, displaying their name, model number, release date.

```
PREFIX ontocam: <https://aperturescience.org/onto/>

SELECT ?productName ?modelValue ?manufacturer ?releaseDate
WHERE {
      ?device ontocam:manufactured_by ontocam:Canon .
}
```

**Problem 7-1.**
- List all of the people who have been president in the United States of America. The ontology does not have a 'president' class, but rather a 'PresidentRole' that the individual bears. Be careful to stipulate that the role has presidential authority in the United States.
- Who has been a president of the USA at some time?

```
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>
PREFIX ontopol: <https://politicalontology.org/schema/ontopol.ttl>

SELECT ?subject
WHERE {
      ?subject ro:has_role ?PresidentialRole ;
      ?PresidentialRole ontopol:authority_in ontopol:United_States.
    }
```

**Problem 7-2.**
- List all of the furniture that has been recalled for reason of child safety. In this RDF model, all furniture has an active safety status of "Approved" or "Recalled" (they do not have a null value).
```
PREFIX furnont: <https://fillingbetterhomes.org/oit/furnitureontology.owl>

SELECT ?commonName ?safetyStatus
WHERE {
      ?furniture rdfs:label ?commonName ;
            furnont:has_safety_status "Recalled" ;
            furnont:recalled_reason "Child Safety" .
    }
```

**Problem 7-3.**
- A local militia group wants to rally potential troops for a coup and has access to the state of Oregon registry to look up demographic information. They only want to find males age 16 and older.
- Find all males’ 16 years or older, and their mailing addresses.

```
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
PREFIX ontopol: <https://politicalontology.org/schema/ontopol.ttl>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

SELECT ?subject ?mbox
WHERE {
      ?subject foaf:birthday ?birthDate ;
            foaf:gender “male” ;
            foaf:mbox ?mbox .
      FILTER (?birthdate < "2007-03-27T00:00:00+05:30"^^xsd:dateTime)
}
```

**Problem 7-4.**
- A tour guide in western Michigan wants to create a new lighthouses tour, based on lighthouses that provide support for boats on Lake Michigan, but from Michigan's side and only on the lower peninsula.
- Lighthouses overlooking Lake Michigan, located in Michigan’s Lower Peninsula.
```
PREFIX touronto: <https://americathebeautiful.com/tours/ontology/>

SELECT ?facility
WHERE {
      ?facility rdf:type touronot:Lighthouse ;
            touronto:located_in touronto:LowerPeninsulaMichigan ;
            touronto:nearby_location touronto:LakeMichigan .
}
```

**Problem 7-5.**
- The National Park and Recreation Department is concerned about recent adverse changes in natural habitat for the ruby-throated thrush. Find all parks that may be affected by these conservation efforts.
- Return all parks that are the natural habits of ruby-throated thrush.
```
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>
PREFIX touronto: <https://americathebeautiful.com/tours/ontology/>

SELECT ?park
WHERE {
      ?park ro:located_in bfo:site ;
      bfo:site touronto:contains_habitat touronto:naturalHabitat ;
      touronto:naturalHabitat touronto:habitat_of zoo:rubyThroatedThrush .
}
```

**Problem 7-6.**
- Find all cameras manufacturerd by Fujifilm (ontocam:manufacturer), released in the year 2020, and has a bluetooth connection function.
- Return camera name (ontocam:productName), model number (ontocam:modelValue), release date (ontocam:releaseDate).
```
PREFIX ontocam: <https://aperturescience.org/onto/>
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>

SELECT ?productName ?modelValue ?releaseDate
WHERE {
      ?device ontocam:manufactured_by ontocam:Fujifilm ;
      ?device rdfs:type ontocam:Camera ;
      ?device ontocam:released_in_year "2020" ;
      ?device ro:has_function ontocam:Bluetooth .
}
```

**Problem 7-7.**
- A store manager is assessing what summer furniture needs to be put on sale. First, she is interested only in those furniture that is designed for outdoors. Second, she wants to start with the type that has the most inventory. Third, she wants to limit the sale to the top 5 furniture models, irrespective of brand.
- Return the furniture name, model, and current inventory, ordered by inventory descending, but only the five models with the greatest inventory.

```
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>
PREFIX homedev: <http://homeandgarden.com/ontology/>

SELECT ?productName ?productModelValue ?inventoryValue
WHERE {
  ?product ro:instance_of homedev:outdoorFurniture ;
           ro:bearer_of ?function ;
           ro:composed_primarily_ of ?material ;
           homedev:has_sale_price ?salePriceValueUSD .
  FILTER (?function != homedev:twoShelf && 
          ?salePriceValueUSD < 150 && 
          ?material = homedev:woodMaterial && 
          ?material != homedev:metalwireMaterial)
}
```
- L

```
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>
PREFIX ontopol: <https://politicalontology.org/schema/ontopol.ttl>

SELECT ?facility
WHERE {
      ?facility rdf:type touronot:Lighthouse .
}
```

**Problem 7-8.**
- 
- L

```
PREFIX touronto: <https://americathebeautiful.com/tours/ontology/>

SELECT ?facility
WHERE {
      ?facility rdf:type touronot:Lighthouse .
}
```

**Problem 7-9.**
- 
- L

```
PREFIX touronto: <https://americathebeautiful.com/tours/ontology/>

SELECT ?facility
WHERE {
      ?facility rdf:type touronot:Lighthouse .
}
```

**Problem 7-10.**
- 
- L

```
PREFIX touronto: <https://americathebeautiful.com/tours/ontology/>

SELECT ?facility
WHERE {
      ?facility rdf:type touronot:Lighthouse .
}
```

**Problem 6-1.**
- You’re an IT administrator working with a printer support maintenance contractor to update and replace parts for covered assets such as the Brother brand printers on site. You want to prioritize those printers that are on the network and display a warning status, especially for “low” toner.
- Get all printers on the network that have model made by Brother and which have a warning status on “high”, optional: get their toner level status.

```
PREFIX itdev: <https://www.rando.org/ontology/>
 
SELECT ?printerDevice ?warningStatus
WHERE {
      ?printer itdev:manufactured_by itdev:Brother .
      ?printer itdev:device_status ?warningStatus .
      ?warningStatus itdev:severity_level “High” .
      OPTIONAL SELECT { ?printer itdev:toner_value “Low” .}
}
```

**Problem 5-1.**
- List all senators or congresspersons who held office in a state that is not the state of their birthplace. Return both birthplace state and state in which they held office.
- This query calls for a disjunction. Be sensitive to what is being negated.
```
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>
PREFIX ontopol: <https://politicalontology.org/schema/ontopol.ttl>

SELECT * WHERE
{
{ SELECT ?person ?birthState ?officeState WHERE {
      ?person ro:has_role ?SenatorRole ;
      ?SenatorRole a ontopol:politicalOfficerRole ;
      ?politicalOfficerRole ontopol:authority_in ?State ;
      BIND (?State) AS ?officeState .
      ?person ontopol:has_birthplace ?State ;
      BIND (?State) AS ?birthState .
      }
}
UNION
{ SELECT ?person ?birthState ?officeState WHERE {
      ?person ro:has_role ?congressPersonRole ;
      ?congressPersonRole a ontopol:politicalOfficerRole ;
      ?politicalOfficerRole ontopol:authority_in ?State ;
      BIND (?State) AS ?officeState .
      ?person ontopol:has_birthplace ?State ;
      BIND (?State) AS ?birthState .
      }
}
FILTER(?birthState != ?officeState)
```

**Problem 5-2.**
- A customer is searching for shelving and wants to filter results in a catalog online, with specific functionality and material type and within a price range.
- Get the USD price for all shelves that are not two-shelf, that cost less than $150 USD, and are made out of wood rather than wire frame.
```
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>
PREFIX homedev: <http://homeandgarden.com/ontology/>

SELECT ?tallShelf ?salePriceValueUSD
WHERE {
  ?shelf ro:instance_of homedev:Shelf ;
           ro:bearer_of ?function ;
           ro:composed_primarily_ of ?material ;
           homedev:has_sale_price ?salePriceValueUSD .
  FILTER (?function != homedev:twoShelf && 
          ?salePriceValueUSD < 150 && 
          ?material = homedev:woodMaterial && 
          ?material != homedev:metalwireMaterial)
}
```

**Problem 5-3.**

Setup prompt
- The federal department of education gives special grants to those educational institutions that garner the highest enrollments in the state (only one per state), whether that school is public or private. The total enrollment includes both undergraduate and postgraduate students. Find the college or university that would be eligible for such a grant in the state of California.
- Give the name of the institution and number of students of a post-secondary educational institution located in California with the highest enrollment of students (undergrad and grad together).
```
PREFIX onto-ed: <https://www.nj.gov/admin/oit/ontology/>

SELECT ?institution (MAX(?totalEnrollment) AS ?topEnrollment)
WHERE {
  ?institution a onto-ed:EducationalInstitution ;
               onto-ed:type "PostsecondaryEducation" ;
               onto-ed:located_in_state "California" ;
               onto-ed:enrollment_number ?postgradEnrollment ;
               onto-ed:enrollment_number ?undergradEnrollment ;
               BIND (?postgradEnrollment + ?undergradEnrollment AS ?totalEnrollment) .
}
```
- Difficulty level: KATA-5


**Problem 4-1.**

Setup prompt
- Around the world there are large buildings that bear the same shape as the famous Egyptian pyramids. These are called ziggurats. However, Egyptians were not the first to build this kind of structure. Which structures have the greatest estimated age?
- Display the name of the oldest 25 ziggurats, current country location, name of associated culture when it was formed, and estimated age. Order by estimated age, descending (or date of completion ascending).
```
PREFIX anthro: <http://anthropologywiki.org/schema/ontology/>

SELECT ?zigguratName ?countryName ?cultureName ?estimatedCompletionDate
WHERE {
  ?ziggurat a anthro:Building ;
            rdfs:type anthro:Ziggurat ;
            anthro:location_in ?country ;
            anthro:cultural_originator ?culture ;
            anthro:formation_datecompleted ?estimatedCompletionDate .
  ?country rdfs:label ?countryName .
  ?culture rdfs:label ?cultureName .
  FILTER(lang(?cultureName) = 'en')
}
ORDER BY ASC(?estimatedCompletionDate)
LIMIT 25

```
- Difficulty level: KATA-4


**Problem 4-2.**

Setup prompt
- Find all public elections for president held in sovereign states that were formerly members of the USSR and not currently dissolved. Display the country and the winner as well.
- Note: be sensitive to the open world assumption.
```
PREFIX dbp-prop: <http://dbpedia.org/property/>
PREFIX ontopol: <https://politicalontology.org/schema/ontopol.ttl>

SELECT DISTINCT ?election ?electionWinner ?country
WHERE {
  ?election a ontopol:Public_Election ;
            ontopol:candidate_office ontopol:President ;
            dbp-prop:located_in ?country .

  ?country ontopol:member_of_union ontopol:Soviet_Union ;
           dbp-prop:status ?status .
  
  FILTER (?status != "Dissolved") .
}
```
- Difficulty level: KATA-4
