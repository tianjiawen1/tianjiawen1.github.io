---
layout: post
title: Robot Embodiments
date: 2026-07-12 00:00:00
description: A catalog of 20 robot embodiments aligned into a Unified Action Space
img: assets/img/yiwa.jpg
tags: robot-embodiments
categories: work
giscus_comments: true
---
<!-- Unified Action Space catalog, styled after LingBot-VLA 2.0 -->

<div class="uas">
  <div class="uas-head">
    <h3 class="uas-title">Unified Action Space</h3>
    <p class="uas-desc">
      This page catalogs <strong>20</strong> robot embodiments available on the market, aligned into a shared
      action representation for scalable real-robot training.
    </p>
  </div>
  <!-- Central action-space card with the shared action components -->
  <div class="uas-card">
    <div class="uas-card-title">Unified Action Space</div>
    <div class="uas-tags">
      <span class="uas-tag" data-key="Arm" style="--c: 85, 95, 255;"><span class="uas-tag-label">Arm</span><span class="uas-tag-dof"></span></span>
      <span class="uas-tag" data-key="EEF" style="--c: 255, 138, 0;"><span class="uas-tag-label">EEF</span><span class="uas-tag-dof"></span></span>
      <span class="uas-tag" data-key="Gripper" style="--c: 32, 178, 107;"><span class="uas-tag-label">Gripper</span><span class="uas-tag-dof"></span></span>
      <span class="uas-tag" data-key="Move" style="--c: 255, 61, 154;"><span class="uas-tag-label">Move</span><span class="uas-tag-dof"></span></span>
      <span class="uas-tag" data-key="Waist" style="--c: 255, 126, 138;"><span class="uas-tag-label">Waist</span><span class="uas-tag-dof"></span></span>
      <span class="uas-tag" data-key="Head" style="--c: 198, 79, 24;"><span class="uas-tag-label">Head</span><span class="uas-tag-dof"></span></span>
      <span class="uas-tag" data-key="Hand" style="--c: 22, 166, 200;"><span class="uas-tag-label">Hand</span><span class="uas-tag-dof"></span></span>
    </div>
  </div>
  <!-- Robot embodiment grid -->
  <div class="uas-grid">
    {% assign robots = site.data.robots %}
    {% for r in robots %}
    <div class="uas-robot" data-dof='{{ r.dof | jsonify }}'>
      <div class="uas-robot-figure" aria-hidden="true">
        <img class="uas-robot-img" src="{{ '/assets/img/robots_src/' | append: r.img | replace: ' ', '%20' | relative_url }}" alt="{{ r.name }}" loading="lazy" onerror="this.closest('.uas-robot-figure').classList.add('no-img')">
        <svg class="uas-robot-ph" viewBox="0 0 48 48" width="46" height="46" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round">
          <rect x="14" y="16" width="20" height="16" rx="4"></rect>
          <circle cx="20" cy="23" r="2" fill="currentColor" stroke="none"></circle>
          <circle cx="28" cy="23" r="2" fill="currentColor" stroke="none"></circle>
          <path d="M24 16V9"></path>
          <circle cx="24" cy="7" r="2"></circle>
          <path d="M14 22H9M34 22h5M18 32v6M30 32v6"></path>
        </svg>
      </div>
      <div class="uas-robot-name">{{ r.name }}</div>
      <div class="uas-robot-type">{{ r.type }}</div>
      <div class="uas-robot-stats">
        <span class="uas-stat"><span class="uas-stat-num">{{ r.total }}</span> DoF</span>
        <span class="uas-stat-sep">·</span>
        <span class="uas-stat">{{ r.freq }}</span>
        <span class="uas-stat-sep">·</span>
        <span class="uas-stat">{{ r.ee }}</span>
      </div>
    </div>
    {% endfor %}
  </div>
</div>

<style>
  .uas {
    max-width: 980px;
    margin: 0 auto;
    color: #0e0e0e;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  }
  .uas-head { max-width: 860px; margin-bottom: 22px; }
  .uas-title {
    font-size: 28px;
    font-weight: 600;
    line-height: 38px;
    color: #262626;
    margin: 0;
  }
  .uas-desc {
    margin-top: 6px;
    font-size: 16px;
    line-height: 24px;
    color: #6a6a6a;
  }
  .uas-desc strong { color: #555fff; }

  /* Central Unified Action Space card — sticks to the top of the
     viewport so it stays visible while scrolling through the robots. */
  .uas-card {
    position: sticky;
    top: 68px;
    z-index: 10;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: 28px auto 40px;
    padding: 20px 14px;
    max-width: 420px;
    border-radius: 10px;
    border: 1px solid #e5e7eb;
    background: rgba(255, 255, 255, 0.92);
    backdrop-filter: saturate(180%) blur(8px);
    -webkit-backdrop-filter: saturate(180%) blur(8px);
    box-shadow: 0 10px 28px rgba(18, 26, 48, 0.05);
  }
  .uas-card-title {
    font-size: 20px;
    font-weight: 600;
    line-height: 28px;
    color: #0e0e0e;
  }
  .uas-tags {
    margin-top: 14px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 8px;
  }
  .uas-tag {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    min-height: 34px;
    min-width: 78px;
    padding: 6px 10px;
    border-radius: 8px;
    border: 1px solid rgb(var(--c));
    background: #fff;
    color: rgb(var(--c));
    font-size: 12px;
    font-weight: 600;
    line-height: 16px;
    text-align: center;
    box-shadow: 0 8px 18px rgba(85, 95, 255, 0.1);
    transition: all 0.2s ease;
  }
  .uas-tag:hover { transform: translateY(-2px); box-shadow: 0 12px 24px rgba(var(--c), 0.22); }
  .uas-tag-dof { font-weight: 700; }
  .uas-tag-dof:not(:empty) { margin-left: 5px; }

  /* Hover-linked highlight/dim: when a robot is focused, its action
     components stay lit while the rest fade out. */
  .uas.is-focusing .uas-tag { opacity: 0.22; box-shadow: none; transform: scale(0.96); }
  .uas.is-focusing .uas-tag.is-on {
    opacity: 1;
    transform: scale(1.08);
    box-shadow: 0 12px 26px rgba(var(--c), 0.3);
  }

  /* Robot grid */
  .uas-grid {
    display: grid;
    grid-template-columns: repeat(5, minmax(0, 1fr));
    gap: 14px;
  }
  .uas-robot {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-end;
    padding: 16px 8px 14px;
    border-radius: 8px;
    border: 1px solid #e3e6ef;
    background: #fff;
    box-shadow: 0 10px 28px rgba(18, 26, 48, 0.05);
    transition: all 0.2s ease;
    text-align: center;
  }
  .uas-robot:hover {
    transform: translateY(-4px);
    border-color: #a8adff;
    box-shadow: 0 16px 34px rgba(85, 95, 255, 0.16);
  }
  .uas-robot-figure {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 120px;
    color: #555fff;
  }
  .uas-robot-img {
    max-height: 100%;
    max-width: 100%;
    object-fit: contain;
  }
  .uas-robot-ph { display: none; }
  .uas-robot-figure.no-img .uas-robot-img { display: none; }
  .uas-robot-figure.no-img .uas-robot-ph { display: block; }
  .uas-robot-name {
    margin-top: 8px;
    font-size: 13px;
    font-weight: 600;
    line-height: 18px;
    color: #262626;
  }
  .uas-robot-type {
    margin-top: 2px;
    font-size: 11px;
    line-height: 15px;
    color: #9ea6ba;
  }
  .uas-robot-stats {
    margin-top: 6px;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    gap: 4px;
    font-size: 10.5px;
    line-height: 14px;
    color: #6a6a6a;
  }
  .uas-stat-num { font-weight: 700; color: #555fff; }
  .uas-stat-sep { color: #c8cdd9; }

  @media (max-width: 900px) {
    .uas-grid { grid-template-columns: repeat(3, minmax(0, 1fr)); }
  }
  @media (max-width: 560px) {
    .uas-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); }
    .uas-title { font-size: 24px; line-height: 32px; }
  }
</style>

<script>
  (function () {
    var root = document.querySelector(".uas");
    if (!root) return;
    var tags = Array.prototype.slice.call(root.querySelectorAll(".uas-tag"));
    var robots = Array.prototype.slice.call(root.querySelectorAll(".uas-robot"));

    function focus(robot) {
      var map = {};
      try { map = JSON.parse(robot.getAttribute("data-dof") || "{}"); } catch (e) { map = {}; }
      root.classList.add("is-focusing");
      robot.classList.add("is-active");
      tags.forEach(function (t) {
        var key = t.getAttribute("data-key");
        var dofEl = t.querySelector(".uas-tag-dof");
        if (Object.prototype.hasOwnProperty.call(map, key)) {
          t.classList.add("is-on");
          if (dofEl) dofEl.textContent = map[key] + "D";
        } else {
          t.classList.remove("is-on");
          if (dofEl) dofEl.textContent = "";
        }
      });
    }
    function clear(robot) {
      root.classList.remove("is-focusing");
      if (robot) robot.classList.remove("is-active");
      tags.forEach(function (t) {
        t.classList.remove("is-on");
        var dofEl = t.querySelector(".uas-tag-dof");
        if (dofEl) dofEl.textContent = "";
      });
    }

    robots.forEach(function (robot) {
      robot.addEventListener("mouseenter", function () { focus(robot); });
      robot.addEventListener("mouseleave", function () { clear(robot); });
      // Touch / keyboard focus support
      robot.setAttribute("tabindex", "0");
      robot.addEventListener("focus", function () { focus(robot); });
      robot.addEventListener("blur", function () { clear(robot); });
    });
  })();
</script>
