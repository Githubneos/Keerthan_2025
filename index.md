---
layout: base
title: Student Home 
description: Home Page
author: Keerthan Karumudi
hide: true
comments: true
---


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Keerthan Karumudi</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: radial-gradient(circle at top, #0e0e2c, #1b1b2f);
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      color: #f0f0f0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .container {
      width: 90%;
      max-width: 500px;
      padding: 20px;
    }
    .card {
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: 24px;
      padding: 40px;
      box-shadow: 0 0 30px rgba(0, 255, 255, 0.08);
      backdrop-filter: blur(15px);
      text-align: center;
    }
    h1 {
      font-size: 2rem;
      margin-bottom: 8px;
      letter-spacing: 1px;
    }
    .subtitle {
      color: #cccccc;
      font-size: 1rem;
      margin-bottom: 25px;
    }
    .button-group {
      display: flex;
      flex-direction: column;
      gap: 15px;
    }
    .button-group a {
      text-decoration: none;
      background-color: #00d4ff;
      color: #0e0e2c;
      font-weight: 600;
      padding: 12px;
      border-radius: 12px;
      transition: background 0.3s ease, transform 0.2s ease;
      box-shadow: 0 5px 15px rgba(0, 212, 255, 0.25);
    }
    .button-group a:hover {
      background-color: #00bbff;
      transform: translateY(-2px);
    }
  </style>
</head>
<body>
  <main class="container">
    <div class="card">
      <h1>Keerthan Karumudi</h1>
      <p class="subtitle">Developer · Researcher · Designer</p>
      <div class="button-group">
        <a href="https://yourdomain.com/resume.pdf" target="_blank">Resume</a>
        <a href="https://cad.onshape.com/documents" target="_blank">Onshape Portfolio</a>
        <a href="https://www.artstation.com/your-blender-portfolio" target="_blank">Blender Portfolio</a>
        <a href="mailto:keerthan.karumudi@gmail.com">Email Me</a>
        <a href="https://www.linkedin.com/in/keerthan-karumudi" target="_blank">LinkedIn</a>
      </div>
    </div>
  </main>
</body>
</html>

