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
**c.** Use object property shorthand not nice at all



## 3. Functions
----------

**a.** Use default parameter syntax

```js
//Bad
function changeHandler(args) {
   args = args || {};
   //...
}

//Good
function changeHandler(args = {}) {
  //...
}
```

**b.** Put default parameters last

```js
//Bad
function changeHandler(lastName = "", firstName) {
  //...
}

//Good
function changeHandler(firstName, lastName = "") {
  //...
}
```

**c.** Spacing is a function. (Good for consistency and readability)

```js
//Bad
const a = function(){}

//Good
const a = function () {};
const a = function changeHandler() {};
```

* **Note:** Blank space should not be used between a method name and its opening parenthesis. This helps to distinguish keywords from method calls.

**c.** Functions with multiline signatures should indented just like any other else code blocks.

```js
//Bad
function changeHandler(firstName,
                       lastName,
                       age) { //... }

//Good
function changeHandler(
  firstName,
  lastName,
  age
) {
  //...
}
```

## 4. Arrow Functions
----------

**a.** When using function expressions use arrow functions.

```js
//Bad
[1, 2, 3].map(function (number) {
  return number * 2;
});

//Good
[1, 2, 3].map((number) => {
  const newNumber = x + 2;
  return newNumber - number;
});

//Good
[1, 2, 3].map(number => number * 2 );
```

## 5. Properties
----------

**a.** Use dot notation when accessing object properties.

```js
//Good
const employer = {
  firstName: 'Patric',
  lastName: 'Jane'
};

const employerName = employer.firstName;
```

**b.** Use [ ] notation when using variables to access object proerties.

```js
//Good
const employer = {
  firstName: 'Patric',
  lastName: 'Jane'
};

function getName(property) {
  return employer[property];
}

const employerName = getName('firstName');
```
