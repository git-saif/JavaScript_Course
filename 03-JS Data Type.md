JavaScript এর সবচেয়ে গুরুত্বপূর্ণ ও বেসিক টপিকগুলোর একটি — **Data Types**।  এইটা ভালোভাবে বুঝলে JS এর প্রায় সব অংশই অনেক সহজ মনে হবে। নিচে এর বিস্তারিত আলোচনা করা হলোঃ

---

# **1. Data Type কী?**

### Definition:

**Data Type** মানে হলো কোনো **variable-এ কী ধরণের মান (value)** রাখা আছে — যেমন সংখ্যা, লেখা, true/false, object, ইত্যাদি।

> JavaScript হলো **Dynamic Typing Language** . অর্থাৎ, variable declare করার সময় data type বলে দিতে হয় না, JS নিজেই বুঝে নেয়।

---

### Example:

```javascript
let name = "Saiful";   // String
let age = 25;          // Number
let isAdmin = true;    // Boolean
let user = null;       // Null
let country;           // Undefined
```

---

## **2. Data Type এর দুই ধরণ:**

|ধরন|নাম|
|---|---|
|**Primitive**|String, Number, Boolean, Null, Undefined, Symbol, BigInt|
|**Non-Primitive (Reference)**|Object, Array, Function|

---

## **3. Primitive Data Types (মৌলিক টাইপ)**

### 1 **String**

লেখা (text) বা character এর data — একে string বলে।  আর এটি লিখতে হয় **single (' ')** বা **double (" ")** বা **backtick ( )** দিয়ে।

```javascript
let name1 = "Saiful";
let name2 = 'Islam';
let name3 = `My name is ${name1} ${name2}`;

console.log(name3); // Output: My name is Saiful Islam

/*
 * single (' ') বা double (" ") – দুইভাবেই string লিখা যাবে।
 * আর যদি quote এর ভেতরে quote লিখতে হয়, তাহলে \ ব্যবহার করতে হয়।
 */

let firstName = 'Saiful';       // single quote string
firstName = 'Islam';            // মান পরিবর্তন করা হলো

let fullName1 = 'My Name is \'Saiful\'';   // একক quote এর ভেতরে quote ব্যবহার (escape করা হয়েছে)
let fullName2 = "My Name is 'Saiful'";     // double quote ব্যবহার করায় escape দরকার হয়নি

// Template Literal (backtick ব্যবহার করে dynamic string তৈরি)
let finalName = `My Name is ${firstName}`;

console.log(firstName);  // Output: Islam
console.log(fullName1);  // Output: My Name is 'Saiful'
console.log(fullName2);  // Output: My Name is 'Saiful'
console.log(finalName);  // Output: My Name is Islam

```

**⚠️ ভুল ব্যবহার:**

```javascript
let name = 'Saiful";  // ❌ Error (mismatched quotes)
```

**✅ Best practice:**

- একই প্রোজেক্টে এক ধরনের quote ব্যবহার করা (prefer `" "` or `' '` )।
- Dynamic string চাইলে **template literal ( )** ব্যবহার করা।

---

### 2 **Number**

সাধারণ সংখ্যা (integer বা float) বোঝায়।

```javascript
let age = 25;
let price = 99.99;

console.log(typeof age);   // "number"
console.log(typeof price); // "number"
```

✅ JS-এ সব সংখ্যাই **number type** (integer বা float আলাদা টাইপ না)।

**⚠️ Error case:**

```javascript
let x = 10 / "abc";  // NaN (Not a Number)
console.log(x);      // Output: NaN
```

**✅ Best practice:**

- সংখ্যাকে text-এ রূপান্তর করতে `String()` বা `toString()` ব্যবহার করা।
- text থেকে number এ রূপান্তর করতে `Number()`, `parseInt()`, বা `parseFloat()` ব্যবহার করা।
    

---

### 3 **Boolean**

এটি কেবল দুইটি মান নিতে পারে — `true` বা `false`।

```javascript
let isOnline = true;
let isLoggedIn = false;
console.log(typeof isOnline); // "boolean"
```

**Example (use case):**

```javascript
let age = 18;
let canVote = (age >= 18);
console.log(canVote); // true
```

**✅ Best practice:**  
Logic বা condition এ boolean use করা হয় (e.g. `if`, `while`, `for` ইত্যাদি)।

---

### 4 **Undefined**

যখন কোনো variable declare করা হয়েছে কিন্তু কোনো মান দেওয়া হয়নি।

```javascript
let city;
console.log(city);        // Output: undefined
console.log(typeof city); // "undefined"
```

**✅ Best practice:**  
`undefined` নিজে থেকে assign না করে, বরং মান না দিলে JS নিজেই `undefined` দেবে।

---

### 5 **Null**

`null` মানে হলো — ইচ্ছাকৃতভাবে **“খালি” বা “কিছু নেই”** বোঝানো।

```javascript
let car = null;
console.log(car); // Output: null
```

**⚠️ গুরুত্বপূর্ণ:**  
`typeof null` দেয় `"object"` (JS-এর পুরোনো bug, কিন্তু এটা এখনো আছে 😅)

---

### 6 **Symbol** (Unique value)

ES6 এ এসেছে। এটি **unique identity** তৈরি করতে ব্যবহৃত হয়।

```javascript
let id1 = Symbol("id");
let id2 = Symbol("id");

console.log(id1 === id2); // false
```

**✅ Best practice:**  
`Symbol` সাধারণত object key বা unique ID হিসেবে ব্যবহৃত হয় (Advanced use cases)।

---

### 7 **BigInt**

খুব বড় সংখ্যা handle করতে (যা normal number type এ ফিট হয় না)।

```javascript
let bigNumber = 123456789012345678901234567890n;
console.log(bigNumber); // 123456789012345678901234567890n
```

⚠️ BigInt এর সাথে normal number mix করা যাবে না:

```javascript
let x = 10n + 5; // ❌ Error: Cannot mix BigInt and other types
```

✅ সঠিকভাবে করতে হবে:

```javascript
let x = 10n + 5n; // ✅ OK
```

---

## **4. Non-Primitive (Reference) Data Types**

### 1 **Object**

একটি object হলো key-value pair এর collection।

```javascript
let person = {
  name: "Saiful",
  age: 25,
  city: "Dhaka"
};

console.log(person.name);   // Saiful
console.log(person["city"]); // Dhaka
```

**মান পরিবর্তন করা যায়:**

```javascript
person.age = 26;
person.country = "Bangladesh";
console.log(person);
```

**⚠️ Error case:**

```javascript
const user = { name: "Saiful" };
user = { name: "Islam" };  // ❌ Error: can't reassign const object
```

✅ **Best practice:**  
`const` দিয়ে object declare করা, এবং ভিতরের মান পরিবর্তন করা যাবে। কিন্তু নতুন object assign না করাই best Practice।

---

### 2 **Array**

একটি variable এ একাধিক মান রাখতে ব্যবহৃত হয়।

```javascript
let fruits = ["Mango", "Banana", "Apple"];
console.log(fruits[0]); // "Mango"
console.log(fruits.length); // 3
```

**মান পরিবর্তন করা:**

```javascript
fruits[1] = "Orange";   // ✅ allowed
console.log(fruits);
```

**⚠️ ভুল উদাহরণ:**

```javascript
const fruits = ["Apple"];
fruits = ["Mango"]; // ❌ Error
```

✅ **Best practice:**  
Array কে `const` দিয়ে declare করা, মান update করা যাবে কিন্তু নতুন array assign করা যাবে না।

---

### 3 **Function**

একটি Function হলো reusable কোড ব্লক যা **বারবার ব্যবহার করা যায়**।

```javascript
function greet(name) {
  return "Hello, " + name + "!";
}

console.log(greet("Saiful")); // Output: Hello, Saiful!
```

✅ **Best practice:**

- meaningful নাম দেয়া
- camelCase convention ব্যবহার করা (e.g. `calculateTotal`)

---

## **5. typeof Operator দিয়ে Data Type চেক করা**

```javascript
console.log(typeof "Hello");   // string
console.log(typeof 10);        // number
console.log(typeof true);      // boolean
console.log(typeof undefined); // undefined
console.log(typeof null);      // object (bug)
console.log(typeof {});        // object
console.log(typeof []);        // object
console.log(typeof function(){}); // function
```

---

## ✅ **6. সারাংশ টেবিল**

|ধরন|Data Type|পরিবর্তনযোগ্য (mutable)?|typeof রেজাল্ট|উদাহরণ|
|---|---|---|---|---|
|**Primitive**|String|❌|"string"|`"Hello"`|
||Number|❌|"number"|`42`|
||Boolean|❌|"boolean"|`true`|
||Undefined|❌|"undefined"|`let x;`|
||Null|❌|"object"|`null`|
||Symbol|❌|"symbol"|`Symbol("id")`|
||BigInt|❌|"bigint"|`123n`|
|**Non-Primitive**|Object|✅|"object"|`{name: "Saiful"}`|
||Array|✅|"object"|`["a","b","c"]`|
||Function|✅|"function"|`function() {}`|

---
