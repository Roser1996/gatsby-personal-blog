---
path: js-tricks-1
date: 2021-04-26T23:56:36.592Z
title: 5 JavaScript Tricks - 01
description: Javascript Series
---
## 1 `??` operator
If the assigned value is falsy, then it will take the fallback value, otherwise the operation result will be the assigned value.
```javascript
const a = 10 ?? "default value"; // 10
const b = undefined  ?? "default value"; // default value
```
**Note: Not all the browser support this syntax** 

## 2 Styling console log
Add percent c to the front of the output, then add the css style string as the second parameter of console log.

```javascript
console.log("%c Hello World", "font-weight: bold; font-size: 1rem;");
```

## 3 Optional Chaining
Used for interacting with an object while you don't know if a certain property is exist or not.

```javascript
const person = {
    address: {
        street: "street line 1"
    },
    print: function() {
        console.log("Hello")
    },
    hobbies: ["cook"]
}
console.log(person?.address?.street) // street line 1

// It can also used for check a function is exist or not
person?.print() // Hello
person?.printName() // undefined

// Also can be used in array
person.hobbies?.[0] // cook
person.hobbies?.[1] // undefined
```

## 4 Object Shorthand
If the key name is the exact same as the variable when we are creating the object, then we just put the variable name
```javascript
const name = "Tom";
const age = 16;
const people = {
    name,
    age
}
```

## 5 Defer/Async Loading
If you put the `script` tag to the head of the HTML file, in order to make sure it works properly, add a `defer` tag to the `script` so it can asynchronously load the scripts file.

Compared to put the script tag to the bottom, this can load faster.

```html
<script src="script.js" defer />
```

