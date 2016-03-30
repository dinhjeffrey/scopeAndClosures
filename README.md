# Scope
The current context of execution. The context in which values and expressions are "visible," or can be referenced. If a variable or other expression is not "in the current scope," then it is unavailable for use. Scopes can also be layered in a hierarchy, so that child scopes have access to parent scopes, but not vice versa.

##Preview: Scope
Consider the following code:
```javascript
var a = 1
b = 2
function example() {
   var c = 5
   d = 6
}
example()
console.log(a)
console.log(b)
console.log(c)
console.log(d)
```

##Anatomy
```javascript
var add = function(a,b) {
	return a+b
}
add(3,4)
```

##Local Scope
```javascript
var func = function() {
	var local = true
}
console.log(local)
```

##Parent vs. Child Scope
```javascript
function blender(fruit) {
	var f = fruit
	var y = 'yogurt'
	function fs(){
		console.log(f + ' and ' + y + ' makes ' + f + ' swirl' )
	}
	fs()
}
blender('blueberry')
```
##Precedence
```javascript
var g = 'global'
function go() {
	var l = 'local'
	var g = 'in here!'
	alert (g + ' inside go')
}
go()
alert(g + ' outside go')
```

##Block Scope vs. Functional Scope
```javascript
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

```javascript
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

```javascript
var makeStopwatch = function() {
	console.log('initialized')
	var elapsed = 0
	console.log(elapsed)

	var stopwatch = function() {
		console.log('stopwatch')
		return elapsed
	}

	var increase = function() { 
		elapsed++ 
	}

	setInterval(increase, 1000)

	return stopwatch
}

var x = makeStopwatch()
x()
```
