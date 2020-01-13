Instructor: [0:00] When the class keyword came out with ES6, many thought that JavaScript finally got classes into the language. However, this is not the case. It is just syntactic sugar over regular functions, and it utilizes the prototype chain for inheritance.

[0:15] In fact, if you're using Babel within your application, Babel will turn our class on line 1 into something that looks like this. If you wanted to desugar a class, you could get pretty close by just creating a function instead. I say pretty close because even though classes are sugar over functions, they have some special rules that apply only to them in different scenarios.

[0:37] To create a basic implementation of a class, we simply write the class keyword, the name we want to call this class, and then curly braces for the body. Classes come with a number of special keywords that we could use to make our classes more dynamic.

[0:50] At a small level, we could declare fields by simply writing out an assignment like this. Also, similar to object, we can add methods by declaring them within the class body as well.

[1:02] I mentioned before that classes work on the prototype chain. We're able to do this by utilizing the extends keyword for classes. The extends keyword is how we can connect two classes together through the prototype chain.

[1:15] As our console.log shows us, as we extend our square class with the rectangle class, we run Object.getPrototypeOf, we see that the next in line prototype object of square is our rectangle class.

[1:29] We can desugar the extends keyword by changing our classes to functions and then using the Object.setPrototypeOf method. This assigns squares next in line prototype object to be the rectangle function. As you can see that our console.log gives us the same result. We're getting rectangle as the prototype of square.

[1:48] When we use the new keyword against our square function, our getPrototypeOf method tells us that the __proto__ object of Shape is the .prototype object of Square. However, the next in line __proto__ object after this square.prototype object is the native global object.prototype method, and not the .prototype object of rectangle, as you might assume.

[2:13] Regardless of the fact that we are trying to connect the prototypes with the setPrototypeOf method, this is where trying to desugar our classes completely falls short. If you're confused at what I'm trying to show here with this code, the key point I want you to take away from this that two layers deep in our __proto__ chain is the global Object.prototype object, even though we connect the two functions up here with the setPrototypeOf.

[2:39] If we change your functions back to classes as they were initially, we still [inaudible] up a square class. Now look at our console.log. We see that two levels deep is the Rectangle.prototype object and not the Object.prototype object.
