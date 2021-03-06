# ["Up & Going" (Book 1)](https://github.com/getify/You-Dont-Know-JS/blob/master/up%20&%20going/README.md#you-dont-know-js-up--going)
# [Table of Contents](https://github.com/getify/You-Dont-Know-JS/blob/master/up%20%26%20going/toc.md)
# [Foreword](https://github.com/getify/You-Dont-Know-JS/blob/master/up%20%26%20going/foreword.md) (by [Jenn Lukas](http://jennlukas.com/)) ✔
# [Preface](https://github.com/getify/You-Dont-Know-JS/blob/master/preface.md) ✔
# [Chapter 1: Into Programming](https://github.com/getify/You-Dont-Know-JS/blob/master/up%20%26%20going/ch1.md) ✔
## Code
- Syntax is the word for computer language
- Statements are a group of words, numbers, and operators that performs a specific task
- There are variables, literal values, and operators
- 
var a = 42;

(function IIFE(){




















})
rograms are a collection of many statments 
- This statement has 4 expressions: literal value, variable, arithmetic, assignment
```js
a = b * 2;
var a = 42;

(function IIFE(){




















})
```
- JavaScript is an interpreted language meaning it is processed each time it runs
- Other languages are compiled beforehand

## Try It Yourself
- Use developer tools in the console of your browser to practice JavaScript
- Use console.log() instead of alert() to output your results
- Try out code examples:
```js
a = 21;
b = a * 2;
console.log(b);
```
- We can also get input from the user
```js
var age = prompt('Please tell me your age:');
console.log(age);
```

## Operators
- Operators are how we perform operations on values and variables
- Notice the source value is usually to the left of the = sign
- We use "var" to declare variables
- There are many operators including:
- Assignment 
- Math 
- Compound assignment
- Increment/decrement 
- Object property access 
- Equality 
- Comparison 
- Logical

## Values & Types
- Primitive values or literals in your source code:
- String
- Number
- Boolean value

### Converting between types
- **Coercion** is a conversion between the primitive values
- There is explicit and implicit coercion

## Code Comments
- Write comments to make your code easier to read by humans
- There are single-line comments (using //) and multi-line comments (using /* and */)
- Good rules to follow:
1. Write some comments
2. Don't write more than 2 comments per line
3. Comments explain the why and how, not what

## Variables
- Holds values that can be changed over time
- There's dynamic typing (weak typing) which can hold any type of value
- There's static typing (type enforcement) which can only hold certain types of values like numbers or strings
- String() method converts values into strings and toFixed() methods converts numbers to 2 decimals
- Typical constants use capital letters (IE var TAX_RATE) but ES6 now has const to declare variables that doesn't change

## Blocks
- Blocks are when we see code inside {...}
- Typically in JS, you'll see this within if...else statements
- They do not need to end with a semicolon

## Conditionals
- Uses if...else, loops, or switch statements
- Will coerce values into Booleans

## Loops
- There are do...while, while...do, and for loops
- Difference between do...while vs while...do is that do...while tests the condition after the first iteration
- For the for loop, there is the initation, conditional, and update clauses

## Functions
- Has a name that can be called to run the code inside the function
- Functions are useful if you plan to call the code multiple times, but okay to help organize and call only once also

### Scope
- Lexical Scope is how variables have different degree of access
- A variable inside of a function can access anything outside of that function
- An inner function, nested within an outer function, can also access the variable in the outer function
```js
function
 outer() {
    var a = 1;

    function inner() {
        var b = 2; // we can access both `a` and `b` here
        console .log( a + b ); // 3
    }
    inner(); // we can only access `a` here
    
    console.log( a ); // 1
} 
outer();    
```    

## Practice
- Write a program to calculate the total price of your phone purchase.  You  will  keep  purchasing  phones  (hint:  loop!)  until  you
run out of money in your bank account. You’ll also buy accessories  for  each  phone  as  long  as  your  purchase  amount  is  below
your mental spending threshold.
- After  you’ve  calculated  your  purchase  amount,  add  in  the  tax,
then  print  out  the  calculated  purchase  amount,  properly  for‐
matted.
- Finally, check the amount against your bank account balance to
see if you can afford it or not.
- You  should  set  up  some  constants  for  the  “tax  rate,”  “phone
price,”  “accessory  price,”  and  “spending  threshold,”  as  well  as  a
variable for your “bank account balance.”
- You should define functions for calculating the tax and for formatting  the  price  with  a  “$”  and  rounding  to  two  decimal
places.
- Bonus  Challenge:
Try  to  incorporate  input  into  this  program, perhaps with the 
prompt(..) covered in “Input” on page 6. You
may prompt the user for their bank account balance, for example. Have fun and be creative!
- My code:      
```js
const taxRate = 0.053;
const phonePrice = 799;
const phoneAcc = 20;
var subtotal = "";
var total = "";
var bankBalance = prompt("What is your bank balance?");
var spendThreshold = prompt("How much are you willing to spend on your new phone?");

function calculate() {
    subtotal = phonePrice + (phonePrice * taxRate);

    var buyAcc = prompt("You total is: $" + subtotal.toFixed(2) + ". Would you like to buy a phone case? It's $20 dollars more. (Type yes or no)");

    if (buyAcc == "yes") {
        total = subtotal + phoneAcc;
        alert("Your grand total is: $" + total.toFixed(2));
    } else {
        total = subtotal;
        alert("Okay, Your grand total is: $" + total.toFixed(2));
    }

    function priceCheck() {
        if (bankBalance > total && spendThreshold > total) {
            alert("Okay, thanks for purchasing with us. Please come back again soon!");
        } else if (bankBalance > total && spendThreshold < total) {
            alert("Sorry, doesn't look like you are willing to spend $" + total.toFixed(2) + " for the phone. Your limit is: $" + spendThreshold + ".");
        } else if (bankBalance < total && spendThreshold > total) {
            alert("You got the want ($" + total + ") but you don't got the funds ($" + bankBalance + ")!");
        } else {
            alert("You are poor. You have only have $" + bankBalance + " to your name. Go home.");
        }
    }
    priceCheck();
}
calculate();    
```      
      
- The book's solution:
```js
const SPENDING_THRESHOLD = 200;
const TAX_RATE = 0.08;
const PHONE_PRICE = 99.99;
const ACCESSORY_PRICE = 9.99;

var bank_balance = 303.91;
var amount = 0;

function calculateTax(amount) {
    return amount * TAX_RATE;
}

function formatAmount(amount) {
    return "$" + amount.toFixed(2);
}

// keep buying phones while you still have money
while (amount < bank_balance) {
    // buy a new phone!
    amount = amount + PHONE_PRICE;

    // can we afford the accessory?
    if (amount < SPENDING_THRESHOLD) {
        amount = amount + ACCESSORY_PRICE;
    }
}

// don't forget to pay the government, too
amount = amount + calculateTax(amount);

console.log("Your purchase: " + formatAmount(amount)); // Your purchase: $334.76

// can you actually afford this purchase?
if (amount > bank_balance) {
    console.log(
        "You can't afford this purchase. :("
    );
} // You can't afford this purchase. :()
```
      
## Review
- You need *operators* to perform actions on.
- You need *values* and *types* to perform different kinds of actions like math on **numbers** or output with **strings**.
- You need *variables* to store data (aka *state*) during your program's execution.
- You need conditionals like **if** statements to make decisions
- You need *loops* to repeat tasks until a condition stops being true.
- You need *functions* to organize your code into logical and reusable chunks

# [Chapter 2: Into JavaScript](https://github.com/getify/You-Dont-Know-JS/blob/master/up%20%26%20going/ch2.md)
## Values & Types
- Use typeof to determine the type of value of the variable
```js
var a = 'Hello';
typeof a; // string

// Note that typeof null is an object, weird!
```
      
### Objects
- Useful to store lots of information
- Arrays and functions are thought of as subtypes of object
- can be accessed with *dot notation* (ie obj.a) or *bracket notation* (ie obj["a"])
```js
var obj = {
    a: "hello world",
    b: 42,
    c: true
};

obj.a; // "hello world"
obj.b; // 42
obj.c; // true

obj["a"] // "hello world"
obj["b"] // 42
obj["c"] // true
```
      
- However, bracket notation is useful for key/value pairs
```js
var obj = {
    a: "hello world",
    b: 42
};

var b = "a";

obj[b]; // "hello world"
ojb["b"]; // 42
``` 

### Arrays
- Holds values which are indexed by position and not by key/value pairs
- Best approach is to use arrays for numerically positioned values and use objects for named properties
```js
var arr = ]
    "hello world",
    42,
    true
];

arr[0]; // "hello world"
arr[1]; // 42
arr[2]; // true
arr.length; // 3

typeof arr; // "object"
```
      
### Functions
- Are objects but typeof will return "function"
- It can also have properties like how you would only use foo.bar in limited cases
```js
function foo() {
    return 42;
}

foo.bar = "hello world";

typeof foo; // "function"
typeof foo(); // "number"
typeof foo.bar; // "string"
```
      
### Built-In Type Methods
- There are under the hood methods that we don't need to worry about how they work
- Just know that they are there and that they function properly
```js
var a = "hello world";
var b = 3.14159;

a.length; // 11
a.toUpperCase(); // "HELLO WORLD"
b.toFixed(4); // "3.1416"
```
      
### Comparing Values
### Coercion
- Types can be explicitly and implicitly coerced
- A string like "42" can be coerced using Number() (explicit coercion)
- A string like "42" can be multiplied by a number which forces "42" the string to be coerced into a number (implicit coercion)
      
### Truthy & falsy
- A non-boolean value only follows this list if forcibly coerced into a boolean value
- Falsy list:
1. "" (empty string)
2. 0, -0, NaN (invalid number)
3. null, undefined
4. false
- Truthy list:
1. "hello"
2. 42
3. true
4. [], [1, "2", 3] (arrays)
5. {}, {a: 42} (objects)
6. functions foo() {..} (functions)

### Equality
- == checks for value equality with coercion allowed
- === checks for value equality without allowing coercion (aka strict equality)
- Many programmers swear by === but == can be useful as well
- Bang operator (!) means not
- != pairs with ==
- !== pairs with ===
```js
var a = "42";
var b = 42;

a == b; // true
a === b; // false
```
- Arrays are coered to strings by default!
```js
var a = [1,2,3];
var b = [1,2,3];
var c = "1,2,3";

a == c; // true
b == c; // true
a == b; // false
```
          
### Inequality
- We can compare numbers and strings also
- There is no strict equality here (===)
- In example 1, b < c is true because rule is with 2 strings that it follows alphabetically
```js
var a = 41;
var b = "42";
var c = "43";

a < b; // true
b < c; // true
```
- But when we compare a string and number, the string is coerced into a NaN
```js
var a = 42;
var b = "foo";

a < b; // false
a > b; // false
a == b; // false
```

## Variables
- Can be a-z, A-Z, $, 0-9, or _.
- "Reserved words" can be used as property names but not variables
1. JS keywords (for, in, if, etc.)
2. null
3. true
4. false
    
### Function Scopes
- Use var to declare a variable

### Hoisting
- When a var is conceptually "moved" to the top of its enclosing scope
- It is good practice to use hoisted function declarations to appear before its formal declaration
- So have the function foo(){} declared before calling the function foo()
```js
var a = 2;

foo();  // works because foo() declaration is "hoisted"

function foo() {
    a = 3;
    console.log(a); //3
    var a;  // declaration is "hoisted" to the top of foo()
}

console.log(a); // 2 
```
      
### Nested Scope
- You can only access variables nested inside of a function but outside of the function, the variable can't be accessed
- Always declare your variables formally with var or let, or else it might become top-level scoped variable
- So don't just use `a = 2`, use `var a = 2`
- In ES6, the **let** keyword belongs only to that individual code block
```js
function foo() {
    var a = 1;

    if (a >= 1) {
        let b = 2; // b belongs only to the if code block

        while (b < 5) {
            let c = b * 2; // c belongs only to the while code block
            b++;

            console.log(a + c);
        })
    }
}

foo();
// 5 7 9
```

## Conditionals
- Use the if...else if...else to specify conditions
- Switch is also available but make sure to use break statement
- Otherwise, the "fall through" will continue to the next case's statement
- The "conditional operator" (aka ternary operator) is more concise than if..else
```
var a = 42;
var b = (a > 41) ? "hello" : "world";
```
- The most common usage with assignment, but this is not the only case
```js
var a = 42;
var b = (a > 41) ? "hello" : "world";

// similar to:

// if (a > 41) {
//    b = "hello";
// } else {
//    b = "world";
// }
```
## Strict Mode
- `"use strict"` tightens the rules for certain behaviors 
- Can use for an entire file or just where you introduce the command
- It optimizes and makes your code more safe
- One improvement: disallowing implicit auto-global variable declartion
```js
function foo() {
    "use strict";   // turn on strict mode
    a = 1;          // `var` missing, ReferenceError
}

foo();
```

## Functions As Values
- The function itself is a value just like `42` or `[1,2,3]`
- It should be thought of as an expression, just like any other value or expression
```js
var foo = function() {  // An anonymous function
    // ..
}

var x = function bar() {    // A named function
    // ..
}
```

### Immediately Invoked Function Expressions (IIFEs)
- Functions that are invoked immediately with ()
- The outer ( .. ) surrounds the inner function (function IIFE() { .. })
- Activated immediately with the () on the end:
```js
(function IIFE() {
    console.log("Hello!");
})();
// "Hello!"
```
  
- It also creates a variable scope that won't affect the code outside of it:
```js
var a = 42;

(function IIFE(){
    var a = 10;
    console.log(a); // 10
})();

console.log(a);     // 42
```
  
- It can also have return values:
```js
var x = (function IIFE() {
    return 42;
})();

x;  // 42
```

### Closure
- We will go into more depth later
- One of the most powerful concepts in JS
- Just understand that it's a way to remember and continue to access a function's scope (its variables) even once the function has finished running
- In this instance, x is "remembered" and used for subsequent function calls:
```js
function makeAdder(x) {
    function add(y) {
        return y + x;
    };

    return add;
}

var plusOne = makeAdder(1);
var plusTen = makeAdder(10);

plusOne(3);     // 4 = 1 + 3
plusOne(41);    // 42 = 1 + 3
plusTen(13);    // 23 = 10 +13
```

### Modules
- One common usage pattern of closures
- Lets you define private implementation details that are hidden from the outside world
- Running User() creates a whole new instance of the User module each time
```js
function User() {
    var username, password;

    function doLogin(user,pw) {
        username = user;
        password = pw;

        // do the rest of the login work
    }

    var publicAPI = {
        login: doLogin
    };

    return publicAPI;
}

var fred = User();

fred.login("fred", "12Battery34!");
```
## this Keyword
- Refers to the parent object, not a function (a common misconception)
- A quick illlustration:
```js
function foo() {
    console.log(this.bar);
}

var bar = "global";

var ojb1 = {
    bar: "obj1",
    foo: foo
};

var obj2 = {
    bar: "obj2"
};

// -----
foo();          // "global"
obj1.foo();     // "obj1"
foo.call(obj2); // "obj2"
new foo();      // undefined
```
- `this` in foo() refers to the global object window in non-strict mode, would be undefined in strict mode
- Literally, `this.bar` means `window.bar`
- Notice that obj1 is an object and this would refer to obj1 object and not the window object

## Prototypes
- This concept is quite complicated but visited in chapter 4-6 of this & Object Prototypes
- Basically, it is a fallback for when a property doesn't exist when you try to reference it
- JS will automatically look at that object's internal prototype reference to find another object to find it
- This internal reference is created at the time the object is created
```js
var foo = {
    a: 42
}

// create `bar` and link it to `foo`
var bar = Object.create(foo);

bar.b = "hello world";

bar.b; // "hello world"
bar.a;  // 42 <-- delegated to `foo`
```
- The most common way this feature is used is to try to emulate/fake a "class" mechanism with "inheritance"
- Another popular pattern is "behavior delegation"
- You intentionally link objects to be able to delegate from one to the other for parts of the needed behavior

## Old & New
- How do we implement new JS technology to older browsers?
- We can use polyfilling and transpiling

### Polyfilling
- Definition: To take the definition of a newer feature and produce a piece of code that's equivalent to the behavior, but is able to run in older JS environments
- Number.isNaN(..) is a utility to provide an accurate, non-buggy check for NaN values, deprecating original isNaN(..)
```js
if (!Number.isNan) {
    Number.isNaN = function isNaN(x) {
        return x !== x;
    };
}
```
- The if statement here guards for ES6 browsers
- NaN is a value that is never equal to itself so it is the only that makes x !== x out to be true
- Not all features are fully polyfillable
- There are small deviations
- You have to be really careful with adhering to specifications when implementing a polyfill yourself
- A good source to get polyfills: [ES5-Shim](https://github.com/es-shims/es5-shim) and [ES6-Shim](https://github.com/paulmillr/es6-shim)

### Transpiling
- Definition: A tool that converts your newer code into older code equivalents. A creation from transforming + compiling
- You generally insert it into your build process along with like a code linter or minifier
  
- Why write new code to transpile to old one anyways?
1. New code is more readable and maintainable
2. New code takes advantage of browser performance optimizations
3. New code provides earlier feedback for new syntax for the JavaScript committee to fix issues
  
- An example of transpiling from an ES6 feature to older environments:
```js
function foo(a = 2) {
    console.log(a);
}

foo();      // 2
foo(42);    //42
```
- transpiles to:
```js
function foo() {
    var a = arguments[0] !== (void 0) ? arguments[0] : 2;
    console.log(a);
}
```
- Transpilers are now the standard part of JS development ecosystem and process
- Two great transpilers to choose from:
1. [Bable](https://babeljs.io/repl/) - Transpiles ES6+ into ES5
2. [Traceur](https://github.com/google/traceur-compiler) - Transpiles ES6, ES7, and beyond into ES5

## Non-JavaScript
- The most common non-JavaScript JavaScript you'll encounter is the DOM API 
- It provides a document variable that contains special methods like `getElementById(..)`, `input/output`, `alert(..)`, `console.log(..)`
```js
var el = document.getElementById("foo");
```

## Review
- Most of the concepts here were covered only on the surface
- This series will delve deeper into the language of JS

# [Chapter 3: Into YDKJS](https://github.com/getify/You-Dont-Know-JS/blob/master/up%20%26%20going/ch3.md)
## Scope & Closures
- JavaScript is a language that is compiled right before it is run or even during
- We need to understand how it interprets code based on scope
- Closures are a key fundamental concept and prevalently used with the module pattern

## this & Object Prototypes
- A common misconception is "this" refers to the function it is in
- "this" keyword is a dynamically bound keyword based on how the function is executed
- There are 4 simple rules to understand the keyword
  
- Object prototypes looks up chains for properties and closely related to "this" keyword
- A common misconception is that it is used to emulate "fake" classes and (so called "prototypal") inheritance
- A common issue related to this is "behavior delegation"

## Types & Grammar
- Many complaints are about type coercion and implicit coercion
- As most people are confused as to how it works

## Async & Performance
- Asynchrony helps the performance of our application and the critical factor for writability and maintainability
- We will see that callbacks are no longer sufficient in modern demands
- There are 2 major deficiencies of callback coding: Inversion of Control trust lost and lack of linear reason-ability
- Now we looks towards promises and generators
- Promises are a time-independent wrapper around a "future value," which lets you reason about and compose them regardless of if the value is ready or not yet
- Generators are a new most of execution for JS functions which can pause at yield points and be resumed asynchornously later
- It makes our synchronous  code to be processed asynchronously behind the scenes
- Much of the ES7 will be using these two foundations in the technology
### Other optimizations in the future
- Program parallelism with Web Workers
- Data parallelism with SIMD
- Low-level optimization techniques like ASM.js

## ES6 & Beyond
- ES6 offers many new features like:
1. Destructuring
2. Default parameter values,
3. Symbols
4. Concise methods
5. Computed properties
6. Arrow functions
7. Block scoping
8. Promises
9. Generators
10. Iterators
11. Modules
12. Proxies
13. Weakmaps

# [Appendix A: Thank You's!](https://github.com/getify/You-Dont-Know-JS/blob/master/up%20%26%20going/apA.md)