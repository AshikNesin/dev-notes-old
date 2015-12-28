## Functions


```js
	function myFunction(a,b){
		// code here...
		return x;
	}
```

-	Extra parameter are ignored
-	Missing are passed as "undefined"

## Anonymous Functions


However, we can create functions without names, just be leaving the name out:

```js
      function () {
          return "this function has no name";
	  }

```


We can assign a function (named or anonymous) to a variable, and execute it with that variable name.

```js
	var console = {
		log : function () {
		// code here
		}
	}
```

This is called an anonymous self-invoking function

```js
		function(){
			// code here...
		}();
```

## String


### length

Length property of a string is the number of characters in the string. This one is actually a property, not a method.

### indexOf

This method returns a number, the index of your “search term.”

```js
	str.indexOf("abc")
	str.indexOf("abc",STARTING_INDEX)
```

### slice

slice(STARTING_INDEX,ENDIND_INDEX)


```js
	var name="Ashik Nesin";
	
	name.slice(0,4); // "Ashi"
```

If you leave the second one off, it will slice until the end of the string.
      
### substr

substr(STARTING_INDEX,LENGTH_OF_STRING)


```js
	name.substr(6,3); // "Nes"

	// you can use a negative number for the  first parameter

	name.substr(-5,5) // "Nesin" 

```

### substring [NEED TO CLARIFY IT]

A negative value for either parameter acts as 0—it refers to the start of the string. The neat thing about substring is that, unlike slice, the second parameter can be lower than the  rst (while still positive). When this is the case, substring goes back to the character of that index. For example

substring(STARTING_INDEX,GO_BACK_TO_INDEX)


### split

It splits an string and make it to an array.

```js
	var arr="Ashik Nesin".split(" ");
```


### toLowerCase and toUpperCase

Converts text to upper case or lower case


## Numbers 


1. toExponential()

2. toFixed()

3. toPrecision()

It returns string.

You can use the global function **parseInt and parseFloat**

isNaN(x) => Checks whether its Number or not.


## Date Methods

### Method Name & Return Value

# ASCII TABLE HERE....


getDate => day of month, 1 – 31
getDay  => day of week, 0 – 6
getFullYear => year
getHours => hour, 0 – 23
getMilliseconds => milliseconds, 0 – 999
getMinutes => minutes, 0 – 59
getMonth => month, 0 – 11
getSeconds => seconds, 0 – 59
getTime => milliseconds since January 1, 1970
getTimezoneOffset => difference between GMT and local time, in minutes


* setDate
* setMinute
* setFullYear
* setMonth
* setHours
* setSeconds
* setMilliseconds
* setTime

### parse

It actually converts date to a number, the number of milliseconds since midnight on January 1, 1970


## Array Methods


### join

It will join all the elements in the array into a string. You can pass a single parameter to join that will be put between each element in the array.

``` ["Ashik","Nesin"].join(' ') // "Ashik Nesin" ```

By default it leaves comma (,) bitween them

### pop / shift

pop removes the last item and returns the length of the array.

shift removes the first item in array and returns it.

### push / unshift

Same as pop & push but it adds item.

### reverse

It returns the reverse of the array.

### slice


Unfortunately, it sorts numbers “alphabetically,” too, which
means that the array [0, 5, 10, 15, 20, 25] will be sorted
to [0, 10, 15, 20, 25, 5].

To sort number,

```js
	  var arr = [5, 2, 3, 4, 1];
      arr.sort(function (a, b) {
          return a - b;
      });
      console.log(arr); // [1, 2, 3, 4, 5];

```

## Math Functions


* min
* max
* random
* round => nearest whole number
* ceil	=> round up
* floor => round down
* pow

