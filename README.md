2025 Advanced JavaScript Interview Q&A
--------------------------------------

Q-1: Fix This Code
------------------
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

Q-2: What is diff b/w let and var in javascript?
---------------

Ans-: var is a function-scoped and let is a blocked scopeed. Variable decleare with the var and hoisted to the top of their function scope. while variable decleare with the let are not hoisted.


Q-3: Fix this code
----------------
let arr=[1,2,3];
arr.push(4);
console.log(arr);

Ans-: This code already corrected and this console print [1, 2, 3, 4]
       push add 4 to the  end of array.

Q-4: What is function decleriation in javascript?
--------------------------------------------------

Ans-: A function decleriation is way to defined function in javascript using "Function" keyword followed by a function name a set of parantheses. and st of curly brackets.

    function greet(name) {
      console.log("Hello, " + name + "!");
    }
    
    greet("Satendra Kumar");  // Output: Hello, Satendra Kumar!

Q-5: Fix the Code
-----------------
let arr = [1,2,3];
for (let i =0; i< arr.length; i++){
    console.log(arr[i]);
}

Ans-: This code is already correct and console print 
      1
      2
      3
       
Explanation=>

arr.length → returns 3 (the total number of elements).
The for loop runs from i = 0 to i < 3.
arr[i] prints each element one by one.

Q-6: What is an array in javascript?
-------------------------------------
Ans-: An array is a data structure thar store  collection of elements. which can be an any of data type.
 Array in javascript dyanamic and can grow or srink to size if as needes.

 Multiple way create in array:

 1-: Using array literal[]

    const fruits =["Apple","Banana","Mango"];

    When to use:    
    => Ye sabse simple aur fast method hai.
    => Jab tumhe ek fixed ya normal list chahiye.
    => 99% cases me isi ka use hota hai.

2-: Using new Array() construtor

    const number = new Array(10,20,30);
    
    When to use:
    => Rarely use hota hai.
    => Useful jab tumhe fixed length empty array banana ho.


3-: using Array.of()
 
    const arr = Array.of(5);
    console.log(arra); // [5]
    
    When to use:
    => Jab tumhe number se hi array banana ho, aur new Array(5) jaise confusion avoid karna ho.

4-: Using Array.from()

    const arr = Array.from("HELLO");
    console.log(arra); //['H','E','L','L','O']

    When to use:
    => Jab tumhe iterable (string, Set, Map, NodeList, etc.) se array banana ho.
    => Useful in DOM, string conversion, or unique list making.


Q-7: Fix this code
------------------

    function greet(name){
        console.log(`Hello, ${name}!`);
    }
    greet("Satendra");

Ans-: this code already correct and print 'Hello, Satendra!'

Q-8: What is this keyword in javasrcipt?
-------------------------------------------
Ans-: The this keyword refers to the object that currently excuting the code. Its value depend on how and where the function is called.

Example: 

1 =>  Global context

      console.log(this); //In browserc-> window object

2 =>  Inside a object method

      const person ={
        name: "satendra",
        greet: function(){
            console.log(this.name);
        }
      }
      person.greet(); //Satendra

3 => Inside a regular function

     function greet(){
        console.log(this);
     }
     greet();// strict mode: undefined  || Non strict mode : window

4 => Inside a cunstrutor

     function user(name){
          this.name= name;
     }
     const u1 =new user("satendra");
    console.log(u1.name); //Satendra

5 => Inside an arrow function

     const obj ={
        name: "satendra",
        greet:()=>{
            console.log(this.name);
        }
     }
     obj.greet();   //undefined
  
    Arrow functions apna khud ka this nahi banate —
    wo apne outer (parent) scope se this inherit karte hain.

Q-9: What is an object in javascript?
-------------------------------------
Ans-: An object is a collection of key-value pairs. where the key are string and value can be any data type. Object in javascript are dyanamic and properties removed or added in runtime.

Multiple Way create an object:

1 => Using Object literals:

    const car ={name:"Tesla", model:"s"};

    When to use:
    => Jab simple data store karna ho.
    => Static / small object chahiye (ek hi object banaana hai).
    => Most common and easiest way.

2 => Using new object():

    const car = new object();
    car.brand="tata";
    car.color="red";

     When to use:
    => Bahut rarely use hota hai.
    => Same result deta hai jaise {}, but zyada verbose hai.
    => Useful only jab dynamically properties assign karni ho after object creation.

3 => Using Constructor function

    function persion(name,age){
        this.name=name;
        this.age=age;
    }
    const p1 =new person("satendra",25);

    When to use:
    => Jab multiple similar objects banana ho.
    => Function ke andar this har naye object ko represent karta hai.
    => Reusable template jaisa kaam karta hai.

 4 => Using class (ES6)

    class person{
        constructor(name,age){
            this.name=name;
            this.age=age;
        }
    }
    const p2 = new person("Rocky", 25);

    When to use:
    => Jab modern, OOP-style code likhna ho. 
    => Reusable structure banana ho (like blueprint for users, products, etc.) 
    => Class me methods aur properties easily manage hote hain.

Q-10: Fix this code
 
    function double(arr){
        arr.foreach(function(val){
          val*2;
        });
        return arr;
    }
    console.log(double([1,2,3])); // [1,2,3]
    
What actually happens =>

=> You call double([1, 2, 3]).
=> Inside the function, you loop through each element (val) with forEach.
=> But inside the forEach, you do val * 2 — and you don’t store or return that result anywhere.
=> forEach also doesn’t return a new array — it just runs a function for each element.
=> So the array arr never changes.

    function double(arr){
       arr.map(function(val){
           return val*2;
       })
    }
    console.log(double([1,2,3]));  //[ 2,4,6]
