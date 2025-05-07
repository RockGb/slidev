---
layout: center
transition: fade-out
---

# [Month 1 Week 2]{.gradient-text}

<!-- CSS styling for .gradient-text class -->
<style>
    .gradient-text {
      background: linear-gradient(45deg, #4EC5D4 10%, #008080 20%);
      -webkit-background-clip: text;
      -moz-background-clip: text;
      -webkit-text-fill-color: transparent;
      -moz-text-fill-color: transparent;
      font-size: 2em; 
    }
   
</style>

---

## [📄 DOM in JavaScript (Selecting an Element by Its Unique Identifier (Id) and Styling It Within JavaScript)]{.text-teal-400}

<br>

### Summary:
<v-clicks>

- DOM (also known as **Document Object Model**) is the object representation of HTML.  
- An HTML document could be declared with an empty body.  
- The **Id** of each empty element node can then be selected using `querySelector` or `getElementById`.  
- The `innerHTML` can then be assigned a value after a variable has been declared.  
- The selected elements can be styled as preferred within the JavaScript code.

</v-clicks>

---

### Example of a Document with an Empty Body

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="./index.js" defer></script>
    <title>Dom in JavaScript</title>
  </head>
  <body>
    <div id="container">
      <h1 id="circle_5"></h1>
      <p id="semester_2"></p>
    </div>
  </body>
</html>
```

<br>

**Example of Selecting an Element by Its Unique Identifier (Id) Using `querySelector` and `getElementById`, and Styling the Selected Elements...**


---

You can select HTML elements by their unique `id` using either `querySelector` or `getElementById`. After selection, you can modify their content and apply styles directly with JavaScript.

```js
//Selecting elements by id using the querySelector
const divElement = document.getElementById("container");
const h1Element = document.querySelector("#circle_5");
const h2Element = document.getElementById("semester_2");
//throw an error if elements are not found
if (h1Element === null) {
}
if (h2Element === null) {
}
//If found, display these messages into the inner text and style it
divElement.style =
  "Justify-content: center; text-align: center; background-color: #f7f7f7; padding: 20px; margin: 20px 0; border: 1px solid #ccc;border-radius: 15px;";
h1Element.innerHTML = "Altschool FrontEnd Circle-5";
h2Element.innerHTML =
  "Summary of what we have learnt since the beginning of 2nd semester.";
```

