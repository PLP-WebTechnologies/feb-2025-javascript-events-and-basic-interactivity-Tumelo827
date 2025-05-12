# 🎯 JavaScript Event Handling & Interactive Elements Assignment

Welcome to the **ultimate JavaScript playground**! 🎉 This assignment is where we turn boring web pages into dynamic, responsive, *alive* experiences. Get ready to master **event handling**, build **interactive components**, and validate forms like a pro! 💪

## 📁 Assignment Structure

```
📂 js-event-assignment/
├── index.html         # Your playground – where it all comes together
├── style.css          # Keep it cute (optional but encouraged)
└── script.js          # The JavaScript wizardry happens here
```

---

## 🧪 What to Build

Here’s what your interactive bundle of joy should include:

### 1. Event Handling 🎈  
- Button click ✅  
- Hover effects ✅  
- Keypress detection ✅  
- Bonus: A secret action for a *double-click* or *long press* 🤫

### 2. Interactive Elements 🎮  
- A button that changes text or color  
- An image gallery or slideshow  
- Tabs or accordion-style content  
- Bonus: Add some animation using JS or CSS ✨

### 3. Form Validation 📋✅  
- Required field checks  
- Email format validation  
- Password rules (e.g., min 8 characters)  
- Bonus: Real-time feedback while typing

---

## 🧙‍♂️ Pro Tips

- Keep your code clean and commented – your future self will thank you!
- Think about **user experience** – what makes your site more *fun* to use?
- Don’t be afraid to **Google and experiment** – that’s how real developers roll!

---

## 🎉 Now Go Make It Fun!

Remember – this isn't just code. It's your **first step toward creating magical user experiences**. So play around, break stuff (then fix it), and most of all, have FUN! 😄

Happy Coding! 💻✨  




<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Interactive JS Page</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      padding: 20px;
      background-color: #f8f8f8;
      line-height: 1.6;
    }

    h1, h2 {
      text-align: center;
    }

    button {
      padding: 10px 20px;
      margin: 10px;
      background-color: #0077cc;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    button:hover {
      background-color: #005fa3;
    }

    #magicBox {
      width: 150px;
      height: 150px;
      background-color: #eee;
      border: 3px dashed #ccc;
      margin: 20px auto;
      transition: transform 0.3s ease, background-color 0.3s ease;
    }

    #gallery img {
      width: 200px;
      margin: 10px;
      border-radius: 10px;
      transition: transform 0.2s;
    }

    #gallery img:hover {
      transform: scale(1.1);
    }

    .tab-content {
      display: none;
      padding: 10px;
      background: #fff;
      border: 1px solid #ccc;
      border-top: none;
    }

    .tabs {
      display: flex;
      gap: 10px;
    }

    .tabs button {
      background-color: #f4f4f4;
      color: #333;
      border: 1px solid #ccc;
    }

    .tabs button.active {
      background-color: #fff;
      border-bottom: none;
    }

    .feedback {
      color: red;
      font-size: 0.9em;
    }

    .valid {
      color: green;
    }
  </style>
</head>
<body>

  <h1>🎉 Interactive JavaScript Playground</h1>

  <!-- EVENT HANDLING -->
  <h2>1. Event Handling 🎈</h2>
  <button onclick="buttonClick()">Click Me</button>
  <div id="hoverBox" onmouseover="hoverEffect()" onmouseout="resetHover()" style="width:100px;height:100px;background:#ccc;margin:10px auto;"></div>
  <input type="text" placeholder="Type something..." onkeypress="detectKeypress(event)" style="padding:5px;">
  <button ondblclick="secretAction()">Double-Click Me 🤫</button>

  <!-- INTERACTIVE ELEMENTS -->
  <h2>2. Interactive Elements 🎮</h2>
  <button onclick="changeBox()">Change Box</button>
  <div id="magicBox"></div>

  <div id="gallery">
    <img src="https://picsum.photos/200/150?1" alt="gallery">
    <img src="https://picsum.photos/200/150?2" alt="gallery">
    <img src="https://picsum.photos/200/150?3" alt="gallery">
  </div>

  <div class="tabs">
    <button onclick="showTab('tab1')" class="active">Tab 1</button>
    <button onclick="showTab('tab2')">Tab 2</button>
  </div>
  <div id="tab1" class="tab-content" style="display:block;">This is Tab 1 content.</div>
  <div id="tab2" class="tab-content">This is Tab 2 content.</div>

  <!-- FORM VALIDATION -->
  <h2>3. Form Validation 📋✅</h2>
  <form onsubmit="return validateForm()" novalidate>
    <label>Name: <input type="text" id="name" required></label> <span id="nameFeedback" class="feedback"></span><br><br>
    <label>Email: <input type="email" id="email" required></label> <span id="emailFeedback" class="feedback"></span><br><br>
    <label>Password: <input type="password" id="password" required></label> <span id="passFeedback" class="feedback"></span><br><br>
    <button type="submit">Submit</button>
  </form>

  <script>
    // EVENT HANDLING
    function buttonClick() {
      alert("Button clicked!");
    }

    function hoverEffect() {
      document.getElementById("hoverBox").style.background = "#00b894";
    }

    function resetHover() {
      document.getElementById("hoverBox").style.background = "#ccc";
    }

    function detectKeypress(e) {
      console.log("Key pressed: " + e.key);
    }

    function secretAction() {
      alert("🎉 You found the hidden action!");
    }

    // INTERACTIVE ELEMENTS
    function changeBox() {
      const box = document.getElementById("magicBox");
      box.style.backgroundColor = "#ff7675";
      box.style.transform = "rotate(10deg)";
    }

    function showTab(tabId) {
      document.querySelectorAll(".tab-content").forEach(el => el.style.display = "none");
      document.querySelectorAll(".tabs button").forEach(btn => btn.classList.remove("active"));
      document.getElementById(tabId).style.display = "block";
      event.target.classList.add("active");
    }

    // FORM VALIDATION
    function validateForm() {
      const name = document.getElementById("name");
      const email = document.getElementById("email");
      const password = document.getElementById("password");

      let valid = true;

      if (name.value.trim() === "") {
        document.getElementById("nameFeedback").textContent = "Name is required.";
        valid = false;
      } else {
        document.getElementById("nameFeedback").textContent = "";
      }

      const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      if (!emailPattern.test(email.value)) {
        document.getElementById("emailFeedback").textContent = "Invalid email format.";
        valid = false;
      } else {
        document.getElementById("emailFeedback").textContent = "";
      }

      if (password.value.length < 8) {
        document.getElementById("passFeedback").textContent = "Password must be at least 8 characters.";
        valid = false;
      } else {
        document.getElementById("passFeedback").textContent = "";
      }

      return valid;
    }

    // REAL-TIME FEEDBACK
    document.getElementById("password").addEventListener("input", function () {
      const msg = document.getElementById("passFeedback");
      if (this.value.length >= 8) {
        msg.textContent = "✓ Strong password";
        msg.className = "feedback valid";
      } else {
        msg.textContent = "Password must be at least 8 characters.";
        msg.className = "feedback";
      }
    });
  </script>

</body>
</html>

