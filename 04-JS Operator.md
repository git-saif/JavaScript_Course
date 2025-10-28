## **JavaScript Operators**

**Operator** হলো এমন প্রতীক (symbol) যা **variable বা value-এর উপর কিছু কাজ (operation)** করে। সহজভাবে বললে — Operator মানে **কাজ করানোর চিহ্ন**।
যেমন: যোগ, বিয়োগ, তুলনা, লজিক্যাল চেক ইত্যাদি।  

---

### Example:

```javascript
let x = 10;
let y = 5;

let sum = x + y;  // + হলো Operator
console.log(sum); // Output: 15
```

> এখানে:

- `x`, `y` → Operand (যার উপর কাজ করা হচ্ছে)
- `+` → Operator

---

## ⚙️ **JavaScript Operators এর ধরন (Overview):**

| ধরণ                      | Example                                        | কাজ / ব্যবহার                                            |
| ------------------------ | ---------------------------------------------- | -------------------------------------------------------- |
| **Arithmetic Operators** | `+`, `-`, `*`, `/`, `%`, `**`, `++`, `--`      | গাণিতিক কাজ (যোগ, বিয়োগ, গুণ, ভাগ, ঘাত ইত্যাদি)          |
| **Assignment Operators** | `=`, `+=`, `-=`, `*=`, `/=`, `%=`              | কোনো variable এ মান (value) অ্যাসাইন বা আপডেট করা        |
| **Comparison Operators** | `==`, `===`, `!=`, `!==`, `>`, `<`, `>=`, `<=` | দুই মানের মধ্যে তুলনা করা (সমান, অসমান, বড়, ছোট ইত্যাদি) |
| **Logical Operators**    | `&&`,  \|\| , `!`                              | multiple condition একসাথে যাচাই করা                      |
| **Type Operators**       | `typeof`, `instanceof`                         | কোনো মানের ডেটা টাইপ বা অবজেক্ট টাইপ যাচাই করা           |
| **String Operators**     | `+`, `+=`                                      | স্ট্রিং (text) যোগ বা সংযুক্ত করা                        |

---

# **1. Arithmetic Operators (গাণিতিক অপারেটর)**

**Arithmetic Operator** ব্যবহার হয় **সংখ্যার (numeric)** মানের মধ্যে **গাণিতিক (mathematical)** কাজ করার জন্য। অর্থাৎ, যোগ, বিয়োগ, গুণ, ভাগ ইত্যাদি গাণিতিক অপারেশন করার সময় **Arithmetic Operators** ব্যবহার করা হয়।

### Types of JavaScript Arithmetic Operators:

| Operator Name               | Operator | উদাহরণ         | কাজের ধরন (Description)                    | ফলাফল (Result) উদাহরণ                  |
| --------------------------- | -------- | -------------- | ------------------------------------------ | -------------------------------------- |
| **Addition Operator**       | `+`      | `x + y`        | দুটি সংখ্যা **যোগ** করে                    | `5 + 3 = 8`                            |
| **Subtraction Operator**    | `-`      | `x - y`        | প্রথম সংখ্যা থেকে দ্বিতীয়টি **বিয়োগ** করে  | `8 - 3 = 5`                            |
| **Multiplication Operator** | `*`      | `x * y`        | দুটি সংখ্যা **গুণ** করে                    | `4 * 2 = 8`                            |
| **Division Operator**       | `/`      | `x / y`        | প্রথম সংখ্যা কে দ্বিতীয় দ্বারা **ভাগ** করে | `10 / 2 = 5`                           |
| **Modulus Operator**        | `%`      | `x % y`        | ভাগের **শেষাংশ (remainder)** দেয়           | `10 % 3 = 1`                           |
| **Increment Operator**      | `++`     | `x++` বা `++x` | **১ যোগ** করে মান বাড়ায়                    | যদি `x = 5`, তাহলে `x++` এর পর `x = 6` |
| **Decrement Operator**      | `--`     | `x--` বা `--x` | **১ বিয়োগ** করে মান কমায়                   | যদি `x = 5`, তাহলে `x--` এর পর `x = 4` |
| **Exponentiation Operator** | `**`     | `x ** y`       | কোনো সংখ্যার **power (ঘাত)** হিসাব করে     | `2 ** 3 = 8`                           |

---

#### **1 : Addition (`+`)**

**কাজ:** দুটি মান যোগ করা (সংখ্যা হলে গাণিতিক যোগ, string হলে text যোগ)

```javascript
let x = 10;
let y = 5;
console.log(x + y); // 15
```

📘 **String যোগের সময়:**

```javascript
let firstName = "Saiful";
let lastName = "Islam";
console.log(firstName + " " + lastName); // "Saiful Islam"
```

⚠️ **Error/Confusion case:**

```javascript
let result = 5 + "10";  
console.log(result); // "510" (string যোগ, number না!)
```

👉 JS automatically number কে string এ convert করে (Type coercion)।

✅ **Best practice:**

- যোগ করার সময় নিশ্চিত হতে হবে, যে দুটি value ই number.

```javascript
   let result = Number(5) + Number("10"); // 15
```
   

---

#### **2 : Subtraction (`-`)**

**কাজ:** একটি মান থেকে অন্যটি বিয়োগ করা

```javascript
let x = 20;
let y = 5;
console.log(x - y); // 15
```

**⚠️ বিশেষ বিষয়:**

```javascript
console.log("20" - 5); // 15 (string হলেও JS number বানায়)
console.log("Saiful" - 5); // NaN
```

✅ **Best practice:**

- বিয়োগের সময় value numeric কিনা চেক করতে হবে:

```javascript
   if (isNaN(value)) console.error("Invalid number");
```

---

#### **3 : Multiplication (`*`)**

**কাজ:** দুটি মান গুণ করা

```javascript
let a = 4;
let b = 3;
console.log(a * b); // 12
```

**⚠️ ভুল ব্যবহার:**

```javascript
console.log("abc" * 2); // NaN
```

✅ **Best practice:**

- শুধুমাত্র numeric মান ব্যবহার করতে হবে।
- গুণের আগে ইনপুট যাচাই করতে হবে (`Number()` বা `parseFloat()` দিয়ে।

---

#### **4 : Division (`/`)**

**কাজ:** প্রথম মানকে দ্বিতীয় মান দিয়ে ভাগ করা।

```javascript
let x = 10;
let y = 2;
console.log(x / y); // 5
```

**⚠️ ভুল ব্যবহার:**

```javascript
console.log(10 / 0); // Infinity
console.log("abc" / 2); // NaN
```

✅ **Best practice:**

- divisor (ভাগফল) 0 কিনা আগে চেক করতে হবে:

```javascript
   if (y === 0) console.error("Cannot divide by zero!");
```


---

#### **5 : Modulus (`%`)**

**কাজ:** ভাগশেষ (remainder) বের করা। 

```javascript
console.log(10 % 3); // 1
console.log(15 % 5); // 0
```

**Example (even-odd check):**

```javascript
let num = 8;
if (num % 2 === 0) {
  console.log("Even number");
} else {
  console.log("Odd number");
}
```

✅ **Best practice:**

- যখন remainder দরকার (যেমন even/odd check), `%` ব্যবহার করতে হবে।

---

#### **6 : Exponentiation (`**`)**

**কাজ:** কোনো সংখ্যার power বের করা

```javascript
console.log(2 ** 3); // Output: 8
```

**⚠️ ভুল Example:**

```javascript
console.log(2 ^ 3); // 1 ❌ (এটা bitwise XOR, exponent নয়!)
```

✅ **Best practice:**

- Power গণনায় সবসময় `**` ব্যবহার করতে হবে, `^` নয়।


---

#### **7 : Increment (`++`)**

**কাজ:** মান ১ করে বাড়ায়।

```javascript
let a = 5;
a++;
console.log(a); // 6
```

**Pre vs Post increment:**

```javascript
let x = 5;
console.log(++x); // 6 (আগে বাড়ায়, তারপর ব্যবহার)
console.log(x++); // 6 (আগে ব্যবহার, তারপর বাড়ায়)
console.log(x);   // 7
```

✅ **Best practice:**

- Loop এর মধ্যে counter হিসেবে ব্যবহার করতে হবে:

```javascript
   for (let i = 0; i < 5; i++) {
     console.log(i);
   }
```
   

---

#### **8 : Decrement (`--`)**

**কাজ:** মান ১ করে কমায়।

```javascript
let a = 5;
a--;
console.log(a); // 4
```

**Pre vs Post decrement:**

```javascript
let x = 10;
console.log(--x); // 9 (আগে কমে)
console.log(x--); // 9 (আগে ব্যবহার হয়, পরে কমে)
console.log(x);   // 8
```

✅ **Best practice:**

- Loop বা countdown এ ব্যবহার করো (যেমন reverse iteration)।

---

## **3. Common Errors in Arithmetic Operators ⚠️**

| ভুল কোড     | সমস্যা     | কারণ                      |
| ----------- | ---------- | ------------------------- |
| `"5" + 2`   | `"52"`     | String যোগ হচ্ছে          |
| `"5" - 2`   | `3`        | JS auto convert করছে      |
| `10 / 0`    | `Infinity` | 0 দিয়ে ভাগ                |
| `10n + 5`   | ❌ Error    | BigInt + Number মিক্স করা |
| `"abc" * 2` | `NaN`      | invalid number            |

---

## **4. Best Practice Notes 📝**

✅ সবসময় data type নিশ্চিত করতে হবে (Number বা String)।  
✅ গাণিতিক কাজের আগে input validate করতে হবে।    
✅ Loop counter হিসেবে `++` ও `--` ব্যবহারে pre/post behavior বুঝতে হবে।  
✅ Mixed-type অপারেশনে type conversion handle করতে হবে (e.g. `Number()` / `String()` ব্যবহার করে।  
✅ Readability বাড়াতে bracket ব্যবহার করতে হবে।

```javascript
let result = (a + b) * c;
```

---
_____
