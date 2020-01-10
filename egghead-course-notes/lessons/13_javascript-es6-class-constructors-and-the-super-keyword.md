Instructor: [0:00] Whenever the new keyword is used against a function, the entire function body is invoked. However, when dealing with classes, the only body of the class that is executed with the new keyword is the constructor body.

[0:11] The constructor keyword is specific to classes only and receives any params that are passed to it when it gets newed up.

[0:19] There can only be constructor per class. If you're working with a class that is extending another class, in order to use a constructor at all, as well as use the this keyword from within that constructor, you have to first call the super keyword.

[0:33] The super keyword is used to access and call functions on a class's parent. Super tends to be used mainly to call the constructor function found on the parent class we're extending.

[0:42] Here, we have two classes. One is a rectangle with a constructor function that takes in a height and width. Inside of the constructor, we're assigning properties to the instance of rectangle, which include name, height, and width.

[0:53] Next, we have a square class that extends rectangle. Inside of its constructor, we're calling super, passing through length to both. This super call will invoke rectangle's constructor, which again creates these properties.

[1:07] Back to square, we assign name as square to the instance. When we use a new keyword for my shape, we're creating a new object. New will first invoke square's constructor. The super calls rectangle's constructor, which assigns the properties to the new object being created by the new keyword.

[1:26] Then we mutate the name property, originally rectangle, to be square. Our console.log shows us this final object. Again, even if our rectangle class did not have a constructor, we'd still need to call super within the square's constructor because it is required when we're working with subclasses that have constructors and when the this keyword is used in the constructor.
