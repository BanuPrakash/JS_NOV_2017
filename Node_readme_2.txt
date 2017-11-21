
MongoDB, Mongoose and Express
-----------------------------

MongoDB is a NoSQL database, not Relational

BSON format ==> Binary Script Object notation

RDBMS 										MongoDB

1) Relational								not Relational
	EMP 								
	EMP_NO  NAME DEPT_NO (FK)					{
													"empno": 1,
	DEPT 											"name" : "Smith",		
	DEPT_NO NAME LOC								"dept" : {
														"loc" : "Noida"
													}
												}
2) Table 									Collection
3) columns 									fields
4) rows 									instance

----------------------------------------------

1) install mongodb
2) Add MongodB [C:\Program Files\MongoDB\Server\3.4\bin] to PATH variable
3) create a folder "data" for storing BSON data
4) Start MONGO Database 
	$ mongod --dbpath ./data
5) start MONGO Shell
	$ mongo
6) DOWNLOAD "sales.json" from https://github.com/BanuPrakash/JS_NOV_2017

7) Import JSON data into mongodb database
mongoimport --file sales.json --db my_db --drop --collection sales

8) Run MONGO DB commands in mongo Shell
  a) use my_db
  b) show collections;
  c) db.<<collection>>.command
  	example:
  		db.sales.find()
  		db.sales.find().pretty() // shows 20 records at a time [ use "it" for next iteration]

  		db.sales.find().pretty().limit(2)


  		Where clause:
  		db.sales.find({"quarter":1}).pretty()
  		db.sales.find({"quarter":1, "category": "Beverages"}).pretty()

  		Where [ quarter = 1 or category = 'Beverages']
  		db.sales.find({"$or":[{"quarter":1}, {"category": "Beverages"}]}).pretty()

  		Select fields:
  		[ select category from sales where quarter = 1]
  		db.sales.find({"quarter":1}, {"category": 1 } ).pretty()

  		db.sales.find({"quarter":4}, {"category": 0 } ).pretty()

  		db.sales.insertOne({"quarter":2,"category":"test","sales":4444});

  		db.sales.insertMany([{},{},{}])

  		update sales set "sales" = 50000 where quarter = 1;
  		db.sales.updateMany({"quarter":1}, {"sales":50000});
  ---------------------------------------

  	EXPRESS is a framework for building traditional web application and also
  	RESTful web services

  	Install express and express-generattor globally

  	npm i -g express express-generator

  ==> Build express application

  $ express -e myexpressapp

  	-e ===> EJS
  	if you don't mention this it takes "JADE" instead on EJS

  Templates
  Server Side Templates 					Client Side Templates
  JSP										Underscore
  PHP										Mustache
  ASP, ASP.NET 								Handlebars
  EJS, JADE , PUG               			jQuery Templates

  ---
  install npm modules:
  myexpressapp>npm install

  -----
  	EXPRESS <==  DRIVERS [ MONGOOSE] ==> MongoDB
  
  	Mongoose is a MongoDB object modeling tool

  	npm i --save mongoose
