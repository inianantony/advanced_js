# advanced_js
project to expalin the advanced concepts of JS

Credits to 

```
Advanced JavaScript by Kyle Simpson
```

## Create a Node js project

Detailed explanation in https://github.com/inianantony/es6/blob/master/README.md

## Concepts

### Compiled vs Interpreted
1. JS is kink of compiled language , I would call as a parsed 1st time language
2. Every time JS runs in browser its compiled or parsed by the JS engine in browser
3. JS is not an interpreted langauge like bash programming, where bash dont know the next line of code until its executing reached that line

### Auto global scope creation

```javascript
function baz(foo){
	foo = "bam";
	bam = "yay";
}
```

In the line `bam = "yay"`, JS will look for `bam` in the function scope of `baz` and the scope manager will give up since it cant find , so JS engine will look for the variable in one scope above which is global scope. And since we look for an LHS ( left hand side) scope lookup the scope manager will create one variable in global scope as `bam` and will pass to us. So when we assign "yay" we are assigning in the global scope. If the lookup was for RHS then it will throw an exception

### Scopes shadow and they dont pollute

```javascript
var foo = "bar";
function bar(){
	var foo = "baz"; // This is local scope of bar and it shadowed the global scope

	function baz(foo){
		foo = "bam"; // this is the local scope of baz and it shadowed the bar's scope of foo
		bam = yay";"
	}
	baz();
}
bar();
foo; // Since scopes shadow and they dont pollute, the value of foo is stil "bar"
```


### Function definition vs Function expression

if function keyword is the start of the statement then its the function definition, else its function expression. Named function expression as shown in the 2nd expample we name our function expression as bar, so we can even reference ourself inside this bar function and also the debugging stck strace shows our name and the code is self documenting

```javascript
//Anonymous function expression

var foo = function(){
	//....
}

//Named function expression

var foo = function bar(){
	//....
	// we can reference ourself 'bar' in here
}
```

## Code explanation
