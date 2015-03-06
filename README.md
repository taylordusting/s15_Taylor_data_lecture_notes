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

###### Visit education.github.com for student developer pack. (on professor's github)

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

---
## Lecture 3 - "RESTful Web Services"

SOAP - simple object access protocol  

REST is an approach to developing web services that mimic the design of the Web itself.  

Search URL ex: api/1.0/search?q=tattersail  

ISSUES:  
Security: How to authenticate users?  
Identity: How are ids assigned to resources?  
Failure: How to handle failure situations?  
* Could use HTTP Status codes, or JSON handlers or combination of both
Persistance: How are resources stored?  

Contacts Web Service  
Technologies Used:  
* Sinatra  
* Rspec  
* Typhoeus  
* Node  
* Express  

Rspec uses methods like 'describe' and 'it'  


---
## Lecture 4 - "Git and GitHub presentations"

Git  

Untracked - files not yet in the repo  

'git init' - starts a repository  
'git clone *remote_repository_address*' - clones existing repo  

HEAD - shortcut for what's the latest commit for the branch I'm on?  

GitHub  
:shipit:

---
## Lecture 5 - "Node.js"  

http.createServer() - will initiate a server with node  

Javascript is dynmaically typed (no types)  

Event loop - while there are events to be handled, do something.  

Can connect to the event loop with funcitons like:
* process.nextTick()
* process.setTimeout()
* log()
* etc..  

setTimeout() takes a second parameter that sepcifies how long to wait before the function is executed  
setInterval() takes a parameter that specifies the interval at which this function should be executed  


---
## Lecture 6 - "Express"  

Express - web applicatin framework written in Javascript for use in Node.js
* Design influenced by Sinatra

npm init creates a package.json  
npm install will download dependencies


---
## Lecture 7 - "Angular JS"  
A web application framework on the client side (lives in the browser)  
* Written in Javascript
* Implements model-view-controller to produce modular web clients
* Gets complicated in a hurry, but is VERY powerful

Core Concepts
* Data bindings
  * Value of HTML tag can be associated with a model object, when one changes, Angular updates the others automatically.
* Controllers
  * Controllers are associated with a portion of yuor HTML and define all of the state methods that can be accessed within that section of the page
  * With controllers, you can modularize your web app and decompose data and functionality into small chunks
* Services
  * Controllers are used to manage data for some portion of a page while it is being displayed. As you move from page to page, controllers will come into and go out of existence all the time
  * If you need to maintain states between invocations of a controller of if you need to share a state between to controllers, you can create a service
  * Services are created when an Angular app is intialized
* Directives
  * Directives are ubiquitous in Angular, their primary use is to allow Angular to integrate into HTML in a natural way
  * They can also be used to create reusable components that combine controllers, data, and HTML
     * A _login form_ for instance, that can be re-used across multiple projects
* Embeddable
  * Angular can control as much or as little of a web page as you specify
  * It is easy to embed a small Angular component into an existing page, then expand it out 
* Injectable
  * Angular makes use of a concept called dependancy injection
  * Rather than use a main routine to wire everything together, Angular controllers and services declare their dependencies up front (Spring framework)
  * Angular at run-time then locates the dependencies and injects them into the component that needs them at run-time  

Modules
* A module is the primary way to package up a set of controllers into an Angular app.
* To create a module, give it a name and list its dependencies
```java
angluar.module('contactApp',[])
```
* This creates a module called contactsApp, and this modules has no dependencies
* Once you have create a module, you gain a handle to it by calling anglular.modules('contactsApp')

Controllers
* declared using the controller function
```java
<MODULE_NAME>.controller('MainController', [function() {
  code
}]);
```

```java
<MODULE>.controller('MainController', ['$http, function($http) {
  var self = this;
  self.name = "Dustin";
  self.update = function() {
    return $http.get('/api/1.0/update_name').then(fucntion(response))
      self.name = response.data.new_name;
      return response;
    });
  };
}]);
```
Hello world
```java
<!DOCTYPE html>
<html ng-app="hello">
  <head>
    <title> Hello Controller </title>
  </head>
  <body ng-controller= "HelloController as c">
    <p> The message is: <input size="30" type="text" ng-model="c.message"></p>
    <p> The message is: {{c.message}}</p>
    <p><button ng-click=c.changeMessage()">Change Message</button></p>
    <script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.3.11/angular.min.js"></script>
    <script>
      angular.module('hello', []).controller('HelloController', [
        function() {
          var self = this;
          self.message = "Hello from the Controller";
          self.changeMessage = function() {
            self.message = "Goodbye from the Controller";
          }
        }
      ]);
    </script>
  </body>
</html>
```

---
## Lecture 8 - "Angular JS (cont.)" 

Lots of talk about code.  


---
## Lecture 9 - "Twitter App" 

Takled about setting up a Twitter App.

---
## Lecture 10 - "Twitter App (cont.)"

Continued discussing the set up of the app.

---
## Lecture 11 - "Twitter App (cont.)"

Continued discussing the set up of the app.

---
## Lecture 12 - "Intro to NoSQL"

Homework 3 - fork repo, sync a fork, create branch, add functionality to app, create pull request.  

Sharding a database - need multiple instances of a database server, each with its own server

NoSQL databases are aware of their distributed nature
*  manages the sharding for you
*  they are HORIZONTALLY scalable
*  are fault tolerant

Types of NoSQL databases:
* Key-value
* Graphs
* Columnar
* Documents

__Key Value stores__ store a simple database that when presented with a string returns an arbitrarily large set of data  
__Graph Stores__ are optimized to store graph structures rather than table/row/column structures, do graph traversals easily  
__Columnar Stores__ are able to scale to large amounts of data, very fast writes. Column families consist of rows that have unique row keys
__Document Stores__ are like a key-value store but with more structure, you insert documents (bags of key value pairs), and then document gets indexed, documents can be grouped into collections, and collections can be grouped into databases.

What about these databases makes them NoSQL?
* They have no schema
* You are often free to store anything in these databases


---
## Lecture 13 - "CouchDB"  

CouchDB is a Document NoSQL Database, implemented in Erlang (used in telecommunications)  
Document databases: self-contained data  

CAP Theorem - Pick ANY TWO  
There are issues involved when running more than one server:
* Consistency
  * clients see the same data even in the presence of concurrent updates
* Availability
  * clients are able to read or write the data store when they want
* Partition Tolerance
  * database can be split across multiple server  


---
## Lecture 14 - "MongoDB" 

mongodb.org/downloads

Homework 3 stuff  

add your file to requests under twitter_framework

def twitter_endpoint
  "/users/show"  <---- put your endpoint here
end

def url
  'https://api/twitter/com/1.1/users/show'
end


---
## Lecture 16 - "More MongoDB" 

http://cu-data-engineering-s15.github.io/lecture_16/#/18 






