When the browser loads a page, it converts the HTML text that you have written into a tree of nodes.This is half of what the browser brings to the table. The other half is the functionality to access all those things: it’s a JavaScript object that allows you to  nd and manipulate this tree of nodes.

These two parts together are called the Document Object Model or DOM, for short.
Working with HTML

## Finding Elements

### By Id

```js
	document.getElementById("id_name")
```

### By Class

```js
	document.getElementsByClassName("class_name")
```

### By Tag Name

```js
	document.getElementsByTagName("p") 
```