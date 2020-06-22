This style guide should be used for all of your written code. If there is old code that you are working with that does not adhere to these standards, please modify the code to ensure that it is.

For single-line comments, always start it off with a lowercase letter and don't punctuate with a period at the end.
```js
// this is a single-line comment
```

For multi-line comments, always start off with an upper case letter, and put a period at the end.
```js
/**
 * For multi-line comments like this one, always start off with
 * an upper case letter, and put a period at the end.
 */
```

We use single-line comments to comment logical block groupings of code.
```js
// combine a person's name together
let first = "Rees";
let last = "Draminski";
let name = first + " " + last;
```

Always use descriptive variable names, use the above as an example of what not to do. First and last are not descriptive enough, they should be something like firstName and lastName.

Always use ```let``` for variable declarations, never ```var```, there are a number of reasons to do this, see [here](https://stackoverflow.com/questions/762011/whats-the-difference-between-using-let-and-var#:~:text=The%20main%20difference%20is%20the,outside%20the%20loop%20for%20example.&text=let%20allows%20you%20to%20declare,on%20which%20it%20is%20used.).
```js
let useThis = true;
var notThis = true;
```

Use ```const``` for values that will never change (constants).
```js
const WORD_BANK = [ "foo", "bar" ];
```

For variables and functions, use Camel Case.
```js
let thisIsAVariable = true;

function thisIsAFunction() {

}
```

Do not use Pascal Case or Snake Case
```js
let PascalCase = false;
let snake_case = false;
```

For constants, use all upper case snake case. This helps you know what is a constant, and what it not when you are reading code that is far away from the constant declaration.
```js
const THIS_IS_A_CONSTANT = true;
```

Always use semicolons at the end of lines.
```js
console.log("This is okay.");
console.log("This is not okay.")
```

When defining an array or JavaScript object, put a space after the first and before the last bracket or curly brace. If the definition can fit on one line (less than 80 characters), then do it on one line. Otherwise, put one property/entry on a line.
```js
// like this with arrays
let words = [ "foo", "bar" ];

// and this for objects
let rees = { name: "Rees" };

// pretend this is a super long array
let longArray = [
    500,
    501,
    502,
    503
]

// pretend this is an object with a lot of properties
let html = {
    "tag": "p",
    "tag": "ul"
}
```

Do not use trailing commas in arrays and JavaScript objects.
```js
// do this
let arr = [ 1, 2, 3 ];

// do not do this
let arr = [ 1, 2, 3, ];

// this
let obj = { "name": "foo", age: 40 };

// not this
let obj = { "name": "foo", age: 40, };
```

Comment each function with a description of what the function does, and the parameter names and types, and a return variable name and return type if applicable. [Visual Studio Code](https://code.visualstudio.com/) will help you do this automatically, so use it for coding if you think it will be a hassle to remember.
```js
/**
 * Add two numbers together, and return the result.
 * @param {Number} a 
 * @param {Number} b 
 * @returns {Number} c
 */
function addTwoNumbers(a, b) {
    let c = a + b;

    return c;
}
```

Do not use magic numbers or strings.
```js
// meatloaf is my favorite food, but you wouldn't know that with a magic string
if (food == "meatloaf") {
  console.log("Yeah!");
}

// use constants to define and provide context to magic strings
const MY_FAVORITE_FOOD = "meatloaf";

if (food == MY_FAVORITE_FOOD) {
  console.log("Yeah!");
}
```

Always use curly braces for conditionals/loops, even if it is only one line.
```js
// don't do this
if (true)
  console.log("Foo");
  
// do this
if (true) {
  console.log("Bar");
}

// and this
while (true) {
  console.log("Baz");
}
```

Use arrow functions whenever possible when creating anonymous functions. Use the "concise arrow body" whenever possible, which is when you have one line, so you are able to omit the curly braces.
```js
// don't do this
document.getElementById("submit").addEventListener("click", function() {
    console.log("Clicked!");
});

// do this
document.getElementById("submit").addEventListener("click", () => console.log("Clicked!"));

// if two lines
let clickCount = 0;
document.getElementById("submit").addEventListener("click", () => {
    clickCount++;
    
    console.log("Clicked!");
});
```
