### Definition

**Loop** মানে হচ্ছে কোনো কাজ বারবার করা যতক্ষণ না একটি নির্দিষ্ট শর্ত পূরণ হয়।  JavaScript-এ loop ব্যবহার করা হয় **repeated কাজ স্বয়ংক্রিয়ভাবে** করার জন্য।

---

## **Types of Loop:**

JavaScript -এ কয়েক ধরণের Loop আছে। সেগুলো হলো:

| Loop Type              | Definition                                                  | Use Case                                  | Example                                                                                                          |
| ---------------------- | ----------------------------------------------------------- | ----------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| **for loop**           | একটি নির্দিষ্ট সংখ্যা অনুযায়ী code block বারবার চালায়।      | যখন iteration সংখ্যা জানা থাকে।           | `js\nfor (let i = 1; i <= 5; i++) {\n console.log(i);\n}\n// Output: 1 2 3 4 5\n`                                |
| **while loop**         | শর্ত (condition) true থাকা পর্যন্ত code block চালায়।        | iteration সংখ্যা আগে থেকে জানা না থাকলে।  | `js\nlet i = 1;\nwhile (i <= 5) {\n console.log(i);\n i++;\n}\n`                                                 |
| **do...while loop**    | অন্তত একবার code block চালায়, তারপর condition চেক করে।      | যখন কমপক্ষে একবার কোড চালাতে হয়।          | `js\nlet i = 1;\ndo {\n console.log(i);\n i++;\n} while (i <= 5);\n`                                             |
| **for...in loop**      | object-এর properties (keys) এর উপর iterate করে।             | object এর key-value পড়তে।                 | `js\nlet user = {name: 'Saiful', age: 25};\nfor (let key in user) {\n console.log(key + ': ' + user[key]);\n}\n` |
| **for...of loop**      | iterable (array, string, etc) এর values এর উপর iterate করে। | array বা string এর প্রতিটি মান পড়তে।      | `js\nlet nums = [10, 20, 30];\nfor (let n of nums) {\n console.log(n);\n}\n`                                     |
| **forEach() method**   | array এর প্রতিটি element এর জন্য function call করে।         | Array এর values process করতে।             | `js\nlet arr = [1,2,3];\narr.forEach(v => console.log(v * 2));\n// Output: 2,4,6\n`                              |
| **break statement**    | লুপ বন্ধ করে দেয় যখন শর্ত পূরণ হয়।                          | নির্দিষ্ট condition এ loop থামাতে।        | `js\nfor (let i = 1; i <= 5; i++) {\n if (i === 3) break;\n console.log(i);\n}\n// Output: 1 2\n`                |
| **continue statement** | লুপের বর্তমান iteration বাদ দিয়ে পরেরটিতে যায়।              | নির্দিষ্ট শর্তে কিছু iteration skip করতে। | `js\nfor (let i = 1; i <= 5; i++) {\n if (i === 3) continue;\n console.log(i);\n}\n// Output: 1 2 4 5\n`         |

_________
## **1. for Loop**

##### Syntax:

```javascript
for (initialization; condition; increment/decrement) {
  // code block
}
```

##### Example:

```javascript
for (let i = 1; i <= 5; i++) {
  console.log("Number:", i);
}
```

**Explanation:**

- `let i = 1;` → লুপ শুরু হওয়ার আগে ভেরিয়েবল ঘোষণা
- `i <= 5;` → লুপ চলবে যতক্ষণ পর্যন্ত এই শর্ত true থাকে
- `i++` → প্রতিবার ১ করে বাড়বে

**Output:**

```
Number: 1
Number: 2
Number: 3
Number: 4
Number: 5
```

**⚠️ Error Example:**

```javascript
for (let i = 1; i <= 5; i--) { // ❌ decrement দেওয়া হয়েছে, infinite loop হবে
  console.log(i);
}
```

**⚡ Best Practice:**

- loop condition সবসময় এমন দিতে হবে যাতে infinite loop না হয়।
- i, j, k — সাধারণত loop variable হিসেবে ব্যবহার করা হয়।

---

## **2. while Loop**

##### Syntax:

```javascript
while (condition) {
  // code block
}
```

##### Example:

```javascript
let i = 1;
while (i <= 5) {
  console.log("While Loop:", i);
  i++;
}
```

**Explanation:**

- প্রথমে শর্ত চেক করা হয়
- শর্ত true হলে কোড রান হয়
- শর্ত false হলে লুপ বন্ধ হয়

**⚠️ Error Example:**

```javascript
let i = 1;
while (i <= 5) {
  console.log(i);
  // ❌ i++ না থাকলে infinite loop হবে
}
```

**⚡ Best Practice:**

- while loop এ increment/decrement ভুলে যাওয়া উচিত না
- condition টি clear রাখা উচিত

---

## **3. do...while Loop**

##### Syntax:

```javascript
do {
  // code block
} while (condition);
```

##### Example:

```javascript
let i = 1;
do {
  console.log("Do While:", i);
  i++;
} while (i <= 5);
```

**Explanation:**

- প্রথমে কোড execute হয়
- তারপর condition চেক হয়
- অর্থাৎ অন্তত একবার লুপ চলবেই

**Error Example:**

```javascript
let i = 10;
do {
  console.log(i);
  i++;
} while (i < 5); // ❌ condition false হলেও একবার রান হবে
```

**⚡ Best Practice:**

- যখন অন্তত একবার লুপ চালাতে হবে নিশ্চিত, তখন do...while উপযুক্ত।

---

## **4. for...in Loop**

##### Syntax:

```javascript
for (let key in object) {
  // code block
}
```

##### Example:

```javascript
let person = {name: "Saiful", age: 25, city: "Dhaka"};

for (let key in person) {
  console.log(key, "=", person[key]);
}
```

**Output:**

```
name = Saiful
age = 25
city = Dhaka
```

**⚠️ Error Example:**

```javascript
let numbers = [1, 2, 3];
for (let key in numbers) {
  console.log(key); // ✅ key হবে index (0,1,2)
}
```

⚠️ **for...in array এর জন্য নয়**, object এর জন্য বেস্ট।

**⚡ Best Practice:**

- object এর key বা property access করতে ব্যবহার করা হয়।
- array এর জন্য ব্যবহার না করাই ভালো।

---

## **5. for...of Loop**

##### Syntax:

```javascript
for (let value of iterable) {
  // code block
}
```

##### Example:

```javascript
let fruits = ["Apple", "Banana", "Mango"];

for (let fruit of fruits) {
  console.log(fruit);
}
```

**Output:**

```
Apple
Banana
Mango
```

**⚠️ Error Example:**

```javascript
let obj = {a:1, b:2};
for (let value of obj) { // ❌ Error: obj is not iterable
  console.log(value);
}
```

**⚡ Best Practice:**

- iterable (array, string, map, set) এর জন্য for...of ব্যবহার করা যায়।
- object এর জন্য নয়।

---

## **6. break & continue**

### ➤ **break:**

লুপ **সম্পূর্ণ বন্ধ** করে বের হয়ে আসে।

```javascript
for (let i = 1; i <= 5; i++) {
  if (i === 3) break;
  console.log(i);
}
```

**Output:**

```
1
2
```

### ➤ **continue:**

এই iteration skip করে **পরের iteration** এ চলে যায়।

```javascript
for (let i = 1; i <= 5; i++) {
  if (i === 3) continue;
  console.log(i);
}
```

**Output:**

```
1
2
4
5
```

---

## **Summery: ✅**

|Loop Type|ব্যবহার|কাজের ধরন|Best Use|
|---|---|---|---|
|`for`|নির্দিষ্ট সংখ্যক বার|শুরুতেই condition check|count-based iteration|
|`while`|condition true থাকা পর্যন্ত|আগে condition check|unknown iteration count|
|`do...while`|অন্তত একবার চালানো দরকার|আগে execute, পরে check|input validation|
|`for...in`|object keys iterate|key-based|object property access|
|`for...of`|iterable data iterate|value-based|arrays, strings, maps, sets|
|`break`|লুপ সম্পূর্ণ বন্ধ করে|-|exit loop early|
|`continue`|বর্তমান iteration skip করে|-|skip specific cases|

---
