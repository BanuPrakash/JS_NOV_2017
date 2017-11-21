
Node JS
-------
	NodeJS is an Enviroment built on V8 engine [ Google ]
	V8 engine --> used in Chrome Browser

	NodeJS ---> based on event driven, Non-Blocking IO and Single Threaded


	first.js
	--------

	function test() {
		setTimeout(function doTask() {console.log("Hello"); }, 1000);
	}

	function best() {
		console.log("you called best!!!");
	}

	document.getElementById("btn").addEventListener("click", function(){
		console.log("you clicked!!!");
	});

	test();
	best();
------------------------------------------------------------
nodeJS is based on CommonJS module system to load modules asynchronouly

 "fs" , "http", "repl", "net", "cluster" , ....


NPM ==> Node Package Manager

Create a new node application:
1) npm init
	creates a package.json 
2) add dependencies
npm install --save-dev mocha request chai
3) install mocha globally [ executable modules need to be installed globally]
npm i -g mocha


