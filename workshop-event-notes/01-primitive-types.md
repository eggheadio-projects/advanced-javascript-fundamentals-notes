## 01 Primitive Types

What is a type?

ways of organizing data that has similar values.

you know what you need to do when you have an array

**primitive types: not an object, has no methods, cannot be mutated**

Data Types :point_up: everything above but inverted.. an object

**`Everything in JS is NOT an object`**

Objects aren't primitive

Primitives: string, number, bigint, boolean, null, undefined, and symbol

null returning an object is a bug waaaay back when. Now it's typeof is an object even when it's not

```js
let obj = { a: **1 **}

function *addTwo*(obj) {

*obj.*a = 2

}

*addTwo*(obj)

// *obj is now {a: 2}*

let num = 1

function addTwo(num) {
  num = num + 2
  console.log(num)
}

addTwo(num)

// console.log(num)
```

num won't be mutated where obj will because the former is a primitive. The reference is passed to the function 

There is an idea of a 'Wrapper Object' that is a container for a primitive type.

A string gets wrapped into an object when it's referenced

Auto-boxing is where the misconception that everything is an object

Use literals where you can. JavaScript is smart with performance and gives you what you need

---

From Me to Everyone: (12:23 PM) Have you ever used a BigInt?
From Charlie Sojka to Everyone: (12:23 PM) I used it for User IDs in a large DB I mean, coming from a large DB