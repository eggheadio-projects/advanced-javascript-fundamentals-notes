Instructor: [00:00] Strict mode is coined as the opposite of sloppy mode. It intentionally has different semantics from normal code.

[00:06] For example, it is not allowed global var as we see here. To enter strict mode, we simply put in a string "use strict" at the top of your file. If you're using compilers like Babel, it is added automatically to your code. ES6 JavaScript modules like import and export "use strict" is also added automatically to your code as well.

[00:24] Some other examples of strict mode trying to help us from potential bugs is when trying to mutate a non-writable object property. In non-strict mode, you can get away with this. However, in strict mode, as we see here, we're going to get a type error.

[00:36] Looking at our code, we're trying to add a property with a value of first and we're making it non-writable, which means that we cannot mutate it later. When we try to mutate it with a new value, we're going to get this type error because we're in strict mode.

[00:49] Here we see another example, the difference between the two modes. We're allowed to use reserved keywords like undefined and infinity as variable names, while in strict mode, we get a type error.

[00:59] Again, another example. Strict mode does not allow parameters to be the same name. We could get away with this in non-strict mode, but in strict mode, we get an error. We also see that we have the ability to scope strict mode to a function block. Strict mode does not have to be at the top of our page. We can scope it by putting it within a function like this.

[01:19] Finally, one of the most common catches that strict mode does in our code is eliminate access to the window object when using the this keyword. For example, outside of strict mode, when we return this, we get the window object. However, in strict mode, we get undefined.
