# scope-hoisting-js
blog entry about variable scope and hoisting in JS

What is variable scope and hoisting in JavaScript?
=========================
Scope is the set of variables you have access to.

Variable Scope (JavaScript) JavaScript has two scopes: global and local. A variable that is declared outside a function definition is a global variable, and its value is accessible and modifiable throughout your program.  Remember that global variables are evil, or so they say.

JavaScript Scope
---
In JavaScript, scope is the set of variables, objects, and functions you have access to. It is important to note that objectss and functions are also variables in JS.  Also, the scope changes inside functions.

Local JavaScript Variables
---
Variables declared within a JavaScript function, become *local* to the function.

Local variables have local scope, meaning that they can only be accessed within the function.

For example

    // code here can not use dogName
    
    function myFunction() {
        var dogName = "Fluffy";
    
        // code here can use dogName
    
    }

