---
title: "Next-Generation Javascript | Modern Javascript  Refresher"
seoTitle: "Next-Generation Javascript | Modern Javascript  Refresher"
datePublished: Mon Jan 10 2022 13:54:46 GMT+0000 (Coordinated Universal Time)
cuid: cky8qyf3e0a948ps13139exov
slug: next-generation-javascript-refresher
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1639584478296/ItulUgXk8.jpeg
tags: js, reactjs, es6

---

In this article, I provided a brief introduction to some 
core next-gen JavaScript features, of course focusing on 
the ones you'll see the most in this courseHere's a quick 
summary!

## let & const
Read more about **let** : https://developer.mozilla.org/en-US/
docs/Web/JavaScript/Reference/Statements/let
Read more about **const** : https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const

**let** and **const** basically replace **var** You use **let**
instead of **var** and **const** instead of **var** if you plan on 
never re-assigning this "variable" (effectively turning it into a 
constant therefore).

## ES6 Arrow Functions
Read more: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions

Arrow functions are a different way of creating functions in 
JavaScriptBesides a shorter syntax, they offer advantages 
when it comes to keeping the scope of the **this** keyword 
(see [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions#No_binding_of_this)).

Arrow function syntax may look strange but it's actually 
simple.
```js
 function callMe(name) { 
    console.log(name);
 }
```
which you could also write as:
```js
 const callMe = function(name) { 
    console.log(name);
 }
```
becomes: 
```js
 const callMe = (name) => { 
    console.log(name);
 }
```

### Important:
When having **no arguments**, you have to use empty 
parentheses in the function declaration:
```js
 const callMe = () => { 
    console.log('Max!');
 }
```
When having **exactly one argument**, you may omit the 
parentheses:
```js
 const callMe = name => { 
    console.log(name);
 }
```
When **just returning a value**, you can use the following 
shortcut:
```js
 const returnMe = name => name
 ```
That's equal to:
```js
const returnMe = name => { 
    return name;
 }
```
## Exports & Imports

In React projects (and actually in all modern JavaScript 
projects), you split your code across multiple JavaScript 
files - so-called modulesYou do this, to keep each file/ 
module focused and manageable.

To still access functionality in another file, you need **export**
(to make it available) and **import** (to get 
access) statements.

You got two different types of 
exports: **default** (unnamed) and **named** exports:

default => **export default ...;** 

named => **export const someData = ...;**

You can import **default exports** like this:
```js
import someNameOfYourChoice from './path/to/file.js'; 
```
Surprisingly, someNameOfYourChoice is totally up to you.
**Named** exports have to be imported by their name:
```js
import { someData } from './path/to/file.js'; 
```
A file can only contain one default and an unlimited amount 
of named exportsYou can also mix the one default with 
any amount of named exports in one and the same file.
When importing named exports, you can also import all 
**named** exports at once with the following syntax:
```js
import * as upToYou from './path/to/file.js'; 
```
**upToYou** is - well - up to you and simply bundles all 
exported variables/functions in one JavaScript objectFor 
example, if you 
```js
export const someData = ..(/path/to/file.js )
```
 you can access it on upToYou like 
this: 
```js
upToYou.someData
```
## Classes

Classes are a feature which basically replace constructor 
functions and prototypesYou can define blueprints for 
JavaScript objects with them

Like this:
```js
class Person {
    constructor () {
        this.name = 'Max';
    }
}

const person = new Person();
console.log(person.name); // prints 'Max'
```
In the above example, not only the class but also a property 
of that class (=> **name** ) is definedThey syntax you see 
there, is the "old" syntax for defining propertiesIn modern 
JavaScript projects (as the one used in this course), you 
can use the following, more convenient way of defining 
class properties:
```js
class Person {
    name = 'Max';
}

const person = new Person();
console.log(person.name); // prints 'Max'
```
You can also define methodsEither like this:
```js
class Person {
    name = 'Max';
    printMyName () {
    console.log(this.name); // this is required to refer to the class!
    }
}

const person = new Person();
person.printMyName();
```
Or like this:
```js
class Person {
    name = 'Max';
    printMyName = () => {
    console.log(this.name);
    }
}

const person = new Person();
person.printMyName();
```
The second approach has the same advantage as all arrow 
functions have: The **this** keyword doesn't change its 
reference.
You can also use **inheritance** when using classes:
```js
class Human {
    species = 'human';
}
.
class Person extends Human {
    name = 'Max';
    printMyName = () => {
    console.log(this.name);
}
}
.
const person = new Person();
person.printMyName();
console.log(person.species); // prints 'human'
```

## Spread & Rest Operator

The spread and rest operators actually use the same 
syntax: 
```js 
..
```

Yes, that is the operator - just three dotsIt's usage 
determines whether you're using it as the spread or rest 
operator.

### Using the Spread Operator:

The spread operator allows you to pull elements out of an 
array (=> split the array into a list of its elements) or pull the 
properties out of an objectHere are two examples:
```js
const oldArray = [1, 2, 3];
const newArray = [...oldArray, 4, 5]; // This now is [1, 2, 3, 4, 5];
```
Here's the spread operator used on an object:
```js
const oldObject = {
    name: 'Max'
};
const newObject = {
    ...oldObject,
    age: 28
};
```
**newObject** would then be
```js
{
name: 'Max',
age: 28
}
```
The spread operator is extremely useful for cloning arrays 
and objectsSince both are [reference types (and not 
primitives)](https://youtu.be/9ooYYRLdg_g), copying them safely (i.epreventing future 
mutation of the copied original) can be trickyWith the 
spread operator you have an easy way of creating a 
(shallow!) clone of the object or array

## Destructuring

Destructuring allows you to easily access the values of 
arrays or objects and assign them to variables.
Here's an example for an array:
```js
const array = [1, 2, 3];
const [a, b] = array;
console.log(a); // prints 1
console.log(b); // prints 2
console.log(array); // prints [1, 2, 3]
```
And here for an object:
```js
const myObj = {
    name: 'Max',
    age: 28
}
const {name} = myObj;
console.log(name); // prints 'Max'
console.log(age); // prints undefined
console.log(myObj); // prints {name: 'Max', age: 28}
```
Destructuring is very useful when working with function 
argumentsConsider this example:
```js
const printName = (personObj) => {
console.log(personObj.name);
}
printName({name: 'Max', age: 28}); // prints 'Max'
```
Here, we only want to print the name in the function but we 
pass a complete person object to the functionOf course 
this is no issue but it forces us to call personObj.name 
inside of our functionWe can condense this code with 
destructuring:
```js
const printName = ({name}) => {
console.log(name);
}
printName({name: 'Max', age: 28}); // prints 'Max')
```

We get the same result as above but we save some code
By destructuring, we simply pull out the **name** property and 
store it in a variable/ argument named **name** which we then 
can use in the function body.

## JS Array Functions
Not really next-gen JavaScript, but also important: JavaScript array functions like **map**() , **filter**() , **reduce**()  etc.

You'll see me use them quite a bit since a lot of React concepts rely on working with arrays (in immutable ways).

The following page gives a good overview over the various methods you can use on the array prototype - feel free to click through them and refresh your knowledge as required: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array

Particularly important in this course are:

map()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map

find()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find

findIndex()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex

filter()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter

reduce()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce?v=b

concat()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat?v=b

slice()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice

splice()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice
