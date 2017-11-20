
JavaScript

Banu Prakash C
banuprakashc@yahoo.co.in
banu@advantech-global.com
banu@lucidatechnologies.com
---------------------------

	Softwares Required:
	1) Chrome Browser
	2) Sublime text 
	3) Node JS
	4) mongoDB
	5) Visual Studio Code
----------------------------------------------

	JavaScript -> Scripting language, loosely typed

	number, string, boolean, object, undefined , null

	ECMA 5 version

	keyword "var" is used to decalre a variable

	var data = 10;

	data = "Harry";

	data = true;

	----------

	JavaScript functions

	a.js

	var data = 100;
	function doTask() {
		var one = 10;

		if(data > one) {
			var two = 20; //hoisting
			three = 30; // will be hoisted to global scope because no "var" keyword
		}

		console.log(data, one, two, three);
	}

	console.log(data, one, two, three);

	--------------------------------

	function add(x, y) {
		var result = x + y;
	}


	console.log(add(4,5)); // ?

	--------------------------

	Every function is an instance of "Function"

	var add = new Function("x","y", "return x + y");

	console.log(add(4,5));

	------------------------------------------------

	JS Engines

		V8 ---> Google [ Chrome, NodeJS]
		Chakra ---> MS [ IE]
		Continnium --> MS [ Edge]
		SpiderMonkey --> FireFox, Adobe 
	---------------------------------------------------------

	OOP, Functional Programming, Design Patterns, ES 6


	Object Oriented Programming

	1) var obj = new Object();

		obj.id = 10;
		obj.name = "Tim";

		obj.doTask = function() {
			//
		}

	console.log(obj.id);
	console.log(obj["name"]);

	2) JSON
		JavaScript Object notation

		{
			id : 100,
			name : "Smith",
			doTask : function() {

			}

		}
   3) Constructor Pattern [ function ]

   	function Employee(id, name ) {
   		this.id = id;
   		this.name = name;

   	}

   var emp =	new Employee()

   	3.1) Object owned instance method
   	3.2) class owned instance method
   	3.3) class method


   	Object owned instance method
   	function Employee(id, name ) {
   		this.id = id;
   		this.name = name;
   		// 
   		this.getDetails = function() {
   			return this.id + this.name
   		}
   	}

   	var e1 = new Employee(2,"A");
   	var e2 = new Employee(4,"B");

   	e1.getDetails();
   	e2.getDetails();

   	class owned instance method

   	function Employee(id, name ) {
   		this.id = id;
   		this.name = name;
   		
   	}


   	Employee.prototype.getDetails = function() {
   			return this.id + this.name
   	}

   	// class method
   	Employee.someTask = function() {

   	}
 -------------------------


 	Functional Programming with JavaScript

 	OOP 								Functional
 	tightly coupled 					just a behavior without tightly coupled to object
 	to state of object

 	Functional Programming using High Order Functions.

 	High Order Functions are functions:
 	1) which takes function as an argument
 	2) returns a function


 	var data = [3,5,6,22,62,6];

 	for(var i = 0; i < data.length; i++) {
 		console.log(data[i]);
 	}

 	for(var i = 0; i < data.length; i++) {
 		alert(data[i]);
 	}

 	With High Order functions:

 	function iterate(elems, action) {
 		for(var i = 0; i < elems.length; i++) {
 			action(elems[i]);
 		}
 	}

 	iterate(data, console.log);
 	iterate(data, alert);

 	--------

 	Commonly used High Order functions:
 		1) MAP
 		2) FILTERS
 		3) ITERATE ==> forEach
 		4) REDUCE
 		5) SORT
------------------------------

	test.js

	var data = 100;
	function doTask() {
		var one = 10;

		function second() {
			var two = 11;
			console.log(data, one, two);
		}		
}


2) High Order Functions [ Functions return a functions]

	function adder(x, y) {
		return x + y;
	}

	console.log(5,3); // 8

	function adder(x) {
		return function(y) {
			return x + y;
		}
	}

	var fiveAdder = adder(5);

	var tenAdder = adder(10);

	console.log(fiveAdder(3));

------------------------------------------------------

	Closure can be used to implement Memoize design pattern [ Cache]
---------------------------------------------------------------------


IIFE ( Immedieatly Invoke Function Expression)
	
	// Self invoking function
	(function(){

	})();

Design Patterns:
	1) Module Pattern
	2) Factory Pattern
	3) Memoize pattern
	4) Chain
	5) Observer Pattern
	6) Singleton

--------
Module Pattern : brings in the concept of encapsulation to JS

semi-colon insertion
function add(x, y) {
			return
					x + y;
}

console.log(add(4,5)); // 9 ==> undefined
-------------------------------

Factory Pattern

Observer Pattern
		function() {

		}();
--------------------------------------------------

Chain of Responsibilty
		
	JSON is a singleton

	https://github.com/BanuPrakash/JS_NOV_2017
--------------------------------------------------

 Modules -> Encapsulation, avoids data corruption

 In Hugh web application, we may have many modules, each module maybe in
 a seperate "js" file.

 Problems:	
 	1) Depdendency
 	2) Heavy

 AMD ===> Asynchronous module Defintions

 requireJS
---------------------------------------

ES 6 ===> ECMA 6 ===> ECMA 2015 
	
	1) Scope variables and constants
	let and const keywords

	var data = 100;
	function doTask() {
		var one = 10;

		if(data > one) {
			let two = 20; //no hoisting
			three = 30; // will be hoisted to global scope because no "var" keyword
		}

		console.log(data, one, two, three); // two is not visible
	}

	for(let i = 0; i < 5; i++) {

	}

	console.log(i);

2) Deconstructing

	var colors = ["red","green","blue","pink","orange"];

	// prior to ES2015

	var r = colors[0];
	var g = colors[1];

	// now with Es 2105

		var [r,g,b, ...others] = colors;

3) Arrow Operator

	function add(x,y) {
		return x + y;
	}

	var add = function(x,y) {
		return x + y;
	}

	with ES2015

	var sub = (x,y) => {
		return x + y;
	}

	var sub = (x,y) => x + y;

4) Promise API
	
5) class

class Employee {
	id;
	name;

	constructor(id, name) {
		this.id = id;
		this.name = name;
	}

	getDetails() {
		return this.id + ", " + this.name;
	}
}

let e = new Employee(2,"Test");
-----------------------------------


