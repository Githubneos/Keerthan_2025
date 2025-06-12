---
layout: base
title: Student Home 
description: Home Page
author: Keerthan Karumudi
hide: true
comments: true
---
<!DOCTYPE html>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;500;700&display=swap" rel="stylesheet" />
<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Inter', sans-serif;
  }
  body {
    background: linear-gradient(to right, #0f2027, #203a43, #2c5364);
    color: #f0f0f0;
    line-height: 1.6;
    padding: 2rem;
  }
  header {
    text-align: center;
    margin-bottom: 3rem;
    animation: fadeIn 1.2s ease-in-out;
  }
  h1 {
    font-size: 2.5rem;
    font-weight: 700;
  }
  p.tagline {
    font-size: 1.2rem;
    color: #ccc;
  }
  .container {
    max-width: 900px;
    margin: auto;
    padding: 2rem;
    border-radius: 1rem;
    background-color: rgba(255, 255, 255, 0.05);
    box-shadow: 0 0 30px rgba(0, 0, 0, 0.3);
  }
  h2 {
    font-size: 1.6rem;
    margin-top: 2rem;
    color: #90cdf4;
  }
  ul {
    list-style: none;
    padding-left: 1rem;
  }
  li {
    margin: 1rem 0;
  }
  a {
    color: #63b3ed;
    text-decoration: none;
    transition: 0.3s;
  }
  a:hover {
    color: #bee3f8;
    text-decoration: underline;
  }
  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }
</style>
<header>
  <h1>Keerthan Karumudi</h1>
  <p class="tagline">Engineering, Research, and Development</p>
</header>

<div class="container">
  <h2>About Me</h2>
  <p>I’m a high school developer and researcher passionate about applying engineering and physics to solve real-world problems and inspire the next generation of innovators.</p>

  <h2>Hard Skills — Code. Research. Build.</h2>
  <ul>
    <li><strong>Software Development</strong>: Full-stack developer at PilotCity and Open Coding Society; built scalable APIs and interactive tools to support data-driven, user-focused applications.</li>
    <li><strong>Physics Research</strong>: Intern at UC San Diego; conducted theoretical analysis on plasma-surface interactions in magnetized environments to support fusion research and materials science.</li>
    <li><strong>Technical Design</strong>: Vice President of the 3D Animation Club; led instructional modeling projects using Blender and Onshape, merging engineering principles with visual storytelling.</li>
  </ul>

  <h2>Soft Skills — Lead. Teach. Connect.</h2>
  <ul>
    <li><strong>STEM Education</strong>: Curriculum Lead at Project Flight; developed and led outreach programs that brought aerospace and engineering to K–12 classrooms across Southern California.</li>
    <li><strong>Team Leadership</strong>: Directed cross-functional teams in research, development, and education; known for balancing technical rigor with mentorship and collaboration.</li>
    <li><strong>Mission-Driven Mindset</strong>: Focused on bridging engineering, education, and accessibility—committed to building tools that make a lasting impact and cultivate lifelong curiosity.</li>
  </ul>

  <h2>Links</h2>
  <ul>
    <li><a href="your-resume-link.pdf" target="_blank">Resume</a></li>
    <li><a href="https://www.linkedin.com/in/keerthankarumudi" target="_blank">LinkedIn</a></li>
    <li><a href="https://your-onshape-portfolio-link" target="_blank">Onshape Portfolio</a></li>
    <li><a href="https://your-blender-portfolio-link" target="_blank">Blender Portfolio</a></li>
    <li><a href="mailto:your-email@gmail.com">Gmail</a></li>
  </ul>
</div>
