##Immediately-Invoked Function Expressions (IIFEs)

> Produces a lexical scope using JavaScript's function scoping

*Sometimes refered to as a "self-executing anonymous function".* 

An IFFE is used for may reasons, but they generally have one thing in common, **scope**. I'm not going to get into all the gory details here, but scope can definitely be a tricky thing in JavaScript and you can get started looking into it [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Scope_Cheatsheet). 

```javascript
(function(){
  //Fresh, clean function scope for you to not disrupt other code
})();
```

Lets discuss the format a bit before diving deeper. I'm going to break this into 4 sections `(`, `function(){}`, `)` and `()`.

- The initial `(` is simply an indicator that this is no ordinary function expression. Some prefer `!`, but it has the same outcome, absolutely nothing.
- `function(){}` you've seen this plenty of times before I'm sure, but this is the (anonymous) function expression piece.
- Since I use the `(` to indicate that something awesome is about to happen, I have to close that paren.
  - *Note: This can come before or after the next step*
- Lastly we invoke the function immediately using `()`.

###Immediately-Invoked

It invokes itself immediately after being defined. You'll notice the `()` right after the definition of the function. 

###Function Expression

> The main difference between a function expression and a function statement is the function name, which can be omtted in function expressions to create anonymous functions


###Benifits

#####Less Global Scope Pollution

By wrapping all your code in an IFFE, you can reduce the amount of global variables created, as well as decrease the change of overwriting (or being overwritten) by another script/library.

#####[Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Closures)

The concept if fairly simple, but overwhelmingly powerful. 

#####Making sure undefined === undefined

*In modern browsers (JavaScript 1.8.5), undefined is a non-configurable, non-writable property per the ECMAScript 5 specification.*

Prior to JavaScript 1.8.5, it was possible to do something like this:

```javascript
undefined = true; //of some value other than undefined.
```

Which could easily cause issues if you were checking if a value was infact `undefined`:

```javascript
if(true === undefined){
  //Since we reset undefined above, this is reachable
}
```

As this is quickly becoming a non-issue, and in most cases is not an issue at all, it's still nice to know about. There are plenty of solutions for this, but since we're on the subject, you can use the following snippet.

```javascript
(function(undefined){
  //Since we didn't pass any arguments, undefined === undefined.
})();
```
