# Lecture notes for Data Engineering in Spring 2015
---
---
## Lecture 1 - "Big Data Software Engineering"

###### Tasked to create presentation on Markdown for Thursday's class.

### What do you think of when we hear the term 'Big Data'?
  * Social Networks
  * Data analytics
    * Sampling
    * Machine Learning
  * Storage
    * NoSQL - Originally referred to databases with strictly No SQL
      * Data Modeling is 'wicked hard'
    * Document Databases
    * Graph Databases
    * Key Value Stores
    * Colomnar Stores
  
Big Data changed the way we look at data because we don't need to sample as much, we can store everything (clicks, likes, visits, ...)

You can create table structures (schemas) for particaular data you're interested in.

NoSQL systems are bad at performing arbitrary queries.
SQL systems are good at performing arbitrary queries.

### Data Collection + Cleaning - collect data, and get it into a format you can actually use

InfoViz
* D3 - helps visualize data
* Tablo
* Excel
* R

### Data Lifecycle
* Begin with a question
* Curation ( choosing which data source to use )
* Triage ( prioritization )
  * Collection
    * Generation
  * Clean Up
  * Storage
  * Processing/Analysis
  * Query + Visualize + Act 
* Request Response Cycle
* HTTP requests -> HTTP Server -> HTML File
  * GET
  * POST
  * PUT
  * DELETE  
 
---
## Lecture 2 - "Services"

###### Visit education.github.com for student developer pack.

Web browser -> Web server -> (GET, POST, PUT, DELETE, etc...) -> Handler

You have about 2 seconds before you lose most users.

Requests make call to server for an index.html file to load.

RESTful
* REpresentational State Trasfer
* URIs as resources

CRUD
* Create
* Read
* Update
* Destroy

For example, on a /users URL
GET - Read operation ( /users/{ID} )
POST - Create a new user
PUT - Update existing user
DELETE - Destroy user

To create a service, we must decide, what will my Database look like?
* IDs
* Input
* Output
* Error handling
