# Javascript

## Basics

#### Coercion
* explicit: see from code that a conversion will occur

```javascript
var a = "42";
var b = Number( a );
```

* implizit: conversion is not obvious

```javascript
var a = "42";
var b = a * 1;	// "42" implicitly coerced to 42 here
```

#### truthy & falsy

what happens if a non-boolean value coerces to boolean?

* __"falsy":__ "", 0, -0, NaN, null, undefined, false
* __"truthy:"__ "foo", 42, true, objects, arrays, functions

#### Equality

 four equality operators (__==,===,!=,!==__). == checks for value equality with coercion allowed and === checks for value equality without allowing coercion. Rules for coercion in '==' can be found under following link: http://www.ecma-international.org/ecma-262/5.1/

 rule of thumb for operator choosing:

* If either value (aka side) in a comparison could be the true or false value, avoid == and use ===.
* If either value in a comparison could be of these specific values (0, "", or [] -- empty array), avoid == and use ===.
* In all other cases, you're safe to use ==. Not only is it safe, but in many cases it simplifies your code in a way that improves readability.

#### Function Scope
var: variable belongs to current function scope or global scope if declared at top.

##### Hoisting
Wherever a var appears inside a scope, that declaration is taken to belong to the entire scope and accessible everywhere throughout. This behavior is called hoisting, when a var declaration is conceptually "moved" to the top of its enclosing scope.

```javascript
var a = 42;

foo();

function foo() {
	a = 43;
  console.log( 'in foo(): ' + a ); // => 43
  var a;
}

console.log( a ); // => 42
```
