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
# 2 **JavaScript Assignment Operators**

**Assignment Operator** ব্যবহার হয় **কোনো variable এ মান (value) রাখার জন্য**। অর্থাৎ, একটি মান variable এর মধ্যে সংরক্ষণ (assign) করতে Assignment Operator ব্যবহার করা হয়।

---

## **JavaScript Assignment Operators এর ধরন**

| Operator Name                 | Operator | উদাহরণ    | সমান অর্থে লেখা যায় | কাজ                            |
| ----------------------------- | -------- | --------- | ------------------- | ------------------------------ |
| **Simple Assignment**         | `=`      | `x = 10`  | —                   | মান অ্যাসাইন করা               |
| **Addition Assignment**       | `+=`     | `x += 5`  | `x = x + 5`         | যোগ করে মান অ্যাসাইন করা       |
| **Subtraction Assignment**    | `-=`     | `x -= 5`  | `x = x - 5`         | বিয়োগ করে মান অ্যাসাইন করা     |
| **Multiplication Assignment** | `*=`     | `x *= 5`  | `x = x * 5`         | গুণ করে মান অ্যাসাইন করা       |
| **Division Assignment**       | `/=`     | `x /= 5`  | `x = x / 5`         | ভাগ করে মান অ্যাসাইন করা       |
| **Modulus Assignment**        | `%=`     | `x %= 5`  | `x = x % 5`         | ভাগশেষ মান অ্যাসাইন করা        |
| **Exponentiation Assignment** | `**=`    | `x **= 3` | `x = x ** 3`        | power বের করে মান অ্যাসাইন করা |

---

### **1 : Simple Assignment `(=)`**

- **কাজ:** মান অ্যাসাইন করা।

```javascript
let a = 10;
console.log(a); // 10
```

> এখানে সরাসরি 10 মানটি `a` তে দেওয়া হয়েছে।

⚠️ **Error Case:**

```javascript
x = 5; // ReferenceError যদি x আগে declare না করা থাকে (strict mode এ)
```

✅ **Best practice:**

- সবসময় variable আগে `let`, `const`, বা `var` দিয়ে declare করতে হবে।

---

### **2 : Addition Assignment `(+=)`**

- **কাজ:** মান যোগ করে অ্যাসাইন করা।

```javascript
let x = 5;
x += 3;   // x = x + 3
console.log(x); // 8
```

**✅ Best Practice:**

```javascript
let total = 100;
total += 50; // total এখন 150
```

**⚠️ ভুল ব্যবহার:**

```javascript
const a = 10;
a += 5; // ❌ Error: Assignment to constant variable
```

> কারণ `const` variable এর মান পরিবর্তন করা যায় না।

---

### **3 : Subtraction Assignment `(-=)`**

- **কাজ:** মান বিয়োগ করে অ্যাসাইন করা।

```javascript
let x = 10;
x -= 4;  // x = x - 4
console.log(x); // 6
```

**Example:**

```javascript
let balance = 500;
balance -= 120; // ব্যয় বাদে বাকি
console.log(balance); // 380
```

✅ **Best practice:**  
যখন কোনো মান ক্রমাগত কমাতে হবে (e.g., discount, countdown ইত্যাদি) তখন `-=` ব্যবহার করতে হবে।

---

### **4 : Multiplication Assignment `(*=)`**

- **কাজ:** মান গুণ করে অ্যাসাইন করা।

```javascript
let x = 5;
x *= 3;  // x = x * 3
console.log(x); // 15
```

**Use case:**

```javascript
let price = 100;
price *= 1.1; // 10% increase
console.log(price); // 110
```

⚠️ **Error:**

```javascript
let name = "Saiful";
name *= 2;  // NaN ❌ (string কে multiply করা যায় না)
```

✅ **Best practice:**  
যখন সংখ্যা গুণ করতে হবে, তখন নিশ্চিত করতে হবে, যে value **numeric** টাইপের।

---

### **5 : Division Assignment `(/=)`**

- **কাজ:** মান ভাগ করে অ্যাসাইন করা।

```javascript
let x = 20;
x /= 4;  // x = x / 4
console.log(x); // 5
```

⚠️ **Error case:**

```javascript
let num = 10;
num /= 0;   // Output: Infinity ❌
```

✅ **Best practice:**  
ভাগ করার আগে divisor 0 কিনা তা চেক করতে হবে:

```javascript
if (divisor === 0) console.error("Cannot divide by zero!");
```

---

### **6 : Modulus Assignment `(%=)`**

- **কাজ:** মান এর ভাগশেষ বের করে অ্যাসাইন করা।

```javascript
let x = 10;
x %= 3;   // x = x % 3
console.log(x); // 1
```

**Example (even-odd):**

```javascript
let number = 7;
if (number % 2 === 0) {
  console.log("Even");
} else {
  console.log("Odd");
}
```

✅ **Best practice:**  
`%=` সাধারণত বাকি মান (remainder) বা cycle type হিসাবের জন্য ব্যবহৃত হয়।

---

### **7 : Exponentiation Assignment `(**=)`**

- **কাজ:** মান Power বের করে অ্যাসাইন করা।

```javascript
let x = 2;
x **= 3; // x = x ** 3
console.log(x); // 8
```

⚠️ **Common mistake:**

```javascript
let y = 2;
y ^= 3;  // ❌ ভুল (এটা bitwise XOR)
```

✅ **Best practice:**  
Exponentiation এর জন্য `**=` ব্যবহার করতে হবে, কখনো `^=` নয়।

---

## **4. একসাথে একাধিক Assignment**

চাইলে এক লাইনেই একাধিক variable assign করা যায়:

```javascript
let a, b, c;
a = b = c = 10;
console.log(a, b, c); // Output: 10 10 10
```

⚠️ **সতর্কতা:**  
এভাবে assign করা allowed, কিন্তু readability কমে যায়।

✅ **Better practice:**

```javascript
let a = 10;
let b = 10;
let c = 10;
```

---

## **5. Type Coercion with Assignment**

JavaScript ডেটা টাইপ auto-convert করে ফেলতে পারে।

```javascript
let x = "5";
x += 2; // "52" (number না, string যোগ হয়েছে!)
```

✅ **Best practice:**

```javascript
let x = Number("5");
x += 2; // 7 ✅
```

---

## ⚠️ **6. Common Errors**

|ভুল কোড|সমস্যা|কারণ|
|---|---|---|
|`x += 2;`|ReferenceError|variable declare করা হয়নি|
|`const x = 5; x += 1;`|TypeError|constant variable পরিবর্তন করা যায় না|
|`name *= 2;`|NaN|string কে গুণ করা যায় না|
|`num /= 0;`|Infinity|0 দিয়ে ভাগ করা হয়েছে|
|`y ^= 3;`|ভুল ফলাফল|bitwise XOR হয়েছে, power নয়|

---

## 📝 **7. Best Practice Notes**

✅ সবসময় variable আগে declare করতে হবে (`let` বা `const`)  
✅ `const` variable-এ কোনো Assignment Operator ব্যবহার করা যাবে না (কারণ মান স্থির)  
✅ Arithmetic operation এর আগে value numeric কিনা যাচাই করতে হবে 
✅ `**` এর জায়গায় `^` কখনো ব্যবহার করা যাবে না  
✅ Readability বজায় রাখতে ছোট ছোট assignment আলাদা লাইনে লিখা ভালো 
✅ যখন string যোগ করা হবে, তখন type conversion বুঝে নিতে হবে (`+` string যোগও করতে পারে)

---
