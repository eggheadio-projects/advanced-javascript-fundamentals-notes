Scope is bucketing values together. You can go from the most enclosed → outwards. You cant go from out to in.

### lexical scoping

Lexical is related to 'author' time

`this` gives us that dynamic 'run-time' scope

Anti-pattern :)

From James Churchill to Everyone: (03:14 PM) (^ referring to defining all of your variables globally)

### block scoping

### hoisting

var only respects the function context

### var, let, and const

let doesn't create properties onto the window object

let respects block scope

const follows same rules as let

const only makes top level variable immutable - if you make an array or object the insides can be changed

Temporal dead zone

you can't use that variable in that scope until its defined later on in the page