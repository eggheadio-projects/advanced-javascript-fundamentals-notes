Instructor: [00:00] It immediately invokes function expressions or functions that are called right after they are declared. Normally when functions are declared, they're put on the global space like the window object. However, IIFEs, for sure, are not.

[00:12] The magic behind an IIFE is the initial wrapping of the function with the open/close parens. This is called the grouping operator. This makes it an expression because the grouping operator returns whatever is inside of the parens.

[00:26] Again, because it is an expression, you cannot access the IIFE in the global namespace. This includes any variable or any other function defined within the IIFE. We have no access to these variables from outside. This is because const A and anything else we define within this function is scoped only to this function findName. Since we can access findName from the global scope, it acts like a private variable.

[00:50] We see IIFEs used a lot when working on code that is private and when we don't want other scopes to access its state. This is the syntax for creating an IIFE using an arrow function. All the same scoping rules apply, which again means we can't access anything inside of the arrow function because of the function's block scope and its inability to be accessed.
