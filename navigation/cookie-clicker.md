---
layout: page
title: Cookie Clicker
description: Pair Programming
permalink: /cookie-clicker/
---

%%html
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cookie Clicker Game</title>
</head>
<body>
    <h1>Cookie Clicker Game</h1>
    <div id="cookieCount">Cookies: 0</div>
        <img id="cookieButton" src="{{site.baseurl}}/Users/keerthan/nighthawk/Keerthan_2025/Keerthan_2025/images/image-removebg-preview.png" alt="Cookie;" style="cursor: pointer;"><br>
    <button id="upgradeButton">Cursor (Cost: 10 Cookies)</button><br>
    <button id="upgradeButton2">Grandma (Cost: 100 cookies)</button><br>
    <button id="upgradeButton3">Farm (Cost: 1000 cookies)</button>
    <div id="upgradeInfo">Cursor Level: 0</div>
    <div id="upgradeInfo2">Grandma Level: 0</div>
    <div id="upgradeInfo3">Farm Level: 0</div>
    <audio id="clickSound" src="{{site.baseurl}}/audio/068243_crunchy-cookie-eatingwav-81661.mp3"></audio>
    <script>
        let cookieCount = 0;
let cursorLevel = 0;
let cursorCost = 10;
let grandmaLevel = 0;
let grandmaCost = 100;
let farmLevel = 0;
let farmCost = 1000;
let cookiesPerSecond = 0;
const cookieCountDisplay = document.getElementById("cookieCount");
const cookieButton = document.getElementById("cookieButton");
const upgradeButton = document.getElementById("upgradeButton");
const upgradeButton2 = document.getElementById("upgradeButton2");
const upgradeButton3 = document.getElementById("upgradeButton3");
const upgradeInfo = document.getElementById("upgradeInfo");
const upgradeInfo2 = document.getElementById("upgradeInfo2");
const upgradeInfo3 = document.getElementById("upgradeInfo3");
const clickSound = document.getElementById("clickSound");
// Function to update cookie count display
function updateDisplay() {
    cookieCountDisplay.textContent = `Cookies: ${cookieCount}`;
    upgradeInfo.textContent = `Cursor Level: ${cursorLevel}`;
    upgradeInfo2.textContent = `Grandma Level: ${grandmaLevel}`;
    upgradeInfo3.textContent = `Farm Level: ${farmLevel}`;
    upgradeButton.textContent = `Upgrade Cursor (Cost: ${cursorCost} Cookies)`;
    upgradeButton2.textContent = `Upgrade Grandma: (Cost: ${grandmaCost} Cookies)`;
    upgradeButton3.textContent = `Upgrade Farm: (Cost: ${farmCost} Cookies)`;
}
// Click cookie button
cookieButton.addEventListener("click", () => {
    cookieCount++;
    clickSound.play(); // Play the sound
    updateDisplay();
});
// Upgrade auto-clicker
upgradeButton.addEventListener("click", () => {
    if (cookieCount >= cursorCost) {
        cookieCount -= cursorCost;
        cursorLevel++;
        cookiesPerSecond++;
        cursorCost = Math.floor(cursorCost * 1.5); // Increase cost
        updateDisplay();
    }
});
upgradeButton2.addEventListener("click", () => {
    if (cookieCount >= grandmaCost) {
        cookieCount -= grandmaCost;
        grandmaLevel++;
        cookiesPerSecond+=10;
        grandmaCost = Math.floor(grandmaCost * 1.5);
        updateDisplay();
    }
});
upgradeButton3.addEventListener("click", ()=> {
    if (cookieCount >= farmCost) {
        cookieCount -= farmCost;
        farmLevel++;
        cookiesPerSecond+=100;
        farmCost = Math.floor(farmCost * 1.5);
        updateDisplay();
    }
});
// Automatically collect cookies
setInterval(() => {
    cookieCount += cookiesPerSecond;
    updateDisplay();
}, 1000);
// Initial display update
updateDisplay();
    </script>
</body>
</html>