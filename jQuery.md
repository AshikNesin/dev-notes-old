### Load Document

```js

$(function(){
	//code
});

$(document).ready(function(){
	//code
});

```


### Fastest to slowest selector are:

-	The ID selector ("#AnElementWithID")
-	Element selectors ("form","button","input", etc.)
-	Class selector (".someClass")
-	Pseudo & Attribute selectors (":visible, :hidden, [attribute=value] etc.")

### Caching Variables

Each $('.whatever') will re-run your search of the DOM and return a new collection

```js
	var parents = $('.parents');
	var children = $('.parents').find('.child') //bad

	var children = parents.find('.child') //good
```

### Chaining

Almost all jQuery methods return a jQuery Object and support chaning

After you've run a method on your selection, you can continue running more!

Less code, easier to write and it runs faster!

```js
	
	var parents = $('.parents').doSomething().doSomethingElse();

```
