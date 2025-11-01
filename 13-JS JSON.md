## **JSON কী?**

👉 **JSON (JavaScript Object Notation)** হলো **data exchange format**,  যা সাধারণত **server ↔ client** এর মধ্যে ডেটা আদান-প্রদানের জন্য ব্যবহার করা হয়।

📦 Example:

```json
{
  "name": "Saiful",
  "age": 25,
  "city": "Dhaka"
}
```

🔸 **JSON** দেখতে JavaScript Object এর মতো, কিন্তু এটি **pure text format**।

---

## **JSON vs JavaScript Object**

|বিষয়|JSON|JavaScript Object|
|---|---|---|
|ফরম্যাট|Text|Key-value pair|
|Key|অবশ্যই **"double quotes** এ থাকতে হবে|quotes না দিলেও চলে|
|Value|কেবল string, number, boolean, array, object, null|Function, undefined ইত্যাদি থাকতে পারে|
|ব্যবহার|Data transfer|Programming logic|

📦 Example:

```javascript
// ✅ JSON
let jsonData = '{"name":"Saiful","age":25}';

// ✅ JavaScript Object
let obj = {name: "Saiful", age: 25};
```

---

## **JSON থেকে JavaScript Object বানানো**

👉 JSON string কে JavaScript object এ রূপান্তর করা হয় `JSON.parse()` দিয়ে।

📦 Example:

```javascript
let jsonStr = '{"name":"Saiful","age":25,"skills":["HTML","JS","PHP"]}';
let user = JSON.parse(jsonStr);

console.log(user.name); // "Saiful"
console.log(user.skills[1]); // "JS"
```

---

## **JavaScript Object থেকে JSON বানানো**

👉 Object কে JSON string এ রূপান্তর করা হয় `JSON.stringify()` দিয়ে।

📦 Example:

```javascript
let user = { name: "Saiful", age: 25, city: "Dhaka" };
let jsonStr = JSON.stringify(user);

console.log(jsonStr);
// Output: {"name":"Saiful","age":25,"city":"Dhaka"}
```

---

## **Nested JSON**

📦 Example:

```json
{
  "user": {
    "name": "Saiful",
    "info": {
      "email": "saiful@example.com",
      "skills": ["HTML", "CSS", "JS"]
    }
  }
}
```

👉 Access:

```javascript
let data = {
  user: {
    name: "Saiful",
    info: { email: "saiful@example.com", skills: ["HTML", "CSS", "JS"] }
  }
};

console.log(data.user.info.email); // "saiful@example.com"
console.log(data.user.info.skills[2]); // "JS"
```

---

## **JSON Array (Objects এর লিস্ট)**

📦 Example:

```json
[
  {"id": 1, "name": "Saiful"},
  {"id": 2, "name": "Rakib"},
  {"id": 3, "name": "Hasan"}
]
```

👉 Access:

```javascript
let jsonStr = '[{"id":1,"name":"Saiful"},{"id":2,"name":"Rakib"}]';
let users = JSON.parse(jsonStr);

console.log(users[0].name); // "Saiful"
```

---

## **JSON Looping**

📦 Example:

```javascript
let users = [
  { name: "Saiful", age: 25 },
  { name: "Rakib", age: 22 },
  { name: "Hasan", age: 27 }
];

for (let user of users) {
  console.log(user.name + " is " + user.age + " years old.");
}
```

---

## **JSON এবং Local Storage**

Browser এর **localStorage** এ JSON ব্যবহার করা হয় data সংরক্ষণের জন্য।

📦 Example:

```javascript
let user = { name: "Saiful", age: 25 };

// Object → JSON → Store
localStorage.setItem("user", JSON.stringify(user));

// Retrieve → JSON → Object
let data = JSON.parse(localStorage.getItem("user"));
console.log(data.name); // "Saiful"
```

---

## **JSON ফাইল থেকে ডেটা আনা (Fetch API)**

📦 উদাহরণ (data.json ফাইল থেকে ডেটা পড়া):

```javascript
fetch("data.json")
  .then(res => res.json())
  .then(data => {
    console.log(data);
  });
```

🧠 এখানে `.json()` method response কে JSON object এ রূপান্তর করে।

---

## **JSON Error Handling**

যদি JSON data invalid হয়, তাহলে `JSON.parse()` error দেয়।  
তাই `try...catch` ব্যবহার করতে হয়।

📦 Example:

```javascript
let jsonStr = '{"name":"Saiful", "age":25'; // missing closing brace

try {
  let user = JSON.parse(jsonStr);
} catch (error) {
  console.log("Invalid JSON:", error.message);
}
```

---

## **JSON Advanced — Replacer & Space Parameter**

`JSON.stringify()` এর দ্বিতীয় ও তৃতীয় প্যারামিটার দিয়ে **custom control** করা যায়।

📦 Example:

```javascript
let user = { name: "Saiful", age: 25, city: "Dhaka" };

// শুধু নির্দিষ্ট key রাখতে চাই
let str = JSON.stringify(user, ["name", "city"]);
console.log(str); // {"name":"Saiful","city":"Dhaka"}

// সুন্দরভাবে ফরম্যাট করা JSON
let pretty = JSON.stringify(user, null, 4);
console.log(pretty);
```

---

## **JSON.stringify() Limitation**

JSON-এ function, date, undefined, Symbol ইত্যাদি থাকে না।

📦 Example:

```javascript
let data = {
  name: "Saiful",
  dob: new Date(),
  show: function(){ console.log("Hello"); },
  undef: undefined
};

console.log(JSON.stringify(data));
// Output: {"name":"Saiful","dob":"2025-10-28T14:30:00.000Z"}
```

---

## **JSON Deep Copy (Clone Object)**

📦 Example:

```javascript
let obj1 = { name: "Saiful", info: { city: "Dhaka" } };
let obj2 = JSON.parse(JSON.stringify(obj1));

obj2.info.city = "Rajshahi";

console.log(obj1.info.city); // "Dhaka" — unaffected
```

---

## **Summary Table**

|Method|কাজ|
|---|---|
|`JSON.parse()`|JSON string → JavaScript Object|
|`JSON.stringify()`|Object → JSON string|
|`fetch(url).then(res => res.json())`|Server থেকে JSON পড়া|
|`localStorage.setItem()`|Data সংরক্ষণ|
|`localStorage.getItem()`|Data পড়া|
|`try...catch`|Invalid JSON Handle|

---

## **Real-Life Example (API Data Render)**

📦 Example:

```html
<ul id="list"></ul>

<script>
fetch("https://jsonplaceholder.typicode.com/users")
  .then(res => res.json())
  .then(users => {
    let output = "";
    users.forEach(u => {
      output += `<li>${u.name} (${u.email})</li>`;
    });
    document.getElementById("list").innerHTML = output;
  });
</script>
```

---
