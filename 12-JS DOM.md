## **DOM — সংজ্ঞা (Definition)**

👉 **DOM (Document Object Model)** হলো একটি **Tree-like Structure**,  
যেখানে HTML ডকুমেন্টের প্রতিটি অংশ (element, attribute, text) কে object হিসেবে represent করা হয়।

🧠 সহজভাবে বললে —  
HTML ডকুমেন্টকে JavaScript দিয়ে manipulate (পরিবর্তন) করতে হলে, সেই HTML কে object আকারে দেখতে হয় —  
এই object structure কেই বলা হয় DOM।

---

### Example HTML:

```html
<html>
  <body>
    <h1 id="title">Hello DOM</h1>
  </body>
</html>
```

JavaScript এ এটিকে DOM Object হিসেবে access করা যায়:

```javascript
document.getElementById("title").innerText; // "Hello DOM"
```

---

## **DOM Tree Structure**

```
Document
 └── html
      ├── head
      └── body
           ├── h1
           ├── p
           └── div
```

প্রতিটি HTML ট্যাগকে JavaScript এ একটি **node** হিসেবে ধরা হয়।  
যেমন — element node, text node, attribute node ইত্যাদি।

---

## **DOM Selectors (Element ধরার উপায়)**

|Method|Description|Example|
|---|---|---|
|`getElementById()`|নির্দিষ্ট id এর element ধরতে|`document.getElementById("title")`|
|`getElementsByClassName()`|class নাম অনুযায়ী element ধরতে|`document.getElementsByClassName("para")`|
|`getElementsByTagName()`|tag নাম অনুযায়ী ধরতে|`document.getElementsByTagName("p")`|
|`querySelector()`|CSS selector অনুযায়ী প্রথম element ধরে|`document.querySelector(".class")`|
|`querySelectorAll()`|CSS selector অনুযায়ী সব element ধরে|`document.querySelectorAll("p")`|

📦 Example:

```html
<h2 id="heading">Hello</h2>
<p class="para">Paragraph 1</p>
<p class="para">Paragraph 2</p>

<script>
let h = document.getElementById("heading");
let ps = document.querySelectorAll(".para");
console.log(h.innerText); // Hello
console.log(ps.length);   // 2
</script>
```

---

## **DOM Content পরিবর্তন করা**

|Property|কাজ|উদাহরণ|
|---|---|---|
|`innerText`|টেক্সট পরিবর্তন করে|`el.innerText = "Hello!"`|
|`innerHTML`|HTML কনটেন্ট পরিবর্তন করে|`el.innerHTML = "<b>Hi</b>"`|
|`textContent`|Hidden text সহ সব টেক্সট নেয়|`el.textContent`|

📦 Example:

```javascript
document.getElementById("heading").innerText = "Welcome!";
document.getElementById("heading").style.color = "blue";
```

---

## **DOM Attribute পরিবর্তন করা**

|Method|কাজ|
|---|---|
|`getAttribute()`|attribute এর মান নেয়|
|`setAttribute()`|attribute এর মান পরিবর্তন করে|
|`removeAttribute()`|attribute মুছে দেয়|
|`hasAttribute()`|attribute আছে কিনা চেক করে|

📦 Example:

```html
<img id="photo" src="old.jpg">

<script>
let img = document.getElementById("photo");
img.setAttribute("src", "new.jpg");
console.log(img.getAttribute("src")); // "new.jpg"
</script>
```

---

## **DOM Style পরিবর্তন করা**

HTML element এর CSS style JS দিয়ে পরিবর্তন করা যায়।

📦 Example:

```html
<p id="text">Change my color!</p>

<script>
let txt = document.getElementById("text");
txt.style.color = "red";
txt.style.fontSize = "24px";
txt.style.backgroundColor = "yellow";
</script>
```

⚡ **Best Practice:**  
Inline style না দিয়ে **class যোগ/বাদ** করা ভালো:

```javascript
txt.classList.add("highlight");
txt.classList.remove("hidden");
```

---

## **DOM Element Create, Append & Remove**

### ✅ Create Element

```javascript
let div = document.createElement("div");
div.innerText = "Hello New Element";
```

### ✅ Append Element

```javascript
document.body.appendChild(div);
```

### ✅ Remove Element

```javascript
document.body.removeChild(div);
```

---

## **Insert Element (Before / After)**

```javascript
let newP = document.createElement("p");
newP.innerText = "Inserted paragraph";

let parent = document.getElementById("container");
let oldP = document.getElementById("oldPara");

parent.insertBefore(newP, oldP); // oldP এর আগে ইনসার্ট
```

---

## **Class & ID Control**

```javascript
let el = document.getElementById("box");

el.classList.add("active");     // নতুন class যোগ
el.classList.remove("hidden");  // class বাদ
el.classList.toggle("dark");    // class থাকলে বাদ, না থাকলে যোগ
el.classList.contains("active"); // true / false
```

---

## **DOM Traversing (Parent, Child, Sibling)**

|Property|Description|
|---|---|
|`parentNode`|প্যারেন্ট element নেয়|
|`children`|child element গুলো দেয়|
|`firstElementChild`|প্রথম child|
|`lastElementChild`|শেষ child|
|`nextElementSibling`|পরের sibling element|
|`previousElementSibling`|আগের sibling element|

📦 Example:

```html
<ul id="list">
  <li>One</li>
  <li>Two</li>
  <li>Three</li>
</ul>

<script>
let list = document.getElementById("list");
console.log(list.firstElementChild.textContent); // One
console.log(list.children[1].textContent); // Two
</script>
```

---

## **DOM Event Handling**

ইভেন্ট add করা যায় element এ সরাসরি।

📦 Example:

```html
<button id="btn">Click</button>
<p id="output"></p>

<script>
document.getElementById("btn").addEventListener("click", function(){
  document.getElementById("output").innerText = "Button Clicked!";
});
</script>
```

---

## **Form Input Value Access**

```html
<input type="text" id="name" placeholder="Enter name">
<button id="save">Save</button>

<script>
document.getElementById("save").addEventListener("click", function(){
  let name = document.getElementById("name").value;
  alert("Hello " + name);
});
</script>
```

---

## **DOM Nodes vs Elements**

|Node Type|Description|
|---|---|
|Element Node|HTML ট্যাগ (যেমন `<p>`)|
|Text Node|টেক্সট কনটেন্ট|
|Attribute Node|Element এর attribute গুলো|

📦 Example:

```javascript
let el = document.getElementById("text");
console.log(el.nodeName); // "P"
console.log(el.nodeType); // 1 (element node)
```

---

## **DOM Events + Dynamic Elements Example**

📦 Example:

```html
<button id="add">Add Item</button>
<ul id="list"></ul>

<script>
let addBtn = document.getElementById("add");
let list = document.getElementById("list");

addBtn.addEventListener("click", function(){
  let li = document.createElement("li");
  li.textContent = "New Item";
  list.appendChild(li);
});
</script>
```

---

## **Best Practices**

|ভুল|সঠিক|
|---|---|
|Inline JS ব্যবহার করা|Separate JS ফাইল ব্যবহার করা|
|সরাসরি innerHTML ব্যবহার|textContent বা createElement ব্যবহার|
|Inline CSS সেট করা|classList দিয়ে CSS handle করা|
|Loop এ DOM update করা|Fragment বা batch update ব্যবহার|
|Page load হওয়ার আগে DOM access|`DOMContentLoaded` event ব্যবহার|

📦 Example:

```javascript
document.addEventListener("DOMContentLoaded", () => {
  console.log("DOM fully loaded!");
});
```

---

## **Summary Table**

|বিষয়|কাজ|
|---|---|
|DOM|HTML কে object tree আকারে উপস্থাপন করে|
|Selector|Element ধরার পদ্ধতি|
|innerText / innerHTML|কনটেন্ট পরিবর্তন|
|setAttribute / getAttribute|Attribute নিয়ন্ত্রণ|
|createElement / appendChild|নতুন element তৈরি|
|classList|Class নিয়ন্ত্রণ|
|parentNode / children|DOM ট্রাভার্সিং|
|addEventListener|ইভেন্ট সংযোজন|
|preventDefault|ডিফল্ট কাজ বন্ধ|
|removeChild|Element মুছে ফেলা|

---
