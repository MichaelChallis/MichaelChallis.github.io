---
layout: archive
title: "Miscellaneous"
permalink: /fun/
author_profile: true
---

Here are a few miscellaneous things that I find fun/cool.

<div class="fun-panel genealogy-card">
  <p>
    The <a href="https://www.mathgenealogy.org/" target="_blank" rel="noopener">Mathematics Genealogy Project</a>
    tracks advisor-student relationships in mathematics and related fields, making it possible to trace academic lineages across generations.
    <a href="https://www.mathgenealogy.org/id.php?id=236370" target="_blank" rel="noopener">Herakles M. Polemarchakis</a> is my supervisor and through him I have many famous academic ancestors.
  </p>
  <p>
    The rotating panel below highlights some of the people connected to my mathematical genealogy.
  </p>

  <div class="genealogy-rotator" id="genealogy-rotator" aria-live="polite">
    <img id="genealogy-photo" alt="Portrait" loading="lazy" decoding="async" />
    <div class="genealogy-rotator-content">
      <h3 id="genealogy-name"></h3>
      <p id="genealogy-bio"></p>
      <div class="genealogy-links">
        <a id="genealogy-link" class="btn btn--info btn--small" target="_blank" rel="noopener">Math Genealogy</a>
        <a id="wiki-link" class="btn btn--primary btn--small" target="_blank" rel="noopener">Wikipedia</a>
      </div>
    </div>
  </div>

  <div class="genealogy-controls" aria-label="Genealogy navigation controls">
    <button type="button" id="genealogy-prev">← Previous</button>
    <span id="genealogy-index"></span>
    <button type="button" id="genealogy-next">Next →</button>
  </div>
</div>



<div class="fun-panel fun-pdf-card">
  <div class="fun-pdf-header">
    <a class="btn btn--primary" href="/files/Cool_Stuff.pdf" target="_blank" rel="noopener">Open PDF in New Tab</a>
  </div>

  <iframe
    class="fun-pdf-frame"
    src="/files/Cool_Stuff.pdf#view=FitH"
    title="Cool Stuff PDF"
    loading="lazy">
  </iframe>
</div>

<script>
  (function () {
    const relatives = [
      {
        name: "Kenneth Arrow",
        genealogy: "https://www.genealogy.math.ndsu.nodak.edu/id.php?id=51175",
        wiki: "https://en.wikipedia.org/wiki/Kenneth_Arrow",
        image: "/images/Kenneth Arrow.jpg",
        bio: "American economist and mathematician, Nobel laureate, known for Arrow's impossibility theorem and foundational work in social choice and general equilibrium."
      },
      {
        name: "Harold Hotelling",
        genealogy: "https://www.genealogy.math.ndsu.nodak.edu/id.php?id=35422",
        wiki: "https://en.wikipedia.org/wiki/Harold_Hotelling",
        image: "/images/Harold Hotelling.jpg",
        bio: "American mathematical statistician and economist associated with principal components analysis and Hotelling's law."
      },
      {
        name: "Oswald Veblen",
        genealogy: "https://www.mathgenealogy.org/id.php?id=805",
        wiki: "https://en.wikipedia.org/wiki/Oswald_Veblen",
        image: "/images/Oswald Veblen.jpg",
        bio: "American mathematician who contributed to topology and geometry and helped shape mathematics at Princeton's Institute for Advanced Study."
      },
      {
        name: "Siméon Denis Poisson",
        genealogy: "https://www.mathgenealogy.org/id.php?id=17865",
        wiki: "https://en.wikipedia.org/wiki/Sim%C3%A9on_Denis_Poisson",
        image: "/images/Siméon Denis Poisson.jpg",
        bio: "French mathematician and physicist remembered for Poisson distribution, Poisson brackets, and major work in mechanics."
      },
      {
        name: "Pierre-Simon Laplace",
        genealogy: "https://www.mathgenealogy.org/id.php?id=108295",
        wiki: "https://en.wikipedia.org/wiki/Pierre-Simon_Laplace",
        image: "/images/Pierre-Simon Laplace.jpg",
        bio: "French scholar whose work in celestial mechanics and probability theory profoundly influenced modern mathematical science."
      },
      {
        name: "Joseph-Louis Lagrange",
        genealogy: "https://www.mathgenealogy.org/id.php?id=17864",
        wiki: "https://en.wikipedia.org/wiki/Joseph-Louis_Lagrange",
        image: "/images/Joseph-Louis Lagrange.jpg",
        bio: "Italian-French mathematician known for variational calculus, analytical mechanics, and Lagrangian methods used throughout physics and economics."
      },
      {
        name: "Leonhard Euler",
        genealogy: "https://www.mathgenealogy.org/id.php?id=38586",
        wiki: "https://en.wikipedia.org/wiki/Leonhard_Euler",
        image: "/images/Leonhard Euler.jpg",
        bio: "Prolific Swiss mathematician whose foundational contributions span analysis, number theory, mechanics, and modern notation."
      },
      {
        name: "Johann Bernoulli",
        genealogy: "https://www.mathgenealogy.org/id.php?id=53410",
        wiki: "https://en.wikipedia.org/wiki/Johann_Bernoulli",
        image: "/images/Johann Bernoulli.jpg",
        bio: "Swiss mathematician from the Bernoulli family, recognized for developments in calculus and differential equations."
      },
      {
        name: "Jacob Bernoulli",
        genealogy: "https://www.mathgenealogy.org/id.php?id=54440",
        wiki: "https://en.wikipedia.org/wiki/Jacob_Bernoulli",
        image: "/images/Jacob Bernoulli.jpg",
        bio: "Swiss mathematician best known for Bernoulli numbers, early probability theory, and the law of large numbers."
      },
      {
        name: "Gottfried Wilhelm Leibniz",
        genealogy: "https://www.genealogy.math.ndsu.nodak.edu/id.php?id=60985",
        wiki: "https://en.wikipedia.org/wiki/Gottfried_Wilhelm_Leibniz",
        image: "/images/Gottfried Wilhelm Leibniz.jpg",
        bio: "German polymath and co-inventor of calculus whose ideas shaped logic, philosophy, and mathematical analysis."
      },
      {
        name: "Georgios Plethon Gemistos",
        genealogy: "https://www.mathgenealogy.org/id.php?id=131575",
        wiki: "https://en.wikipedia.org/wiki/Gemistos_Plethon",
        image: "/images/Georgios Plethon Gemistos.jpg",
        bio: "Byzantine philosopher of the late medieval period whose revival of Platonism influenced Renaissance scholarship."
      },
      {
        name: "Ibn Sīnā (Avicenna)",
        genealogy: "https://www.mathgenealogy.org/id.php?id=298616",
        wiki: "https://en.wikipedia.org/wiki/Avicenna",
        image: "/images/Ibn Sīnā (Avicenna).jpg",
        bio: "Persian polymath and physician whose encyclopedic works influenced philosophy, medicine, and scientific thought for centuries."
      }
    ];

    const nameEl = document.getElementById("genealogy-name");
    const bioEl = document.getElementById("genealogy-bio");
    const photoEl = document.getElementById("genealogy-photo");
    const genealogyLinkEl = document.getElementById("genealogy-link");
    const wikiLinkEl = document.getElementById("wiki-link");
    const indexEl = document.getElementById("genealogy-index");
    const prevBtn = document.getElementById("genealogy-prev");
    const nextBtn = document.getElementById("genealogy-next");

    let currentIndex = 0;
    let rotateTimer;
    const ROTATION_INTERVAL_MS = 8500;
    const EXIT_TRANSITION_MS = 450;
    const ENTER_TRANSITION_MS = 900;

    function renderCard(index) {
      const person = relatives[index];
      nameEl.textContent = person.name;
      bioEl.textContent = person.bio;
      photoEl.src = person.image;
      photoEl.alt = `${person.name} portrait`;
      genealogyLinkEl.href = person.genealogy;
      wikiLinkEl.href = person.wiki;
      indexEl.textContent = `${index + 1} / ${relatives.length}`;
    }

    function showNext(step) {
      currentIndex = (currentIndex + step + relatives.length) % relatives.length;
      const rotatorEl = document.getElementById("genealogy-rotator");
      const direction = step >= 0 ? "next" : "prev";
      rotatorEl.dataset.direction = direction;
      rotatorEl.classList.add("is-exiting");

      setTimeout(() => {
        renderCard(currentIndex);
        rotatorEl.classList.remove("is-exiting");
        rotatorEl.classList.add("is-entering");
      }, EXIT_TRANSITION_MS);

      setTimeout(() => {
        rotatorEl.classList.remove("is-entering");
      }, ENTER_TRANSITION_MS);
    }

    function restartRotation() {
      clearInterval(rotateTimer);
      rotateTimer = setInterval(() => showNext(1), ROTATION_INTERVAL_MS);
    }

    prevBtn.addEventListener("click", function () {
      showNext(-1);
      restartRotation();
    });

    nextBtn.addEventListener("click", function () {
      showNext(1);
      restartRotation();
    });

    renderCard(currentIndex);
    restartRotation();
  })();
</script>

<style>
  .fun-panel {
    margin-top: 0.75rem;
    margin-bottom: 1.2rem;
    padding: 1rem 1.1rem 1.05rem;
    border: 1px solid rgba(99, 102, 241, 0.28);
    border-left: 4px solid #6366f1;
    border-radius: 14px;
    background: linear-gradient(145deg, rgba(255, 255, 255, 0.95), rgba(99, 102, 241, 0.08));
    box-shadow: 0 14px 30px rgba(15, 23, 42, 0.12);
    color: var(--global-text-color);
  }

  .genealogy-card p {
    margin: 0 0 0.8rem;
    color: var(--global-text-color);
  }

  .genealogy-rotator {
    display: grid;
    grid-template-columns: minmax(110px, 150px) 1fr;
    gap: 1rem;
    align-items: center;
    padding: 1rem;
    border-radius: 14px;
    border: 1px solid rgba(99, 102, 241, 0.22);
    background: linear-gradient(150deg, rgba(255, 255, 255, 0.95), rgba(238, 242, 255, 0.92));
    box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.6), 0 10px 24px rgba(15, 23, 42, 0.08);
    transform-style: preserve-3d;
    backface-visibility: hidden;
    transform-origin: center;
    transition: transform 0.45s ease-in-out, opacity 0.45s ease-in-out;
  }

  .genealogy-rotator.is-exiting[data-direction="next"] {
    opacity: 0.82;
    transform: perspective(1200px) rotateY(-88deg);
  }

  .genealogy-rotator.is-exiting[data-direction="prev"] {
    opacity: 0.82;
    transform: perspective(1200px) rotateY(88deg);
  }

  .genealogy-rotator.is-entering[data-direction="next"] {
    opacity: 0.82;
    transform: perspective(1200px) rotateY(88deg);
  }

  .genealogy-rotator.is-entering[data-direction="prev"] {
    opacity: 0.82;
    transform: perspective(1200px) rotateY(-88deg);
  }

  #genealogy-photo {
    width: 100%;
    max-width: 150px;
    aspect-ratio: 1 / 1;
    object-fit: cover;
    border-radius: 10px;
    border: 1px solid rgba(30, 41, 59, 0.15);
    background: #f8fafc;
    box-shadow: 0 8px 18px rgba(15, 23, 42, 0.18);
    transition: transform 0.35s ease, filter 0.35s ease;
  }

  .genealogy-rotator.is-exiting #genealogy-photo,
  .genealogy-rotator.is-entering #genealogy-photo {
    transform: scale(0.985);
    filter: saturate(0.9);
  }

  .genealogy-rotator-content h3 {
    margin: 0;
    font-size: 1.1rem;
    color: var(--global-text-color);
  }

  #genealogy-bio {
    margin: 0.55rem 0 0.7rem;
    line-height: 1.45;
    color: var(--global-text-color);
  }

  .genealogy-links {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .genealogy-controls {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.8rem;
    margin-top: 0.65rem;
  }

  .genealogy-controls button {
    border: 1px solid rgba(99, 102, 241, 0.4);
    background: linear-gradient(145deg, #ffffff, #f8faff);
    border-radius: 999px;
    padding: 0.38rem 0.78rem;
    cursor: pointer;
    font-size: 0.88rem;
    font-weight: 600;
    color: var(--global-text-color);
    box-shadow: 0 4px 10px rgba(99, 102, 241, 0.16);
    transition: transform 0.18s ease, box-shadow 0.18s ease, border-color 0.18s ease;
  }

  .genealogy-controls button:hover {
    transform: translateY(-1px);
    border-color: rgba(79, 70, 229, 0.55);
    box-shadow: 0 8px 16px rgba(99, 102, 241, 0.24);
  }

  .genealogy-controls button:focus-visible {
    outline: 2px solid rgba(79, 70, 229, 0.55);
    outline-offset: 2px;
  }

  #genealogy-index {
    min-width: 4rem;
    text-align: center;
    font-variant-numeric: tabular-nums;
    color: var(--global-text-color);
    font-weight: 600;
  }

  .fun-pdf-card {
    margin-top: 0.8rem;
    border-radius: 14px;
    padding: 1rem 1.1rem 1.05rem;
  }

  .fun-pdf-header {
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 0.85rem;
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
    .genealogy-rotator {
      grid-template-columns: 1fr;
    }

    #genealogy-photo {
      max-width: 120px;
    }

    .fun-pdf-frame {
      min-height: 65vh;
    }
  }

  html[data-theme="dark"] .fun-panel {
    border-color: rgba(129, 140, 248, 0.35);
    background: linear-gradient(145deg, rgba(30, 41, 59, 0.8), rgba(55, 48, 163, 0.35));
    box-shadow: 0 14px 28px rgba(2, 6, 23, 0.5);
  }

  html[data-theme="dark"] .genealogy-rotator {
    border-color: rgba(129, 140, 248, 0.3);
    background: linear-gradient(155deg, rgba(15, 23, 42, 0.92), rgba(30, 41, 59, 0.95));
    box-shadow: inset 0 1px 0 rgba(148, 163, 184, 0.18), 0 10px 24px rgba(2, 6, 23, 0.42);
  }

  html[data-theme="dark"] .genealogy-controls button {
    border-color: rgba(129, 140, 248, 0.45);
    background: linear-gradient(145deg, rgba(30, 41, 59, 0.96), rgba(51, 65, 85, 0.94));
    box-shadow: 0 8px 18px rgba(2, 6, 23, 0.42);
  }
</style>
