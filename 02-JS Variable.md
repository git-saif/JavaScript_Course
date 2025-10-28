JavaScript শেখার সবচেয়ে গুরুত্বপূর্ণ টপিকগুলোর একটা হলো **Variable**, আর এর তিনটি keyword — `var`, `let`, `const`।  
নিচে এগুলো বিস্তারিত আলোচনা করা হলোঃ

---

## **1. Variable (ভেরিয়েবল) কী?**

### Definition:

**Variable** হলো এমন একটি নামকৃত স্থান (container), যেখানে আমরা **data সংরক্ষণ করি** এবং পরে তা ব্যবহার করতে পারি।

### Example:

```javascript
let name = "Saiful";
let age = 25;

console.log(name);  // Output: Saiful
console.log(age);   // Output: 25
```

🧠 এখানে,
- `let` → variable declare করার keyword
- `name` / `age` → variable name
- `"Saiful"` / `25` → value
- `console.log()` → output দেখানোর জন্য

---

## **2. var, let, const — পার্থক্যসহ বিস্তারিত**

|বৈশিষ্ট্য|`var`|`let`|`const`|
|---|---|---|---|
|Scope (কোথায় কাজ করে)|function scoped|block scoped|block scoped|
|Redeclare (পুনরায় ঘোষণা)|সম্ভব|অসম্ভব|অসম্ভব|
|Reassign (নতুন মান দেওয়া)|সম্ভব|সম্ভব|অসম্ভব|
|Hoisting behavior|hoisted (initially undefined)|hoisted but not initialized|hoisted but not initialized|
|Use in modern JS|❌ পুরোনো|✅ আধুনিক|✅ আধুনিক|

---

## **A. `var` (পুরোনো পদ্ধতি)**

```javascript
var city = "Dhaka";
console.log(city); // Output: Dhaka

var city = "Chittagong"; // Redeclare possible
console.log(city); // Output: Chittagong

city = "Khulna"; // Reassign possible
console.log(city); // Output: Khulna
```

🧠 **Explain:**

- তুমি একই নামে আবারও `var` declare করতে পারো (no error)।
- আবার সেই variable এর মানও পরিবর্তন করতে পারো।

❌ **Problem:**  
`var` এর **scope function-based**, তাই block (যেমন if, loop)-এর মধ্যে declare করলেও বাইরেও accessible হয়ে যায়।

**Example (problem):**

```javascript
if (true) {
  var x = 10;
}
console.log(x); // Output: 10 (should not be accessible!)
```

> এটা অনেক সময় **bug তৈরি করে**, তাই `let` বা `const` ব্যবহার করাই সঠিক।

---

## **B. `let` (modern & safe)**

```javascript
let name = "Saiful";
console.log(name); // Output: Saiful

// let name = "Islam"; ❌ Error: already declared
name = "Islam";    // ✅ Reassign allowed
console.log(name); // Output: Islam
```

🧠 **Explain:**

- একই নামের variable আবার declare করলে error হবে।
- কিন্তু মান পরিবর্তন করা (reassign) যাবে।

**Example (scope):**

```javascript
if (true) {
  let x = 10;
  console.log("Inside block:", x); // Output: 10
}
console.log("Outside block:", x);  // ❌ Error: x is not defined
```

> অর্থাৎ, `let` কেবল **block এর মধ্যে সীমাবদ্ধ (block-scoped)**।

---

## **C. `const` (স্থির মান বা constant)**

```javascript
const country = "Bangladesh";
console.log(country); // Output: Bangladesh

// country = "India"; ❌ Error: Assignment to constant variable
```

🧠 **Explain:**

- `const` মানে **constant (স্থির)** → declare করার পর value পরিবর্তন করা যাবে না।
- একবার মান set করলে, পরবর্তীতে সেই variable এর মান reassign করা যায় না।

**তবে একটা গুরুত্বপূর্ণ বিষয়:**  
`const` দিয়ে যদি **object বা array** declare করো, তাহলে ভিতরের value **change করা যাবে**, কিন্তু পুরো object/array **reassign করা যাবে না**।

**Example (object case):**

```javascript
const person = { name: "Saiful", age: 25 };

person.age = 26; // ✅ Allowed (object property change)
console.log(person); // { name: "Saiful", age: 26 }

person = { city: "Dhaka" }; // ❌ Error: can't reassign entire object
```

---

## **3. Scope Visualization**

```javascript
function testVarLetConst() {
  if (true) {
    var a = 10;
    let b = 20;
    const c = 30;
  }

  console.log(a); // ✅ 10
  console.log(b); // ❌ Error
  console.log(c); // ❌ Error
}

testVarLetConst();
```

> কারণঃ
- `var` → পুরো function এ কাজ করে
- `let` ও `const` → শুধুমাত্র ওই `{}` block এর ভেতরে কাজ করে

---

## **4. Hoisting Behavior**

JavaScript কোড রান করার আগে variable গুলো **"hoist"** করে উপরে নিয়ে যায়।

```javascript
console.log(a); // Output: undefined
var a = 5;

console.log(b); // ❌ Error (Cannot access 'b' before initialization)
let b = 10;
```

🧠**Explain:**

- `var` → hoisted হয় এবং `undefined` হিসেবে initialize হয়
- `let` / `const` → hoisted হয় কিন্তু initialize হয় না → তাই আগে ব্যবহার করা যায় না

---

## ✅ **সারাংশ (Summary Table)**

|Keyword|Redeclare|Reassign|Scope|Hoisted|Use Case|
|---|---|---|---|---|---|
|**var**|✅|✅|Function|Yes (undefined)|পুরোনো কোডে|
|**let**|❌|✅|Block|Yes (TDZ)|সাধারণ ভ্যারিয়েবল|
|**const**|❌|❌|Block|Yes (TDZ)|স্থির মান, object, config|

---
