
**JS**→In js we say ES6: ECMAScript6 which is a Standard Set by Organization called ECMA otherwise all the companies like Microsoft....etc are building there own JS

**JS**→ Dynamically Typed Programming Language where other programming languages are statically typed… & High-Level Language where we use English language terms, in which it doesn’t directly interact with Memory, and unlike to Assembly Language

**JS**→ It is user-friendly, it uses the RAM of the Machine, a Safe programming Language, used to dynamically manipulate the content of the Screen, **JS**→ It doesn’t required any download like Python, Java it just need environment like borwser and Node.Js {Node.js helps OUR COMPUTER to understand, compile and execute JS code.}

### **Difference between let, const, & var**

Let is declared once and initialized, then it can’t be declared again(provided iff re-declared in smae Block), but we can do it using var

In ES6 Standard ⇒ For declaring any variable, we should use let than var

var is FUNCTIONAL Scoped & let/const is Block Scoped

### Data types

8(1 Non-primitive +7 Primitive Data types) ⇒ Objects are Non-Primitive Data-type

Number, BigInt, String, Boolean, Null, Undefined, Symbol

Array and other are special types of Objects

Symbol types are ⇒ Infinity, -Infinity, NaN [These are special Mathematical Symbols and it’s Type is ‘Number’]

Operators like Uninary, binary, ternary….

uninary examples: -5,

And for type convertion generally

Number(’12’) →12 of number type

Similarly, +(’12’) this also same…

+(’hello’) & Number(’hello’) → NaN as value and type will be Number

`+true` or `+""` gives 1 & 0 as output.

We can’t do repetition using * in JS like in Python…

Coming to prefix and postfix calculations

b=1

a=b++, means a=1 and where ever the b again used from this line b value will have 2.

c=++b means c and b will both have 3 means it works like b=b+1

**All Fundamental Stuff:**

**Operators:** Type Conversion:

[**](https://javascript.info/type-conversions)[https://javascript.info/type-conversions**](https://javascript.info/type-conversions**)

Basic Operators:

[**](https://javascript.info/operators)[https://javascript.info/operators**](https://javascript.info/operators**)

Comparisons:

[**](https://javascript.info/comparison)[https://javascript.info/comparison**](https://javascript.info/comparison**)

Logical Operators:

[**](https://javascript.info/logical-operators)[https://javascript.info/logical-operators**](https://javascript.info/logical-operators**)

Nulish operators:

[**](https://javascript.info/nullish-coalescing-operator)[https://javascript.info/nullish-coalescing-operator**](https://javascript.info/nullish-coalescing-operator**)

**Key Rememberings:**

prompt(”text to show”,default value) [this return value we enter which is in String type]

confirm(’Text in which whatever we wanted confirm’) [it returns true if user clicks **ok** if clicks **cancel** then it returns false]

null-1=-1

6-”2”=4, it is converted even for/into mathematical

NaN==NaN, NaN===NaN ⇒ false

undefined == null —> true, but if `===` -->false

null==0, null==”0”, null===+”0” —>false
undefined === 0 or undefined==0 —>false 
In Alphabets a,b,c…. & Numbers 1,2,3 of string’s Comparison Priority increases

&& > || {Precedence}

(something is False/null/undefined) || (whatever is here will be the result)

(Operand1 is True) || (Operand2) ⇒ **Operand1** will be the result

(something is True) && (whatever is here will be the result)

(Operand1 is False) && (Operand2) ⇒ **Operand1** will be the result

**Nullish coalescing operator '??'**

it treats `null` and `undefined` similarly, say that a value is “defined” when it’s neither `null` nor `undefined`.

The result of `a ?? b` is:

- if `a` is defined, then `a`,
- if `a` isn’t defined, then `b`.

example:

```bash
result=a??b is Similar to result = (a !== null && a !== undefined) ? a : b;
```

Single difference between || and ?? operand2 will be the result for using || when operand1 is falsy because it can be false ,0 , null/undefined, “” but using ?? only considers null/undefined at operend1 to give as operand2

Using ?? with either or together of &&, || will give you syntax Error

**functions:** The function **shadows** the outer variable if the variable is declared with the same name again

```jsx
let userName = 'John';

function showMessage() {
  let userName = "Bob"; // declare a local variable

  let message = 'Hello, ' + userName; // Bob
  alert(message);
}

// the function will create and use its own userName
showMessage();

alert( userName ); // John, unchanged, the function did not access the outer variable
```

- Outside the function variables are Global Variables and it is recommended to avoid them unless shadowed by local level functions

**Difference between Parameter and Argument:**

- A parameter is the variable listed inside the parentheses in the function declaration (it’s a declaration time term).
- An argument is the value that is passed to the function when it is called (it’s a call time term).
- we can even pass function that returns something to parameter as a default paramemter value
- Empty returns from a function will always have an **undefined** as result of the return of the function call
- Function Declarations are **hoisted than** Function expressions
- No matter how the function is created, a function is a value.

**Objects & Arrays:**

Objects:

[**](https://javascript.info/object-basics)[https://javascript.info/object-basics**](https://javascript.info/object-basics**)

Arrays:

[**](https://javascript.info/array)[https://javascript.info/array**](https://javascript.info/array**)

```jsx
// ==> Object is created from Object only not from class in Javascript

// Objects Created 2 ways Constructor Function and object Literals
//Below is the Object Constructor
function User(name) {
  // this = {};  (implicitly)

  // add properties to this
  this.name = name;
  this.isAdmin = false;

  // return this;  (implicitly)
}

let user = new User("Jack");

alert(user.name); // Jack
alert(user.isAdmin); // false
//-----------------------------------------
IN the above mentioned Constructor Function without new keyword `user` will have undefined as value
and when we try to get properties from undefined JS gives TypeError
//-----------------------------------------
// to delete key-value in Obj
delete user.age // returns "true" if age is present and deleted  
//if not present still "true" returned
//----------------------------------------------------------------------------------
// using "in" operator
let user = { name: "John", age: 30 };

alert( "age" in user ); // true, user.age exists
alert( "blabla" in user ); // false, user.blabla doesn't exist
//---------------------------------------------------------------------------
const obj={
	myshit1:true,
	"myshit2":false,
	"you know my shit3":true
}
//Accessing --> 
console.log(obj.myshit1,obj["myshit1"],obj["myshit2"],obj["you know my shit3"])

// Actually no limitations on key/property names they can be any string/symbol 
// other types will be converted to strings 
/// example for Key mismatch:
const obj={
	0:"sample"
}
console.log(obj.0)// gives synthax error <<<------------
console.log(obj.[0])// sample as output 
console.log(obj.["0"])// sample as output 

// null is primitive Data type but using typeof it shows Object as type and which is bug in Javascript eailer

// Special property name in which that we can't assign it or set it to a non-Obj value
//which is __proto__
//The __proto__ property is special because it's not just a regular property. 
// It directly affects the internal [[Prototype]] of the object. If you assign a 
// non-object, you're trying to set something like a number or string as the prototype, 
// which doesn't make sense in JavaScript.
//Because JavaScript silently ignores the assignment if the value is not:
// an object or null
const obj = {};

obj.__proto__ = 42; // ignored or throws in strict mode

// and best practice and more modern way:
const obj = {};
const newProto = { 
	// What ever the Code you write as an Object Type
	greet() { console.log("Hello!"); } 
};

Object.setPrototypeOf(obj, newProto);
obj.greet(); // Hello!
////-------------------------------------------
// Explanation of Prototypes, InHeritence, and actual Usage of __proto__
/*
Inheritence is to inherit the properties and methods of One Obj by another obj 
in general programming Languages like: C++, Java etc. which increases Clean & Reuse structures
so, In JS it happens through Prototypes in Objects of Javascript
Simply inheritance is phenomenon and Prototype is used in Objects to have such phenomenon
Actually the prototype itself is hidden thing in Object which is avaiable 
for every Obj as a Property like 
Object.prototype {Native Object in JS->for Object literials}
ConstFunObj.prototype {Constructor Function or Class created Object by developer}

we Know :
Object, Array, Functionm Cnostructor Fun of Obj & Class based  all are OBJECTS 
those are like types 
each type of Object have respective type assosiated Prototype 

Working of Prototype:
it works like referncing the Other Object(Obj2) by one Object(Obj1) to access properties and methods
from other Object(Obj2)
using Obj.__proto__ poperty takes values ONLY Object type like any-Object & null{coz, it is also Object type}
here 
__proto__ is like a referencing vairable to point Gaint Box like Object.prototype [[prototype]] for the respective Object(Obj) Vairable
-->it creates Prototypical Inheritance Chain by applying them [helps in debugging]
-->But not recommended to use the approach to set prototype in production
-->When accessing obj.propertyOrMethod, if JS can't find propertyOrMethod in obj, it looks at corresponding Object's [[prototype]] , 
and so on, until it finds the property or reaches null.[as we can have chianing of prototypes also right!]

As we use Object Literials which has Native JS Object Prototype for every creation of Object from Object literials
The constructor function has a .prototype property, which becomes the prototype 
for all instances created using new ConstructorFunction() — the function’s name 
is not the prototype.
and it will shown the same Prototype for every Instance of the Contructor Fun
Advacntage is what ever the Function or property we try to make it available 
for every Instance we can make it by setting the protype of the ContstructorFun Object 
`ConstructorFunction.prototype`
or set,get, create Methods can also used by any type Creation of Objects
Like :
const newObj=Object.create(Obj1) (to create with a prototype)

Object.setPrototypeOf(newObj,Obj1) (to assign prototype after creation)

Object.getPrototypeOf(Obj1)-->Object.prototype or ConsFunObj.prototype (to inspect prototype)

-->class uses prototype internally.
*/
class Animal {
  speak() {
    console.log("Animal speaks");
  }
}

const a = new Animal();
console.log(a.__proto__ === Animal.prototype); // true

////-------------------------------------------
let user={}
console.log(user.age===undefined) // true
console.log(age in user) // false 
// The best use of the in operator is shown below 
let user={
	age:undefined
}
console.log(user.age===undefined) // true
console.log(age in user) // true --> used to check if that particular key is present or not 

////-------------------------------------------
// Wanted to print or show key names only then
for (let i in user){
	console.log(i) // Here only key names printed.....
}
////-------------------------------------------
// to add new key-value pair
user.new_pro=new_value;

////-------------------------------------------

// Mutability Things
let obj1 = { value: 10 };
let obj2 = obj1;  // This is called as Shallow Copying...

obj2.value = 20;

console.log(obj1.value); // Output: 20
console.log(obj2.value); // Output: 20
// If 
let obj1 = { value: 10 };
let obj2 = { value: 10 };
//Above or below are Same in terms of Memoery and Sense 
let obj2={}
for(let key in obj1){
	obj2[key]=obj[key] // This is called as Hard Copying or Duplicating more like Cloning the things...
}

obj2.value = 20;

console.log(obj1.value); // Output: 10 //<<------This Doesn't Change because obj1 refers to 
///another Object even having same  property but placed in different Objects vairables Assign differently
/// So, It behaves like List in Python as Mutability.
console.log(obj2.value); // Output: 20

// or We can also use assign method to duplicate the Object
let user = {
  name: "John",
  age: 30
};

let clone = Object.assign({}, user); // Object.assign(Object_That_Get_Cloned, Object_that_is_getting_CLONED);
//Object.assign(dest, sources1, sources2...etc) all the source# related properties will get Copied to dest property

alert(clone.name); // John
alert(clone.age); // 30
////------------Finding No of Keys in Object-------------------------------
const myObject = {
  a: 1,
  b: 2,
  c: 3
};

const numberOfKeys = Object.keys(myObject).length;

console.log(numberOfKeys); // Output: 3
console.log(Object.entries(myObject))
//Below is the result of the entries method. 
(3) [Array(2), Array(2), Array(2)]
0 : ['a', 1]
1 : ['b', 2]
2 : ['c', 3]

////------ different ways of creating Function -------------------------------------
const obj={
	user:'sharif',
	age:22,
}
obj.sayHi=function(){
	console.log("hello")
}
// Or
const obj={
	user:'sharif',
	age:22,
	sayHi:function(){
	console.log("hello")
	}
}

////-------Using key's in function of same Object only------------------------------------
const obj1={
	user:'sharif',
	age:22,
	sayHi:function(){
	console.log(`hello ${obj1.user}`)
	}
}
//or 
const obj1={
	user:'sharif',
	age:22,
	sayHi:function(){
	console.log(`hello ${this.user}`) // here this is refering to the obj1 Context 
	}
}

//==> this is unbound in Javascript 
///---------------Understanding "this" in different Modes ---------------------------------------------------------------
//JavaScript code can be executed in either strict mode or non-strict 
// (also known as "sloppy") mode. Strict mode is a feature introduced in 
// ECMAScript 5 that enforces stricter parsing and error handling on the code. 
// It helps catch common coding mistakes and unsafe practices, making the code more 
// robust and maintainable.
// To enable strict mode for a script or a function, you add the directive 
// "use strict"; at the beginning of the script or function body.

function sayHi() {
  alert(this);
}

sayHi(); // undefined
// In this case this is undefined in strict mode. 
// If we try to access this.name, there will be an error
// In non-strict mode the value of this in such case will be the global object.
```

- `this` is evaluated during the run-time, depending on the context.
- **Arrow functions are special:** they don’t have their “own” `this`. If we reference `this` from such a function, it’s taken from the outer “normal” function.
- The regular Object Literals `{...}` Syntax allows us to create one object. But often we need to create many similar objects, like **multiple users** or menu items, and so on. That’s where we use Constructor Function

**Optional Chaining:** The variable before ?. must be declared If there’s no variable user at all, then user `?.` anything triggers an error:

```jsx
// ReferenceError: user is not defined
user?.address;
```

The variable must be declared `(e.g. let/const/var user or as a function parameter).` The optional chaining works only for declared variables.

There are variants for Optional Chaining `?.()` Function Calling `?.[]` To Access Properties SAFELY in Object

- So while deleting, checking a Key in Object, we can use Optional Chaining but **NOT** While **assigning a Key with a Value**

_**Note:**_

- Many built-in objects already exist, such as those that work with dates, errors, HTML elements, etc. They have different properties and methods.
- But, these features come with a cost!
- Objects are “_**heavier**_” than primitives. They _**require additional resources to support the internal machinery.**_
- Primitive is just a Value of it’s primitive Type unlike Object has Power to store, values, Objects, Functions.
- So, Primitives have their own Methods to work upon them
- Irony is

```jsx
alert( typeof 0 ); // "number"

alert( typeof new Number(0) ); // "object"!
// So  this is NOT-recommended using them also Javascript On the other hand, 
// using the same functions String/Number/Boolean without new is totally fine 
// and useful thing. They convert a value to the corresponding type: to a string, 
// a number, or a boolean (primitive).
```

### **Primitive Type Methods**

### String
```javascript


// Strings are Immutable
// Where Indexing is only for +ve Index values
str.at() 
//--> Gives Character from string by taking +ve & -ve Index VALUES from the string
// Str.slice(startIndex,endIndex);
let str = "stringify";

// these are same for substring
alert( str.substring(2, 6) ); // "ring"
alert( str.substring(6, 2) ); // "ring"

// ...but not for slice:
alert( str.slice(2, 6) ); // "ring" (the same)
alert( str.slice(6, 2) ); // "" (an empty string) 
// Mentioning the Length of the substring -->We can even mention -ve Index values
let str = "stringify";
alert( str.substr(-4, 2) ); // 'gi', from the 4th position get 2 characters
str.repeat(n) //–-> repeats the string n times.

// padString is Optional
myString.padStart(targetLength, padString) 
const anotherString = "Geeks";  
const paddedWithChars = anotherString.padStart(10, "XX");  
console.log(paddedWithChars); // Output: "XXXXXGeeks"
```

### Number

```jsx
num.toString() // inside toString() we can mention base(2,8,16) default it's 10
/*
Math.floor
Rounds down: 3.1 becomes 3, and -1.1 becomes -2.
Math.ceil
Rounds up: 3.1 becomes 4, and -1.1 becomes -1.
Math.round
Rounds to the nearest integer: 3.1 becomes 3, 3.6 becomes 4. In the middle cases 3.5 rounds up to 4, and -3.5 rounds up to -3.
Math.trunc (not supported by Internet Explorer)
Removes anything after the decimal point without rounding: 3.1 ecomes 3, -1.1 becomes -1
*/ 
alert( Number.isNaN(NaN) ); // true
alert( Number.isNaN("str" / 2) ); // true

// Note the difference:
alert( Number.isNaN("str") ); // false, because "str" belongs to the string type, not the number type
alert( isNaN("str") ); // true, because isNaN converts string "str" into a number and gets NaN as a result of this conversion
//----------------------------------------------------
alert( Number.isFinite(123) ); // true
alert( Number.isFinite(Infinity) ); // false
alert( Number.isFinite(2 / 0) ); // false

// Note the difference:
alert( Number.isFinite("123") ); // false, because "123" belongs to the string type, not the number type
alert( isFinite("123") ); // true, because isFinite converts string "123" into a number 123
//---------------------------------------------------------------------------
alert( Math.pow(2, 10) ); // 2 in power 10 = 1024

```

**Array Concept:**

```jsx
//--> These are more like speacial Object
//---> Created Using COnstructor Function and Array literals
//---> Generally 0-Based Indexing
//--> we can use myArray.at(negative index) gives corresponding Element in "myArray"

const myArray=[false]
// using push/pop-->works for last part of array
// using unshift/shift-->works for Starting part of array
myArray.push(5)// [false,5] & return length of updated Array
myArray.unShift(1) // [1,false,5] & return length of updated Array
myArray.pop() // [1,false]
myArray.shift() // [false]

//-------------------------------------------------
// Array COmparision is like doing with Object's 
const a1=[false]
const a2=a1  // --> Here we are refering the same Array like Shallow Copy we do in Objects
console.log(a1==a2)// true & same result for ===
const a3=[false] // --> Here we are having the same Array like Hard Copy we do in Objects
console.log(a1==a3)// false & same result for ===
//-------------------------------------------------
let arr = [1, 2, 3];

alert( arr ); // 1,2,3
alert( String(arr) === '1,2,3' ); // true
//----------------------------------------------------------------------------
// Comparision
// Two objects are equal == only if they’re references to the same object.
// If one of the arguments of == is an object, and the other one is a primitive, 
// then the object gets converted to primitive
// This only Happens with == not with === it avoids the Conversion
alert( 0 == [] ); // true

alert('0' == [] ); // false
// after [] was converted to ''
alert( 0 == '' ); // true, as '' becomes converted to number 0

alert('0' == '' ); // false, no type conversion, different strings
//…With an exception of null and undefined that equal == each other and nothing else.
//----------------------------------------------------------------------------
arr.splice([start, deleteCount, elem1, ..., elemN])// Even -ve Index Allowed
//----------------------------------------------------------------------------
let arr = ["t", "e", "s", "t"];

alert( arr.slice(1, 3) ); // e,s (copy from 1 to 3)

alert( arr.slice(-2) ); // s,t (copy from -2 till the end)
//----------------------------------------------------------------------------
arr.concat(arg1, arg2...)
let arr = [1, 2];

// create an array from: arr and [3,4]
alert( arr.concat([3, 4]) ); // 1,2,3,4

// create an array from: arr and [3,4] and [5,6]
alert( arr.concat([3, 4], [5, 6]) ); // 1,2,3,4,5,6

// create an array from: arr and [3,4], then add values 5 and 6
alert( arr.concat([3, 4], 5, 6) ); // 1,2,3,4,5,6
//----------------------------------------------------------------------------
let fruits = ['Apple', 'Orange', 'Apple']

alert( fruits.indexOf('Apple') ); // 0 (first Apple)
alert([NaN].indexOf(NaN)); // -1 -->Incorrect should give 0 as output but JS gives -1
alert( fruits.lastIndexOf('Apple') ); // 2 (last Apple)
//----------------------------------------------------------------------------
let result = arr.find(function(item, index, array) {
  // if true is returned, item is returned and iteration is stopped
  // for falsy scenario returns undefined
});
//----------------------------------------------------------------------------
Arr.sort(Fun) // Fun decides and returns the Bool type
//----------------------------------------------------------------------------
Arr.reverse()
//----------------------------------------------------------------------------
let value = arr.reduce(function(accumulator, item, index, array) {
  // ...
}, [initial]); //initial, index, array is an optional 
//----------------------------------------------------------------------------
// We know Array is type of Object but to check if Array is Array 
Array.isArray({}) // false
Array.isArray([]) // true

```

—>Strings are Iterable using `for.. of` Loop

—> Using Array.form() is a Universal Method to Convert Iterables and array-like values into an Array

```jsx
let arrayLike = {
  0: "Hello",
  1: "World",
  length: 3
};
let arr = Array.form(arrayLike); // ['Hello', 'World', undefined]
let str = '𝒳😂';

// splits str into array of characters
let chars = Array.from(str); // ['𝒳', '😂']
//------------------------------------------
let options = {
  title: "Menu"
};
// sourceVairable:TargetVairable=DefaultValue 
let {width: w = 100, height: h = 200, title} = options;

alert(title);  // Menu
alert(w);      // 100
alert(h);      // 200
//---------------------------------------------------------
let recipeMap = new Map([
  ['cucumber', 500],
  ['tomatoes', 350],
  ['onion',    50]
]);

for (let entry of recipeMap) { // the same as of recipeMap.entries()
  alert(entry); // cucumber,500 (and so on)
}

// runs the function for each (key, value) pair
recipeMap.forEach( (value, key, map) => {
  alert(`${key}: ${value}`); // cucumber: 500 etc
});
//////---------------------------> Mention the type of the itrable Datatype in 3rd argument
// the same with forEach:
mySet.forEach((value, valueAgain, set) => {
  alert(value);
});
```

### Date & Time

- Considering and getting Full Year is Highly encouraged even it’s getFullYear() months -0(Jan) - 11 (Dec),
- Days of week in `getDay()` are also counted from zero (that’s Sunday).
- date → default = 1 is considered
- date1-date2 < date1.getTime()-date2.getTime() [**Performance is Best**]
- The method [Date.parse(str)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/parse) can read a date from a string.
- The string format should be: `YYYY-MM-DDTHH:mm:ss.sssZ`
- The character `"T"` is used as the delimiter
- `HH:mm:ss.sss` – is the time: hours, minutes, seconds and milliseconds.
- Returns milliseconds of the timstamp string (str) we use to parse

### **JSON:**

[https://javascript.info/json#excluding-and-transforming-replacer](https://javascript.info/json#excluding-and-transforming-replacer) This INFO is Enough to Understand the JSON(JavaScript Object Notation) Important Things like:

- While Making JSON stringified we can Choose specific Key-VALUE PAIR only (replacer parameter or even we can return as Functionally)
- Also, While Parsing the JSON we can transform the JSON key-value pair into required TYPE (reviver Parameter which handles)
- In replacer & reviver it goes Nested Also but in replacer we need to mention the key names to allow the JSON Stringification
- Great thing is we will be able to convert the deeper properties/Objects converted to JSON  

—>’’ is for strings “” is for JSON strings and it takes objescts as Input to stringify and parses stringified JSON into respective Object JSON Ignores some Object Properties like

- Function properties (methods).
- Symbolic keys and values.
- Properties that store `undefined`.

### Closure:

- JS is OOP after the Modern ES6+ release but In general it’s also a Function-oriented LANGUAGE
- created/passed function at any moment in the script
- In JavaScript, all functions are naturally closures (there is only one exception, to be covered in [The "new Function" syntax](https://javascript.info/new-function)).
- A [closure](https://en.wikipedia.org/wiki/Closure_\(computer_programming\)) is a function that remembers its outer variables and can access them.
- This Happens with the Help of Lexical Env Concept which has Environment Record property
- For Every call of a Function new Closure is Created and has it’s own and corresponding Data manipulations and Encapsulation.
- The Concept of **Lexical Environment** is Gold to understand how the Vairables from block to functional scope is being assigned and accessed smartly and picks recent one
- Also it contains two things Environment Record and Refrence for Outer Lexical Env
- Good Concept [https://javascript.info/closure](https://javascript.info/closure)
- Lexical Env is removed from Memory when function call Finishes. Iff That’s because there are no references to it. **As any JavaScript object, it’s only kept in memory while it’s reachable.**
- However, if there’s a nested function that is still reachable after the end of a function, then it has `[[Environment]]` property that references the lexical environment.
- In that case the Lexical Environment is still reachable even after the completion of the function, so it stays alive in the memory.
- **In other words, it exists only while there’s at least one nested function referencing it.**

```jsx
let x = 1;
function func() {
  // the local variable x is known to the engine from the beginning of the function,
  // but "uninitialized" (unusable) until let ("dead zone")
  // hence the error
// This zone of temporary unusability of a variable (from the beginning of the code block till let) is sometimes called the “dead zone”.
  console.log(x); // ReferenceError: Cannot access 'x' before initialization

  let x = 2;
}
func();

// To explain this Presicely console.log(x) is in func associated Lexical Env which has x:UnInitialized as it starts finding the x value from the current Lexical Env if not Found then it moves to refrred Lexical Env

// If let x=2 is not present in the func() then Javascript defentily look outside the func() for the vairable.
```

```jsx
/* .. your code for inBetween and inArray */
let arr = [1, 2, 3, 4, 5, 6, 7];

alert( arr.filter(inBetween(3, 6)) ); // 3,4,5,6 => selects only values between 3 and 6.

alert( arr.filter(inArray([1, 2, 10])) ); // 1,2 => selects only elements matching with one of the members of [1,2,3].

```

## **📌 Full Prototype & `__proto__` Revision Sheet**

---
### JS Inheritance mystery:
- Object creation and Function creation inside the Object is Very Costly Operation interms of Memory.
- So, **Inheritance** in JS is prototype-based, even when using `class` syntax—it’s just syntactic sugar over `Object.create` and function prototypes.
- Every Obj/Function also has a **`[[Prototype]]`** property (link to another object), and constructor functions/classes assign this prototype to objects created with `new` Instance.
- Methods/properties on the prototype are **shared** across all instances—reducing memory usage by not duplicating methods for each object and that's how JS effectively using the Inheritance Concept to make things DONE.
### **1️⃣ Object Literal Case**

```jsx
const obj = { a: 1, greet() { console.log("Hello"); } };

console.log(obj.a); // Own property
console.log(obj.__proto__ === Object.prototype); // true
console.log(Object.prototype.__proto__); // null

```

**Instance Chain (Object Literal):**

```
obj (a, greet)
   ↑ __proto__
Object.prototype (toString, hasOwnProperty, ...)
   ↑ __proto__
null

```

---

### **2️⃣ Constructor Function Case**

```jsx
function Person(name) {
  this.name = name; // own property
  #healthScore = 0; // private property

  updateHealthScore(newScore) {
    this.#healthScore += newScore;
  }
}
Person.prototype.sayHello = function() { console.log(`Hi, I'm ${this.name}`); };

const p1 = new Person("Sharif");

console.log(p1.__proto__ === Person.prototype); // true
console.log(Person.prototype.__proto__ === Object.prototype); // true

```

**Instance Chain (Constructor Function):**

```
p1 (name)
   ↑ __proto__ (Person.prototype: sayHello)
   ↑ __proto__ (Object.prototype)
   ↑ __proto__ (null)

```

---

### **3️⃣ Class Case (No Inheritance)**

Btw, Class is a Syntactic Sugar for Constructor Function of Object Creation.

```jsx
class Animal {
  species = "unknown"; // per-instance field
  speak() { console.log("Animal sound"); } // prototype method
  static info = "Static property"; // static
  static identify() { console.log("Animal class"); } // static method
}

const dog = new Animal();

```

**Instance Chain:**

```
dog (species)
   ↑ __proto__ (Animal.prototype: speak)
   ↑ __proto__ (Object.prototype)
   ↑ __proto__ (null)

```

**Static Chain:**

```
Animal (info, identify)
   ↑ __proto__ (Function.prototype: call, bind, ...)
   ↑ __proto__ (Object.prototype)
   ↑ __proto__ (null)

```

---

### **4️⃣ Class Case (With Inheritance)**

```jsx
class Animal {
  speak() { console.log("Animal sound"); }
  static identify() { console.log("Animal class"); }
}

class Dog extends Animal {
  bark() { console.log("Woof!"); }
  static species() { console.log("Dog species"); }
}

const d = new Dog();

```

**Instance Chain (Inheritance):**

```
d
   ↑ __proto__ (Dog.prototype: bark)
   ↑ __proto__ (Animal.prototype: speak)
   ↑ __proto__ (Object.prototype)
   ↑ __proto__ (null)

```

**Static Chain (Inheritance):**

```
Dog (species)
   ↑ __proto__ (Animal: identify)
   ↑ __proto__ (Function.prototype)
   ↑ __proto__ (Object.prototype)
   ↑ __proto__ (null)

```

---

### **🔗 Final Combined Diagram**

```
[INSTANCE CHAIN]
instance
   ↑ __proto__ === Class.prototype / ConstructorFunction.prototype
   ↑ __proto__ === ParentClass.prototype
   ↑ __proto__ === Object.prototype
   ↑ __proto__ === null

[STATIC CHAIN]
Class
   ↑ __proto__ === ParentClass
   ↑ __proto__ === Function.prototype
   ↑ __proto__ === Object.prototype
   ↑ __proto__ === null

```

---

💡 **Key Takeaways**

1. **Instance properties** live **on the instance itself** (own properties).
2. **Instance methods** in classes go on `.prototype`.
3. **Static methods** go on the constructor function itself and follow **static chaining** via `Class.__proto__`.
4. `__proto__` is the **link**, `.prototype` is the **object being linked to**.

---

**Factory Functions - Offer:**

**Flexibility:**Factory functions offer flexibility in object creation, allowing for conditional logic to return different types of objects or objects with varying configurations based on input parameters.

1. No new operator is needed other than that it is just like constructor Function
2. Supports Encapsulation. 
3. This acts as Template to Create the Objects through Instances and When we want the Objects to have similar methods and Properties and we can also Alter these based on condition.
4. **Composition Over Inheritance:** Factory functions emphasize object composition (combining objects to create new ones) over inheritance, which is often considered a more flexible and maintainable approach in JavaScript.
```javascript 

//-----------------------> **Composition Over Inheritance Example** 

// A functional mixin to add the "canAttack" behavior
const canAttack = (state) => ({
  attack: (target) => {
    // Attack logic
    console.log(`${state.name} attacks ${target}`);
  },
});

// A functional mixin to add the "canDefend" behavior
const canDefend = (state) => ({
  defend: () => {
    // Defend logic
    console.log(`${state.name} defends!`);
  },
});

// A factory function that combines these behaviors
const createWarrior = (name) => {
  const state = { name };
  return { ...state, ...canAttack(state), ...canDefend(state) };
};

const warrior = createWarrior('Conan');
warrior.attack('Orc'); 
warrior.defend();

```
5. They don't Inheritance Concept like we have in Constructor and class based Object Creation

Good Doubts Have been Resolved here do check every UI Created in the response of Cluade AI : [https://claude.ai/chat/82fa37ac-57e7-435e-83c9-feb08ed9eb37](https://claude.ai/chat/82fa37ac-57e7-435e-83c9-feb08ed9eb37) —- To even understand for which typeof Objects cretion has the same prototypical strength.

```jsx
JS was initially created for web browsers later introduced in other platforms like Node.js
JS Specification calls that paltforms as a host environments
A Host Env provide it's own Obj, Functions in addition to lang Code..
So, Web Brower is a Such Host by providing features to Control Enitre web page
Similarly Node.js provides server side features and So On....
The Root Object is Called Window Object it has 2 Roles :
1) It is Global Obj for JS Code
2) It is represented as Browser Window and methods to Control the Stuff inside it...

funtion hi(){
	console.log("HI ra")
}
// Here simply hi() is equal working as window.hi()
console.log(window) //itself has Lot more Powerful Properties, Object inside this window Object
//--------------------
DOM Says everything as page content is represented as Object and which can be modified
so to access we use document obj like document.body.style like this...
So, document is entrypoint which is a object and easy to modified 
the DOM Specification's not jsut limited to Browser's only because, DOM Specs explains the structure of Document & provides objects to manupilate 
and there are non-browser platforms that uses DOM too...
// There is Something called CSSOM{CSS Object Model} & BOM {Browser Object Model}
BOM 

```

## _**Promises, await/async, try-catch Stuff**_

### JavaScript Execution Process

Before your JS code _runs_, it goes through two major phases:

1. **Parsing Phase (a.k.a. Compilation phase)**
    
    JS engine reads the entire code _before_ executing it. It checks:
    
    - Syntax (e.g., correct use of brackets, keywords, semicolons).
    - Declarations are properly made.
2. **Execution Phase (a.k.a. Runtime phase)**
    
    JS engine now runs the code _line-by-line_. This is when:
    
    - Variables are assigned.
    - Functions are called.
    - Logic is processed.
    - **Runtime errors may happen** (like accessing undefined variables, division by zero, etc.)

In the case of **`try...catch`**

```jsx
try {
  let x = y + 1; // y is not defined
} catch (err) {
  console.log("Caught an error:", err.message); // ✅ This will work
}

//----------------------------------------------------------
try {
  {{{{{{  // ❌ Syntax Error: unmatched braces
} catch (err) {
  console.log("Won't be caught");
}
here JS not able to understand the Code that's why it throws Syntax Error in the parsing Phase.
If Parsing Phase is Fucked then Execution Phase will not even get started.
```

**`try...catch` works synchronously**

if there is an Exception/Error in Async Code and this is inside the **`try...catch` we can’t catch the error because the `try...catch` block already left out before the completion of the Async Code which is inside the `try...catch` block.**

```jsx
try {
  setTimeout(function() {
    noSuchVariable; // script will die here
  }, 1000);
} catch (err) {
  alert( "won't work" );
}
// That’s because the function itself is executed later, 
// when the engine has already left the try...catch construct.
//-----------------------------------------------------------------
// To catch an exception inside a scheduled function, try...catch 
// must be inside that function:

setTimeout(function() {
  try {
    noSuchVariable; // try...catch handles the error!
  } catch {
    alert( "error is caught here!" );
  }
}, 1000);
```

err has 2 main properties

name, message like `err.name` `err.message` and this `err` is an **optional** Argument

```jsx
try {
  // ...
} catch (err) { // <-- the "error object", could use another word instead of err
  // ...
}
```

We can use `thorw <Error Object>` to create Own Error we can even use Builtin Contructor Functions of the Error

```jsx
let error = new Error("Things happen o_O");

alert(error.name); // Error
alert(error.message); // Things happen o_O
```


### JavaScript Promises Need and Execution: 
CallBacks =⇒ Functions which are argument to another function(f) and used to call inside that same another function (f).

**Many functions are provided by JavaScript host environments that allow you to schedule _asynchronous_ actions. In other words, actions that we initiate now, but they finish later.** Examples: setTimeout, setTimeInterval, Loading scripts, Modules… Making API calls

```jsx
//WHILE Loading a Script which is a Async Action we can provide callback as 
//the another argument and make it below the Aynsc Logic so the Aysnc runs and 
// Completed the operation then we have the callback execution/calls out

//Example:
function loadScript(src, callback) {
  let script = document.createElement('script');
  script.src = src;
  script.onload = () => callback(script);
  document.head.append(script);
}

loadScript('<https://cdnjs.cloudflare.com/ajax/libs/lodash.js/3.2.0/lodash.js>', script => {
  alert(`Cool, the script ${script.src} is loaded`);
  alert( _ ); // _ is a function declared in the loaded script
});
```

After the outer `loadScript` is complete, the callback initiates the inner one.

What if we want one more script…? Making the Pyramid of Doom

```jsx
loadScript('/my/script.js', function(error, script) {
	if (error) handleError(error);
	else {
  loadScript('/my/script2.js', function(error,script) {
		if (error) handleError(error);
		else {
    loadScript('/my/script3.js', function(error,  script) {
      if (error) handleError(error);
			else {
		      // ...continue after all scripts are loaded
		      }
     });
		}
  });
 }
});
```

Above is the Pyramid OF Doom using multiple usages of async actions instead of that we can sperate the call back functions outside to make redable Top-Level Code

#### **—> While Using Promises** 
Code Takes Time is **Producing Code** for loading Script/API/Getting Data from Network
Code that takes result from **Producing Code** and make Logic and calculations is **Consuming Code**
To happen that Possible --> Promise{A Special JavaScript Object} Constructor Function helps for that:
```
let myPromise=new Promise((resolve,reject)=>{

})
```

```
(resolve,reject)=>{

}

// Above mentioned Function is call Executor 
// when new Promise is created executor Run Automatically
```

Should Call an one of these callBacks {resolve(value) or reject(error)} 
by the Promise 
The executor receives two arguments: `resolve` and `reject`. These functions are pre-defined by the JavaScript engine, so we don’t need to create them. We should only call one of them when ready.

**Internally** it have **properties**:
Initially --> {
State: "pending",
result: undefined
}

After Some desired Logic is achieved as expected then 
**resolve(value) is called --> {**
**state: "fulfilled",**
**result: value**
**}**
else If we found any error we need to give 
**resolve(value) is called --> {**
**state: "rejected",**
**result: error**
**}**


## **Important Concepts** 
### JS Event Loop
As JavaScript is **single-threaded**, which means it runs one command at a time in a synchronous fashion.
--->However, **asynchronous operations** like `setTimeout()`, `fetch()`, and `Promises` exist.
To Handle JS Uses:
	**Execution Model = Event Loop + Call Stack + Web APIs + Task Queue + Microtask Queue**

#### It's Execution Flow in Order Priority:
```
-> Call Stack
-> Web APIs (waiting)
-> Task Queues:
     - Microtasks (Promises etc.)
     - Macrotasks (setTimeout etc.)
-> Event Loop (Scheduler decides next)
```
##### 1. **Call Stack**
- Where synchronous code runs.
- Example: basic functions and calculations.
- It works like a stack (Last-In-First-Out).
```javascript
// CallStack LIFO Example
function outer() {
   function inner() {
     console.log("Hello");
   }
   inner();
}
outer();

```
##### 2. **Web APIs (Browser Environment)**

- When you call `setTimeout`, `fetch`, `Dom` , etc., they are handled by the browser APIs _outside_ the JS engine.
- These wait **without blocking the Call Stack**.
##### 3. **Task Queues (Macro and Micro Queues)**
- **Macro Task Queue** (aka **Callback Queue**):
    - Contains: `setTimeout`, `setInterval`, `setImmediate`, UI events, etc.
    - Executed **after** the current call stack is empty.
        
- **Micro Task Queue**:
    - Contains: `.then()` callbacks from **Promises**, `MutationObserver`, `queueMicrotask()`
    - **Higher priority** than macro tasks. These are executed right after the current synchronous code (call stack) finishes.
##### 4. **Event Loop (The Scheduler)**
- The **actual “scheduler”** that:
    1. Waits for the **call stack to be empty**
    2. If there any **WebAPI** related is given **Importance to Execute**
    3. Then **picks tasks from queues**
    4. Gives **priority to microtasks** over macrotasks
```javascript
console.log("start");

setTimeout(() => {
  console.log("timeout");
}, 0);

Promise.resolve().then(() => {
  console.log("promise");
});

console.log("end");

%%  The Output of the ABOVE CODE
start
end
promise    ✅ Microtask runs first
timeout    ✅ Macrotask runs after microtasks
 %%
```

### Need of IIFE(Immediately Invoked Functional Expression) :
 Earlier we don't have `let` and `const` so only `var` is present in which it is functional Scoped and as we know  `let` and `const` are Block scoped. 
So, to have Block-scoped like sense while writing Code.
Developers Created a New way 
```javascript
(function() {
  // code block
})();
// here 
function() {
  // code block
}
// is a - anonymous function - Wrapping in `()` makes it an **expression**
// `()` at the end → immediately invoke
```

Also,
`var` created vairables or funtions are properties of Globacl Object and Browser and Node has it's own named Global OBJECT like window and global
### NFE(Named Function Expressions):
Helps to refernece it's self internally when using Function Expression & as the Name will not access out side the function it still accessed by the usage of the assignment vairable.
```javascript
let sayHi = function func(who) {
  if (who) {
    alert(`Hello, ${who}`);
  } else {
    func("Guest"); // use func to re-call itself
  }
};

sayHi(); // Hello, Guest

// But this won't work:
func(); // Error, func is not defined (not visible outside of the function)
```



### Function.prototype Important Methods (bind, apply, call)

These methods help control **function execution context (`this`)** and **argument passing**.

---
#### call()
- **Purpose:** Immediately invokes a function with a given `this` value and arguments passed individually.  
- **When to use:**  
  - Borrowing methods from other objects.  
  - Running a function in the context of a different object.  
- **Key Point (Interview):** Executes **immediately**, unlike `bind`.
```javascript
function greet(lang) {
  console.log(`${lang}: Hi, I'm ${this.name}`);
}
const user = { name: "Sharif" };
greet.call(user, "EN"); // EN: Hi, I'm Sharif
```
#### apply()
- **Purpose:** Same as `call()`, but arguments are passed as an array. 
- **When to use:**  
  - Useful when you already have arguments in an array. 
  - Common in scenarios like `Math.max.apply(null, arr)`.
- **Key Point (Interview):** Just like `call`, but **array of arguments**.
```javascript
function greet(lang) {
  console.log(`${lang}: Hi, I'm ${this.name}`);
}
const user = { name: "Sharif" };
greet.apply(user, ["EN"]); // EN: Hi, I'm Sharif
```
#### bind()
- **Purpose:** Returns a **new function** with `this` and optional arguments permanently bound.  
- **When to use:**  
  - Event handlers where you want fixed context.
  - Partial application of functions.  
- **Key Point (Interview):**  Unlike `call` and `apply`, `bind` does **not execute immediately**.
```javascript
function greet(lang) {
  console.log(`${lang}: Hi, I'm ${this.name}`);
}
const user = { name: "Sharif" };
const greetSharif = greet.bind(user, "EN");
greetSharif(); // EN: Hi, I'm Sharif
```
### Other Important Points
#### Polyfills:
- **Purpose:** To provide **backward compatibility** in environments where a feature is not available.
- **When to use:** Writing custom implementations of methods like `call`, `bind`, etc.
- **Key Point (Interview):** Often asked to **implement polyfills** in interviews.
```javascript
Function.prototype.myCall = function(context, ...args) {
  context = context || globalThis;
  const fnSymbol = Symbol(); // Unique property key
  context[fnSymbol] = this;
  const result = context[fnSymbol](...args);
  delete context[fnSymbol];
  return result;
};
```
#### Decorators (ES Proposal):
- **Purpose:** Special functions that **wrap or enhance** other functions, methods, or classes.
- **When to use:**
    - Logging, validation, caching, or security checks.
    - Common in frameworks like Angular, NestJS, etc.
- **Key Point (Interview):** Still a **proposal in JavaScript**, but widely used in TypeScript/Angular.
```javascript
function logger(fn) {
  return function(...args) {
    console.log("Args:", args);
    return fn(...args);
  };
}

function sum(a, b) { return a + b; }
const loggedSum = logger(sum);
loggedSum(2, 3); // Logs args then result.
```

## **Global catch**

**Environment-specific**

The information from this section is not a part of the core JavaScript.

Let’s imagine we’ve got a fatal error outside of `try...catch`, and the script died. Like a programming error or some other terrible thing.

Is there a way to react on such occurrences? We may want to log the error, show something to the user (normally they don’t see error messages), etc.

There is none in the specification, but environments usually provide it, because it’s really useful. For instance, Node.js has [`process.on("uncaughtException")`](https://nodejs.org/api/process.html#process_event_uncaughtexception) for that. And in the browser we can assign a function to the special [window.onerror](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onerror) property, that will run in case of an uncaught error.

The syntax:

`window.onerror = function(message, url, line, col, error) {// ...};`

**`message`**Error message.**`url`**URL of the script where error happened.**`line`, `col`**Line and column numbers where error happened.**`error`**Error object.

For instance:

```jsx

<script>
  window.onerror = function(message, url, line, col, error) {
    alert(`${message}\\n At ${line}:${col} of ${url}`);
  };

  function readData() {
    badFunc(); // Whoops, something went wrong!
  }

  readData();
</script>
```








