## **1️. Function Scope (ফাংশনের সীমা বা এলাকা)**

#####  Definition:

**Scope** মানে হলো — কোডের কোন অংশ থেকে কোন ভেরিয়েবল বা ফাংশন অ্যাক্সেস করা যাবে তা নির্ধারণ করে। JavaScript-এ ৩ ধরণের Scope আছে :

|Scope Type|ব্যাখ্যা|উদাহরণ|
|---|---|---|
|**Global Scope**|function এর বাইরে declare করা variable যেটা সব জায়গা থেকে access করা যায়|`let x = 10;`|
|**Local (Function) Scope**|function এর ভিতরে declare করা variable শুধুমাত্র সেই function এর ভিতরে ব্যবহারযোগ্য|`function test(){ let y = 5; }`|
|**Block Scope (ES6)**|`{}` ব্লকের ভিতরে declare করা let/const variable শুধুমাত্র সেই ব্লকের ভিতরে ব্যবহারযোগ্য|`if(true){ let z=20; }`|

---

##### Examples:

```javascript
let x = 10; // Global variable

function show() {
  let y = 5; // Local variable
  console.log(x); // Access global variable ✅
  console.log(y); // Access local variable ✅
}

show();
console.log(x); // ✅ Works
console.log(y); // ❌ Error: y is not defined
```

##### ⚡ Best Practice:

- function-এর বাইরে var ব্যবহার না করাই ভালো (global pollution তৈরি হয়)
- let/const ব্যবহার করা উত্তম কারণ এগুলো block-scope তৈরি করে

---

## **2. Function Hoisting (ফাংশন উপরে তোলা)**

##### Definition:

**Hoisting** হলো JavaScript-এর একটি process যেখানে function declarations এবং variable declarations কোড রান হওয়ার আগে উপরে “তোলা” হয়।

---

##### Example (works):

```javascript
greet(); // ✅ Works even before declaration

function greet() {
  console.log("Hello!");
}
```

**Explanation:**  
`function greet()` পুরো function definition-সহ উপরে উঠে যায়।

---

##### Example (doesn’t work with expression) ⚠️:

```javascript
sayHello(); // ❌ ReferenceError

let sayHello = function() {
  console.log("Hi!");
};
```

> Function Expression কেবল declaration পর্যন্ত hoist হয়, definition নয়।

---

##### Best Practice ⚡:

- Function Declaration ব্যবহার করলে hoisting সমস্যা হয় না।
- Function Expression ব্যবহার করলে সর্বদা আগে define করে পরে কল করতে হবে।

---

## **3️. Parameter vs Argument**

|বিষয়|ব্যাখ্যা|উদাহরণ|
|---|---|---|
|**Parameter**|function এর ভিতরে variable হিসেবে define করা placeholder|`function add(a, b)` → এখানে a,b হলো parameter|
|**Argument**|function call করার সময় পাঠানো মান (value)|`add(5, 10)` → এখানে 5,10 হলো argument|

---

##### Examples:

```javascript
function add(a, b) { // parameters
  console.log(a + b);
}

add(10, 20); // arguments
```

**Output:** `30`

---

##### Error Example ⚠️:

```javascript
function greet(name) {
  console.log("Hello " + name);
}

greet(); // Output: Hello undefined ❌ কারণ argument দেওয়া হয়নি
```

---

##### Best Practice ⚡:

- যদি argument না দেওয়া হয়, তাহলে default parameter ব্যবহার করা উচিত।
- parameter ও argument সংখ্যার পার্থক্য থাকলে সমস্যা হতে পারে (undefined)।

---

## **4️. Default Parameter**

##### Definition:

Function parameter-এর জন্য ডিফল্ট মান নির্ধারণ করা যায়, যাতে argument না দিলেও error না হয়।

---

##### Examples:

```javascript
function greet(name = "Guest") {
  console.log("Hello, " + name);
}

greet("Saiful"); // Output: Hello, Saiful
greet();         // Output: Hello, Guest
```

---

##### Error Example ⚠️:

```javascript
function greet(name) {
  console.log("Hello, " + name);
}

greet(); // Output: Hello, undefined ❌
```

---

##### Best Practice ⚡:

- Optional parameter এর ক্ষেত্রে default value ব্যবহার করা উচিত।
- default parameter সবসময় শেষে রাখা ভালো (যাতে আগে argument miss না হয়)।

---

## **5️. Return Statement**

##### Definition:

`return` keyword ফাংশনের কাজ শেষ করে একটি মান (value) caller-এর কাছে ফেরত পাঠায়।

---

##### Examples:

```javascript
function add(a, b) {
  return a + b;
}

let result = add(5, 3);
console.log(result); // Output: 8
```

---

##### Important Notes ⚠️:

1. `return` এর পরে কোনো কোড থাকলে তা execute হয় না।
2. `return` ছাড়া function কল করলে undefined ফেরত দেয়।

---

##### Error Example ⚠️:

```javascript
function test() {
  console.log("Before return");
  return;
  console.log("After return"); // ❌ Never executes
}
```

---

##### Best Practice ⚡:

- `return` ব্যবহার করলে output value সবসময় variable এ ধরে ব্যবহার করা ভালো।
- যেসব function কিছু কাজ করে কিন্তু output দেয় না (যেমন console.log), তাদের void function বলা হয়।

---

## **Summary Table:**

|বিষয়|সংক্ষিপ্ত ব্যাখ্যা|উদাহরণ|
|---|---|---|
|**Scope**|ভেরিয়েবল কোথা থেকে access করা যাবে|local, global|
|**Hoisting**|JS function ও variable কে execution এর আগে উপরে তোলে|Declaration only|
|**Parameter**|Function এর ভিতরের placeholder variable|`function test(a,b)`|
|**Argument**|Function call করার সময় পাঠানো মান|`test(10,20)`|
|**Default Parameter**|Argument না দিলে fallback মান|`function test(a=5)`|
|**Return**|Function থেকে মান ফেরত দেয়|`return a + b;`|

---
