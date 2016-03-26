# scopeAndClosures

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