coercion is like conversion, think of it like a type converstion of primitive to primitive or object to primitive

theres implicit and explicit conversion 

there are gotchas

```js
const arr = []

if (arr.length) {
  // this arr.length check is coercing the number into a boolean
}
```

---

From KD Singh to Everyone: (01:34 PM)  Many ways to skin the coercion cat here, so again, when we are using coercion deliberatly, what is the best practice?

From Anushree Subramani to Everyone: (01:42 PM) My problem with javascript has been that its hard to remember all these “quirks”. I have learnt these things sooo many times but I forget them because its more of a memory thing rather than logic most often. Any tips for remembering these long term?

If you are trying to explicitly coerced, try to memorize the edgecases. When you are using implicit coercion, you should be fine.