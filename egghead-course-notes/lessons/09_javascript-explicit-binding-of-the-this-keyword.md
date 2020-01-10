Instructor: [00:00] As we try to figure out what the this context is from within a function execution, let's break down the scenario looking for these three questions. Was the function we're looking at invoked? Next, how was it invoked? After answering the first two questions, what's the context that it was invoked in?

[00:19] The answer to number three tells us what do this keyword will reference. Here we have an object called person that has a first name property on it with a value string of Tyler. We also have a function get name that returns this.firstName is my first name. When we invoked this function, we get undefine is my first name.

[00:39] Let's try to figure out where we went wrong by going over our checklist. Our function is invoked on line nine. It is implicitly bound with the open/close parenthesis. With those answered, let's look for the context of the getName function.

[00:52] This function does not live within another object as we can see, which means that it's going to live on the window object. This is most likely always going to be the answer when you see a function declared like so. This is the window object. It does not have a first name property on it, so it returns undefined.

[01:10] Instead, let's explicitly bind the getName function invocation. We can do this in a couple of different ways. First, let's use the call function prototype method. This will invoke the function and will explicitly bind the this context to whatever is supplied to the first argument.

[01:27] If we do getName.call passing in person to the first param, we get Tyler as my first name. Again, this is how we can explicitly bind the this context to another object. All the params after the first context param are funneled into the function that's being called.

[01:46] Another way we can explicitly bind the this context is with the apply method. This is the exact same as call except it takes an array of arguments, and those are spread out into the calling function.

[01:59] There is a third function prototype method that can explicitly bind the this context. It's called the bind method. The bind method does not actually invoke the function like call and apply did, but rather returns a new function that can now be called anywhere, and its first param is now the this context whenever it is actually called.

[02:20] If we were to run this set interval code as it stands here, we would continually see undefined as my first name every three seconds. Looking at our checklist, we see that our function is never actually called, which means that it is being invoked internally within the set interval function and that this is going to be the window object.

[02:39] If we use the bind function prototype method and pass through the person object as the first param designed to designate the explicit this context, we are binding the person object to our getName function.

[02:53] We have total control on what this is from within our getName function. We see Tyler is my first name every time, regardless of how the function is actually executed inside the setInterval.
