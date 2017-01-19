# JavaScript Coding Standard

## 1. Variables
----------

When declaring variables, always use `const` instead of using `var` to ensure you can't reassign your variable. If you should reassign varialbe use `let` instead `var`

```js
//Bad
var foo = "some value",

//Good
let foo = "another value"
const boo = "some value" // Can't reassign 

foo = "changed value";
```

* **Note:** That both `let` and `const` are `block-scoped`
```js
{
  let foo = "value foo"
  const boo = "value boo"
}
console.log(foo); // ReferenceError 
console.log(boo); // ReferenceError

```

## 2. Objects

**a.** Use object literal syntax for object creation

```js
//Bad
const item = new Object();

//Good
const item = {}
```

**b.** Use object method shorthand

```js
//Bad
const foo = {
  man: 1,

  gotoHome: function(location) {
    return location;
  }
}

//Good
const foo = {
  man: 1,

  gotoHome(location) {
    return location;
  }
}
```
**c.** Use object property shorthand