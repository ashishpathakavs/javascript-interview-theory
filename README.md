<h1 align="center">JavaScript Interview Theory</h1>
<h4 align="center">Frequently Asked Theoretical Question in Javascript</h4>

## Question List
<ol>
  <li>Difference between var, let and const</li>
  <li>What is hoisting?</li>
  <li>What is closure? Expalin with example</li>
  <li>What is currying?</li>
  <li>Explain anonymous function, IIFE, function declaration, function expression</li>
  <li>What is first class function? aka First Class Citizens</li>
  <li>What is callback function?</li>
  <li>What is benefit of callback function over normal function?</li>
  <li>What is Higher Order Function?</li>
  <li>What is Pure Function?</li>
  <li>What is generator function?</li>
  <li>map vs forEach</li>
  <li>null vs undefined</li>
  <li>Explain call, apply and bind</li>
  <li>What is Promise in javascript? How it is created and how it consumed, expalin eith simple example?</li>
  <li>What is event loop?</li>
  <li>What is event bubbling?</li>
  <li>Explain debounce and throttle</li>
  <li>Shallow copy vs deep copy</li>
  <li>slice vs splice method</li>
  <li>What is this keyword in javascript?</li>
  <li>What is event Propagation? How to stop event from propagation?</li>
  <li>What is Prototype and prototypical inheritance?</li>
</ol>

## Answers

<details>
  <summary><b>1. Difference between var, let and const</b></summary>

- **Scope**
    
    **va**r: Variables declared with var can have a **global** or functional scope. Global scope is for variables declared outside functions, while functional scope is for variables declared inside functions.
    
    **let, const:** Variables declared with let can have  **block scope.**
    
- **Redeclaration and reassignment**:
    
    var: Variables declared with var can be redeclared and reassigned.
    
    ```jsx
    var name = "shiv";
    var name = "mahesh"
    ```
    
    **let**: can be reassigned to other values, but they cannot be redeclared.
    
    ```jsx
    let name = "shiv";
    name = "mahesh";
    ```
    
    **const**: can not be reassigned or redeclared.
- **Hoisting:**
    
    **var:** Variables declared with var are hoisted to the top of their global or local scope with default value of **undefined**, which makes them accessible before their line of declaration.
    
    **let**: Variables declared with let are hoisted to the top of their global, local, or block scope, but their hoisting is a little different from the one with var.
    
    But, let variables are hoisted without a default initialisation. So when you try to access such variables, instead of getting **undefined**, or **variable is not defined** error, you get **cannot access variable before       initialisation**.
</details>

<details>
  <summary><b>2. What is hoisting?</b></summary>
  Process whereby the interpreter appears to have moved the declaration of functions or variables to the top of their scope, prior to execution of the code.
  
  **var:** Variables declared with var are hoisted to the top of their global or local scope with default value of **undefined**, which makes them accessible before their line of declaration.

**let**: Variables declared with let are hoisted to the top of their global, local, or block scope, but their hoisting is a little different from the one with var.

**Function declarion** Functions declarations are also hoisted up.

But, let variables are hoisted without a default initialisation. So when you try to access such variables, instead of getting **undefined**, or **variable is not defined** error, you get **cannot access variable before initialisation**.
</details>

<details>
  <summary><b>3. What is closure? Expalin with example</b></summary>
  A function along with reference to its outer environment together forms a closure. Or in other words, A Closure is a combination of a function and its lexical scope bundled together.
  
  When a function is returned from another function, that return function does not only have function but also have the outer variables access.
  ```jsx
  function greet() {
    let name = 'John';
    function displayName() {
        // accessing name variable
        return 'Hi' + ' ' + name;
    }
    return displayName;
}
const g1 = greet();
console.log(g1());         // Hi John
```
</details>

<details>
  <summary><b>4. What is currying?</b></summary>

  Currying is a technique used in functional programming that allows you to transform a function with multiple arguments into a sequence of functions, each taking a single argument.

sum(1, 2, 3) => sum(1)(2)(3)

sum(1,2,3)
```jsx
const sum = (a, b, c) => { 
	return a+b+c
}
```
 sum(1)(2)(3)
 ```jsx
const sum = (a) => {
	return (b) => {
		return (c) => {
		   return a+b+c
		}
	}
}
```

```jsx
// Infinie currying

add(5)(6)(2)(3)(4)(5).....()

function add(a){
    return function(b) {
        if(b){
            return add(a+b);
        }
        return a;
    }
}
```

</details>

<details>
  <summary><b>5. Explain anonymous function, IIFE, function declaration, function expression</b></summary>

```jsx
//Anonymous function:
function () {
let x = "Hello!!";
});


//IIFE: Anonymous function can be immediately invoked
(function () {
  let x = "Hello!!";  // I will invoke myself
})();


//Function declaration
function myFunction(a, b) {
	return a * b;
}

//Function expression: Anonymous function stored in a variable.
const x = function (a, b) {return a * b};
```
</details>
