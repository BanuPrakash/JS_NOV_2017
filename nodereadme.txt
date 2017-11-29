https://github.com/BanuPrakash/JS_NOV_2017

Recap
-----
JS features
OOP
Functional Style of Programming
JS Design Patterns ( Module, Observer, Factory)
ES6 features ( scope, arrow, deconstructing, new string literal, promise, modules)
AMD ==> Asynchronous Module Definition
------------------------


NODEJS provides environment for execution of JS, the env is created using V8 engine.

NodeJS is event-driven, NON-BLOCKING IO.

	test.js

	function doTask() {
		setTimeout(function print() {
			console.log("Hello");
		}, 100);
	}

	$("btn").on("click", function message() {
		console.log("you clicked");
	});

	console.log("Start!!!");

	doTask();

	-------------------



	NodeJS uses CommonJS module system
	----------------------------------

	basic.js

	module.exports.add = function() {

	}

	module.exports.sub = function() {

	}

	test.js

	var add = require('./basic').add
	var sub = require('./basic').sub

		add()
		sub()
	-----------------

	nodeJS uses NPM [ Node Package Manager] to manage node modules [ publish, install, uninstall, upgrade]

	-----------------

	built-in modules:
		fs, http, net, repl
-----------------------------------------------------
	
 node module:
 	1) package.json
 		is a file which contains 
 			a) dependency modules
 			b) devDependency modules
 			c) scripts
  Build modules and test them

  JavaScript unit testing frameworks: Jasmine, Mocha

  chai is an assertion library

  npm i --save-dev mocha chai request


  npm i -g mocha

  ----------------------------------

  MongoDB --> noSQL database, not relational stores data as BSON

  RDBMS 									MONGODB
  Database 									Database
  Tables  									Collection
  ROW/ Tuple 								Document
  Columns 									fields


  -----
  1) Start MongoDB server
  	$ mongod --dbpath ./data

  2) Open Mongo Shell
  	$ mongo
  	> show databases

  3)  import json data into mongodb database
  https://raw.githubusercontent.com/BanuPrakash/JS_NOV_2017

   $ mongoimport --file sales.json --db my_db --drop --collection sales

  4) mongo shell
   > use my_db
   > show collections

   Fetching records:
   > db.sales.find()
   > it
   > db.sales.find().pretty()
   > db.sales.find().limit(3).pretty()
   [select * from sales where quarter = 4]
    db.sales.find({'quarter':4}).pretty()

    [select * from sales where quarter = 4 and category = 'Beverages']
    db.sales.find({'quarter':4, 'category': 'Beverages'}).pretty()


    [select * from sales where quarter = 4 OR category = 'Beverages']
    db.sales.find({"$or": [{'quarter':4}, {'category': 'Beverages'}]}).pretty()

    [ select category from sales where quarter = 4]
    db.sales.find({'quarter':4},{'category' : 1}).pretty()

    INSERT:
    db.sales.insertOne({category:"Beverages", product:"ABC", sales:2720.8, quarter:1})
    db.sales.insertMany([{},{},{}])

    db.sales.remove({'product': 'ABC'})

    db.sales.updateMany({'quarter': 3}, {'sales': 3333});

    ------------------------------

    Express Framework for building Traditional web applications and REST APIs



    npm i -g express express-generator

    Templates

    Server Side Templates  						Client Side Templates
    JSP 											HandleBar
    PHP 											Underscore	
    EJS												Mustache
    JADE 											jQuery Templates
    PUG

    --------------------

    	RESTful WEB SERVICES

    	REPRESENTATION STATE TRANSFER
    	 Resource present is server is served in various representations to the client

    	 REST uses "http" protocol

    	 URI identifies the resource
    	 HTTP methods identify the action

    	 GET:
    	 http://adobe.com/customers

    	 send all customers in JSON/CSV/XML represention to the client

    	 http://adobe.com/customers/2
    	 send customer whose id is 2

    	 http://adobe.com/customers?place=bangalore
    	  send all customers from bangalore in JSON/CSV/XML represention to the client



    	 POST:
    	 http://adobe.com/customers
    	 payload contains the new record to be inserted into customers resource

    	 PUT and PATCH:
    	 http://adobe.com/customers/4
    	 payload contains the modified record of customer whose id is 4


    	 DELETE:
     	 http://adobe.com/customers/33
    	 No Payload: delete custoemr with id 33


    	 mongoimport --db my_db --collection customers --file customers.json