Instructor: [0:00] Think of coercion as a conversion. It's the changing of types from primitive to primitive or object to primitive. Here we're using a template string and it has a variable inside of it with the value of 2. Ultimately, you want to return just one type, a string and assign the string value to this variable and return it. What is happening here is what it's called implicit coercion.

[0:21] It's implicit because we're asking JavaScript to coerce the number variable into a string, rather than us supplying a string to the string. Implicit coercion is very common and sometimes is considered a bad practice because it can be difficult to catch potential bugs.

[0:36] Another example of this happens when we work with truthy and falsy values as we see here on line 3. Array.length is returning a number and our if check requires a Boolean. Here again, we're relying on JavaScript to implicitly coerce our number which is currently , because our array's empty on line 1, into a false Boolean.

[0:57] I mention that you might hear to avoid implicit coercion. You'll hear this the most when working with the == and the ===. The == will try to coerce implicitly the value to just comparing first, to see if you get them into the same type. Once they're the same type, then they'll compare their values, while the === will not do any covert coercion and will compare the values by type and value.

[1:22] The feeling on one side is that you should try not to coerce your code and make everything the same type, so it's deterministic throughout. However, the other side will say that coercion is highly valuable, and it should be embraced. One thing is for certain though. It's extremely difficult to go through your code avoiding all types of implicit coercion.

[1:40] Another example was when primitive types are autoboxed into an object. When we treat primitives like an object, JavaScript will coerce the value into an object. As you can imagine, avoiding implicit coercion 100 percent of the time will take a lot of overhead.

[1:54] Much of that overhead will involve explicit coercion, which is shown best with our original template string example. If you wanted to avoid implicit coercion here, we'd first explicitly coerce our number into a string so that when the variable is injected into our template string, it's already a string.

[2:13] Simply put, explicit coercion happens when we are explicitly coercing using built-in methods like strings, number, Boolean, many of the parse methods like parseInt and other methods, instead of relying on JavaScript to just do it for us.
