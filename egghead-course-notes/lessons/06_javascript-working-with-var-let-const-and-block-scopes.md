Instructor: [00:00] Block scoping in JavaScript is defined with the overloaded opening and closing curly braces. It does not become a scope until there is an assignment made inside of it. If no assignment is made, JavaScript will treat it as an object literal, and create a new object.

[00:16] When trying to determine block scopes in your code, you cannot simply look for just curlies, because objects are not scoped, and they do have curlies. Here we see an open and close curly braces, and we also see an assignment made on line four, thus making it a block scope.

[00:31] Now that we've established we have a block scope created, we next need to understand what variable types we're working with. Here we see that we're using two vars. Vars, however, do not respect block scopes, only function execution scopes.

[00:46] You might expect the console log here to print Clark and the last one to print Tyler because the vars are used in two different block scopes. However, like I said, vars only reference function execution context scopes.

[00:59] What is our execution of our context here? It's the global namespace or window object. When we re-declare on line four, we're leaving the block scope and redefining the value on line one. In order to scope the var correctly, we need to change our block scope to a function scope. Now, when we invoke our function and look at the two console logs, we see that it is Clark and Tyler.

[01:22] Some other notes on vars is that before our JavaScript is processed, all var declarations are hoisted only to the top of their execution context with an initial value of undefined. Our code actually looks like this behind the scenes, with an initial value of undefined.

[01:39] Also, any vars declared in a global function context are placed on the window object. If we did window.firstName, we would get Tyler, not Clark again because it is scoped to this function context.

[01:53] Let's go back to our original block scope code and instead of vars, let's use the let variable declaration and see how it responds. We see that unlike our var example, let does scope to block scopes, as well as function execution scopes.

[02:08] We have two different console at log values because these are actually two different variables. Also, unlike var, let is only initialized to a value when the parser evaluates it. In other words, it's not hoisted to this top of the scope with an initial value of undefine like var is.

[02:25] Finally, if we tried to re-declare let within the same scope, it would throw an error while using a var would not. Const has the same rules as let does. Even if we changed our two variables to const, we still get two different console log values because we're creating two different variables within a block scope which it respects.

[02:46] It does not hoist. It cannot be re-declared. However, it has a special rule that states that it can also not be redefined with a different value. We cannot later on change the value to something else because it will throw an error.

[02:59] The caveat on this is that it does not do a deep equal. You can mutate properties within an object and an array, for example, and no error will be thrown.
