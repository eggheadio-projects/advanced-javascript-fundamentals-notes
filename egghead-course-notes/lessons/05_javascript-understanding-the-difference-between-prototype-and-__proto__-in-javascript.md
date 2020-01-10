Instructor: [0:00] Functions in JavaScript are first class objects. This basically means that they can have properties and methods just like any other plain object can. While you don't typically see code that adds properties to a function and treat it like an object, it's essential to understand this principle because it powers prototype or inheritance within functions.

[0:19] Whenever we create a function like we have here, behind the scenes, JavaScript is automatically creating a property for us on this functional object called .prototype. As we see here, this is just an object that has two properties on it. A constructor property that points back to the FOO function and a _proto_ that is referencing another object.

[0:42] If you're new to JavaScript, it might be confusing to understand the difference between a functions.prototype property and the dunder property that lives on objects. Dunder proto is another way of referencing this_proto_property that lives in all objects.

[0:59] To reiterate, whenever we define a function, JavaScript will automatically create this object as the value of a .prototype property. This property is not used in the prototype chain look-up if we were to dot onto the foo function when looking up a property.

[1:17] While on the other hand the dunder proto property is used for prototype inheritance, this dunder proto property is what JavaScript searches when looking up properties within objects. JavaScript automatically creates this dunder proto property on every object automatically.

[1:35] With that in mind, let's take this one step further. The .prototype property object that lives on every function except arrow functions is what becomes the dunder proto value object when the new keyword is used against the function.

[1:50] As we see here, we added a test property to the automatically created .prototype object that lives on the foo function object. Whenever the new keyword is used, a new object is created. The .prototype object that lives in the function the new keyword is called against becomes the next-in-line dunder proto object of the new object created from the new keyword.

[2:13] This is why when we, on line nine, do a console.log name.test, we get "Hello, world." The browser console shows us this relationship a little clearer. If we open up the dunder proto property -- again, this is what's used prototypal inheritance -- we see it is the same object as the .prototype object that lives on the foo function.

[2:35] While the .prototype property and functions is not used in the prototype chain lookup, like dunder proto properties are, you can see that they are related. You might be wondering why you should care about this. If we were to type the keyword Object -- with a capital O -- into our console, you might expect to see an actual object. However, it's actually a function.

[2:56] These are built-in object functions. It's the same for array, map, and set. These are all global functions and not an object type, as it implies. These global functions have a .prototype object just like every other function. This .prototype object holds mini-methods you probably use in your code every day.

[3:18] For example, every time you use the .map function on an array, you're using the global array.prototype object .map method. JavaScript news up these global functions for us, and connects their corresponding global function .prototype object to the instance dunder proto property. In other words, you're using prototype inheritance every time you use any kind of object within your code.
