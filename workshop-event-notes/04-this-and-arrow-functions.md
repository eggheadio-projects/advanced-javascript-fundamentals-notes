This references the execution context of a function's call

depending on how a function is being called - `this` will change

You can see how the function is called during run-time.

In what ways can you execute functions?

with `()` on the function. can use `call` that lives on the prototype. the `new` keyword will invoke a function

Alot of people say "look to the left of the dot" when trying to understand what this is

invoking a function with `this` without a context will make `window` the context

**var puts variables on the window object**

    window.setInterval(person.getName, 3000) // will break because the context is setInterval

You *can* explicitlty invoke `this`

**The way I remember the diff between call and apply is c is comma separated and a is for array**

---

new keyword only invokes constructors right ? It can’t invoke anyother function 2 separate questions ^
From Lucas Minter to Everyone: (02:08 PM) Why use `this` at all then? Seems like it is just confusing things. Why not just use `person`?

It's a really powerful tool, it's dynamic. once you understand it, that power is yours.

It gives us flexibility of using the context that the 
From Anushree Subramani to Everyone: (02:08 PM) You should have that flexibility to invoke the functions in different contexts. Thats why

From Blake Johnson to Everyone: (02:09 PM) this.value.firstname would work for that nested example
From KD Singh to Everyone: (02:10 PM) Is window the top most level context in Js?
From Blake Johnson to Everyone: (02:10 PM) Yes, in the browser
From Blake Johnson to Everyone: (02:10 PM) Js on the server like node it is global

## Arrow functions

arrow functions have no concepts of `this` and treat it like a normal variable

**arrow functions only respect function scoping. not block scope.**

From Anushree Subramani to Everyone: (02:25 PM) There is a common misconception that arrow function have a “flat” scope. But truth is, the parent’s scope is referenced.
```js
const person = {
  firstName: 'tyler',
  getName() { // this is the function scope - which 
    window.setInterval(() => {
      console.log(`${this.firstName} is my first name`) // this goes up a level to the next function scope (at author time)
    }, 3000)
  }
}

person.getName() // "tyler is my first name"
```
arrow functions in arrow functions makes me think how there’s nothing that is actually catching the scope

arrow functions: you really need to know how they are written to understand this. not run-time.

From Anushree Subramani to Everyone: (03:01 PM) Tyler, what happens to “this” in strict mode?