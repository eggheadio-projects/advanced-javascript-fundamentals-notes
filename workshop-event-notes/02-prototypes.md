## 02. Prototypes

Prototype is the way you do inheritance in JS

### dunder proto and .prototype

'dunder proto' is __proto__ - what gets added to an object in JS with methods on it

It's a 'nesting of objects'

JS let's us add on to another objects prototype chain. 

what's the connection between `.prototype` and `__proto__` 

Functions have a `.prototype` property that points to an object with a constructor property, and a `__proto__` property.

On Functions a prototype is also generated

the prototype will have a constructor of the function that points back that itself will have a dunder proto

Object, Array, String - all constructor functions. These are not the same as {}, [], ''

They all have the .prototype objects on them that have a bunch of methods on them

**if it's being added to the prototype, I don't need to reference the global constructor function to utilize this. I can dot onto it from the instance.**

### `new` keyword

Does 4 things - Creates a new object, change the dunder proto property to the .prototype of the object that is being called with it and `this` becomes the object that is called and finally `this` is returned

---

From KD Singh to Everyone: (12:41 PM) Why’s is console.log(b) empty?
From Anushree Subramani to Everyone: (12:41 PM) So, if it keeps searching up the tree until it finds it I guess or errors out it*

From KD Singh to Everyone: (12:42 PM) what good was return “hello” for?
From Anushree Subramani to Everyone: (12:43 PM) What is a good use case to actually assign values to the prototype?

If you are using classes, assigning values to the prototype can be useful

From Me to Everyone: (12:43 PM) Can you b.A() to get “hello” returned?

you *can* return the hello string through b.constructor

From Anushree Subramani to Everyone: (12:45 PM) Es6 classes are just syntactic sugar right? Underneath the hood does it implement this prototype inheritance?

Stick around ;) lesson 5 covers this

From Anushree Subramani to Everyone: (12:50 PM) Nit: Is it down the chain or up the hierarchy chain ?

Say what make sense to you - both could work. 
Thinking of it as nested objects it's down but if you think in terms of heirarchy and instance/class it would be up

### Loops with ProtoTypes

Loops can behave differently when objects have chained prototype objects.

The for...in statement iterates over all non-Symbol, enumerable properties of an object.

.setPrototypeOf another way to connect prototype objects

Object.create is a third way we can connect prototype objects

recommend not using `new` keyword because it does SO much for you. 

You can add functions to the global Object but it has major tradeoffs
 Performance cost, you could be over-writing functions that JS comes out with in the future

```js

function hasArm() {
  return true
}

function hasLeg() {
  return false
}

function hasHead() {
  return 'yes'
}

---
const arm = {
  hasArm() {
    return true
  }
}

const leg = {
  hasLeg() {
    return false
  }
}

const head = {
  hasHead() {
    return 'yes'
  }
}

let armPerson = Object.create(arm)
let armLegPerson = Object.create(armPerson)
let fullPerson = Object.create(armLegPerson)

// or

Object.setPrototypeOf(arm, leg)
Object.setPrototypeOf(leg, head)

const tyler = {}

Object.setPrototypeOf(tyler, arm)
```

---

From Anushree Subramani to Everyone: (12:55 PM) Can you elaborate on the the “non-symbol” clause in this definition?

whenever objects are created with properties