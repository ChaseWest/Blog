##Immediately-Invoked Function Expressions (IIFEs)

> Produces a lexical scope using JavaScript's function scoping

*Sometimes refered to as a "self-executing anonymous function".* 

And IFFE is used for may reasons, but they generally have one thing in common, **scope**. I'm not going to get into all the gory details here, but scope can definitely be a tricky thing in JavaScript and you can get started looking into it [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Scope_Cheatsheet). 


```javascript
(function(){
  //Fresh, clean function scope for you to not disrupt other code
})();
```

###Immediately-Invoked

It invokes itself immediately after being defined. 

###Function Expression

> The main difference between a function expression and a function statement is the function name, which can be omtted in function expressions to create anonymous functions


###Benifits

#####Less Global Scope Pollution

#####Closures

#####Making sure undefined === undefined
  
