Q-1: Fix This Code
let x = 5;
if (x = 5) {
  console.log(x);
}

Problem
----------
The single equal sign = is an assignment operator, not a comparison operator.
So, x = 5 assigns the value 5 to x, making the condition always true.

Fixed Code
----------
let x = 5;
if (x === 5) {
  console.log(x);
}

Output
-------
5

Explanation
-----------
Operator	Meaning	Description
=	Assignment	Assigns value to variable
==	Comparison	Compares values only
===	Strict Comparison	Compares value + type

✔ Using === ensures correct comparison and prints 5 to the console.

Summary
----------
❌ Wrong: if (x = 5) → assigns value

✅ Correct: if (x === 5) → compares value & type