### Table of Cover

-	Syntax
-	Understanding objects
-	Understanding the 'function'
-	Understanding 'this'
-	Understanding the 'prototype'
-	Object Oriented Programming (OOP)
-	Building jQuery Plugin with OOP

## Syntax

-	Dyncamically typed.
-	Everything is an object... Even primitives
-	Functions are first-class objects.
-	Multi-paradigm language

	1. Object Oriented
	2. Impertative (procedural)
	3. Functional (lamda, mathematical)


```js

	var myvariable='Ashik'

	// Everything in string is object

	console.log('Ashik'.length) // 'String' gets converted into object.

	var myfunction = function(){

	};

```

## Pattern

Patterns are just as important as Syntax!

http://AddyOsmani.com/resources/essentialjsdesignpatterns

http://shichuan.github.com/javascript-patterns

Refer Addy's Design Pattern Book

## Objects

An object is an unordered collection of key-value pairs.

Value could be anything a string, function,etc..

Declared in JSON format.

```js
	
	var myObject = {
		first: 'Ashik',
		last: 'Nesin'
		something: function (){...}
	};

```
## Function

-	Functions are first-class objects.
-	Functions can be anonymous and inline.
-	Functions encapsulate and capture context.
-	Closures

### Declaring

It's a proper way to declare a function

```js

	var myFunction = function(){
		
	};

	// Anti Pattern
		
	function myFunction(){

	}

```

Declaring function within object. It's a good practice.

```js
	
	var person = {
		first: 'Ashik',
		last: 'Nesin',
		getName: function(){
			return this.first + ' ' + this.last;
		}
	};


```

### Anonymous Function

```js

	setTimeout(function(){
		alert(person.getName());
		},2000);
```

### Closure Functions


## 'this' Pointer

http://quirksmode.org/js/this.html

In JavaScript 'this' always refers to the "owner" of the **function we're executing** or rather, to the object that a function is a method of.

That function needs to be assigned to a variable or else it'll refer to the document.

In order it to be assigned to something it must be a variable.

## Prototype

A prototype is an object from which other objects inherit properties.

Every object and type has a prototype.

Some browser have `__proto__`

The prototype says... "IF I [the object] don't have a property or method that is requested of me, go to the object that this field references - my prototype - and look for it."

## OOP in JS

Uses the prototype to inherit


```js

var MyClass = function () {
	this.first = '';
	this.last = '';
};

MyClass.prototype.setName = function (_first,_last) {
	this.first = _first;
	this.last = _last;
};

MyClass.prototype.printName=function () {
	alert(this.first + ' ' + this.last)
};

```
