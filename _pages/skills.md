---
layout: page
title: skills
permalink: /skills/
nav: true
nav_order: 6
description: Tools and languages I work with.
---

<style>
  .skills-list {
    margin-top: 1rem;
  }

  .skill-group {
    display: flex;
    gap: 1.1rem;
    padding: 1.1rem 0;
    border-bottom: 1px solid var(--global-divider-color);
    align-items: baseline;
  }

  .skill-group:first-child {
    padding-top: 0;
  }

  .skill-group:last-child {
    border-bottom: none;
  }

  .skill-label {
    flex: 0 0 200px;
    font-weight: 600;
    color: var(--global-text-color);
  }

  .skill-items {
    flex: 1 1 auto;
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem 0.5rem;
    min-width: 0;
  }

  .skill-tag {
    font-size: 0.8rem;
    padding: 0.18rem 0.6rem;
    border-radius: 999px;
    border: 1px solid var(--global-divider-color);
    color: var(--global-text-color-light);
    white-space: nowrap;
  }

  @media (max-width: 576px) {
    .skill-group {
      flex-direction: column;
      gap: 0.5rem;
    }

    .skill-label {
      flex-basis: auto;
    }
  }
</style>

<div class="skills-list">
  <div class="skill-group">
    <div class="skill-label">Formal Methods</div>
    <div class="skill-items">
      <span class="skill-tag">Lean 4</span>
      <span class="skill-tag">Mathlib</span>
      <span class="skill-tag">TLA+/TLC</span>
      <span class="skill-tag">nuSMV</span>
      <span class="skill-tag">PLT Redex</span>
      <span class="skill-tag">temporal logic</span>
      <span class="skill-tag">operational semantics</span>
    </div>
  </div>

  <div class="skill-group">
    <div class="skill-label">Programming</div>
    <div class="skill-items">
      <span class="skill-tag">Python</span>
      <span class="skill-tag">C/C++</span>
      <span class="skill-tag">MATLAB</span>
      <span class="skill-tag">Racket</span>
      <span class="skill-tag">Verilog</span>
      <span class="skill-tag">ARM/x86 Assembly</span>
      <span class="skill-tag">LaTeX</span>
    </div>
  </div>

  <div class="skill-group">
    <div class="skill-label">ML &amp; Scientific Computing</div>
    <div class="skill-items">
      <span class="skill-tag">PyTorch</span>
      <span class="skill-tag">NumPy</span>
      <span class="skill-tag">SymPy</span>
      <span class="skill-tag">AI2-THOR</span>
      <span class="skill-tag">Simulink</span>
    </div>
  </div>

  <div class="skill-group">
    <div class="skill-label">Robotics &amp; Systems</div>
    <div class="skill-items">
      <span class="skill-tag">ROS2</span>
      <span class="skill-tag">URDF/xacro</span>
      <span class="skill-tag">AprilTag</span>
      <span class="skill-tag">Git</span>
      <span class="skill-tag">Linux/macOS</span>
      <span class="skill-tag">Arduino</span>
      <span class="skill-tag">ESP32</span>
    </div>
  </div>

  <div class="skill-group">
    <div class="skill-label">Languages</div>
    <div class="skill-items">
      <span class="skill-tag">English</span>
      <span class="skill-tag">Mandarin</span>
    </div>
  </div>
</div>
