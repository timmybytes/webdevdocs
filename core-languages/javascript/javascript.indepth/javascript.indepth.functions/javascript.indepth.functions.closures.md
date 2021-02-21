# JavaScript: Closures

<em>
<sub><a href='../../../../README.md'>Home</a> > <a href='../../../core-languages.md'>Core Languages</a> > <a href='../../javascript.md'>JavaScript</a> > <a href='../javascript.indepth.md'>JavaScript In-Depth</a><a href='./javascript.indepth.functions.md'> > Functions</a> > Closures</sub>
</em>

<br />
<br />


> A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function’s scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time.
> <br /> — [via MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)

## Contents

* [Lexical Scoping](#lexical-scoping)
* [Closure](#closure)

### Lexical Scoping

```js
function init() {
  var name = 'Mozilla'; // name is a local variable created by init
  function displayName() { // displayName() is the inner function, a closure
    alert(name); // use variable declared in the parent function
  }
  displayName();
}
init();
```

`init()` creates a local variable called name and a function called `displayName()`. The `displayName()` function is an inner function that is defined inside `init()` and is available only within the body of the `init()` function. Note that the `displayName()` function has no local variables of its own. However, since inner functions have access to the variables of outer functions, `displayName()` can access the variable `name` declared in the parent function, `init()`.

### Closure

```js
function makeFunc() {
  var name = 'Mozilla';
  function displayName() {
    alert(name);
  }
  return displayName;
}

var myFunc = makeFunc();
myFunc();
```

Running this code has exactly the same effect as the previous example of the `init()` function above. What's different (and interesting) is that the `displayName()` inner function is returned from the outer function *before* being executed.

A **closure** is the combination of a function and the lexical environment within which that function was declared. This environment consists of any local variables that were in-scope at the time the closure was created. In this case, `myFunc` is a reference to the instance of the function `displayName` that is created when makeFunc is run. The instance of `displayName` maintains a reference to its lexical environment, within which the variable `name` exists. For this reason, when `myFunc` is invoked, the variable `name` remains available for use, and "Mozilla" is passed to `alert`.

## Resources & Links

* [Mastering the JavaScript Interview: What is a Closure?[Medium]](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-closure-b2f0d2152b36)
