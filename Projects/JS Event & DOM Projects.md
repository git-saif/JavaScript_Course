## Project-1 (Simple DOM Event):

```html
<div class="col-5 border ">
	<form action="" id="form-1" onkeypress="pressKey()" >
	  <h4 class="text-center">Form - 1 
		<span id="name-1" class="fs-5 text-success"></span>
		<span id="email-1" class="fs-5 text-success"></span>
		<span id="massage-1" class="fs-5 text-success"></span>
	  </h4>
	  
	  <div class="mb-3 row">
		<label for="Name" class="col-sm-2 col-form-label">Name</label>
		<div class="col-sm-10">
		  <input type="Text" class="form-control" id="inputName" placeholder="Enter Your Name">
		</div>
	  </div>
	  
	  <div class="mb-3 row">
		<label for="Email" class="col-sm-2 col-form-label">E-Mail</label>
		<div class="col-sm-10">
		  <input type="email" class="form-control" id="inputEmail" placeholder="Enter Your E-Mail" oninput="emailField()">
		</div>
	  </div>

	  <div class="mb-3 row">
		<label for="Massage" class="col-sm-2 col-form-label">Massage</label>
		<div class="col-sm-10">
		  <textarea class="form-control" id="inputMassage" rows="3" placeholder="Enter Your Massage"></textarea>
		</div>
	  </div>
	</form>
</div>
```

```js
// Name field Event =========>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
document.getElementById("inputName").oninput = function () {
  document.getElementById("name-1").innerHTML = "(Name Field is Typing)";
  document.getElementById("email-1").innerHTML = ""; // Hide the email field Info
  document.getElementById("massage-1").innerHTML = ""; // Hide the massage field Info
}

// Email field Event =========>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
document.getElementById("inputEmail").oninput = function () {
  document.getElementById("email-1").innerHTML = "(Email Field is Typing)";
  document.getElementById("name-1").innerHTML = ""; // Hide the name field Info
  document.getElementById("massage-1").innerHTML = ""; // Hide the massage field Info
}

// Massage field Event =========>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
document.getElementById("inputMassage").oninput = function () {
  document.getElementById("massage-1").innerHTML = "(Massage Field is Typing)";
  document.getElementById("name-1").innerHTML = ""; // Hide the name field Info
  document.getElementById("email-1").innerHTML = ""; // Hide the email field Info
}
```
