Instructor: [0:00] To understand what a closure is, let's write out some code. Here, we have a const workshop global variable at the top.

[0:06] On line 3, we're going to have a parent function that has a variable itself on line 4. On line 5, we're returning a child function that has a variable inside of it. On line 7, we're going to console.log the global, the parent variable, and the child variable. On line 11, we'll invoke our parent function. On line 13, we're going to invoke our me variable.

[0:27] With this code in front of us, let's define a closure. A closure is an inner function that has access to its lexical scopes, which includes its own scope, its parent scope, and the global scope. This child function is a closure. We see on line 7 that we have access to its own const, the parent const, and the global const.

[0:46] What makes a closure function interesting is that, as we see on line 11, even though we execute parent function, our closure function still retains access to the parent's const.

[0:56] Closures do not close over a value. They only close over variables. In other words, if the global const value changes, a child function reference to it will change as well. It doesn't memorize the connection at alter time. Closures just keep their connection to variables alive even though its surrounding function executes.

[1:16] As we'll see in line 6, closures are a way to make variables private from the outside scope. We have no way of accessing this const here from anywhere else except for inside this function, which hides implementation details which change frequently in our code while programing towards interfaces.

[1:32] You might be wondering if you use closures in your everyday work. The answer is almost to guarantee yes. A common implementation of a closure is callback functions like within the array.prototype.map function. Its callback is a closure because it's a nested function within a function that has access to its parent's scopes.
