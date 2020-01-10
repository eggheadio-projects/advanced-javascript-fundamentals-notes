# [Understanding Prototypal Inheritance within JavaScript](https://egghead.io/lessons/javascript-understanding-prototypal-inheritance-within-javascript)

ProtoTypes are the way that JavaScript powers inheritance. This mimicks some behavior that you would expect out of a class in another language like C# or Java, but JavaScript does not have classes.

JavaScript adds a `__proto__` property on your object that links other methods and properties (which themselves can be objects).

Open up your console and create an empty object `let a = {}`. If you log that variable, you'll see that `__proto__` was automatically added even though the object is 'empty.'

**This __proto__ key is also called Dunder proto.** 

That Dunder proto property is what prototypes and inheritance is in JavaScript.

Every time you work with an object within JavaScript, as long as you don't mutate it later, will automatically be linked through this Dunder proto property to the global object prototype.

[1:29] Let's dive a little deeper into prototypal inheritance. When I created this object, you can see, I didn't add any properties to it, right? It's just an empty object. However, when I toString() on this object, I don't get an error, and instead, I actually get a return value.

## toString an Empty Object
```js
const a = {}

a.toString()

console.log(a) // "[object Object]"
```

Even though this object is empty, when I call `toString` on `a`, JavaScript will first look on the object for the `toString` method. When it doesn't find that method there, it will step into `__proto__` and look for `toString` inside that object. In this case, it finds the `toString` method and calls it.

You could think of this method call as being called like this: `a.__proto__.toString()`.

[2:06] There is also no limit to the number of nested prototypes you can have on an object. Here, I'm using object.create, which is a function that creates a new object and optionally takes a param, which will be the next-in-line Dunder prototype object.

[2:21] If we take a look at what B looks like in our browser console, you can see more clearly that B is just an empty object. Its next-in-line prototype through this Dunder property is the A object. The next-in-line prototype object through the Dunder property is the global object prototype object that all objects are given when no prototype is specified or mutated otherwise.

## Nested Dunder Properties in Objects
```js
const a = {}

const b = Object.create(a)

console.log(b)
/*
{}
  __proto__:
    __proto__: Object
*/
```

[2:45] If we were to give the A object a property of toString(), where this new toString() property is a function that returns true, you can see that our console at log of B is now returning true.

[2:57] If we throw this back in our browser console, we can see this prototypal inheritance more clearly. When we step through the Dunder property of the B object, we will see the A object that has this toString() method we've added.

[3:10] We see the original toString() method on the global object prototype, which is nested within the A object's Dunder prototype object.

[3:19] Whenever we do lookups on an object in JavaScript, it will go through each prototype chained object until it finds the corresponding property, or it will return undefined if it never finds it. It stops searching through this chain as soon as it matches on a property.

[3:35] The original toString() is actually never called. All types of objects within JavaScript have their own global built-in prototype objects that get connected whenever a new instance is created.

[3:47] We saw that to be true with plain objects. It's also true for other sub-types of objects like arrays, maps, sets, and functions. You can see that here with an array, we have this Dunder array object. Those are all the methods we used when we worked with arrays.

[4:02] Same thing with maps, when we create them. There's a Dunder proto map object that correlates with it. It has its own methods that we can use when we instantiate maps. Same thing with sets. It has a Dunder set prototype.

[4:18] It's also true for functions. It has a functional prototype object that gives us methods that we can use when working with functions.
