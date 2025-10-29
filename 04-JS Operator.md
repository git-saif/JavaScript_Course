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

#### **1 : Simple Assignment `(=)`**

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

#### **2 : Addition Assignment `(+=)`**

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

#### **3 : Subtraction Assignment `(-=)`**

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

#### **4 : Multiplication Assignment `(*=)`**

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

#### **5 : Division Assignment `(/=)`**

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

#### **6 : Modulus Assignment `(%=)`**

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

#### **7 : Exponentiation Assignment `(**=)`**

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

## **একসাথে একাধিক Assignment**

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

## **Type Coercion with Assignment**

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

## **Common Errors ⚠️**

|ভুল কোড|সমস্যা|কারণ|
|---|---|---|
|`x += 2;`|ReferenceError|variable declare করা হয়নি|
|`const x = 5; x += 1;`|TypeError|constant variable পরিবর্তন করা যায় না|
|`name *= 2;`|NaN|string কে গুণ করা যায় না|
|`num /= 0;`|Infinity|0 দিয়ে ভাগ করা হয়েছে|
|`y ^= 3;`|ভুল ফলাফল|bitwise XOR হয়েছে, power নয়|

---

## **Best Practice Notes 📝**

✅ সবসময় variable আগে declare করতে হবে (`let` বা `const`)  
✅ `const` variable-এ কোনো Assignment Operator ব্যবহার করা যাবে না (কারণ মান স্থির)  
✅ Arithmetic operation এর আগে value numeric কিনা যাচাই করতে হবে 
✅ `**` এর জায়গায় `^` কখনো ব্যবহার করা যাবে না  
✅ Readability বজায় রাখতে ছোট ছোট assignment আলাদা লাইনে লিখা ভালো 
✅ যখন string যোগ করা হবে, তখন type conversion বুঝে নিতে হবে (`+` string যোগও করতে পারে)

---


# **3. JavaScript Comparison Operators ⚖️**


**Comparison Operator** ব্যবহার করা হয় **দুইটি মানের (values) মধ্যে তুলনা (comparison)** করার জন্য। এর ফলাফল সবসময় হয় একটি **Boolean value**:

- `true` (যদি শর্ত সঠিক হয়)
- `false` (যদি শর্ত ভুল হয়)

---

### Example:

```javascript
let x = 5;
let y = 8;

console.log(x < y);  // true
console.log(x > y);  // false
```

---

## **Comparison Operators এর Types:**

| Operator | অর্থ                                             | উদাহরণ      | ফলাফল   |
| -------- | ------------------------------------------------ | ----------- | ------- |
| `==`     | সমান কিনা (value compare করে)                    | `5 == "5"`  | ✅ true  |
| `===`    | সম্পূর্ণ সমান কিনা (value + type compare করে)    | `5 === "5"` | ❌ false |
| `!=`     | সমান নয় কিনা (value compare করে)                 | `5 != "5"`  | ❌ false |
| `!==`    | সম্পূর্ণ সমান নয় কিনা (value + type compare করে) | `5 !== "5"` | ✅ true  |
| `>`      | বড় কিনা                                          | `10 > 5`    | true    |
| `<`      | ছোট কিনা                                         | `10 < 5`    | false   |
| `>=`     | বড় বা সমান কিনা                                  | `5 >= 5`    | true    |
| `<=`     | ছোট বা সমান কিনা                                 | `3 <= 5`    | true    |

---

#### **1 : Equal To `(==)`**

- **কাজ:** কেবলমাত্র value সমান কিনা, তা compare করে (type নয়)।

```javascript
console.log(5 == "5");   // true (type different হলেও মান একই)
console.log(0 == false); // true (auto type conversion হয়েছে)
```

⚠️ **Error-prone:**

```javascript
console.log(null == undefined); // true ❗ (unexpected behavior)
```

✅ **Best Practice:**  
👉 `==` এর পরিবর্তে `===` ব্যবহার করো (strict equality check এর জন্য)।

---

#### **2 : Strict Equal To `(===)`**

- **কাজ:**  value **এবং** data type — দুটোই সমান কিনা, তা compare করে।

```javascript
console.log(5 === "5");   // false (number vs string)
console.log(5 === 5);     // true
```

✅ **Best Practice:**  
সবসময় `===` ব্যবহার করো, কারণ এটা টাইপ coercion করে না।

---

#### **3 : Not Equal To `(!=)`**

- **কাজ:**  value সমান নয় কিনা, তা পরীক্ষা করে (type উপেক্ষা করে)।

```javascript
console.log(5 != "5"); // false (same value)
console.log(10 != "5"); // true
```

⚠️ **Type coercion হতে পারে** → ভুল ফলাফল আসতে পারে।

✅ তাই এর পরিবর্তে সবসময় `!==` ব্যবহার করা ভালো।

---

#### **4 : Strict Not Equal To `(!==)`**

- **কাজ:**  value এবং type উভয় সমান নয় কিনা, তা আলাদা কিনা পরীক্ষা করে।

```javascript
console.log(5 !== "5"); // true (type different)
console.log(5 !== 5);   // false
```

✅ **Best Practice:**  
সবসময় `!==` ব্যবহার করো।

---

#### **5 : Greater Than `(>)`**

- **কাজ:**  সংখ্যা (number) বড় কিনা, তা compare করার জন্য।

```javascript
console.log(10 > 5);   // true
console.log(5 > 10);   // false
```


⚠️ যদি string compare করো:

```javascript
console.log("b" > "a"); // true (alphabetically compare হয়)
console.log("12" > "2"); // false (string compare rule অনুযায়ী)
```

✅ **Best Practice:**  
string সংখ্যা হিসেবে compare করতে হলে আগে `Number()` দিয়ে convert করতে হবে।

---

#### **6 : Less Than `(<)`**

- **কাজ:**  সংখ্যা (number) ছোট কিনা, তা compare করে।

```javascript
let a = 3, b = 7;
console.log(a < b); // true
```

⚠️ **Type coercion trap:**

```javascript
console.log("25" < "3"); // true ❌ (string comparison)
```

✅ Fix:

```javascript
console.log(Number("25") < Number("3")); // false ✅
```

---

#### **7 : Greater Than or Equal To `(>=)`**

- **কাজ:**  সংখ্যা (number) বড় বা সমান কিনা, তা compare করে।

```javascript
console.log(5 >= 5); // true
console.log(8 >= 5); // true
console.log(2 >= 5); // false
```

✅ যখন শর্তের মধ্যে "বড় বা সমান" বোঝাতে হয়।

---

#### **8 : Less Than or Equal To `(<=)`**

- **কাজ:**  সংখ্যা (number) ছোট বা সমান কিনা, তা compare করে।

```javascript
console.log(5 <= 5); // true
console.log(3 <= 5); // true
console.log(7 <= 5); // false
```

✅ যখন শর্তের মধ্যে "ছোট বা সমান" বোঝাতে হয়।

---

## **Comparison in Conditional Statements 🧠**

Comparison Operators সাধারণত **if**, **while**, **for** এর মতো শর্তভিত্তিক statement-এ ব্যবহার করা হয়।

```javascript
let marks = 85;

if (marks >= 80) {
  console.log("A+ Grade");
} else if (marks >= 70) {
  console.log("A Grade");
} else {
  console.log("Fail");
}
```

---

## **Common Mistakes / Errors ⚠️**

|ভুল কোড|সমস্যা|কারণ|
|---|---|---|
|`if (x = 5)`|সবসময় true হয়|`=` হচ্ছে assignment operator|
|`"5" > 12`|false|string vs number compare|
|`null == 0`|false|JavaScript এর loose equality behavior|
|`undefined > 0`|false|undefined কে number হিসেবে convert করা যায় না|

✅ **Best Practice:**  
`if (x === 5)` এরকম **strict comparison** ব্যবহার করতে হবে।

---

## **Type Conversion Rules (Coercion Trap) 🧾**

JavaScript তুলনা করার সময় স্বয়ংক্রিয়ভাবে টাইপ convert করে ফেলে —  
এটাই **Type Coercion**।

```javascript
console.log(0 == "");      // true
console.log(false == "0"); // true
console.log(null == undefined); // true
```

👉 এগুলো অনেক সময় **bug তৈরি করে**।

✅ তাই **strict comparison (`===`, `!==`)** ব্যবহার করাই সবচেয়ে নিরাপদ।

---

## **Special Comparison Cases 🧩**

|Expression|Result|ব্যাখ্যা|
|---|---|---|
|`NaN == NaN`|false|NaN কখনো কারো সমান নয়|
|`NaN === NaN`|false|একইভাবে false|
|`isNaN(NaN)`|true|সঠিকভাবে চেক করতে হবে|
|`null == undefined`|true|loose equality true|
|`null === undefined`|false|strict equality false|

✅ **Best Practice:**  
NaN check করার জন্য সবসময় `Number.isNaN(value)` ব্যবহার করতে হবে।

---

## **Summary Table**

|Operator|কাজ|উদাহরণ|ফলাফল|
|---|---|---|---|
|`==`|মান সমান কিনা (type নয়)|`5 == "5"`|true|
|`===`|মান ও type সমান কিনা|`5 === "5"`|false|
|`!=`|মান ভিন্ন কিনা (type নয়)|`5 != "5"`|false|
|`!==`|মান ও type ভিন্ন কিনা|`5 !== "5"`|true|
|`>`|বড় কিনা|`10 > 5`|true|
|`<`|ছোট কিনা|`5 < 10`|true|
|`>=`|বড় বা সমান কিনা|`5 >= 5`|true|
|`<=`|ছোট বা সমান কিনা|`5 <= 10`|true|

---

## **Best Practice Notes 📝**

✅ সবসময় `===` ও `!==` ব্যবহার করতে হবে।
✅ string ও number compare করার আগে টাইপ এক করে নিতে হবে। 
✅ conditional check-এ `=` নয়, `==` বা `===` ব্যবহার করতে হবে।
✅ NaN চেক করতে `isNaN()` বা `Number.isNaN()` ব্যবহার করতে হবে।
✅ null ও undefined আলাদা জিনিস — strict comparison করতে হবে। 
✅ user input সবসময় type-convert করে compare করতে হবে।

---

# **4. JavaScript Logical Operators**

**Logical operators** এমন একটি Operator, যা মূলত **multiple conditions** একসাথে চেক করতে ব্যবহৃত হয়। এরা সাধারণত `true` বা `false` মান return করে।

## **Logical Operators এর Types:**

| Operator | নাম         | কাজ                       |
| -------- | ----------- | ------------------------- |
| `&&`     | Logical AND | সব শর্ত true হলে true দেয় |
| \|\|     | logical or  |                           |
| `!`      | Logical NOT | শর্তের উল্টো মান দেয়      |

---

#### **1 : Logical AND (&&)**

- **কাজ:** সব condition `true` হলে তবেই ফলাফল হবে `true`।

##### **Example-1: Basic**

```javascript
let age = 22;
let hasID = true;

if (age >= 18 && hasID) {
  console.log("You can enter the club!");
} else {
  console.log("Access denied!");
}
```

**Output:**  
`You can enter the club!`

**Explanation:**

- প্রথম condition `age >= 18` → true
- দ্বিতীয় condition `hasID` → true
- দুইটাই true ⇒ পুরো expression true ✅

---

##### **Example-2: একটাও false হলে পুরোটা false**

```javascript
let isLoggedIn = true;
let isAdmin = false;

if (isLoggedIn && isAdmin) {
  console.log("Welcome Admin!");
} else {
  console.log("Access denied!");
}
```

**Output:** `Access denied!`

**Reason:**  
একটা condition false ⇒ পুরোটা false।

---

##### **Short-circuiting Behavior**

```javascript
console.log(false && "Hello"); // Output: false
console.log(true && "Hello");  // Output: "Hello"
```

> `&&` operator **short-circuit** করে । প্রথম মান `false` হলে, পরের মান evaluate করে না।

---

#### **2 : Logical OR (||)**

- **কাজ:** অন্তত একটি condition true হলে পুরো expression true হবে।

##### **Example-1: Basic**

```javascript
let day = "Sunday";

if (day === "Saturday" || day === "Sunday") {
  console.log("Weekend!");
} else {
  console.log("Weekday!");
}
```

> **Output:** `Weekend!`

---

##### **Example-2: একটাও true না হলে false**

```javascript
let hasTicket = false;
let isVIP = false;

if (hasTicket || isVIP) {
  console.log("You can enter.");
} else {
  console.log("Entry denied!");
}
```

**Output:** `Entry denied!`

---

##### **Short-circuiting Behavior**

```javascript
console.log(true || "Hello");   // Output: true
console.log(false || "Hello");  // Output: "Hello"
```

> `||` operator **short-circuit** করে । প্রথম মান `true` হলে, পরের মান evaluate করে না।

---

#### **3 : Logical NOT (!)**

- **কাজ:** শর্তের **উল্টো** মান দেয়।

|Input|Output|
|---|---|
|true|false|
|false|true|

##### **Example:**

```javascript
let isOnline = false;

if (!isOnline) {
  console.log("User is offline");
} else {
  console.log("User is online");
}
```

**Output:** `User is offline`

---

##### **Double NOT (!!) ⚠️**

- **কাজ:** একটি value কে boolean এ convert করার জন্য ব্যবহার হয়।

```javascript
console.log(!!"Hello"); // true (non-empty string)
console.log(!!0);       // false (number zero)
console.log(!!null);    // false
console.log(!!{});      // true (object always truthy)
```

---

#### **Combined Example**

```javascript
let username = "Saiful";
let password = "12345";

if (username && password && password.length >= 5) {
  console.log("Login successful!");
} else {
  console.log("Invalid credentials!");
}
```

✅ **সব condition true হলে** → সফল  
❌ **যেকোনো একটি false হলে** → ব্যর্থ

---

#### **Common Mistakes (Error Case) ⚠️**

|ভুল কোড|সমস্যা|কারণ|
|---|---|---|
|`if (x && y)`|ReferenceError|যদি `x` বা `y` undefined থাকে|
|`" " && true`|true|Empty string truthy/falsey বুঝে নিতে হবে|
|`0||"Guest"`|
|`null && something`|null|প্রথম মান falsy, তাই দ্বিতীয়টা check হয় না|

---

#### **Truthy vs Falsy Values 💡**

-  JS-এ কিছু value সবসময় **false** হিসেবে বিবেচিত হয়।

|Falsy Values|True হিসেবে বিবেচিত নয়|
|---|---|
|`false`||
|`0`||
|`""` (empty string)||
|`null`||
|`undefined`||
|`NaN`||

সবকিছু ছাড়া বাকি সব **truthy**।

---

##### 🧠 Example:

```javascript
let name = "";

if (name) {
  console.log("Name exists");
} else {
  console.log("Name is empty");
}
```

> **Output:** `Name is empty` .কারণ খালি string `""` falsy value।

---

#### **Best Practice Notes 📝**

✅ সবসময় condition লেখার আগে নিশ্চিত হতে হবে — variable টি defined কিনা।  
✅ `&&` এবং `||` ব্যবহার করে fallback/default value নির্ধারণ করতে হবে।  
✅ Double NOT (`!!`) দিয়ে boolean conversion check করতে হবে।  
✅ Avoid confusing code — nested `&&`/`||` বেশি ব্যবহার করা যাবে না।  
✅ Remember: `&&` → সব true চাই, `||` → অন্তত একটি true চাই।

---

##### **Practical Example — Default Value 💡**

```javascript
let userName = "";
let displayName = userName || "Guest";

console.log(displayName); // Output: Guest
```

> এখানে যদি `userName` খালি বা undefined হয়, তাহলে `Guest` ব্যবহৃত হবে।

---

##### **Practical Example — Safe Property Access 💡**

```javascript
let user = null;

// Normally ❌ Error: Cannot read properties of null
// console.log(user.name);

console.log(user && user.name); // ✅ Output: null (safe check)
```

> `&&` দিয়ে null-check করা যায় — crash হবে না।

---

#### ✅ ** Summary Table**

|Operator|নাম|কাজ|উদাহরণ|ফলাফল|
|---|---|---|---|---|
|`&&`|AND|সব true হলে true|`true && true`|true|
|`||`|OR|যেকোনো একটি true হলে true|
|`!`|NOT|মান উল্টে দেয়|`!true`|false|

---

#### 🔚 ** Quick Recap:**

- `&&` → সব শর্ত সত্য হতে হবে
- `||` → অন্তত একটি শর্ত সত্য হলেই হবে
- `!` → মানের বিপরীত নেয়
- Truthy/Falsy বুঝে ব্যবহার করা সবচেয়ে জরুরি
- Short-circuit behavior কাজে লাগানো যায়

---
