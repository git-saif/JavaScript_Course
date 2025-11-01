## **JavaScript Object Definition**

**Object** হলো এমন একটি data structure যা **key–value pair** আকারে ডেটা সংরক্ষণ করে।  অর্থাৎ প্রতিটি ডেটার একটি **নাম (key)** এবং একটি **মান (value)** থাকে।

📦 Examples:

```javascript
let person = {
  name: "Saiful",
  age: 25,
  city: "Dhaka"
};
```

---

## **Object Structure**

```javascript
let objectName = {
  key1: value1,
  key2: value2,
  key3: value3
};
```

🔸 **key:** সবসময় string বা symbol  
🔸 **value:** হতে পারে string, number, boolean, array, function, বা এমনকি অন্য object ও।

---

## **Object Creation এর ৩টি প্রধান উপায়**

| উপায়                         | উদাহরণ                                                | বর্ণনা                                  |
| ---------------------------- | ----------------------------------------------------- | --------------------------------------- |
| **Object Literal**           | `let obj = {name: "Saiful"};`                         | সবচেয়ে সহজ ও জনপ্রিয়                    |
| **new Object() Constructor** | `let obj = new Object(); obj.name = "Saiful";`        | কম ব্যবহৃত                              |
| **Object.create()**          | `let obj = Object.create(null); obj.name = "Saiful";` | Prototype ছাড়া object তৈরি করতে ব্যবহৃত |

---

## **Object Access করার উপায়**

### 1. Dot Notation:

```javascript
console.log(person.name); // Output: Saiful
```

### 1. Bracket Notation:

```javascript
console.log(person["age"]); // Output: 25
```

⚠️ **Note:**  
যদি key তে space থাকে, তাহলে bracket notation ব্যবহার করতে হবে।

```javascript
let car = {"car name": "Toyota"};
console.log(car["car name"]); // ✅ Works
console.log(car.car name);    // ❌ Error
```

---

## **Object Add / Update Property**

### Update existing property:

```javascript
person.age = 26;
```

### Add new property:

```javascript
person.country = "Bangladesh";
```

---

## **Delete Property**

```javascript
delete person.city;
console.log(person);
```

---

## **Nested Object**

Object এর ভিতরে Object থাকতে পারে।

```javascript
let user = {
  name: "Saiful",
  contact: {
    email: "saiful@example.com",
    phone: "01700000000"
  }
};

console.log(user.contact.email); // Output: saiful@example.com
```

---

## **Object Method (Function inside Object)**

👉 যখন কোনো Function Object এর property হয়, সেটিকে **method** বলা হয়।

```javascript
let person = {
  name: "Karim",
  greet: function() {
    console.log("Hello, " + this.name);
  }
};

person.greet(); // Output: Hello, Karim
```

**ব্যাখ্যা:**  
`this` বর্তমান object কে নির্দেশ করে।

---

## **Object Display করার বিভিন্ন উপায়**

|পদ্ধতি|কাজ|
|---|---|
|`console.log(obj)`|সরাসরি পুরো object দেখায়|
|`for...in`|প্রতিটি key/value ঘুরে দেখা যায়|
|`Object.keys(obj)`|সব key ফেরত দেয়|
|`Object.values(obj)`|সব value ফেরত দেয়|
|`Object.entries(obj)`|key–value জোড়া ফেরত দেয়|
|`JSON.stringify(obj)`|object কে JSON string এ রূপান্তর করে|

### Examples:

```javascript
let car = {brand: "Toyota", model: "Corolla", year: 2020};

console.log(Object.keys(car));    // ['brand','model','year']
console.log(Object.values(car));  // ['Toyota','Corolla',2020]
console.log(Object.entries(car)); // [['brand','Toyota'],['model','Corolla'],['year',2020]]
console.log(JSON.stringify(car)); // {"brand":"Toyota","model":"Corolla","year":2020}
```

---

## **Looping through Object**

### for...in Loop:

```javascript
let car = {brand: "Toyota", model: "Corolla", year: 2020};

for (let key in car) {
  console.log(key + " : " + car[key]);
}
```

**Output:**

```
brand : Toyota
model : Corolla
year : 2020
```

---

## **Check if Property Exists**

```javascript
let student = {name: "Rahim", age: 20};

console.log("age" in student);   // true
console.log("grade" in student); // false
```

---

## **Copy Object (Reference Issue)**

Objects হলো **reference type**, তাই সরাসরি assign করলে একই মেমোরি reference হয়।

⚠️ ভুল পদ্ধতি:

```javascript
let obj1 = {a: 10};
let obj2 = obj1;
obj2.a = 20;
console.log(obj1.a); // Output: 20 ❌
```

✅ সঠিক পদ্ধতি (Shallow Copy):

```javascript
let obj1 = {a: 10};
let obj2 = Object.assign({}, obj1);
obj2.a = 20;
console.log(obj1.a); // Output: 10 ✅
```

---

## **Object Compare Problem**

Objects কে `==` বা `===` দিয়ে compare করলে শুধু reference চেক হয়, value নয়।

```javascript
let a = {x:1};
let b = {x:1};
console.log(a === b); // false ❌
```

✅ value তুলনা করতে হলে:

```javascript
JSON.stringify(a) === JSON.stringify(b); // true ✅
```

---

## **Object Utility Methods**

|Method|কাজ|
|---|---|
|`Object.keys(obj)`|সব property নাম ফেরত দেয়|
|`Object.values(obj)`|সব property value ফেরত দেয়|
|`Object.entries(obj)`|key–value pair array ফেরত দেয়|
|`Object.assign(target, source)`|এক object থেকে আরেক object এ copy করে|
|`Object.freeze(obj)`|object কে পরিবর্তনযোগ্যতা বন্ধ করে|
|`Object.seal(obj)`|নতুন property যোগ করা বন্ধ, কিন্তু পুরান property update করা যায়|

---

## **typeof Operator দিয়ে Object চেক**

```javascript
typeof {name: "Saiful"}; // "object"
typeof null;              // "object" ⚠️ (JS bug)
```

---

## **Common Mistakes & Best Practices**

|বিষয়|ভুল উদাহরণ|সঠিক উদাহরণ|
|---|---|---|
|Property তে space|`car.car name` ❌|`car["car name"]` ✅|
|Object copy|`obj2 = obj1` ❌|`Object.assign({}, obj1)` ✅|
|Compare|`a == b` ❌|`JSON.stringify(a) === JSON.stringify(b)` ✅|
|Missing comma|`{a:10 b:20}` ❌|`{a:10, b:20}` ✅|
|Missing quote|`{car name:"BMW"}` ❌|`{"car name":"BMW"}` ✅|

---

## **Object Display Best Practice Summary**

|পদ্ধতি|কাজ|
|---|---|
|`console.log(obj)`|দ্রুত দেখা|
|`for...in`|key/value লুপ করা|
|`Object.keys()` / `Object.values()`|key বা value array দেখা|
|`JSON.stringify(obj)`|Object কে পাঠানোর উপযোগী JSON string করা|

---

## **Summary Table:**

|বিষয়|কাজ|
|---|---|
|Object|Key-Value pair data store|
|Access|`obj.key` বা `obj["key"]`|
|Add / Update|`obj.key = value`|
|Delete|`delete obj.key`|
|Nested Object|Object এর ভিতরে Object|
|Method|Function inside Object|
|Display|console.log / JSON.stringify|
|Copy|`Object.assign({}, obj)`|
|Compare|`JSON.stringify(obj1) === JSON.stringify(obj2)`|
|Check Property|`"key" in obj`|
|Freeze / Seal|Object পরিবর্তন প্রতিরোধ|
|Loop|`for...in`|

---

## **Final Note: Best Practice Tips**

1. Object literal ব্যবহার করা সবচেয়ে ভালো।
2. Property নামের মধ্যে space থাকলে quote দেয়া।
3. Reference বুঝে কাজ করতে হবে — copy vs original object।
4. Compare করার সময় সবসময় stringify করতে হবে (deep compare না চাইলে)।
5. Data পাঠাতে বা save করতে `JSON.stringify()` ব্যবহার করতে হবে।

---
