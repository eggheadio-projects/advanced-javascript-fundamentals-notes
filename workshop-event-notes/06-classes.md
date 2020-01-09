classes are just syntactic sugar for functions

while it is just 'syntactic sugar' but the browser and tools like babel add functions to class prototypes

### extends

one way to connect one class to another class

this is just working with the prototypes - similar of using `setPrototypeOf` with two functions

`new` keyword does extra that is hard to replicate 

super() is a way to get access to anything on the parent class like the constructor or static method

you have to call super() in a class constructor before doing anything inside the constructor