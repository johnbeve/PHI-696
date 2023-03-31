**The SPARQL Library of Buffalo**

[Codewars](https://www.codewars.com/dashboard) is a website designed to facilitate algorithmic training for various programming languages. Users supply problem statements and others provide coding solutions to those problems. For example, you might find a problem for Python such as: 

** Jonathan's Kata's for SPARQL **

Comment: I've attempted almost 30 problems.
 - Kata-8's x 1 = 0
 - Kata-7's x 10 = 20
 - Kata-6's x 5 = 15
 - Kata-5's x 5 = 25
 - Kata-4's x 4 = 40

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
      ?PresidentialRole ontopol:authority_in ontopol:UnitedStates.
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

SELECT ?person ?mbox
WHERE {
      ?ontopol:Person foaf:birthday ?birthDate ;
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
- A catalog should display all lighting fixture models that have a multi-brightness function and can be connected as an Internet of Things device (IoT).
- Return the product name, product model, current price, and current inventory that fit this criteria.

```
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>
PREFIX homedev: <http://homeandgarden.com/ontology/>

SELECT ?productName ?productModelValue ?productPriceUSD ?inventoryValue
WHERE {
        ?product ro:instance_of homedev:LightingFixture ;
                ro:has_function homedev:multiSettingBrightness ;
                ro:has_function homedev:internetOfThingsConnection .
}
```

**Problem 7-8.**
- A sample ballot for a local county should display all candidates who are running in an upcoming election.
- Return the candidate name, candidate's political affiliation, and candidate's website address.
```
PREFIX ontopol: <https://politicalontology.org/schema/ontopol.ttl>
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>

SELECT ?PreferredName ?RegisteredPoliticalParty ?OfficialWebsiteURL
WHERE {
        ?ontopol:Citizen ro:referred_by ?ontopol:PreferredName ;
            ro:bearer_of ontopol:PoliticalCandidateRole ;
            ontopol:affiliated_with ?ontopol:RegisteredPoliticalParty ;
            ontopol:platform_described_by ?OfficialWebsiteURL .
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

**Problem 6-2.**
- A store manager is assessing what Summer furniture needs to be put on sale before the next season. First, she is interested only in those furniture that is designed for use outdoors. Second, she wants to start with the type that has the most inventory. Third, she wants to limit the sale to the top 20 furniture models, irrespective of brand or purpose. Fourth, she wants the manufacturer's suggested retail price (MSRP). Lastly, she wants to know what the price would be if that product were 40% off the MSRP.
- Return the furniture name, model, and current inventory, ordered by inventory descending, but only the twenty products with the greatest inventory.
```
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>
PREFIX homedev: <http://homeandgarden.com/ontology/>

SELECT ?productName ?productModelValue ?inventoryValue ?productMSRP ?tentativeSalePrice
WHERE {
  ?product ro:instance_of homedev:outdoorFurniture .
  ?product ro:has_value homedev:inventoryValue .
  BIND (?productMSRP * 0.8 AS ?tentativeSalePrice)
}
```

**Problem 6-3.**
Find all constructed languages present in written works, that are not Star Wars lore, and what those works are.
```
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>
PREFIX ontolit: <http://litararyworlds.org/literature-ontology/ontolit.ttl>

SELECT ?conLang ?literaryArtifact
WHERE {
        ?sentence ontolit:in_language ?conLang ;
            ro:part_of ?litraryArtifact .
        ?litraryArtifact ontolit:has_literary_world ?literaryWorld .
  FILTER !regext(?litraryArtifact ro:has_literary_world ontolit:StarWarsUniverse)
}
```

**Problem 6-4.**
- Find all persons who have a passport issued, the person has not left the country, and the person is over the age of 25
```
PREFIX ontopol: <https://politicalontology.org/schema/ontopol.ttl>
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>

SELECT ?preferredName
WHERE {
        ?person ro:referred_by ?ontopol:preferredName ;
            ontopol:issued_document ?ontopol:Passport .
        FILTER (?age > 25) .
        FILTER NOT EXISTS (?person ro:participates_in ontopol:ActOfCountryDeparture)
}
```

**Problem 6-5.**
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
      BIND(?State AS ?officeState) .
      ?person ontopol:has_birthplace ?State ;
      BIND(?State AS ?birthState) .
      }
}
UNION
{ SELECT ?person ?birthState ?officeState WHERE {
      ?person ro:has_role ?congressPersonRole ;
      ?congressPersonRole a ontopol:politicalOfficerRole ;
      ?politicalOfficerRole ontopol:authority_in ?State ;
      BIND(?State AS ?officeState) .
      ?person ontopol:has_birthplace ?State ;
      BIND(?State AS ?birthState) .
      }
}
FILTER(?birthState != ?officeState)
```

**Problem 6-6.**
- Find all cars manufactured outside the USA, have 360 camera sensors, and rated by JD Power & Associates as having the highest rating in its class. Group by body type.
```
PREFIX ontomobile: <http://carscarscars.org/schemas/ontology/ontomobile.owl>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>

SELECT ?Vehicle ?VehicleBodyType
WHERE {
        ?Vehicle ontomobile:ro:manufactured_by ?Manufacturer ;
            ro:has_part ?360CameraSystem ;
            ontomobile:has_body_type ?VehicleBodyType ;
            ontomobile:has_quality_rating ?QualityRating .
        FILTER MAX(?QualityRating ontomobile:rated_by ontomobile:JDPowerAndAssociates ) .
        GROUP BY ?VehicleBodyType .
}
```


**Problem 6-7.**
- Find all musicians born in 1960s, who were members of some grunge band that was based in Seattle.
```
PREFIX ontomuse: <https://openmusicresources.org/schema/ontomuse.owl>
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>

SELECT ?Name
WHERE {
        ?ontomuse:Person ro:referred_by ?ontomuse:Name ;
            foaf:birthday ?birthDate ;
            ro:member_of ?MusicalGroup .
        ?MusicalGroup ontomuse:has_genre ontomuse:Grunge ;
            ontomuse:has_music_scene_locale ontomuse:Seattle_WA_USA .
        FILTER (?foaf:birthdate > "1960-01-01T00:00:00+05:30"^^xsd:dateTime) .
        FILTER (?foat:birthdate < "1970-01-01T00:00:00+05:30"^^xsd:dateTime)
}
```


**Problem 5-1.**
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

**Problem 5-2.**
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

**Problem 5-3.**
- Your goal is to register a block of unused VINs. Take fields from multiple tables to generate a unique VIN. The third field is a check-digit, which in this case will be "9". Your manufacturing plant will only be assigning 1000, starting at sequence number 31337. Lastly, verify that the output is exactly 17 characters long.
-The order of VIN construction: 
- - WMI (ontomobile:WorldManufacturerIdentifier)
- - Vehicle attributes (ontomobile:VehicleAttributeCode)
- - Check digit
- - Model year (ontomobile:VehicleModel (a subclass of ArtifactModel))
- - Plant code (ontomobile:ManufacturerPlantCode)
- - Sequential number (ontombile:VehicleSequenceValue)
```
PREFIX ontomobile: <http://carscarscars.org/schemas/ontology/ontomobile.owl>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>

CONSTRUCT REDUCED { ?Vehicle ontomobile:has_serial ?VehicleIdentificationNumber }
WHERE {
		?Vehicle ontomobile:designated_by ?VehicleSequenceValue ;
			ontomobile:manufactured_by ?Manufacturer ;
			ontomobile:manufactured_at_location ?ManufactuingPlant ;
			ontomobile:prescribed_by ?ArtifactModel ;
			ontomobile:described_by ?VehicleAttributeCode ;
			ontomobile:has_production_year ?ProductionYear .
		?Manufacturer ontomobile:has_WMI_value ?WorldManufacturerIdentifier .
		?ManufacturingPlant ontomobile:has_plant_code ?ManufacturerPlantCode .
		FILTER (?VehicleSequenceValue > "31336")
		ORDER BY ?VehicleSequenceValue ASC
        LIMIT 1000
		BIND(CONCAT(?WorldManufacturerIdentifier, ?VehicleAttributeCode, STR(9), ?VehicleModel, ?ProductionYear ?ManufacturerPlantCode, ?VehicleSequenceValue)) AS ?VehicleIdentificationNumber
}
```

**Problem 5-4.**
- Find all public elections for president held in sovereign states that were formerly members of the USSR and not currently dissolved. Display the country and the winner as well. Declare that state to bear a "NATO friend" role.
- Note: be sensitive to the open world assumption.
```
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>
PREFIX ontopol: <https://politicalontology.org/schema/ontopol.ttl>

CONSTRUCT { ?country ro:bearer_of ?ontopol:NATOFriendRole . }
WHERE {
		?election a ontopol:Public_Election ;
			ontopol:candidate_office ontopol:President ;
			ro:located_in ?country .
		?country ontopol:member_of_union ontopol:Soviet_Union ;
			ro:has_status ?status .
		FILTER (?status != "Dissolved") .
}
```

**Problem 5-5.**
- New research shows that men who have the.
```
PREFIX ontokrebs: <http://purl.obolibrary.org/obo/krebs.owl>
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>

construct { ?person has_predisposition testicularcancer
WHERE {
	ontokrebs: medical: person has genotype (string)
        person has genotype (string)
}
```
    

**Problem 4-1.**
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

**Problem 4-2.**
- An E. coli breakout has occurred recently and the culprit is contaminated iceberg lettuce pallets in the distribution for fastfood restaurants in the midwestern states. All pallets of lettuce that passed through distribution chains in Arkansas and Nebraska are at risk. Declare all such lettuce to bear an "E. coli risk" role and "recall" quality status, if they were present on shipping routes through these two states. (You must change the safety rating, and then assert a new triple that the pallet bears a risk role with construct)
```
PREFIX foodservont: <http://industrialontologyfoundry.org/ontology/extension/foodservice.owl>
PREFIX ro: <http://purl.obolibrary.org/obo/ro.owl>

DELETE {
		?Pallet foodservont:has_quality_rating ?FoodSafetyRating . 
		?FoodSafetyRating ro:has_value "Safe" . 
		}
INSERT {
		?Pallet foodservont:has_quality_rating ?FoodSafetyRating . 
		?FoodSafetyRating ro:has_value "Recall" .
		}
CONSTRUCT {
		?Pallet ro:bearer_of ?EscherichiaColiRiskRole . 
		?
WHERE {
		?Pallet foodservont:contains_food_stuff ?Lettuce ;
			ro:participates_in ?ShippingProcess .
		?ShippingRoute ro:participates_in ?ShippingProcess ;
			ro:has_part ?ShippingStop .
		?ShippingStop ro:has_location {foodservant:Nebraska_USA|foodservant:Arkansas_USA} .
}
```

**Problem 4.3**
- A research company is working on anemia treatment. They belong to a network of research organizations permitted to make requests from biological banks that contain specimens available for "secondary research," i.e., excess tissues or fluids derived from testing on a patient or withdrawn in some clinic. The database contains attributes such as anonymized patient id, specimen type, biobank locations, and other anonymized medical history information such as prior testing or patient demographics.
- Find all specimens that are instances of blood or bone marrow, derived from a woman younger than 25 years old, who has not tested positive for cancer (and if there has been a negative test result for cancer, include that information), and the specimen is located in the state of Illinois, Indiana, Michigan, or Ohio.
- NOTE: This is largely from ChatGPT, generated 2023-03-25
```
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX dct: <http://purl.org/dc/terms/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX ncit: <http://ncicb.nci.nih.gov/xml/owl/EVS/Thesaurus.owl#>
PREFIX obo: <http://purl.obolibrary.org/obo/>

SELECT ?specimen ?age ?test_result ?state
WHERE {
  ?specimen a ncit:C7057, ?type .
  FILTER (?type IN (obo:OBI_0000299, obo:OBI_0002026))  # blood or bone marrow
  ?specimen dct:subject ?subject .
  ?subject ncit:C16960 ?gender ;  # gender
           ncit:C25197 ?age ;     # age
           ncit:C32701 ?state .   # state
  FILTER (?gender = ncit:C16576)   # female
  FILTER (?age < 25^^xsd:integer)  # younger than 25
  OPTIONAL {
    ?subject ncit:C25194 ?test .  # cancer test
    ?test ncit:C25195 ?test_result ;
          ncit:C25196 ncit:C25205 .  # negative result
  }
  FILTER (!bound(?test_result))   # no positive cancer test
  FILTER (?state IN (ncit:C34404, ncit:C34403, ncit:C34410, ncit:C34405))  # IL, IN, MI, or OH
}
```

**Problem 4.4**
political: find all persons who are registered to a phone and that phone had GPS location US Capitol on January 6, 2022
    filter: not anyone who holds political office or member of the press
    filter: only those who have criminal record == True
    assert: bearer of "FBI watchlist member role"
