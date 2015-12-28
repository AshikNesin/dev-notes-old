### Premitive Values

- String
- Number
- Boolean
- Undefined
- Null

### Reference Types (Objects)

- Object
- Array
- Function
- Date
- RegExp

Everything other than those premetive values are objects including AJAX,etc...


## Properties & Method

A property basically holds some value or even a function (which makes them method)

A method is an action by executing function

 ## Creating Object & Factory functions

 ```js
 	// old way
 	var person = new Object(); // 
 	Vanila object

 	person.firstName="Ashik";
 	person.lastName="Nesin";
 	person.sayHi = function(){
 		return "Hi there";
 	};

 	// object literal notation

 	var person = {
		firstName:'Ashik',
		lastName:'Nesin',
		fullName: function(){
			return this.firstName+ ' '+this.lastName;
		}
 	};

```

In object oriented terminolgy we can say that person object has 3 members (property & method of object)

### Why Object Literal Notation ?

- Performance (single complex stmt is effecient than multiple simple stmt)
- Organization
- Less code

## Factory Function

It create an object and returns it.

```js
	
	var createPerson = function(_firstName,_lastName){
		return {
			firstName:_firstName,
			lastName: _lastName,
			fullName: function(){
				return this.firstName + ' ' + this.lastName;
			}

		};
	}
	
	var aNesin = createPerson('Ashik','Nesin');
```

## this Keyword

The value of **this** is depeneded upon the object that function is attached to.

Whenever global variable/function ,those things are actually as members of a global object(window)

```js
	// var name = 'Jane Doe';
	window.name = 'Jane Doe'

	var globalGreet = function(){
		return "My name is" + this.name; // Jane Doe
	};

	var johnDoe = {
		name: 'John Doe',
		greet: globalGreet // John Doe
		
	};

```

## Bind

Many times we need to assign an object that is still bound to other object

```js
	var johnDoe = {
		name: 'John Doe',
		greet: globalGreet.bind(window) // Jane Doe
		
	};

```

## Data and Accessor Properties

```js
	
	var createPerson = function (_firstName, _lastName) {
		var person = {};
		

		Object.defineProperties(person,{
			firstName: {
				value: _firstName,
				writable: true,
				enumerable: true	

			},
			lastName: {
				value: _lastName

			},
			fullName: {
				get: function(){
						return this.firstName + " " +this.lastName;
					},
				configurable: true
				},
			changeFirstName: {
				set: function(data){
					 this.firstName = data;
				}
			}
		});

		return person;
	};

	var person = createPerson("Ashik","Nesin");

	Object.defineProperty(person,"fullName",{
		get: function(){
			return this.lastName +", " + this.firstName;
		}
	});

	Object.keys(person) // ['firstName']
```