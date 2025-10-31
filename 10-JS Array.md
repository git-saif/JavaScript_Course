## 🔹 **1️⃣ Array Definition**

👉 **Array** হলো এমন একটি **special object**, যা একাধিক ডেটা একসাথে একটি ভেরিয়েবল এ সংরক্ষণ করতে সাহায্য করে।  
প্রতিটি ডেটার একটি **index number** থাকে, যা 0 থেকে শুরু হয়।

📦 উদাহরণ:

```javascript
let fruits = ["Apple", "Banana", "Mango"];
```

এখানে,

- `fruits[0]` → `"Apple"`
- `fruits[1]` → `"Banana"`
- `fruits[2]` → `"Mango"`

---

## 🔹 **2️⃣ Array Syntax**

```javascript
let arrayName = [item1, item2, item3, ...];
```

🔸 Values গুলো যেকোনো type হতে পারে — number, string, boolean, object, function ইত্যাদি।

📦 উদাহরণ:

```javascript
let mix = [10, "Text", true, {name: "Saiful"}, [1, 2, 3]];
```

---

## 🔹 **3️⃣ Array তৈরি করার বিভিন্ন উপায়**

|পদ্ধতি|উদাহরণ|মন্তব্য|
|---|---|---|
|Literal (✅ Best Practice)|`let arr = [1,2,3];`|সবচেয়ে সহজ ও জনপ্রিয়|
|new Array() Constructor|`let arr = new Array(1,2,3);`|কম ব্যবহৃত, সতর্ক থাকতে হয়|
|Empty Array|`let arr = []; arr[0] = "A";`|পরে মান যোগ করা যায়|
|Array.of()|`let arr = Array.of(5);`|১টি উপাদান থাকলেও Array তৈরি করে|
|Array.from()|`let arr = Array.from("HELLO");`|String → Array রূপান্তর করে|

---

## 🔹 **4️⃣ Array Access**

```javascript
let cars = ["BMW", "Toyota", "Tesla"];

console.log(cars[0]); // BMW
console.log(cars[2]); // Tesla
```

### ⚠️ যদি index না থাকে:

```javascript
console.log(cars[5]); // undefined
```

---

## 🔹 **5️⃣ Array Update**

```javascript
cars[1] = "Honda";
console.log(cars); // ["BMW", "Honda", "Tesla"]
```

---

## 🔹 **6️⃣ Array Length**

```javascript
let fruits = ["Apple", "Banana", "Mango"];
console.log(fruits.length); // 3
```

---

## 🔹 **7️⃣ Array Add/Remove Elements**

|Method|কাজ|উদাহরণ|
|---|---|---|
|push()|শেষে যোগ করা|`arr.push("Kiwi")`|
|pop()|শেষে থেকে বাদ দেওয়া|`arr.pop()`|
|unshift()|শুরুতে যোগ করা|`arr.unshift("Apple")`|
|shift()|শুরু থেকে বাদ দেওয়া|`arr.shift()`|

📦 উদাহরণ:

```javascript
let fruits = ["Banana", "Mango"];
fruits.push("Orange"); // ["Banana","Mango","Orange"]
fruits.pop();          // ["Banana","Mango"]
```

---

## 🔹 **8️⃣ Array Method (Common & Useful)**

### 🔸 concat()

দুই বা তার বেশি array merge করতে ব্যবহৃত হয়।

```javascript
let a = [1,2];
let b = [3,4];
let c = a.concat(b);
console.log(c); // [1,2,3,4]
```

---

### 🔸 slice()

Array এর নির্দিষ্ট অংশ কেটে নেয় (original array অপরিবর্তিত থাকে)।

```javascript
let fruits = ["Banana","Mango","Orange","Apple"];
let sliced = fruits.slice(1,3);
console.log(sliced); // ["Mango","Orange"]
```

---

### 🔸 splice()

Array থেকে উপাদান যোগ/বাদ দিতে পারে (original array পরিবর্তিত হয়)।

```javascript
let arr = ["A","B","C","D"];
arr.splice(2,1,"X"); // 2 index থেকে 1টা বাদ দিয়ে "X" যোগ
console.log(arr); // ["A","B","X","D"]
```

---

### 🔸 join()

Array কে String এ রূপান্তর করে।

```javascript
let arr = ["HTML","CSS","JS"];
console.log(arr.join(" - ")); // "HTML - CSS - JS"
```

---

### 🔸 reverse()

Array এর উপাদান উল্টে দেয়।

```javascript
let arr = [1,2,3];
arr.reverse(); // [3,2,1]
```

---

### 🔸 includes()

Array এর ভিতরে কোনো মান আছে কিনা যাচাই করে।

```javascript
let arr = ["A","B","C"];
console.log(arr.includes("B")); // true
```

---

### 🔸 indexOf() / lastIndexOf()

```javascript
let arr = ["A","B","A"];
console.log(arr.indexOf("A"));      // 0
console.log(arr.lastIndexOf("A"));  // 2
```

---

## 🔹 **9️⃣ Array Search Methods**

|Method|কাজ|
|---|---|
|indexOf()|প্রথম মিল পাওয়া index|
|lastIndexOf()|শেষ মিল পাওয়া index|
|includes()|মান আছে কিনা true/false|
|find()|শর্ত অনুযায়ী প্রথম value|
|findIndex()|শর্ত অনুযায়ী প্রথম index|

📦 উদাহরণ:

```javascript
let num = [10, 20, 30, 40];
let found = num.find(x => x > 25);
console.log(found); // 30
```

---

## 🔹 **🔟 Array Sort**

```javascript
let arr = [30, 4, 100, 25];
arr.sort();
console.log(arr); // [100,25,30,4] ❌ (alphabetical)
```

### ✅ সংখ্যাগতভাবে sort করতে:

```javascript
arr.sort((a,b)=>a-b); // Ascending
arr.sort((a,b)=>b-a); // Descending
```

---

## 🔹 **11️⃣ Array Iterations**

|Method|কাজ|Return|
|---|---|---|
|forEach()|প্রতিটি item এ কাজ করে|কিছু return করে না|
|map()|প্রতিটি item modify করে|নতুন array return করে|
|filter()|শর্ত পূরণ করা item গুলো নেয়|নতুন array return করে|
|reduce()|একাধিক মানকে একত্র করে|single value return করে|

📦 উদাহরণ:

```javascript
let numbers = [1,2,3,4,5];

numbers.forEach(n => console.log(n * 2));

let doubled = numbers.map(n => n * 2);
console.log(doubled); // [2,4,6,8,10]

let even = numbers.filter(n => n % 2 === 0);
console.log(even); // [2,4]

let sum = numbers.reduce((total, n) => total + n);
console.log(sum); // 15
```

---

## 🔹 **12️⃣ Array Reference**

Array হলো **reference type**, তাই assign করলে একই জায়গায় রেফার করে।

```javascript
let arr1 = [1,2,3];
let arr2 = arr1;
arr2[0] = 100;

console.log(arr1[0]); // 100 ❌
```

✅ সঠিক পদ্ধতি (copy করতে):

```javascript
let arr2 = arr1.slice();
```

---

## 🔹 **13️⃣ Array Const**

Const দিয়ে Array ঘোষণা করলে পুরো array পরিবর্তন করা যায় না —  
তবে এর ভিতরের elements পরিবর্তন করা যায়।

```javascript
const arr = [1,2,3];
arr[0] = 10; // ✅ Allowed
arr.push(4); // ✅ Allowed
// arr = [5,6]; ❌ Error (reassign not allowed)
```

---

## 🔹 **14️⃣ Multi-Dimensional Array (Array inside Array)**

```javascript
let matrix = [
  [1,2,3],
  [4,5,6],
  [7,8,9]
];

console.log(matrix[1][2]); // 6
```

---

## 🔹 **15️⃣ Common Mistakes & Best Practices**

|ভুল|সঠিক|
|---|---|
|Array compare করতে `==` বা `===` ব্যবহার করা|সবসময় `.every()` বা `.join()` ব্যবহার করে তুলনা করো|
|সরাসরি array copy করা|`slice()` বা `concat()` দিয়ে copy করো|
|`new Array(5)` ব্যবহার|`Array.of(5)` ব্যবহার করো|
|Index ভুলভাবে ব্যবহার|সর্বদা `arr.length` দেখে loop চালাও|
|Empty slot রাখা|Avoid sparse arrays (যেমন `[1,,3]`)|

---

## 🔹 **16️⃣ Summary Table**

|বিষয়|কাজ|
|---|---|
|Array|একাধিক মান রাখার জন্য|
|Access|`arr[index]`|
|Add/Remove|`push`, `pop`, `shift`, `unshift`|
|Search|`find`, `includes`, `indexOf`|
|Sort|`sort()`|
|Iterate|`forEach`, `map`, `filter`, `reduce`|
|Copy|`slice()` / `concat()`|
|Const|value change হয়, array reference নয়|
|Reference|assign করলে same reference|
|Multi Array|nested array support করে|

---

চাও কি আমি পরের নোটে **“JavaScript String (Basic to Advance, with all methods like slice, substring, replace, split, trim, etc.)”** তৈরি করি?  
এটি array এর পরের সবচেয়ে গুরুত্বপূর্ণ chapter।