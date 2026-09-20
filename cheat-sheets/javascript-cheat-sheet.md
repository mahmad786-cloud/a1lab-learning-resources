# JavaScript Cheat Sheet

<div align="center">

# 🟨 JavaScript Beginner-to-Advanced Cheat Sheet

### Quick syntax and concept reference following the A1Lab JavaScript learning sequence.

Part of **[A1Lab Learning Resources](https://a1lab.tech)**

<br>

<a href="https://a1lab.tech/javascript/introduction">
  <img
    src="https://img.shields.io/badge/Learn_JavaScript-A1Lab-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"
    alt="Learn JavaScript on A1Lab"
  />
</a>

<a href="../roadmaps/javascript-roadmap.md">
  <img
    src="https://img.shields.io/badge/View-JavaScript_Roadmap-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E"
    alt="JavaScript Roadmap"
  />
</a>

</div>

---

## 📚 Quick Navigation

1. JavaScript Basics
2. Input & Output
3. Operators
4. Strings
5. Numbers & Math
6. Conditions
7. Loops
8. Functions
9. Arrays
10. Objects
11. Dates
12. DOM
13. Events
14. Browser APIs
15. JSON & Storage
16. Modern JavaScript (ES6+)
17. Error Handling & OOP

---

# 1. JavaScript Basics

## JavaScript in HTML

```html
<script>
    console.log("Hello JavaScript");
</script>
```

---

## External JavaScript

```html
<script src="script.js"></script>
```

---

## JavaScript Syntax

```javascript
const name = "Ali";

console.log(name);
```

---

## Statements

```javascript
let age = 20;

console.log(age);
```

---

## Comments

```javascript
// Single-line comment

/*
Multi-line
comment
*/
```

---

## Variables

```javascript
var oldStyle = "var";
let changeable = 10;
const fixed = 20;
```

Prefer `const` by default and `let` when reassignment is needed.

---

## var Keyword

```javascript
var name = "Ali";
```

`var` is function-scoped and can be redeclared.

---

## let Keyword

```javascript
let score = 10;

score = 20;
```

`let` is block-scoped.

---

## const Keyword

```javascript
const PI = 3.14159;
```

A `const` variable cannot be reassigned.

---

## Data Types

Primitive types:

```text
string
number
bigint
boolean
undefined
symbol
null
```

Objects:

```text
Object
Array
Function
Date
Map
Set
```

---

## typeof

```javascript
typeof "Hello";
typeof 42;
typeof true;
typeof undefined;
typeof {};
```

Important:

```javascript
typeof null;
```

returns:

```text
"object"
```

This is a historical JavaScript behavior.

---

## Type Conversion

```javascript
Number("123");
String(123);
Boolean(1);
```

---

# 2. Input & Output

## console.log()

```javascript
console.log("Hello");
```

---

## alert()

```javascript
alert("Welcome");
```

Browser-only API.

---

## confirm()

```javascript
const result = confirm("Continue?");
```

Returns `true` or `false`.

---

## prompt()

```javascript
const name = prompt("Enter your name:");
```

Returns a string or `null`.

---

## document.write()

```javascript
document.write("Hello");
```

Generally avoid using `document.write()` in modern production pages.

---

## innerHTML

```javascript
element.innerHTML = "<strong>Hello</strong>";
```

Be careful with untrusted content because it can create security risks.

---

## innerText

```javascript
element.innerText = "Hello";
```

---

## textContent

```javascript
element.textContent = "Hello";
```

---

# 3. Operators

## Arithmetic Operators

```javascript
+
-
*
/
%
**
```

Example:

```javascript
const total = 10 + 5;
```

---

## Assignment Operators

```javascript
=
+=
-=
*=
/=
%=
**=
```

---

## Comparison Operators

```javascript
===
!==
>
<
>=
<=
```

Prefer strict equality:

```javascript
value === 10;
```

instead of:

```javascript
value == 10;
```

when type coercion is not desired.

---

## Logical Operators

```javascript
&&
||
!
```

---

## String Operator

```javascript
const fullName = "Ali" + " Khan";
```

---

## Ternary Operator

```javascript
const status =
    age >= 18
        ? "Adult"
        : "Minor";
```

---

## Nullish Coalescing

```javascript
const username =
    inputName ?? "Guest";
```

Uses the fallback only for `null` or `undefined`.

---

## Optional Chaining

```javascript
const city =
    user?.address?.city;
```

---

# 4. Strings

## String

```javascript
const name = "Ali";
```

---

## String Length

```javascript
name.length;
```

---

## Escape Characters

```javascript
const text =
    "He said, \"Hello\"";
```

---

## Template Literals

```javascript
const name = "Ali";
const age = 20;

const message =
    `My name is ${name} and I am ${age}.`;
```

---

## Common String Methods

```javascript
text.toUpperCase();
text.toLowerCase();
text.trim();
text.slice(0, 5);
text.substring(0, 5);
text.includes("JavaScript");
text.startsWith("Java");
text.endsWith("Script");
```

---

## Search Methods

```javascript
text.indexOf("JavaScript");
text.lastIndexOf("JavaScript");
text.includes("JavaScript");
text.search(/JavaScript/);
```

---

## Replace

```javascript
text.replace(
    "JavaScript",
    "JS"
);
```

Replace all:

```javascript
text.replaceAll(
    "JavaScript",
    "JS"
);
```

---

## slice()

```javascript
const result =
    text.slice(0, 5);
```

---

## split()

```javascript
const words =
    text.split(" ");
```

---

## trim()

```javascript
const clean =
    text.trim();
```

---

# 5. Numbers & Math

## Numbers

```javascript
const age = 20;
const price = 99.95;
```

JavaScript uses the `number` type for most numeric values.

---

## Number Methods

```javascript
Number.isInteger(10);
Number.isNaN(value);
Number.parseInt("123");
Number.parseFloat("12.5");
```

---

## toFixed()

```javascript
const price = 12.345;

price.toFixed(2);
```

Returns a string.

---

## Math Object

```javascript
Math.PI;
Math.sqrt(25);
Math.pow(2, 3);
Math.abs(-10);
Math.max(1, 5, 3);
Math.min(1, 5, 3);
```

---

## Random Number

```javascript
Math.random();
```

Random integer from `0` to `9`:

```javascript
const number =
    Math.floor(
        Math.random() * 10
    );
```

---

## Rounding

```javascript
Math.round(4.5);
Math.floor(4.9);
Math.ceil(4.1);
Math.trunc(4.9);
```

---

## Number Conversion

```javascript
Number("42");
parseInt("42", 10);
parseFloat("42.5");
```

---

## NaN

```javascript
const result =
    Number("Hello");

Number.isNaN(result);
```

---

## Infinity

```javascript
const value = Infinity;

Number.isFinite(value);
```

---

# 6. Conditions

## Boolean Values

```javascript
true
false
```

---

## Truthy Values

Examples:

```text
"hello"
1
[]
{}
```

---

## Falsy Values

```text
false
0
-0
0n
""
null
undefined
NaN
```

---

## if

```javascript
if (age >= 18) {
    console.log("Adult");
}
```

---

## if...else

```javascript
if (age >= 18) {
    console.log("Adult");
} else {
    console.log("Minor");
}
```

---

## else if

```javascript
if (score >= 90) {
    console.log("A");
} else if (score >= 80) {
    console.log("B");
} else {
    console.log("C");
}
```

---

## switch

```javascript
switch (day) {
    case 1:
        console.log("Monday");
        break;

    case 2:
        console.log("Tuesday");
        break;

    default:
        console.log("Unknown");
}
```

---

## Nested if

```javascript
if (age >= 18) {
    if (hasId) {
        console.log("Allowed");
    }
}
```

---

# 7. Loops

## for Loop

```javascript
for (
    let i = 0;
    i < 5;
    i++
) {
    console.log(i);
}
```

---

## while Loop

```javascript
let i = 0;

while (i < 5) {
    console.log(i);
    i++;
}
```

---

## do...while

```javascript
let i = 0;

do {
    console.log(i);
    i++;
} while (i < 5);
```

---

## for...of

Use for iterable values:

```javascript
const numbers = [
    10,
    20,
    30
];

for (const number of numbers) {
    console.log(number);
}
```

---

## for...in

Use for enumerable property keys:

```javascript
const user = {
    name: "Ali",
    age: 20
};

for (const key in user) {
    console.log(
        key,
        user[key]
    );
}
```

---

## break

```javascript
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break;
    }
}
```

---

## continue

```javascript
for (let i = 0; i < 5; i++) {
    if (i === 2) {
        continue;
    }

    console.log(i);
}
```

---

# 8. Functions

## Function Declaration

```javascript
function add(a, b) {
    return a + b;
}
```

---

## Parameters

```javascript
function greet(name) {
    console.log(
        `Hello ${name}`
    );
}
```

---

## Return Statement

```javascript
function square(number) {
    return number * number;
}
```

---

## Function Expression

```javascript
const add = function (a, b) {
    return a + b;
};
```

---

## Arrow Function

```javascript
const add = (a, b) => {
    return a + b;
};
```

Short form:

```javascript
const add =
    (a, b) => a + b;
```

---

## Default Parameters

```javascript
function greet(
    name = "Guest"
) {
    console.log(name);
}
```

---

## Rest Parameters

```javascript
function sum(...numbers) {
    return numbers.reduce(
        (total, number) =>
            total + number,
        0
    );
}
```

---

## Scope

```javascript
{
    const blockValue = 10;
}
```

`let` and `const` are block-scoped.

---

## Hoisting

Function declarations can be called before their declaration:

```javascript
greet();

function greet() {
    console.log("Hello");
}
```

`let` and `const` are hoisted but cannot be accessed before initialization.

---

## Closure

```javascript
function createCounter() {
    let count = 0;

    return function () {
        count++;
        return count;
    };
}

const counter =
    createCounter();

counter();
counter();
```

---

# 9. Arrays

## Array

```javascript
const numbers = [
    10,
    20,
    30
];
```

---

## push()

```javascript
numbers.push(40);
```

Adds to the end.

---

## pop()

```javascript
numbers.pop();
```

Removes from the end.

---

## shift()

```javascript
numbers.shift();
```

Removes from the beginning.

---

## unshift()

```javascript
numbers.unshift(5);
```

Adds to the beginning.

---

## splice()

```javascript
numbers.splice(
    1,
    1,
    99
);
```

Can modify the original array.

---

## slice()

```javascript
const part =
    numbers.slice(0, 2);
```

Does not modify the original array.

---

## concat()

```javascript
const combined =
    first.concat(second);
```

---

## join()

```javascript
const text =
    numbers.join(", ");
```

---

## sort()

For numbers:

```javascript
numbers.sort(
    (a, b) => a - b
);
```

Default sorting is string-based.

---

## reverse()

```javascript
numbers.reverse();
```

Modifies the array.

---

## forEach()

```javascript
numbers.forEach(
    (number) => {
        console.log(number);
    }
);
```

---

## map()

```javascript
const doubled =
    numbers.map(
        (number) =>
            number * 2
    );
```

---

## filter()

```javascript
const adults =
    users.filter(
        (user) =>
            user.age >= 18
    );
```

---

## find()

```javascript
const user =
    users.find(
        (item) =>
            item.id === 1
    );
```

---

## reduce()

```javascript
const total =
    numbers.reduce(
        (sum, number) =>
            sum + number,
        0
    );
```

---

## some()

```javascript
const hasAdult =
    users.some(
        (user) =>
            user.age >= 18
    );
```

---

## every()

```javascript
const allAdults =
    users.every(
        (user) =>
            user.age >= 18
    );
```

---

## includes()

```javascript
numbers.includes(20);
```

---

# 10. Objects

## Object

```javascript
const user = {
    name: "Ali",
    age: 20
};
```

---

## Access Properties

```javascript
user.name;
user["age"];
```

---

## Object Method

```javascript
const user = {
    name: "Ali",

    greet() {
        console.log(
            `Hello ${this.name}`
        );
    }
};
```

---

## this Keyword

In an ordinary object method:

```javascript
const user = {
    name: "Ali",

    showName() {
        console.log(this.name);
    }
};
```

`this` behavior depends on how a function is called.

---

## Object Destructuring

```javascript
const {
    name,
    age
} = user;
```

---

## Object.keys()

```javascript
Object.keys(user);
```

---

## Object.values()

```javascript
Object.values(user);
```

---

## Object.entries()

```javascript
Object.entries(user);
```

---

## Spread with Objects

```javascript
const updatedUser = {
    ...user,
    age: 21
};
```

---

## Object.assign()

```javascript
const copy =
    Object.assign(
        {},
        user
    );
```

---

# 11. Dates

## Date Object

```javascript
const now =
    new Date();
```

---

## Specific Date

```javascript
const date =
    new Date(
        "2026-09-20T12:00:00"
    );
```

---

## Date Methods

```javascript
date.getFullYear();
date.getMonth();
date.getDate();
date.getDay();
date.getHours();
date.getMinutes();
date.getSeconds();
```

Remember:

```text
getMonth()
```

returns `0` for January through `11` for December.

---

## Formatting Dates

```javascript
const formatted =
    date.toLocaleDateString();
```

---

# 12. DOM

## Select by ID

```javascript
const element =
    document.getElementById(
        "title"
    );
```

---

## querySelector()

```javascript
const button =
    document.querySelector(
        ".btn"
    );
```

Returns the first matching element.

---

## querySelectorAll()

```javascript
const items =
    document.querySelectorAll(
        ".item"
    );
```

---

## Change HTML

```javascript
element.innerHTML =
    "<strong>Hello</strong>";
```

---

## Change Text

```javascript
element.textContent =
    "Hello";
```

---

## Change CSS

```javascript
element.style.fontSize =
    "24px";
```

---

## Attributes

```javascript
element.setAttribute(
    "title",
    "Hello"
);

element.getAttribute(
    "title"
);

element.removeAttribute(
    "title"
);
```

---

## classList

```javascript
element.classList.add(
    "active"
);

element.classList.remove(
    "active"
);

element.classList.toggle(
    "active"
);

element.classList.contains(
    "active"
);
```

---

## Create Element

```javascript
const paragraph =
    document.createElement(
        "p"
    );

paragraph.textContent =
    "Hello";

document.body.appendChild(
    paragraph
);
```

---

## Remove Element

```javascript
element.remove();
```

---

## DOM Navigation

```javascript
element.parentElement;
element.children;
element.firstElementChild;
element.lastElementChild;
element.nextElementSibling;
element.previousElementSibling;
```

---

# 13. Events

## addEventListener()

```javascript
button.addEventListener(
    "click",
    () => {
        console.log(
            "Clicked"
        );
    }
);
```

---

## Mouse Events

```text
click
dblclick
mouseenter
mouseleave
mousedown
mouseup
mousemove
```

---

## Keyboard Events

```text
keydown
keyup
```

Example:

```javascript
document.addEventListener(
    "keydown",
    (event) => {
        console.log(event.key);
    }
);
```

---

## Form Events

```text
submit
input
change
focus
blur
```

---

## Event Object

```javascript
button.addEventListener(
    "click",
    (event) => {
        console.log(
            event.target
        );
    }
);
```

---

## preventDefault()

```javascript
form.addEventListener(
    "submit",
    (event) => {
        event.preventDefault();
    }
);
```

---

## stopPropagation()

```javascript
event.stopPropagation();
```

Stops further propagation through the DOM event path.

---

# 14. Browser APIs

## Window Object

```javascript
window.innerWidth;
window.innerHeight;
```

In browsers, `window` is the global window object.

---

## setTimeout()

```javascript
setTimeout(
    () => {
        console.log(
            "Hello"
        );
    },
    1000
);
```

---

## clearTimeout()

```javascript
const timer =
    setTimeout(
        callback,
        1000
    );

clearTimeout(timer);
```

---

## setInterval()

```javascript
const interval =
    setInterval(
        () => {
            console.log(
                "Running"
            );
        },
        1000
    );
```

---

## clearInterval()

```javascript
clearInterval(interval);
```

---

## Location Object

```javascript
window.location.href;
window.location.hostname;
window.location.pathname;
```

---

## History Object

```javascript
history.back();
history.forward();
history.go(-1);
```

---

## Navigator Object

```javascript
navigator.language;
navigator.userAgent;
navigator.onLine;
```

Availability and reliability vary by browser/API.

---

# 15. JSON & Storage

## JSON

JavaScript object:

```javascript
const user = {
    name: "Ali",
    age: 20
};
```

Convert to JSON:

```javascript
const json =
    JSON.stringify(user);
```

Convert back:

```javascript
const object =
    JSON.parse(json);
```

---

## localStorage

Store:

```javascript
localStorage.setItem(
    "name",
    "Ali"
);
```

Read:

```javascript
const name =
    localStorage.getItem(
        "name"
    );
```

Remove:

```javascript
localStorage.removeItem(
    "name"
);
```

Clear:

```javascript
localStorage.clear();
```

Values are stored as strings.

---

## Store Object

```javascript
localStorage.setItem(
    "user",
    JSON.stringify(user)
);
```

Read object:

```javascript
const savedUser =
    JSON.parse(
        localStorage.getItem(
            "user"
        )
    );
```

---

## sessionStorage

```javascript
sessionStorage.setItem(
    "token",
    "abc123"
);

sessionStorage.getItem(
    "token"
);

sessionStorage.removeItem(
    "token"
);
```

Data normally lasts for the page's browser session.

---

# 16. Modern JavaScript (ES6+)

## let vs const

Use:

```javascript
const name = "Ali";
```

when reassignment is not needed.

Use:

```javascript
let score = 10;

score = 20;
```

when reassignment is needed.

---

## Destructuring

Array:

```javascript
const [
    first,
    second
] = [10, 20];
```

Object:

```javascript
const {
    name,
    age
} = user;
```

---

## Spread Operator

Arrays:

```javascript
const combined = [
    ...first,
    ...second
];
```

Objects:

```javascript
const updated = {
    ...user,
    active: true
};
```

---

## Rest Operator

```javascript
function sum(
    ...numbers
) {
    return numbers.reduce(
        (total, number) =>
            total + number,
        0
    );
}
```

---

## Modules

Export:

```javascript
export function add(
    a,
    b
) {
    return a + b;
}
```

Import:

```javascript
import {
    add
} from "./math.js";
```

Browser:

```html
<script
    type="module"
    src="app.js">
</script>
```

---

## Promise

```javascript
const promise =
    new Promise(
        (
            resolve,
            reject
        ) => {
            const success = true;

            if (success) {
                resolve("Done");
            } else {
                reject(
                    new Error(
                        "Failed"
                    )
                );
            }
        }
    );
```

---

## Promise Handling

```javascript
promise
    .then((result) => {
        console.log(result);
    })
    .catch((error) => {
        console.error(error);
    })
    .finally(() => {
        console.log(
            "Finished"
        );
    });
```

---

## async Function

```javascript
async function loadData() {
    return "Done";
}
```

An `async` function returns a promise.

---

## await

```javascript
async function loadData() {
    const result =
        await promise;

    console.log(result);
}
```

---

## Fetch API

```javascript
async function loadUsers() {
    const response =
        await fetch(
            "https://example.com/users"
        );

    if (!response.ok) {
        throw new Error(
            `HTTP error: ${response.status}`
        );
    }

    const data =
        await response.json();

    return data;
}
```

---

# 17. Error Handling & OOP

## try...catch

```javascript
try {
    riskyOperation();
} catch (error) {
    console.error(
        error.message
    );
}
```

---

## finally

```javascript
try {
    console.log("Try");
} catch (error) {
    console.error(error);
} finally {
    console.log(
        "Always runs"
    );
}
```

---

## throw

```javascript
function divide(a, b) {
    if (b === 0) {
        throw new Error(
            "Cannot divide by zero"
        );
    }

    return a / b;
}
```

---

## JavaScript Class

```javascript
class Student {
    constructor(
        name,
        age
    ) {
        this.name = name;
        this.age = age;
    }

    greet() {
        console.log(
            `Hello ${this.name}`
        );
    }
}
```

---

## Create Object

```javascript
const student =
    new Student(
        "Ali",
        20
    );
```

---

## Constructor Method

```javascript
class User {
    constructor(name) {
        this.name = name;
    }
}
```

---

## Inheritance

```javascript
class Animal {
    speak() {
        console.log(
            "Animal sound"
        );
    }
}

class Dog extends Animal {
    speak() {
        console.log(
            "Bark"
        );
    }
}
```

---

## super

```javascript
class Person {
    constructor(name) {
        this.name = name;
    }
}

class Student extends Person {
    constructor(
        name,
        course
    ) {
        super(name);

        this.course = course;
    }
}
```

---

## Static Method

```javascript
class MathHelper {
    static add(a, b) {
        return a + b;
    }
}

MathHelper.add(
    10,
    20
);
```

---

# ⚡ Frequently Used JavaScript Patterns

## Safe Default Value

```javascript
const name =
    userName ?? "Guest";
```

---

## Safe Nested Property

```javascript
const city =
    user?.address?.city;
```

---

## Copy Array

```javascript
const copy = [
    ...numbers
];
```

---

## Copy Object

```javascript
const copy = {
    ...user
};
```

---

## Remove Duplicates

```javascript
const unique =
    [...new Set(numbers)];
```

---

## Find by ID

```javascript
const user =
    users.find(
        (item) =>
            item.id === targetId
    );
```

---

## Filter Array

```javascript
const activeUsers =
    users.filter(
        (user) =>
            user.active
    );
```

---

## Transform Array

```javascript
const names =
    users.map(
        (user) =>
            user.name
    );
```

---

## Sum Numbers

```javascript
const total =
    numbers.reduce(
        (sum, number) =>
            sum + number,
        0
    );
```

---

## DOM Ready

With a deferred script:

```html
<script
    src="app.js"
    defer>
</script>
```

`defer` allows HTML parsing to continue before the script executes.

---

# 🧠 JavaScript Equality Quick Reference

```text
===  Strict equality
!==  Strict inequality

==   Loose equality with coercion
!=   Loose inequality with coercion
```

Prefer `===` and `!==` in most application code.

---

# 🧠 Array Method Quick Reference

```text
push()      Add to end
pop()       Remove from end
shift()     Remove from start
unshift()   Add to start
splice()    Insert/remove items
slice()     Copy part of array
map()       Transform items
filter()    Keep matching items
find()      Find first matching item
reduce()    Combine values
some()      Check if any match
every()     Check if all match
includes()  Check for value
```

---

# 🧠 DOM Quick Reference

```javascript
document.getElementById("id");

document.querySelector(
    ".class"
);

document.querySelectorAll(
    ".item"
);

document.createElement(
    "div"
);

element.textContent =
    "Hello";

element.classList.add(
    "active"
);

element.addEventListener(
    "click",
    handler
);
```

---

# 🎯 JavaScript Learning Flow

```text
JavaScript Basics
       ↓
Variables & Types
       ↓
Operators
       ↓
Strings & Numbers
       ↓
Conditions
       ↓
Loops
       ↓
Functions
       ↓
Arrays
       ↓
Objects
       ↓
DOM
       ↓
Events
       ↓
Browser APIs
       ↓
JSON & Storage
       ↓
Modern JavaScript
       ↓
Promises
       ↓
async / await
       ↓
Fetch API
       ↓
Error Handling
       ↓
Classes & OOP
```

---

# 📘 Complete JavaScript Roadmap

For the complete topic-by-topic learning sequence:

## [Open the JavaScript Learning Roadmap →](../roadmaps/javascript-roadmap.md)

---

# 🌐 Learn JavaScript With A1Lab

A1Lab combines:

- 🎓 Structured JavaScript lessons
- 💻 Interactive coding
- 🧠 Visual explanations
- 🧪 Practical examples
- 📝 Practice activities
- ❓ MCQs and learning checks
- 💬 Developer discussions

<div align="center">

<a href="https://a1lab.tech/javascript/introduction">
  <img
    src="https://img.shields.io/badge/Start_JavaScript_Course-A1Lab-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"
    alt="Start JavaScript Course on A1Lab"
  />
</a>

<br><br>

## [Explore A1Lab →](https://a1lab.tech)

</div>

---

# 👨‍💻 Maintainer

**Muhammad Ahmad**

Founder & Full-Stack Developer behind
**[A1Lab](https://a1lab.tech)**

GitHub:

[mahmad786-cloud](https://github.com/mahmad786-cloud)

---

<div align="center">

# 🟨 Learn. Code. Build.

### JavaScript quick reference from fundamentals to modern web development.

**A1Lab Learning Resources**

### [Start Learning JavaScript →](https://a1lab.tech/javascript/introduction)

</div>
