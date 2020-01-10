Instructor: [00:00] This keyword references the execution context of a function's call, which just determine how that function was called and a non-strict mode is always a reference to an object.

[00:12] This keyword can be different depending how the function is called. In other words, you cannot look at how a function was declared and know what this context will be. You have to see how the function is called at run time.

[00:25] These statements are true for all functions, except of error functions. As soon as we look at this code here, we want to look for three things in order to figure out what the keyword is. First off, what's the getName function invoked? How was it invoked? Finally, in what context, was it invoked in?

[00:43] To answer number one, we see on line eight, the getName function was invoked with what is called implicit binding, which means we use one of the three ways a function can be invoked. This is done with the open/close parens pattern, which answers number two.

[00:59] To figure out in what context, we could easily look at the object where this function lives, which is the object immediately to the left of the function property. Knowing that the function was actually invoked, it wasn't implicitly binded, we can see that the person object is the context of the this keyword.

[01:18] Looking back at our getName function, knowing that person is indeed our function context, it is saying return person.firstName within the string as we see from the console.log. Let's look at some other examples. If we nested getName within another object within the person object, how does it affect our new execution context of this?

[01:38] Let's answer our questions again. Our function is invoked. It's still using implicit binding with open and close parens, and the object immediately to the left of the getName function is now the new context. We get the same console log statement.

[01:53] Keep in mind that it is the value object that is in fact the new context that this is referencing and it's no longer person. We see this more clearly if we move the firstName property up into the person object. Now our console.log says undefined is my first name, because firstName no longer lives on the value object.

[02:15] What if we were to move the getName function outside of all objects? What's the new this context? The function is still invoked, still with implicit binding in the parens. However, there appears to be no object immediately to the left. What is our context?

[02:31] There actually is an object to the left. We just can't see it here. Whenever a function is declared, it is automatically added to the window object. What we see here -- a browser -- we treat it like this, window.the function name. Window is our this context.

[02:47] Unfortunately, my vs code extension can't handle the window object, but we see this more clearly within the Chrome console. You can see by even though we put this window.git name, we don't get an error, and we undefined as my first name.

[02:59] If we're to add a variable first name to the window object, we would get the right response. Window is now the context object. Because it is the context object, now that it has a first name property on it of Tyler, this keyword used within the git name function, looks for that first name property on the window object.

[03:19] We get Tyler as my first name. Let's look at one more example of this keyword in action. Here, we're back to our git name function within the person object. What if we created another object and called it another person?

[03:31] Then, we assigned the git name person function from person onto a new property within another person object. Then, we invoke the git name function from another person. We see that we get undefined as my first name. Let's look at our list again. Git names invokes only on line 12 and not on line 10, still with implicit binding.

[03:51] However, another person is the context object that this keyword will reference since it's the next in line object of when the function was called. Another person does not have a first name property on it. Again, even though the git name function was defined on person originally, that does have a first name property.

[04:09] Because it was copied over to another person, the another person object is what the function is actually called. Thus, making another person the context that this is going to reference.
