# **JavaScript Function**

---

## **Function কী? (Definition)**

**Function** হলো কোডের একটি ব্লক (block of code) যা নির্দিষ্ট কোনো কাজ (task) করার জন্য তৈরি করা হয়। Function বারবার ব্যবহার করা যায় — অর্থাৎ **“write once, use many times”**।

---

## **Function তৈরি করার উদ্দেশ্য**

- কোড পুনরায় ব্যবহার (reusability)
- কোডকে ছোট ছোট ভাগে ভাগ করা (modularity)
- কোড সহজে পড়া ও বুঝা যায় (readability)
- বারবার একই কাজ করতে হলে শুধুমাত্র function কল করা লাগে

---

## **Function এর সাধারণ কাঠামো (Syntax)**

```javascript
function functionName(parameter1, parameter2, ...) {
  // Function body
  // কোড ব্লক
}
```

**Function কল (Call):**

```javascript
functionName(argument1, argument2, ...);
```

---

## **Function Types**

| Function Type                                         | Named / Anonymous                    | Example                                                                                                                                                            |
| ----------------------------------------------------- | ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **1. Function Declaration**                           | **Named** Function                   | এখানে function এর নাম দেওয়া থাকে। যেমন:`function greet() { ... }`                                                                                                  |
| **2. Function Expression**                            | **Named / Anonymous** দুটোই হতে পারে | যদি নাম দেওয়া হয় → Named Expressionযদি নাম না দেওয়া হয় → Anonymous Expression. উদাহরণ:**Named:** `let f = function sayHi(){}`**Anonymous:** `let f = function(){}` |
| **3. Anonymous Function**                             | **Anonymous**                        | একদম নামবিহীন function। সাধারণত expression, callback, IIFE ইত্যাদিতে ব্যবহার হয়।                                                                                   |
| **4. Function with Parameters**                       | **Named** (সাধারণত)                  | সাধারণত Named function হয়। তবে চাইলে anonymous function-এও parameter থাকতে পারে।যেমন: `function(a,b){}`                                                            |
| **5. Function with Return Value**                     | **Named** (সাধারণত)                  | সাধারণত Named function, তবে anonymous function-ও return করতে পারে।                                                                                                 |
| **6. Nested Function**                                | **Named / Anonymous** উভয়ই হতে পারে  | ভিতরের function নামসহ বা নামবিহীন দুইভাবেই declare করা যায়।                                                                                                        |
| **7. Recursive Function**                             | **Named**                            | recursion এর জন্য function-এর নাম থাকা দরকার, কারণ function নিজেকেই কল করে।                                                                                        |
| **8. Immediately Invoked Function Expression (IIFE)** | **Anonymous** (সাধারণত)              | বেশিরভাগ সময় anonymous থাকে। তবে চাইলে নামও দেওয়া যায়।যেমন:Anonymous → `(function(){})();`Named → `(function greet(){})();`                                        |

---

### **1. Function Declaration (Named Function)**

##### Definition:

function keyword দিয়ে নামসহ ঘোষণা করা সাধারণ ফাংশন, যেটা hoisting সমর্থন করে।

##### Example:

```javascript
function greet() {
  console.log("Hello, World!");
}

greet(); // function call
```

##### Explanation:

- `function` → keyword
- `greet` → function name
- `{ ... }` → function body
- `greet();` → কল করলে function রান হয়

##### Error Example ⚠️:

```javascript
greet(); // ❌ Cannot access before declaration
function greet() { console.log("Hi"); }
```

(Actually এটি hoisting-এর কারণে চলবে, কিন্তু function expression হলে চলবে না।)

---

### **2. Function Expression**

##### Definition:

কোনো নামবিহীন function কে একটি ভেরিয়েবলে সংরক্ষণ করা হয়; hoisting সমর্থন করে না।

##### Example:

```javascript
let greet = function() {
  console.log("Hello, JS Learner!");
};

greet();
```

##### Explanation:

- এখানে function কে `let greet` ভেরিয়েবলে রাখা হয়েছে।
- function এর কোনো নাম নাই (anonymous function)।
- hoisting এখানে কাজ করবে না।

##### Error Example ⚠️:

```javascript
greet(); // ❌ ReferenceError
let greet = function() { console.log("Hi"); };
```

---

### **4. Anonymous Function**

##### Definition:

কোনো নাম ছাড়াই তৈরি function, সাধারণত callback বা event handler হিসেবে ব্যবহৃত হয়।

##### Example:

```javascript
setTimeout(function() {
  console.log("This runs after 2 seconds");
}, 2000);
```

##### Explanation:

- কোনো function নাম ছাড়াই সরাসরি ব্যবহার করা হয়েছে।
- সাধারণত event, callback ইত্যাদিতে ব্যবহৃত হয়।

---

### **4. Function with Parameters**

##### Definition:

এমন function যা ইনপুট হিসেবে মান (parameter) গ্রহণ করে এবং সেই মান ব্যবহার করে কাজ সম্পন্ন করে।

##### Example:

```javascript
function add(a, b) {
  console.log(a + b);
}

add(10, 5); // Output: 15
add(2);     // Output: NaN
```

##### Explanation:

- `a, b` হলো parameters
- `add(10, 5)` তে arguments পাস করা হয়েছে
- যদি কোনো parameter এর মান না দেওয়া হয় → `undefined` হয়

##### Best Practice⚡:

- ডিফল্ট মান দেয়া :

```javascript
function greet(name = "Guest") {
  console.log("Hello " + name);
}
greet(); // Output: Hello Guest
```

---

### **5. Function with Return Value**

##### Definition:

এমন function যা কাজ শেষে একটি মান (value) ফেরত দেয়, যাতে পরে ব্যবহার করা যায়।

##### Example:

```javascript
function multiply(x, y) {
  return x * y;
}

let result = multiply(4, 5);
console.log(result); // Output: 20
```

##### Explanation:

- `return` দিয়ে ফাংশন থেকে মান ফেরত দেওয়া হয়।
- return করার পরে ফাংশনের পরের কোড আর execute হয় না।

##### Error Example ⚠️:

```javascript
function test() {
  console.log("Before");
  return;
  console.log("After"); // ❌ এই অংশ চলবে না
}
```

---

### **6. Nested Function (Function Inside Function)**

##### Definition:

একটি function-এর ভিতরে আরেকটি function ঘোষণা করা হয়, যা শুধুমাত্র সেই outer function-এর মধ্যে থেকে কল করা যায়।

##### Example:

```javascript
function outer() {
  console.log("Outer Function");

  function inner() {
    console.log("Inner Function");
  }

  inner();
}

outer();
```

##### Explanation:

- এক ফাংশনের ভিতরে আরেকটি ফাংশন define করা যায়।
- inner function শুধুমাত্র outer function এর ভিতরে থেকে কল করা যায়।

---

### **8. Recursive Function (Self Calling Function)**

##### Definition:

function নিজেই নিজেকে কল করে একই ধরনের কাজ পুনরায় সম্পন্ন করে (যেমন factorial হিসাব)।

##### Example:

```javascript
function factorial(n) {
  if (n === 0) return 1;
  return n * factorial(n - 1);
}

console.log(factorial(5)); // Output: 120
```

##### Explanation:

- ফাংশন নিজেই নিজেকে কল করে (recursion)।
- প্রতিবার ছোট সমস্যায় ভেঙে কাজ সম্পন্ন করে।

⚠️ **Error Example:**

```javascript
function loop() {
  loop(); // ❌ infinite recursion → stack overflow
}
```

---

### **8. IIFE (Immediately Invoked Function Expression)**

##### Definition:

function তৈরি হওয়ার সাথে সাথেই execute হয়; সাধারণত গ্লোবাল scope দূষণ এড়াতে ব্যবহৃত হয়।

##### Example:

```javascript
(function() {
  console.log("This function runs instantly!");
})();
```

##### Explanation:

- ফাংশন ঘোষণা করেই সাথে সাথে কল করা হয়।
- সাধারণত গ্লোবাল স্কোপ দূষণ (pollution) এড়াতে ব্যবহৃত হয়।

##### Best Practice⚡:

- ছোট utility কোড বা initialization এর জন্য IIFE ভালো।
    

---

## **Function Scope & Hoisting (Basic Idea)**

- Function Declaration → Hoisting হয় (আগে কল করা গেলেও চলে)
- Function Expression → Hoisting হয় না (আগে কল করলে error)
- Function এর ভিতরের variable গুলো শুধুমাত্র সেই ফাংশনের ভিতরে কাজ করে (local scope)
- Function এর বাইরে থেকে access করলে error হয়।

**Example:**

```javascript
function test() {
  let x = 10;
  console.log(x); // ✅ Works
}
console.log(x); // ❌ ReferenceError
```

---

##  **Summary Table ✅**

|Function Type|Hoisting|Name Required|Return Possible|Use Case|
|---|---|---|---|---|
|Function Declaration|✅ Yes|✅ Yes|✅ Yes|Reusable named functions|
|Function Expression|❌ No|❌ Optional|✅ Yes|Dynamic functions, callbacks|
|Anonymous Function|❌ No|❌ No|✅ Yes|Callbacks, event handlers|
|Function with Parameters|Depends|✅|✅|Dynamic input values|
|Function with Return|Depends|✅|✅|Return output|
|Nested Function|Depends|✅|✅|Modular code|
|Recursive Function|Depends|✅|✅|Repeated process (factorial, fibo)|
|IIFE|❌ No|Optional|✅|Initialization, isolation|

---
