Instructor: [0:00] Arrow functions have no concept of this, meaning they treat the this context keyword the same as it would a regular variable. In other words, if you define this keyword inside of an arrow function, it will lexically resolve it by looking up its scope for this. As our code currently stands, we're going to see undefined as myFirstName printed to the console every three seconds.

[0:20] This is because the function is not actually invoked on line 8 and is internally invoked within the setInterval function, which would make its context be the window object. The window object does not have a firstName property on it, so it returns undefined as myFirstName.

[0:36] Sometimes, people will rush to arrow functions as the fix-all solution when having trouble with a this keyword. However, an arrow function on line 3 will still have the same problem. Our browser console will show this to us.

[0:48] Even with this arrow function, we're still getting undefined as myFirstName. To really understand how the arrow function resolves the this keyword when it's defined inside of an arrow function, we need to understand what lexical scope is.

[1:01] Lexical scope is a fundamental concept in JavaScript that involves the fact that every function creates a new scope. Lexical scope references author time of our code and not run time.

[1:12] An example of the opposite of lexical scope is the this keyword itself. The this keyword is dynamic, meaning it depends on its run time in order to understand what its value is. Again, lexical scope is the opposite. We are looking for the next non-arrow function scope at author time.

[1:29] Once we find that next function scope, how is that function invoked? The inner arrow function takes on the context of that parent function's context. With that in mind, we can answer why did the arrow function we defined not take the firstName property within their person object? It's because person's an object and not a function scope.

[1:50] What is the next lexical scope for our arrow function again? Person is not within another function, right? It's defined that pure at the top. The next scope is going to be the global window object, which again, does not have a firstName property on it and we're going to get undefined.

[2:05] In order to fix our lexical scope problem, we can make the getName function a regular function again that returns this arrow function. What is this arrows next lexically scoped or its authors time scope function? It's now getName, right?

[2:20] Now we look to invoke getName on line 11, which its this context is now a person because person is the context that's invoking getName. When the arrow function is finally called within the setInterval function, its this context will be person because it inherits it from getName, which context's is in fact person. We see that on line 11.

[2:43] We can confirm this with the browser console. We see Tyler is my first name because the arrow function lexically resolves person as the this context.
