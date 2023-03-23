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

****

**[1] Kata 8 Challenge: Video Games - 0 point**

Jack is a new international student at University at Buffalo. After taking a two-month part-time job, he finally saved enough money and bought a desktop computer which is equipped with a video card of RTX 3060 Ti. So he can start with his journey to video games! At a time, Jack occasionally played a game called “the Witcher 3”, and found it as one of the best action RPGs (role-play games) he has played so far. Now he can’t help but want to experience more games of the same type. Can you use a SPARQL endpoint (for example, http://dbpedia.org/snorql/) to find at least 10 action role-playing games which are released after 2015? Please write your SPARQL query and return your results.

You might use the following namespaces:

PREFIX rdf: < http://www.w3.org/1999/02/22-rdf-syntax-ns# >

PREFIX dbo: < http://dbpedia.org/ontology/ >

PREFIX dbr:< http://dbpedia.org/resource/ >

**Sample Solution**:

PREFIX dbo: < http://dbpedia.org/ontology/ >

PREFIX dbr:< http://dbpedia.org/resource/ >

PREFIX rdf: < http://www.w3.org/1999/02/22-rdf-syntax-ns# >

SELECT ?game 

WHERE{

?game dbo:releaseDate ?date .

?game rdf:type dbo:VideoGame .

?game dbo:genre dbr:Action_role-playing .

FILTER (?date>"2015-01-01"^^xsd:date)

}

LIMIT 10

****

**[2] Kata 3 Challenge SPARQL Version: Game Store - 20 points**


After graduation, Jenny is now a new employee working at a local video game store. Unfortunately, her boss Mark is very rude and often picks fault with Jenny. Today when Mark found that Jenny was sitting down at her computer and gazed attentively at its screen, he said irritably to her: 

“Jenny, I don’t think an employee can do irrelevant things during working hours, even if she works for a game store.”

“No, I don’t.” Jenny raised her head and said, “I am looking through recently released games. Maybe we need to update our inventory of game copies. You know, some of our games are somewhat old.”

“Oh?” Mark glanced at Jenny’s screen quickly and scratched his head awkwardly. “Sounds good. Why don’t you give me a report of recent games? We can discuss it in our monthly meeting.”

“Sure, I can do that, my boss.” Jenny said, “What requirements do you have for this report?” 

“Fine. So your report is supposed to *list 100 video games released in the past three years. I want to know their English names, categories, publishers, release dates, and what awards they won.*”

“Just these things?”

“You see, we might sell those games later, so they must be released for *operating platforms like PlayStation 5, Xbox Series S or X*. Your data should be *in descending order of release dates*.”

“Okay, I will prepare for my report ASAP.” Jenny sighed and replied. 

“No rush,” Mark added, “Do you know about our database? You should *store* your search results there. Moreover, if your report includes some games which were released last year and won some game award, don’t forget to mark them as *‘recommended games’*.”

This is a laborious task. Putting yourself in Jenny's shoes, you have to use SPARQL to model the above process of generating a data report:

(a) Find new relevant data;

(b) Store those data in the local store's existing database;

(c) Mark some of the found data as "recommended games".

**Sample Solution**

**STEP 1**

PREFIX dbo: < http://dbpedia.org/ontology/ >

PREFIX dbr:< http://dbpedia.org/resource/ >

PREFIX dbp: < https://dbpedia.org/property/ >

PREFIX rdf: < http://www.w3.org/1999/02/22-rdf-syntax-ns# >

PREFIX rdfs: < http://www.w3.org/2000/01/rdf-schema# >

PREFIX dct: < http://purl.org/dc/terms/ >

SELECT ?name ?genre ?publisher ?date ?award

WHERE {

?game rdfs:label ?name ;

      rdf:type dbo:VideoGame ;

      dbo:genre ?genre ;

      dbo:publisher ?publisher ;
  
      dbo:releaseDate ?date .

{?game dct:subject dbc:PlayStation_5_games . }

UNION

{?game dct:subject dbc:Xbox_Series_X_and_Series_S_games . }

FILTER (?date>"2019-12-31"^^xsd:date)

FILTER (?date <"2023-01-01"^^xsd:date)

FILTER(lang(?name) = "en")

{
  
  SELECT ?award

  WHERE {

    OPTIONAL

    {?game dbo:wikiPageWikiLink ?award .}

    FILTER(regex(?award, “award”, “i”))

  }

}

}

ORDER BY DESC(?date)

LIMIT 100

**STEP 2**

Save search results as a named graph “ex100.ttl”.

**STEP 3**

PREFIX rdf: < http://www.w3.org/1999/02/22-rdf-syntax-ns# >

PREFIX rdfs: < http://www.w3.org/2000/01/rdf-schema# >

PREFIX dbo: < http://dbpedia.org/ontology/ >

PREFIX dbr:< http://dbpedia.org/resource/ >

PREFIX ex: < http://example.org/ >

CONSTRUCT

{
?game rdfs:label ?name ;

      rdf:type ex:RecommendedGame . 
}

WHERE

{
GRAPH <ex100.TTL> {

?game rdfs:label ?name ;

      dbo:releaseDate ?date ;

      dbo:wikiPageWikiLink ?award .

FILTER (?date >"2021-12-31"^^xsd:date)

}

}

****

**[3] Kata 3 Challenge SQL Version: Game Store - 10 points**

This is a SQL version of the challenge "Game Store". Given the same scenario description, please give any appropriate SQL query to model the above process of generating a data report of new games.


**Sample Solution**

Suppose all game data are stored in yearly tables such as "games_2022", "games_2021" and so on in a game database. Also, each yearly table includes columns "game_id", "game_name", "category", "publisher", "platform", "release_date" and "awards". So the above process can be modeled via the following SQL query.

SELECT 

    game_name, category, publisher, release_date, awards 

    CASE 
    
    WHEN release_date BETWEEN '2022-01-01' AND '2022-12-31' AND awards IS NOT NULL THEN 'Recommended Game' ELSE '' 
    
    END AS recommended

FROM 

(
  SELECT

    game_name, category, publisher, release_date, awards
  
  FROM

    games_2022
  
  UNION ALL

  SELECT

    game_name, category, publisher, release_date, awards

  FROM

    games_2021

  UNION ALL

  SELECT

    game_name, category, publisher, release_date, awards

  FROM

    games_2020

) AS all_games

WHERE 

    platform IN ('PS5', 'XBOX') AND release_date BETWEEN '2020-01-01' AND '2022-12-31'

GROUP BY 

    game_id, game_name, category, publisher, release_date, awards

HAVING 

    COUNT(DISTINCT game_id) = 100

ORDER BY 

    release_date DESC

****

**[4] Kata 4 Challenge SPARQL Version: Picky Boss Mark Again - 10 points**

As we know, Jenny is working for a local video game store owned by Mark. Jenny submitted a survey report of new games in the past three years, which was approved by last monthly meeting. Nonetheless, picky Mark finds fault with her again today.

"Hey!" Mark shouts to Jenny, "What about our sale since we have updated our video game inventory last time?"

"*ELDEN RING* is one of the best sellers," Jenny replies, "but there are some games which do not sell very well."

"Oh shoot," Mark complains, "it would have been better if you were more careful in your market survey."

"It's not my fault." Jenny says impatiently, "It is our group decision!"

"Ok, why don't you make more efforts for our group?" Mark says, "Now you have a new task. Write a sales report of our new introduced games. Pick the top 10 worst-sellers from them. Also, find the top 10 games which have the most episodes. Compare them and tells me *how many games with the most episodes have the worst selling performance.* Maybe we should introduce games with less episodes next time. You know, gamers are becoming lazier than before. BTW, don't give me their id numbers. I only want their English names!"

Please write a *single* SPARQL query to output what Marks wants. How poor Jenny is! You may use the following namespaces: 

PREFIX schema: < http://schema.org/ >
PREFIX ex:< http://example.org/videoGames/ >, where we have properties like "ex:hasEpisode"

**Sample Solution**

PREFIX schema: < http://schema.org/ >
PREFIX ex:< http://example.org/videoGames/ >
PREFIX rdf: < http://www.w3.org/1999/02/22-rdf-syntax-ns# >
PREFIX rdfs: < http://www.w3.org/2000/01/rdf-schema# >

SELECT (COUNT(?name1) AS ?overlap)

WHERE{

{

SELECT ?name1 

WHERE{

?game1 rdfs:label ?name1 ;

      rdf:type schema:VideoGame ;

      schema:sales ?sale .

FILTER(lang(?name) = "en")

}

ORDER BY ?sale

LIMIT 10

}

{

SELECT ?name2 (COUNT(?episode) AS ?num_episodes)

WHERE{

?game2 rdfs:label ?name2 ;

      rdf:type schema:VideoGame ;

      ex:hasEpisode ?episode .

FILTER(lang(?name) = "en")

}

ORDER BY DESC(?num_episodes)

LIMIT 10

}

Filter(?name1=?name2)

}

****

**[5] Kata 4 Challenge SQL Version: Picky Boss Mark Again - 5 points**

This is a SQL version of the challenge "Picky Boss Mark Again". Given the same scenario description, please give a *single* SQL query to tell Mark *how many games with the most episodes have the worst selling performance.*

**Sample Solution**

SELECT COUNT(name1) AS overlap

FROM (

  SELECT name1

  FROM (

    SELECT rdfs_label AS name1, schema_sales AS sale

    FROM games

    WHERE lang = 'en'

    ORDER BY sale

    LIMIT 10

  ) top_sales

  INNER JOIN (

    SELECT games.rdfs_label AS name2, COUNT(episodes.id) AS num_episodes

    FROM games

    INNER JOIN episodes ON games.id = episodes.game_id

    WHERE lang = 'en'

    ORDER BY num_episodes DESC

    LIMIT 10

  ) top_episodes ON top_sales.name1 = top_episodes.name2

) overlap_query

****

**[6] Kata 2 Challenge: Mars Base Commander - 25 points**

As the commander of a human base on Mars, and you are defending your base from the invasion of Mars natives. Those natives can convert themselves to human-like creatures so they often infiltrate your base and harm your soldiers. There are only two ways to enter your base, by either the elevator A or the elevator B. Each elevator have two main sorts of status: on_status or off_status. If an elevator has an on_status, then it is activated to move from a floor to another one; and if it has an off_status, then it must be either dormant or off. Two elevators are automatically controlled by a SPARQL-based control system so that all system commands will be received, sent and stored as RDF triples (s,p,o). Now you decide to introduce the following new rules to limit any external access to them:

Rule#1: At any time, it is normally expected that only one elevator is running. That is, in a normal case, if the elevator A(B) has an on_status at *t*, then the elevator control system will send an order to make the elevator B(A) dormant after 30 seconds.

Rule#2: If two elevators both have some on_status at the same time, then the control system will sent a warning command saying "This elevator may be abnormally controlled" to them respectively, and then they will be forced to closed after 30 seconds.

Rule#3: Each access to an elevator must be approved. If you want to take the elevator A or B, then you have to press the "start" button and enter your gene code and expected floor number. After that, your request will be processed by an AI system or a human agent. If your request is processed by an AI system, then an AI system of any security level can approve your request. But if your request is processed by a human agent, then only human agents of more than job grade 4 (for A) or 6 (for B) can approve it. After your request is approved, your elevator will get an on_status.

Pleasue use SPARQL to construct the following rules. Moreover, you should also use daily data produced by the control system to query each elevator's daily abnormality rate(=the number of daily warnings/the number of total status) every day.

All particular RDF resources are stored in the namespace *mars*. So be free to use terms like "mars:on_status", "mars:off_status", "mars:dormant" (state), "mars:off" (state), "mars:warning", "mars:elevator", "mars:elevatorA", "mars:elevatorB", "mars:genecode", mars:receiveCommand mars:start (command), mars:floorNumber(command) and so on. 

**Sample Solution**

PREFIX rdf: < http://www.w3.org/1999/02/22-rdf-syntax-ns# >

PREFIX xsd: < http://www.w3.org/2001/XMLSchema# >

PREFIX mars:< http://mars.org >

PREFIX time: < http://www.w3.org/2006/time# >

**Rule#1 is modeled as:**

CONSTRUCT

{

mars:elevatorA mars:off_status mars:dormant ;

               xsd:dateTime ?t2 .
}

WHERE

{

mars:elevatorB rdf:type mars:elevator ;

               mars:on_status ?Bstatus ;

               xsd:dateTime ?t1 .
  
BIND(time:add(time:seconds(30) , ?t1) AS ?t2)

FILTER NO EXISTS {mars:elevatorA mars:on_status ?Astatus }

}

CONSTRUCT

{

mars:elevatorB mars:off_status mars:dormant ;

               xsd:dateTime ?t2 .
}

WHERE

{

mars:elevatorA rdf:type mars:elevator ;

               mars:on_status ?Astatus ;

               xsd:dateTime ?t1 .
  
BIND(time:add(time:seconds(30) , ?t1) AS ?t2)

FILTER NO EXISTS {mars:elevatorB mars:on_status ?Bstatus }

}

**Rule#2 is modeled as:**

CONSTRUCT

{

mars:elevatorA mars:warning mars:warn42 ;

               rdfs:comment “This elevator may be abnormally controlled” ;

               mars:off_status mars:off ;

               xsd:dateTime ?t2 .

mars:elevatorB mars:warning mars:warn42 ;

               rdfs:comment “This elevator may be abnormally controlled” ;

               mars:off_status mars:off ;

               xsd:dateTime ?t2 .
}

WHERE

{

mars:elevatorA rdf:type mars:elevator ;

               mars:on_status ?Astatus ;

               xsd:dateTime ?t1 .

mars:elevatorB rdf:type mars:elevator ;

               mars:on_status ?Bstatus ;

               xsd:dateTime ?t1 .

BIND(time:add(time:seconds(30) , ?t1) AS ?t2)              

}

**Rule#3 is modeled as:**

CONSTRUCT

{

mars:elevatorA mars:on_status ?status ;

               xsd:dateTime ?t .

}

WHERE

{

?a mars:genecode ?code .
   
?code mars:getApprovalFrom ?d .

mars:elevatorA rdf:type mars:elevator;

               mars:receiveCommand mars:start;

               mars:receiveCommand mars:floorNumber.

{

?d rdf:type mars:AI_system ;

   mars:securityLevel ?level .

} 

UNION

{

?d rdf:type mars:human_agent ;

   mars:jobGrade ?grade .

}

FILTER ((bound(?level)) || (?grade>4))

}

CONSTRUCT

{

mars:elevatorB mars:on_status ?status ;

               xsd:dateTime ?t .

}

WHERE

{

?a mars:genecode ?code .

?code mars:getApprovalFrom ?d .

mars:elevatorB rdf:type mars:elevator;

               mars:receiveCommand mars:start;

               mars:receiveCommand mars:floorNumber.

{

?d rdf:type mars:AI_system ;

   mars:securityLevel ?level .

} 

UNION

{

?d rdf:type mars:human_agent ;

   Mars:jobGrade ?grade .

}

FILTER ((bound(?level)) || (?grade>6))

}

**Each elevator's daily abnormality rate can be found via the following query**

SELECT ?elevator ?date ?totalStatus ?abnormalityRate 

WHERE

{

?elevator rdf:type mars:elevator ;

          xsd:date ?date .
   
OPTIONAL

{

?elevator mars:off_status ?s1 ;

          xsd:dateTime ?t1 .

}

OPTIONAL

{

?elevator mars:on_status ?s2 ;

          xsd:dateTime ?t2 .

}

OPTIONAL

{

?elevator mars:warning mars:warn42 ;

          xsd:dateTime ?t3 .

}
          
BIND(COUNT(?t1)+COUNT(?t2) AS ?totalStatus)

BIND(COUNT(?t3) / COUNT(?t1)+COUNT(?t2) AS ?abnormalityRate)

}

****

**[7] Kata 3 Challenge SPAQRL VERSION - Geralt of Rivia - 20 points**

Geralt of Rivia is one of the leading roles in the video game series The Witcher. Old witchers usually seek for little orphans and raise them. Then, those little children had to undergo a cruel ritual called “the Trial of the Grasses”, and only a few of them like Geralt finally survive it. After that, Geralt’s body has a mutation: Though he becomes infertile, he develops strong magical powers and a high resistance to injury and aging. Now Geralt becomes a sword master, and he often fights with monsters by virtue of his martial arts and magical spells. 

Unfortunately, like other peer witchers, Geralt is on the fringes of society and thus has to earn his living by undertaking quests with the head “Witcher urgently needed”. Each quest gives its *name, category (e.g. monster-hunting, weapon-making, missing-people-finding, and so on), place, deadline, publishers, release dates, difficulty level (from level 1 to level 5) and (most importantly) rewards*. Now it is the year of 1500. Geralt is only interested in two kinds of quests: *monster-hunting and missing-people-finding*, given that they often provide a generous reward of more than 100 gold pieces. Among them, Geralt prefers those ones which *were released in Novigrad, Oxenfurt or Velen, have the difficulty level at 4 and provide a reward of more than 300 gold pieces*. 

As his friend, you want to do him a favor. Fortunately, you master a witchcraft called **“SPARQL”** so that you can have access to information about all quests in an instant! Please use SPARQL to find 50 monster-hunting quests and 50 missing-people-finding quests which are released in 1499, list their names, release dates and difficulty levels, and order them by difficult levels in a descending way, respectively. Also, you want to calculate the *reward-difficulty ratio* for each quest, measuring which quests are worth undertaking. After that, you plan to mark those ones personally preferred by Geralt among them if any. 

**Sample Solution**

(a) Query 1:

PREFIX rdf: < http://www.w3.org/1999/02/22-rdf-syntax-ns# >

PREFIX rdfs: < http://www.w3.org/2000/01/rdf-schema# >

PREFIX wit:< http://example.org/witchers/ >

SELECT ?name ?date ?level ?rate

{

SELECT ?name ?date ?level (?reward / ?level AS ?rate)

WHERE {

?quest rdf:type wit:quest ;

       rdfs:label ?name ;

       wit:task_category wit:monster-hunting ;

       wit:level ?level ;

wit:releaseDate ?date ;

wit:reward ?reward .

FILTER (?date >"1498-12-31"^^xsd:date && ?date1 <"1500-01-01"^^xsd:date)

}

ORDER BY DESC (?level)

LIMIT 50

}

{

SELECT ?name ?date ?level (?reward / ?level AS ?rate)

WHERE {

?quest rdf:type wit:quest ;

       rdfs:label ?name ;

       wit:task_category wit:monster-hunting ;

       wit:level ?level ;

wit:releaseDate ?date ;

wit:reward ?reward .

FILTER (?date >"1498-12-31"^^xsd:date && ?date2 <"1500-01-01"^^xsd:date)

}

ORDER BY DESC (?level)

LIMIT 50

}

}

(b) Query 2: Store results of Query 1 as "wit100.ttl", and then run the following query against wit100.ttl.

PREFIX rdf: < http://www.w3.org/1999/02/22-rdf-syntax-ns# >

PREFIX rdfs: < http://www.w3.org/2000/01/rdf-schema# >

PREFIX wit:< http://example.org/witchers/ >

PREFIX schema: < http://schema.org/ >

CPNSTRUCT

{

?quest rdfs:label ?name ;

      rdf:type wit:PreferedQuest .

}

WHERE

{

GRAPH<wit100.ttl>{

?quest rdfs:label ?name ;
      
      wit:level 4 ;

      wit:reward ?reward ;

      wit:location ?location .

?reward schema:priceCurrency ?currency .

FILTER (?reward > 300)

FILTER (?currency = wit:goldPieces)

FILTER (?location IN (wit:Novigrad, wit:Oxenfurt, wit:Velen))

}

}

****

**[8] Kata 3 Challenge SQRL VERSION - Geralt of Rivia - 10 points**

This is a SQL version of the challenge "Geralt of Rivia". Given the same scenario description, please use SQL to return *50 monster-hunting quests and 50 missing-people-finding quests* which are released in 1499 and ordered by difficulty levels in a descending way, respectively. List their  their names, release dates and difficulty levels, and  reward-difficulty ratios (defined as a quest's ratio of reward and difficulty level). Moreover, you should mark those *preferred ones* among them.

**Sample Solution**

Suppose all quest data in the witchers’s world are stored in a quest database including yearly tables such as "quests_2022", "quests_2021" and so on. Also, each yearly table includes columns "quest_id", "quest_name", "task_category", "publisher", "release_date", "difficulty_level", "location" and "reward". So the above query requirements can be realized via the following SQL query.

SELECT 

  quest_name,

  release_date,

  difficulty_level,

  reward/q.difficulty_level AS reward_difficulty_ratio

  CASE

    WHEN q.location IN ('Novigrad', 'Oxenfurt', 'Velen') AND q.difficulty_level = 4 AND q.reward > 300 THEN 'preferred quest'

    ELSE NULL

  END AS preference,

FROM 

  (

    SELECT 
    
      *
    
    FROM 

      quests_1499

    WHERE 

      task_category = 'monster-hunting'

    ORDER BY 

      difficulty_level DESC

    LIMIT 50

  ) 

  UNION

  (

    SELECT 

      *
    
    FROM 

      quests_1499

    WHERE 
      
      task_category = 'missing-people-finding'
    
    ORDER BY 
     
      difficulty_level DESC
    
    LIMIT 50

  )

****

**Total point**: 0 (challenge 1) + 20 (challenge 2) + 10(challenge 3) + 10 (challenge 4) + 5 (challenge 5) + 25(challenge 6) + 20 (challenge 7) + 10 (challenge 8) = 100 points
