---

# 🧩 **JavaScript Events (Basic to Advance)**

---
## **Event — সংজ্ঞা (Definition)**

👉 **Event** হলো এমন কোনো কাজ বা ঘটনা (action) যা browser এ ঘটে।  
যেমনঃ

- একজন ব্যবহারকারী **button ক্লিক করে**,
- **mouse সরায়**,
- **keyboard এ কিছু লেখে**,
- **page load হয়** —  
    এসবই হলো JavaScript event।

---

## **Event এর ধরন (Types of Events)**

|Event Type|Description|Example|
|---|---|---|
|Mouse Events|মাউসের কাজের সাথে সম্পর্কিত|`onclick`, `onmouseover`, `onmouseout`|
|Keyboard Events|কীবোর্ডের কাজের সাথে সম্পর্কিত|`onkeydown`, `onkeyup`, `onkeypress`|
|Form Events|ফর্মের কাজের সাথে সম্পর্কিত|`onsubmit`, `onchange`, `onfocus`, `onblur`|
|Window Events|ব্রাউজার বা উইন্ডো ইভেন্ট|`onload`, `onresize`, `onscroll`, `onunload`|
|Clipboard Events|কপি-পেস্ট সম্পর্কিত|`oncopy`, `oncut`, `onpaste`|

---

## **Event Handling (ইভেন্ট ধরার উপায়)**

JavaScript এ ইভেন্ট হ্যান্ডেল করার ৩টি প্রধান উপায় আছে 👇

---

### **Method 1: Inline Event Handler (HTML এর মধ্যে লেখা)**

```html
<button onclick="alert('Button Clicked!')">Click Me</button>
```

⚠️ **Cons:** HTML ও JS একসাথে মেশানো ভালো practice নয়।

---

### **Method 2: DOM Property Method (Script এর মধ্যে)**

```html
<button id="btn">Click</button>

<script>
document.getElementById("btn").onclick = function(){
  alert("Button clicked!");
};
</script>
```

---

### **Method 3: addEventListener() (✅ Best Practice)**

```html
<button id="btn">Click</button>

<script>
document.getElementById("btn").addEventListener("click", function(){
  alert("Clicked using addEventListener!");
});
</script>
```

**🧠 ব্যাখ্যা:**

- প্রথম parameter → ইভেন্ট টাইপ (যেমন `"click"`)
- দ্বিতীয় parameter → callback function

---

## **Common Mouse Events Example**

|Event|কাজ|
|---|---|
|click|ক্লিক করলে|
|dblclick|ডাবল ক্লিক করলে|
|mouseover|মাউস hover করলে|
|mouseout|মাউস চলে গেলে|
|mousedown|মাউস বোতাম চেপে ধরলে|
|mouseup|মাউস বোতাম ছেড়ে দিলে|

📦 উদাহরণ:

```html
<button id="btn">Hover Me</button>

<script>
let btn = document.getElementById("btn");

btn.addEventListener("mouseover", function(){
  btn.style.background = "green";
});

btn.addEventListener("mouseout", function(){
  btn.style.background = "";
});
</script>
```

---

## **Keyboard Events Example**

|Event|কাজ|
|---|---|
|keydown|কোনো কি চাপলে|
|keyup|কি ছেড়ে দিলে|
|keypress|কি প্রেস করলে (deprecated কিছু browser এ)|

📦 উদাহরণ:

```html
<input type="text" id="txt">

<script>
let input = document.getElementById("txt");

input.addEventListener("keydown", function(event){
  console.log("Pressed key:", event.key);
});
</script>
```

---

## **Form Events Example**

|Event|কাজ|
|---|---|
|submit|ফর্ম সাবমিট করলে|
|change|ইনপুট পরিবর্তন হলে|
|focus|ইনপুটে ক্লিক করলে|
|blur|ইনপুট ছেড়ে দিলে|

📦 উদাহরণ:

```html
<form id="myForm">
  <input type="text" id="name">
  <button type="submit">Send</button>
</form>

<script>
document.getElementById("myForm").addEventListener("submit", function(e){
  e.preventDefault(); // ফর্ম রিফ্রেশ বন্ধ করে
  alert("Form submitted!");
});
</script>
```

---

## **Event Object**

প্রতিটি ইভেন্ট ঘটলে, JavaScript একটি **Event Object** তৈরি করে যা ইভেন্ট সম্পর্কিত তথ্য বহন করে।

📦 উদাহরণ:

```html
<button id="btn">Click</button>

<script>
document.getElementById("btn").addEventListener("click", function(e){
  console.log(e.type); // click
  console.log(e.target); // <button> element
});
</script>
```

|Property|Description|
|---|---|
|`e.type`|ইভেন্ট টাইপ (click, keydown ইত্যাদি)|
|`e.target`|যে এলিমেন্টে ইভেন্ট ঘটেছে|
|`e.preventDefault()`|ডিফল্ট আচরণ বন্ধ করে|
|`e.stopPropagation()`|bubbling বন্ধ করে|

---

## **Event Propagation**

Event Propagation হলো ইভেন্টের প্রবাহ (flow)।

দুইভাবে ঘটে 👇

1. **Capturing Phase (outer → inner)**
    
2. **Bubbling Phase (inner → outer)**
    

📦 উদাহরণ:

```html
<div id="parent">
  <button id="child">Click</button>
</div>

<script>
document.getElementById("parent").addEventListener("click", ()=> {
  console.log("Parent clicked!");
}, true); // capturing phase

document.getElementById("child").addEventListener("click", ()=> {
  console.log("Child clicked!");
}, false); // bubbling phase
</script>
```

---

## **Event Delegation**

যদি অনেক child element এ ইভেন্ট লাগে, তবে parent এ একটি ইভেন্ট ব্যবহার করো।

📦 উদাহরণ:

```html
<ul id="list">
  <li>Apple</li>
  <li>Banana</li>
  <li>Mango</li>
</ul>

<script>
document.getElementById("list").addEventListener("click", function(e){
  if(e.target.tagName === "LI"){
    console.log("Clicked:", e.target.textContent);
  }
});
</script>
```

✅ Best Practice:  
Event Delegation DOM performance বাড়ায় এবং cleaner কোড দেয়।

---

## **Remove Event Listener**

যখন দরকার নেই তখন ইভেন্ট বন্ধ করতে পারো।

```javascript
function greet(){
  alert("Hello!");
}

btn.addEventListener("click", greet);
btn.removeEventListener("click", greet);
```

---

## **Window Events Example**

|Event|কাজ|
|---|---|
|load|পেজ লোড হলে|
|resize|উইন্ডো সাইজ পরিবর্তন হলে|
|scroll|স্ক্রল করলে|
|unload|পেজ বন্ধ হলে|

📦 উদাহরণ:

```javascript
window.addEventListener("load", ()=>console.log("Page Loaded"));
window.addEventListener("resize", ()=>console.log("Resized!"));
window.addEventListener("scroll", ()=>console.log("Scrolling..."));
```

---

## **Common Mistakes & Best Practice**

|Mistake|Best Practice|
|---|---|
|Inline event ব্যবহার|JS থেকে addEventListener ব্যবহার|
|একই ইভেন্টে একাধিক function সরাসরি কল|Named function ব্যবহার|
|preventDefault ভুলে যাওয়া|ফর্ম সাবমিটে সবসময় e.preventDefault()|
|bubbling নিয়ন্ত্রণ না করা|stopPropagation() ব্যবহার|
|বড় অ্যাপ এ child element এ event দেওয়া|event delegation ব্যবহার করা|

---

## **Summary Table**

|বিষয়|ব্যাখ্যা|
|---|---|
|Event|Browser এ কোনো Action|
|Event Type|Mouse, Keyboard, Form, Window|
|addEventListener|ইভেন্ট ধরার আধুনিক পদ্ধতি|
|Event Object|ইভেন্ট সম্পর্কিত তথ্য|
|Propagation|Bubbling & Capturing flow|
|Delegation|Parent এ event দিয়ে child handle|
|preventDefault|Default কাজ বন্ধ করে|
|stopPropagation|Bubble flow বন্ধ করে|

---
