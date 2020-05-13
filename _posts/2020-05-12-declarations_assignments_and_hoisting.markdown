---
layout: post
title:      "Declarations, Assignments, and Hoisting"
date:       2020-05-13 01:53:05 +0000
permalink:  declarations_assignments_and_hoisting
---

When JavaScript runs code, it runs in two separate phases: the compiling phase and the execution phase.

In the compiling phase, JavaScript searches the file for variables and saves them to memory. After the compiling phase is over, it then runs through the execution phase. In the execution phase, JavaScript reads the code line by line, executing each line in order. 

```
function returnNum () {
   let num;
   num = 4;
   return num;
}
```

Running `returnNum()` from the console will return the number 4. Simple.

The first line of the function body is a declaration. This is letting JavaScript know that there's a variable I want to be called `num` so save it for later because I'm going to need it. In the compiling phase, JavaScript finds this variable and allocates it some memory space. Since that is the only variable declaration, the compiling phase ends and we step into the execution phase.

The execution phase is self explanatory: it's just JavaScript executing lines of code. It starts at the top, reads left to right, then executes one line at a time. My variable `num` has already been saved and there are no other variables to save, so JS moves on to the next line. On the next line, I tell JavaScript that there is a variable called `num` somewhere in here and I want it assigned to the number 4. JavaScript executes this line and then moves on.

On the last line, when JavaScript executes, it finds that variable I told it about, checks whatever value it holds, and then returns to me that value. One of the most important fundamentals of JavaScript to remember is that it runs in two separate phases. It hoists variable *declarations* to the top of the scope, but not their actual *values*. It's similar to Order of Operations in Math. 

Please Excuse My Dear Aunt Sally (or PEMDAS) is something we all learn in order to properly solve complex mathematical equations. You start with reducing at the parentheses, then the exponents, then multiplication, division, addition, and subtraction, resepectively. Order of Operations in JavaScript and programming in general is just as important. If I were to restructure `returnNum`:

```
function returnNum () {
  let num;
  return num;
	num = 4;
}
	```
	
My return value has now changed to `undefined`. Why? Because my variable got hoisted. Additionally, this is **valid JavaScript code.** JavaScript won't throw an error, it's simply doing what I asked. 

In the compiling phase, JavaScript found my variable `num`. It allocates the memory and can't find any other variables, so it moves on to execution. In execution, it reads line by line. When it reaches the next line, the value of `num` isn't *assigned*, only the variable itself has been *declared*. JS knows that the variable exists, but when it comes time to return it's value, it doesn't have a value until the *next* line. As a result, `returnNum` evaluates to `undefined`.

This can and will cause subtle bugs if not accounted for, especially in larger projects. The simplest practice that will avoid this altogether is to keep all declarations and assignments at the top of the function body. Variables can be assigned and declared on the same line:

```
function returnNum () {
   let num = 4;
   return num;
}
```

The variable still gets hoisted in the compiling phase. However, now when it reaches the return line in the execution phase, JavaScript has already assigned the variable its own memory space and a value. 


