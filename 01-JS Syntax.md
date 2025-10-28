আমরা এই তিনটা টপিক (JS Syntax, JS Statements, JS Comments) নিয়ে আলোচনা করবো —

---

## **1. JavaScript Syntax**

### Definition:

**Syntax** মানে হলো— কোনো প্রোগ্রামিং ভাষার **নিয়ম বা কাঠামো**, যেভাবে কোড লিখলে কম্পিউটার বুঝতে পারে।  
অর্থাৎ JavaScript এর ক্ষেত্রে **কোড লেখার নিয়ম-কানুনই Syntax**।

---

### Example:

```javascript
let name = "Saiful";
console.log(name);
```

### Explain:

- `let` → keyword (variable declare করার নিয়ম)
- `name` → variable name
- `=` → assignment operator
- `"Saiful"` → string value
- `console.log()` → output দেখানোর function

> এগুলো ঠিকভাবে না লিখলে **syntax error** হবে।

**Example (syntax error):**

```javascript
let name "Saiful"  // ❌ Missing equal sign (=). This is Syntax Error
console.log(name)
```

---

## **2. JavaScript Statements**

### Definition:

একটি **statement** মানে হলো **একটি সম্পূর্ণ নির্দেশ বা কমান্ড**, যেটি JavaScript এক্সিকিউট করে।  
একটি JS প্রোগ্রাম অনেকগুলো স্টেটমেন্ট দিয়েই গঠিত হয়।

---

### Example:

```javascript
let x = 5;
let y = 10;
let sum = x + y;
console.log(sum);
```

### Explain:

- `let x = 5;` → ১টি স্টেটমেন্ট (variable declare)
- `let y = 10;` → আরেকটি স্টেটমেন্ট
- `let sum = x + y;` → আরেকটি স্টেটমেন্ট
- `console.log(sum);` → আরেকটি স্টেটমেন্ট (output)

> প্রতিটি স্টেটমেন্ট **`;`** দিয়ে শেষ করা ভালো অভ্যাস (optional, কিন্তু recommended)।

---

## **3. JavaScript Comments**

### Definition:

**Comments** মানে হলো — কোডের এমন অংশ যা **ব্রাউজার এক্সিকিউট করে না**, বরং শুধু **ডেভেলপারদের বোঝার জন্য বা কোনো নোট রাখার জন্য** লেখা হয়।

---

### Types of Comments:

JavaScript-এ ২ ধরণের comment আছে :

#### ➤ **Single-line Comment:**

```javascript
// এটি একটি single line comment
let name = "Saiful"; // এই লাইনেও করা যায়
```

#### ➤ **Multi-line Comment:**

```js
/*
This is
multi-line
comment
*/
let x = 10;
```

##### ➤ **Colorful Multi-line Comment:**

```js
/*
  * This is Green Comment
  ! This is Red Comment
  ? This is Blue Comment
  TODO: This is Orange Comment
*/
```

>এর জন্য Better Comment Extension Use করতে হবে।

---

### Use Case?

- কোড বুঝতে সাহায্য করে
- ভবিষ্যতে কোড মেইনটেইন করা সহজ হয়
- টেস্ট করার সময় কিছু লাইন সাময়িকভাবে বন্ধ রাখতে পারো

---

## **Summery:**

|বিষয়|মানে|উদাহরণ|
|---|---|---|
|**Syntax**|কোড লেখার নিয়ম|`let x = 5; console.log(x);`|
|**Statement**|JS-এ নির্দেশ বা কমান্ড|`x = 10;`|
|**Comment**|ব্যাখ্যার জন্য লেখা, রান হয় না|`// This is a comment`|

---
