
```

# CSS

display:inline-block // Display that block in same line

display:block

### z-index



**Note** 

z-index works on positioned elements (po-a,po-r,po-f)

### Show only portion of Image

```css
	.container {
		position:relative;
	}
	#clip {
	position:absolute;
	// clip : rect(top,right,bottom,left)
	}
	clip-path : inset
```

### When targeting img within div
```
	#bgContainer img{
	
	}
```


### Picture to align center
```
	#over img{
		display:block;
		margin-left:auto;
		margin-right:auto;
	}

```

### Center href

```
	a{
		display:block;
		text-align:center;
	}
```


### Remove underline from <a>

``` text-decoration:none;```

### Fit background image to div

```css
	background-size:contain;
	background:url('...') no-repeat;
```

### Center a div

```css
	.container{
	margin-left:auto;
	margin-right:auto;
	}
```



### Pass combobox value to JS

```
	function getComboboxValue(cmb1,cmb2){
		var code1= document.getElementById(cmb1).value;
		var code2= document.getElementById(cmb2).value;
	}
```

If we use two "id" then second one will be neglected

### Check empty variable in JS

```
if(variableName)

if(variableName[0].value)

```

### Execute JS after few seconds/minutes

```js
	setTimeOut(function(){ customFunction(); },5000);
```

### Call function within $() ready

```js
	var globalFn();
	globalFn() = myFunction(){ }
```

