## this

In JavaScript 'this' always refers to the "owner" of the **function we're executing** or rather, to the object that a function is a method of.

That function needs to be assigned to a variable or else it'll refer to the document.

In order it to be assigned to something it must be a variable.

## new

The new operator creates an instance of a user-defined object type or of one of the built-in object types that has a constructor function.

```js
	function Person(name, age, sex) {
	  this.name = name;
	  this.age = age;
	  this.sex = sex;
	}

	var rand = new Person("Rand McNally", 33, "M");
	var ken = new Person("Ken Jones", 39, "M");

```


## call and apply

Since functions are objects, they can have properties and methods. call and apply are two methods that functions have by default.

The only reason for these functions to exist is to change the value of this within the function. 

```js

 function Truck (model, num_of_tires) {
          this.num_of_tires = num_of_tires;
          this.kilometers = 0;
          this.model = model;
      }
      var basic_vehicle = { year : 2011 };
     
      console.log(basic_vehicle); // Object {year: 2011}

      Truck.call(basic_vehicle, "Speedio", 4);
      
      console.log(basic_vehicle); // Object {year: 2011, num_of_tires: 4, kilometers: 0, model: "Speedio"}

```


## Prototype

A prototype is an object from which other objects inherit properties.

Every object and type has a prototype.

Some browser have `__proto__`

The prototype says... "IF I [the object] don't have a property or method that is requested of me, go to the object that this field references - my prototype - and look for it."

```js
	function Product(name) {
          if (name) {
              this.name = name;
          }
      }
      Product.prototype.name = "To be announced";
      Product.prototype.rating = 3;
      var ipad = new Product("iPad");
      alert( ipad.name ); // "iPad";
      alert( ipad.rating ); // 3

```


## Object Methods

### hasOwnProperty

It returns ONLY its properties not its prototypes

```js
	function Person(name) {
        this.name = name;
    }
    Person.prototype.legs = 2;
    var person = new Person("Joe"), prop;
    for (prop in person) {
    	         console.log(prop + ": " + person[prop]);
    }
    // in console:
    // name : Joe
    // legs: 2
	for (prop in person) {
        if (person.hasOwnProperty(prop)) {
            console.log(prop + ": " + person[prop]);
        }
	}
    // console:
    // name: Joe

```

## Closure

JavaScript doesn’t have this, but we can use closure to “make” private variables.

```js
	var revealSecret = (function () {
	          var secretNumber = 1024;
	          return function (password) {
	              if (password === "please") {
	                  return secretNumber++;
	              }
	return 0; };
	      }());
	      alert( revealSecret("please") ); // 1024
	      alert( revealSecret("please") ); // 1025

```

## Errors

There are really two types of errors: errors you make while coding—things like syntax errors and typos—and errors that are unforeseeable—things are break because of something outside your code, such as the user’s input, or a missing feature in the JavaScript engine. 

While the JavaScript engines usually silently solves small errors (such as a missing semicolon), a larger mistake will make it throw (yes, that’s the technical term—throw) an error. Also, we can throw our own errors, if something goes wrong.

Here’s the error-protection syntax:

```js
	try {
	          // code that might cause an error here
	      } catch (e) {
	         // deal with the error here
	}
```

Different web browsers include different properties on the error object. But the main ones are name and message, which are the type of error and a description of what happened, respectively.



## Testing your JavaScript

There are two main types of testing: performance testing and unit testing.
###Unit testing

1. **Unit testing** refers to testing each bit of functionality (each unit) in your code.

2. **Performance testing** refers to making sure you have written your code in the fastest way possible.

## Organizing your JavaScript

### Global Variables

If all the code relies on global variables, there’s a really good chance that one script will overwrite the variables of another script.

Because of this, it’s a best practice to use as few global variables as possible.

If all your code can be contained in one place, you can do this:

```js 
      (function () {
          // all your code goes here
		}());
```

