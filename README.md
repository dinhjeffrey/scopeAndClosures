# Scope
The current context of execution. The context in which values and expressions are "visible," or can be referenced. If a variable or other expression is not "in the current scope," then it is unavailable for use. Scopes can also be layered in a hierarchy, so that child scopes have access to parent scopes, but not vice versa.

##Preview: Scope
Consider the following code:
```
(function() {
   var a = b = 5;
})();

console.log(b);
```
What will be printed on the console?

```
(function() {
   'use strict';
   var a = window.b = 5;
})();

console.log(b);
```

##Anatomy
```
var add = function(a,b) {
	return a+b
}
add(3,4,5)
```

##Local Scope
```
var func = function() {
	var local = true
}
console.log(local)
```

##Parent vs. Child Scope
```
function blender(fruit) {
	var f = fruit
	var y = 'yogurt'
	function fs(){
	var x = 'asdf'
	console.log(f + ' and ' + y + ' makes ' + f + ' swirl' )
	}
	fs()
}
blender('blueberry')
```
##Precedence
```
var g = 'global'
function go() {
	var l = 'local'
	var g = 'in here!'
	alert (g + ' inside go')
}
go()
alert(g + ' outside go')
```

##Block Scope
```
var inBlock = false
for (var i=0; i<5; i++) {
	var inBlock = true
}
if (inBlock) {
	console.log('Is there block scope?' + !inBlock)
}
```

```
// scope exercises
```

#Closures
Closures are functions that refer to independent (free) variables. In other words, the function defined in the closure 'remembers' the environment in which it was created.

A function serves as a closure in JavaScript, and thus creates a scope, so that (for example) a variable defined exclusively within the function cannot be accessed from outside the function or within other functions.

```
var scope = "global scope"
function checkScope() {
	var scope = "local scope"
	function innerFunc() {
		return scope
	}
	return innerFunc
}
var test = checkScope()
test
test()
```