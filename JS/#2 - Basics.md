## Variables



### Naming

You can name your variables whatever you want.

1. letters
2. numbers (can't start with it)
3. _ (underscore)
4. $

### Declaring

When creating variables, you need to put the keyword ``` var``` before the variable name.

```js
	var name;
	name="Ashik";
	var fullname="Ashik Nesin"
```

## Data Types


###  Number

Unlike other programming languages, both integer and float is same in js.



### String 

A string of text must be surrounded by either double or single quotes.

```js
	alert("Here is some text");
    alert('This text is surrounded by single quotes');
```


### Array 

Array are used hold bunches of data. They’re very similar to objects, but without the keys.

An array is delimited by brackets and each value is separated by a comma. You aren’t limited to only one data types. In face you can declare an array within array.

```js
	  var arr1=["Facebook", "Twitter", "Google +"];
      var arr2=["string", 20, false, null, { "id" : 8888 }];
      var arr=[arr1,arr2];
```

Array item indices are **zero-based**, which means the  rst item is 0, the second is 1, and so on.


### Object

Think of an object as a wrapper for a bunch of primitive or reference values. Here’s an example:

Inside the object, we have a list of key-value pairs.Each pair, except for the last one, ends with a comma.

And you can get the value in it in two ways.

```
    var obj = { name : "Joe", age : 10 };
    alert( obj.name ); // "Joe"
    alert( obj["age"] ) ; // 10
```

### Date Object

To make a JavaScript Date object, you’ll do this:

```js
	var myDate = new Date() 
```

The new keyword simply means we want to create a new object; in this case, that’s a date object. Date, in this case, is the name of a function. 

There are several parameters you can use to create other dates. You can pass in a string date:
 
```js
	new Date("January 17, 2012") 
```

Or, you can pass a list of parameters, corresponding to the following list: year, month, day, hour, minute, second, millisecond.

```js
	new Date(2009, 3, 20, 17, 30) 
```

Month number is **zero-based**. This means that to get January, you use the number 0 and to get December, you use 11.

### Null and Undefined

When you try to get a value that doesn’t exist (like a variable with no value), you’ll get **undefined** back.


### Comments

To make a single-line comment, use two backslashes.

```js
	// This is a single line comment 
```

If you want multi-line comments, use a backslash and an asterisk; reverse that to end the comment:

```js
	/*
      This is multiline comment...
      author : Ashik Nesin
      email :  mail@ashiknesin.com
      
	*/

```


## Operators


### Arithmetic Operators

 They’re your standard math operators.

 ```js
 	var four = 2 + 2, //addition operator
		hour = 24 - 13, // subtraction operator
		seventy = 7 * 10, // multiplication operator      
        avg_days_per_week = 365 / 52, // division operator 
		remainder = 31 % 2, // modulus operator
		msg = "the time is " + hour + " o'clock"; // concatenate the strings
 ```

### Comparison Operators

Besides acting on values, you’ll want to compare them. You’ll be familiar with some of these:

```js

	  console.log( 10 < 5 ); // false
      console.log( 10 > 5 ); // true
      console.log( 4 <= 3 ); // false
      console.log( 4 >= 3 ); // true

```

We can also compare string.

Well, each letter has a **character code**, a number that  identifies it. It’s the numbers that are compared. All the capital letters come before the lower case ones,so"A" < "z" is true.

### Unary Operators

#### Increment & decrement

There are several operators that only work with one value. First off, we’ve got the incrementing and decrementing operators:

```js
    var i = 5;
    i++ // returns 5 BUT sets i = 6
	++i // returns 7 & sets i = 7
    
    i--; // 7
	--i; // 5

```

These operators return a value too, just like the other ones. In this case, they return the value of the number they are incrementing

prefix (that the operator on the front) operators increment the number before returning the value, which the postfix operators return the value, then increment the number.


#### Typeof Operator

Typeof operator will return the type of the given variable

typeof true => boolean
typeof null => object
typeof 'Hello' => string


```js
	console.log(typeof(10)) // number
	console.log(typeof("Hello World")) // string
	console.log(typeof(new Date)) // object
```

### Assignment Operators

We’ve looked at assigning with the = operator; but there are a few others that I think are taught best by demonstration:

```js
	var num = 10;
	num += 5;
	num -= 2;
	num *= 8;
	num /= 4;
	num %= 2;
```

These assignment operators are used to perform an operation on a value already in a variable and re-assign the new value to the variable.

### Boolean 

Boolean operators are used to test the **trueness or falseness** of a value. Every value in JavaScript can be evaluated as a Boolean. Some values are considered false and others are considered true; you’ll see how this is important later on in this chapter. 

For now, know that these values are considered false:
* false
* null
* undefined
* "" (an empty string)
* 0
* NaN (what you get when you try to add, subtract, etc. a number and another non-number value)

Every other value are considered **true**

#### Logical NOT ( ! )

The logical NOT operator converts the given value to the opposite Boolean value.

#### Logical AND ( && )

It only returns true if both sides of the operator are true. 

#### Logical OR ( || )

It returns true as long as just one of the values are true.

### Conditional Statements 

 If something is true, do this; otherwise, do that.

#### If Statements
It check condition line by line.

```js

	if(condition){
		...
	}
	else if(condition 2){
		...
	}
	else{
		...
	}
```


#### Switch Statements

It check condition line by line. With the switch statement, you only write the expression to evaluate once; it goes in parentheses at the top, right after the keyword switch.

```js
	var something="...";

	switch(something){
		case "..." :{
			// stmt
			break;
		}
		default{
			// stmt
		}
	}
```
Without any break statements, the code under each case will run, but it will “fall through” to the next case statement and execute the code there.


#### Conditional Operator (Ternary Operator)

```js
 	condition ? true : false 
```

### Looping Statements 

#### For Loops

Example

```js
	var person = {
              name: 'Ashik Nesin',
              email: 'mail@ashiknesin.com',
              blog: 'http://blog.ashiknesin.com'
		},prop;
		for (prop in person) {
			console.log("His " + prop + " is " + person[prop]);
		}

```
#### While Loop



