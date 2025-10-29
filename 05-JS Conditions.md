# JavaScript Conditional Statements (Conditions)

JavaScript-এ **Conditional Statements** ব্যবহার করা হয় নির্দিষ্ট শর্ত অনুযায়ী প্রোগ্রামের **flow নিয়ন্ত্রণ** করার জন্য। যখন কোনো শর্ত **true** হয়, তখন নির্দিষ্ট কোড অংশটি execute হয়।  যদি **false** হয়, তাহলে বিকল্প কোড অংশ চলতে পারে।

---

## **1. if Statement**

##### **Definition:**

`if` statement কোনো নির্দিষ্ট শর্ত **true** হলে নির্দিষ্ট কোড execute করে।

##### **Syntax:**

```javascript
if (condition) {
  // code to execute if condition is true
}
```

##### **Example:**

```javascript
let age = 20;

if (age >= 18) {
  console.log("Eligible for vote");
}
```

##### **Explanation:**

- শর্ত: `age >= 18`
- মান true → কোড চলবে
- মান false → কিছুই হবে না

##### **Notes:**

> Condition অবশ্যই Boolean (`true` / `false`) এ evaluate হতে হবে।
> একাধিক if statement আলাদা আলাদা শর্ত যাচাই করতে পারে।

---

## **2. if...else Statement**

##### **Definition:**

`if...else` statement শর্ত **true** হলে একটি কোড block, আর **false** হলে অন্য কোড block execute করে।

##### **Syntax:**

```javascript
if (condition) {
  // code if true
} else {
  // code if false
}
```

##### **Example:**

```javascript
let marks = 40;

if (marks >= 50) {
  console.log("Pass");
} else {
  console.log("Fail");
}
```

##### **Explanation:**

- `marks >= 50` → false
- তাই else block execute হয়েছে।

##### **Notes:**

- `if` ছাড়া `else` ব্যবহার করা যায় না।
- `else` block সর্বদা ঐচ্ছিক (optional)।

---

## **3. if...else if...else Statement**

##### **Definition:**

এই structure একাধিক শর্ত যাচাই করতে ব্যবহৃত হয়।  প্রথম যে শর্ত true হয়, তার কোড block execute হয় এবং বাকিগুলো skip হয়।

##### **Syntax:**

```javascript
if (condition1) {
  // code if condition1 is true
} else if (condition2) {
  // code if condition2 is true
} else {
  // code if none of the above is true
}
```

##### **Example:**

```javascript
let score = 75;

if (score >= 80) {
  console.log("Grade: A+");
} else if (score >= 70) {
  console.log("Grade: A");
} else if (score >= 60) {
  console.log("Grade: B");
} else {
  console.log("Fail");
}
```

##### **Explanation:**

- `score >= 80` → false
- `score >= 70` → true ⇒ “Grade: A” প্রিন্ট হয়েছে।

##### **Notes:**

- একাধিক `else if` থাকতে পারে।
- কেবল প্রথম true condition-এর block চালু হয়।
- সব শর্ত false হলে `else` block execute হয়।

---

## **4. switch Statement**

##### **Definition:**

`switch` statement কোনো মানকে বিভিন্ন case এর সাথে তুলনা করে নির্দিষ্ট কোড চালায়।  এটি একাধিক `if...else` statement এর বিকল্প।

##### **Syntax:**

```javascript
switch (expression) {
  case value1:
    // code block
    break;

  case value2:
    // code block
    break;

  default:
    // code block if none matches
}
```

##### **Example:**

```javascript
let day = 3;
let dayName;

switch (day) {
  case 1:
    dayName = "Sunday";
    break;
  case 2:
    dayName = "Monday";
    break;
  case 3:
    dayName = "Tuesday";
    break;
  default:
    dayName = "Invalid day";
}

console.log(dayName);
```

##### **Explanation:**

- `day = 3` → `case 3` এর সাথে মিলে গেছে
- break না থাকলে পরের case-ও চলবে (fall-through behavior)।

##### **Notes:**

- `break` ব্যবহার না করলে পরের case গুলোও execute হবে।
- `default` block ঐচ্ছিক, তবে রাখা উত্তম।
- `switch` ব্যবহার করা হয় যখন একই variable-এর বিভিন্ন মান যাচাই করতে হয়।

---

## **5. Ternary Operator (?:)**

##### **Definition:**

Ternary operator হচ্ছে `if...else` এর সংক্ষিপ্ত রূপ। এটি এক লাইনে condition যাচাই করে ফলাফল প্রদান করে।

##### **Syntax:**

```javascript
condition ? expression_if_true : expression_if_false;
```

##### **Example:**

```javascript
let age = 18;
let result = (age >= 18) ? "Adult" : "Minor";

console.log(result);
```

**Output:** `Adult`

##### **Explanation:**

- যদি `age >= 18` → true, তাহলে প্রথম অংশ “Adult” return করবে।
- false হলে দ্বিতীয় অংশ “Minor” return করবে।

---

##### **Nested Example:**

```javascript
let marks = 85;
let grade = (marks >= 80) ? "A+" :
            (marks >= 70) ? "A" :
            (marks >= 60) ? "B" : "Fail";

console.log(grade);
```

**Output:** `A+`

---

##### **Notes:**

- এক লাইনে ছোট decision নিতে ব্যবহৃত হয়।
- অনেক nested ternary ব্যবহার কোডকে জটিল করে ফেলে।
- বড় condition structure এর জন্য `if...else` ব্যবহার উপযুক্ত।

---

## **Common Mistakes ⚠️**

|ভুল কোড|সমস্যা|কারণ|
|---|---|---|
|`if (x = 5)`|সবসময় true|`=` হলো assignment operator|
|`switch(x)` এ `break` না দেওয়া|সব case execute হয়|break না থাকলে fall-through হয়|
|Nested ternary বেশি ব্যবহার|কোড পড়া কঠিন|readability কমে যায়|

---

## **Best Practice Notes 🧾**

✅ `===` এবং `!==` ব্যবহার করা উচিত type-safe comparison এর জন্য  
✅ ছোট condition এর জন্য ternary operator ব্যবহার করা যায়  
✅ বড় decision tree এর জন্য `if...else if...else` ব্যবহার করা উত্তম  
✅ `switch` ব্যবহার করা উচিত যখন একটি variable-এর একাধিক নির্দিষ্ট মান compare করতে হয়  
✅ `break` সর্বদা `switch` case এ ব্যবহার করা উচিত  
✅ nested condition এর readability বাড়াতে indentation বজায় রাখা প্রয়োজন

---

## **Summary Table ✅**

|Statement|কাজ|ব্যবহার ক্ষেত্র|
|---|---|---|
|`if`|এক শর্ত যাচাই|একক শর্ত|
|`if...else`|true/false অনুযায়ী দুই কোড চালায়|দুই সম্ভাবনা|
|`if...else if...else`|একাধিক শর্ত যাচাই|বিভিন্ন গ্রেড, রেঞ্জ ইত্যাদি|
|`switch`|এক মানের বিভিন্ন case যাচাই|নির্দিষ্ট মানের ভিত্তিতে কোড নির্বাচন|
|`? :` (Ternary)|এক লাইনে if...else|সংক্ষিপ্ত condition|

---
