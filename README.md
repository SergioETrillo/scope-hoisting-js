What is variable scope and hoisting in JavaScript?
=========================

Keyword | Meaning
------------------------- | -------------
Variable | A storage location
Function | Block of code designed to perform a particular task
Scope | Where a variable can be accessed
Local | Accessible locally (within a function)
Global | Accessible globally (within the program)
Hoisted | Bringing a variable to the top
Runtime | Virtual machine which interprets and executes code


Scope
--
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

This gives us the ability to use variables with the same names in other functions, as they are not globally known. 

Global JavaScript Variables
--
Any variable that is not declared within a function is global.

A global variable has access to all scripts and functions.

For example

    var dogName = "Fluff";
    
    // code here can use dogName
    
    function myFunction() {
    
        // code here can use dogName 
    
    }


Function arguments (parameters) work as local variables inside functions.

Automatically Global
--
Assigning a value to a variable that has not been declared before will create that variable as global.

For example
// code here can use dogName

function myFunction() {
    dogName = "Fluff";

    // code here can use fullName

}
In order to make a variable local, you need to use the keyword `var`

A day in the life of JS Variables
--

A JavaScript variable is born when it is declared.
Local variables die when the function is completed.
Global variables die when you close the page or the JS program ends.

Global Variables in HTML
--
With JavaScript, the global scope is the complete JavaScript environment.

In HTML, the global scope is the window object:  All global variables belong to the window object.

For example:

    // code here can use window.dogName
    
    function myFunction() {
        dogName = "Fluff";
    }

Hoistering
--
*What is that?*

Hoisting is JavaScript's default behaviour of moving all declarations to the top of the current scope (to the top of the current script or the current function).
*What does it mean?*

Let's consider the following example:

    var text= 'my text'; 
      
    (function() { 
      alert(text); // undefined Whaaat??? JS is insane!!!!
      var text = 'local text'; 
    })();

At first sight, you might expect that when running the function an alert of "local text" would pop up. 
**Wrong.**

*How does really work?*

In JS, variables are "hoisted" within the current scope, to the top of the scope.  But, only the variable declaration is hoisted.  The initialisation is not!

*Sorry, can you explain it like if I was 5?*

Consider the example again:


    (function() { 
      alert(text); // undefined Whaaat??? JS is insane!!!!
      var text = 'local text'; 
    })();

In the hoisting, JS does the following:

    (function() { 
	  var text;
      alert(text); // undefined Whaaat??? JS is insane!!!!
      text = 'local text'; 
    })();

Does it make more sense now?  the text variable has been hoisted to the top of the function scope, but only the declaration of the variable (i.e. `var text;` ). At this stage, text is undefined. Then we execute alert(text), but text is currently undefined! We only assign the value 'local text' to our variable after the alert is trigerred.  Too late!
