---
layout: page
title: Javascript Cell
permalink: /Javascript cell/
---


<div id="js-output" style="padding: 10px; border: 1px solid #ccc; margin: 20px 0; font-size: 18px;">
  <!-- This is where the JavaScript output will be displayed -->
  Click the button to see JavaScript in action.
</div>

<button onclick="displayMessage()" style="padding: 10px 20px; background-color: #007bff; color: white; border: none; cursor: pointer;">
  Click Me
</button>

<script>
  function displayMessage() {
    document.getElementById('js-output').innerHTML = 'Hello from JavaScript!';
  }
</script>

