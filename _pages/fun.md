---
layout: archive
title: "Fun"
permalink: /fun/
author_profile: true
---

Here are a few miscellaneous things that I find fun/cool.

<div class="genealogy-card">
  <p>
    The <a href="https://www.mathgenealogy.org/" target="_blank" rel="noopener">Mathematics Genealogy Project</a>
    tracks advisor-student relationships in mathematics and related fields, making it possible to trace academic lineages across generations.
    <a href="https://www.mathgenealogy.org/id.php?id=236370" target="_blank" rel="noopener">Herakles M. Polemarchakis</a> is my supervisor and through him I have many famous academic ancestors.
  </p>
  <p>
    The rotating panel below highlights people connected to my mathematical genealogy.
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

<script>
  (function () {
    const relatives = [
      {
        name: "Herakles M. Polemarchakis",
        genealogy: "https://www.mathgenealogy.org/id.php?id=236370",
        wiki: "https://en.wikipedia.org/wiki/Herakles_Polemarchakis",
        image: "/images/Herakles.webp",
        bio: "Greek economist and game theorist known for work in general equilibrium and strategic behavior under incomplete information."
      },
      {
        name: "Harold Hotelling",
        genealogy: "https://www.genealogy.math.ndsu.nodak.edu/id.php?id=35422",
        wiki: "https://en.wikipedia.org/wiki/Harold_Hotelling",
        image: "/images/Harold Hotelling.jpg",
        bio: "American mathematical statistician and economist associated with principal components analysis and Hotelling's law."
      },
      {
        name: "Kenneth Arrow",
        genealogy: "https://www.genealogy.math.ndsu.nodak.edu/id.php?id=51175",
        wiki: "https://en.wikipedia.org/wiki/Kenneth_Arrow",
        image: "/images/Kenneth Arrow.jpg",
        bio: "American economist and mathematician, Nobel laureate, known for Arrow's impossibility theorem and foundational work in social choice and general equilibrium."
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
      renderCard(currentIndex);
    }

    function restartRotation() {
      clearInterval(rotateTimer);
      rotateTimer = setInterval(() => showNext(1), 5000);
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
  .genealogy-card {
    margin-top: 0.75rem;
    margin-bottom: 1.2rem;
    padding: 0.9rem 1rem;
    border-left: 3px solid #6366f1;
    border-radius: 10px;
    background: rgba(99, 102, 241, 0.06);
  }

  .genealogy-card p {
    margin: 0 0 0.8rem;
  }

  .genealogy-rotator {
    display: grid;
    grid-template-columns: minmax(110px, 150px) 1fr;
    gap: 0.9rem;
    align-items: center;
    padding: 0.9rem;
    border-radius: 12px;
    border: 1px solid rgba(99, 102, 241, 0.3);
    background: rgba(255, 255, 255, 0.6);
  }

  #genealogy-photo {
    width: 100%;
    max-width: 150px;
    aspect-ratio: 1 / 1;
    object-fit: cover;
    border-radius: 10px;
    border: 1px solid rgba(30, 41, 59, 0.15);
    background: #f8fafc;
  }

  .genealogy-rotator-content h3 {
    margin: 0;
    font-size: 1.1rem;
  }

  #genealogy-bio {
    margin: 0.55rem 0 0.7rem;
    line-height: 1.4;
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
    background: #ffffff;
    border-radius: 999px;
    padding: 0.35rem 0.7rem;
    cursor: pointer;
    font-size: 0.88rem;
  }

  #genealogy-index {
    min-width: 4rem;
    text-align: center;
    font-variant-numeric: tabular-nums;
    color: #334155;
  }

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
</style>
