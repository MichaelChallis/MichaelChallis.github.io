---
layout: archive
title: "Fun"
permalink: /fun/
author_profile: true
---

Here are a few miscellaneous things that I find fun/cool.

<div class="fun-pdf-card">
  <div class="fun-pdf-header">
    <h2>Cool Stuff</h2>
    <a class="btn btn--primary" href="/files/Cool_Stuff.pdf" target="_blank" rel="noopener">Open PDF in New Tab</a>
  </div>

  <iframe
    class="fun-pdf-frame"
    src="/files/Cool_Stuff.pdf#view=FitH"
    title="Cool Stuff PDF"
    loading="lazy">
  </iframe>
</div>

<style>
  .fun-pdf-card {
    margin-top: 1rem;
    border-radius: 14px;
    padding: 1rem;
    background: linear-gradient(145deg, rgba(62, 106, 255, 0.1), rgba(138, 52, 255, 0.12));
    border: 1px solid rgba(99, 102, 241, 0.25);
    box-shadow: 0 12px 28px rgba(15, 23, 42, 0.16);
  }

  .fun-pdf-header {
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 0.85rem;
  }

  .fun-pdf-header h2 {
    margin: 0;
    font-size: 1.35rem;
  }

  .fun-pdf-frame {
    display: block;
    width: 100%;
    min-height: 72vh;
    border: 0;
    border-radius: 10px;
    background: #ffffff;
  }

  @media (max-width: 767px) {
    .fun-pdf-frame {
      min-height: 65vh;
    }
  }
</style>
