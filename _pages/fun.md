---
layout: archive
title: "Miscellaneous"
permalink: /fun/
author_profile: true
---

Here are a few miscellaneous things that I have made, find interesting, etc. The order the blocks appear in is randomized so when you refresh the page something different may appear first! If you would like to randomize it yourself without having to refresh the page just press this button: <button type="button" id="fun-randomize" class="btn btn--primary fun-page-button fun-page-button--randomize fun-randomize-button">Randomize</button>

<div id="fun-panels">
  <div id="economist-quiz-panel" class="fun-panel economist-quiz-card">
    <h3>What Type of Economist Should I Be?</h3>
    <p>
      Many of my non-economist friends have heard me talk about "applied-micro economists" or "development economists" and asked me: "What type of economist would I be?" This (very silly) BuzzFeed-style quiz is the culmination of these conversations.
    </p>
    <a class="btn btn--primary fun-page-button" href="/economist-quiz/">Take the quiz</a>
  </div>

  <div id="genealogy-panel" class="fun-panel genealogy-card">
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
          <a id="genealogy-link" class="btn btn--primary fun-page-button" target="_blank" rel="noopener">Math Genealogy</a>
          <a id="wiki-link" class="btn btn--primary fun-page-button" target="_blank" rel="noopener">Wikipedia</a>
        </div>
      </div>
    </div>

    <div class="genealogy-controls" aria-label="Genealogy navigation controls">
      <button type="button" id="genealogy-prev" class="btn btn--primary fun-page-button">← Previous</button>
      <span id="genealogy-index"></span>
      <button type="button" id="genealogy-next" class="btn btn--primary fun-page-button">Next →</button>
    </div>
  </div>

  <div id="sue-challis-panel" class="fun-panel sue-challis-card">
    <h3>My mother, Sue Challis (née Shotton)</h3>
    <p>
      My mother, Sue Challis (née Shotton), was a professional trampolinist.
      According to AinsworthSports, she had two careers, each worthy of being in the top 50 greatest female trampoline athletes of all time.
      Under her maiden name, Sue Shotton, she is ranked as the 14th greatest, and under her married name, Sue Challis, she is ranked as the 46th greatest.
      She was also part of the inaugural class of the Loughborough Sport Hall of Fame
      and is listed in the World Acrobatics Society Trampoline / Tumbling Legends Hall of Fame.
    </p>
    <p>Career highlights include:</p>
    <ul class="sue-challis-accomplishments">
      <li>11-time British Ladies Champion.</li>
      <li>Double European Ladies Champion (1983, 1993).</li>
      <li>Triple gold medalist at the 1984 Trampoline Gymnastics World Championships (individual, synchro, and team).</li>
    </ul>
    <div class="sue-challis-links">
      <a class="btn btn--primary fun-page-button"
         href="https://ainsworthsports.com/womens_trampoline_athlete_rankings_all_time_1_to_1000.htm"
         target="_blank" rel="noopener">AinsworthSports rankings</a>
      <a class="btn btn--primary fun-page-button"
         href="https://intersportstats.com/athletes/3000420493"
         target="_blank" rel="noopener">Competition results</a>
      <a class="btn btn--primary fun-page-button"
         href="https://www.lboro.ac.uk/sport/loughborough-sport/hall-of-fame/"
         target="_blank" rel="noopener">Loughborough Hall of Fame</a>
    </div>
  </div>

  <div id="quotes-panel" class="fun-panel quotes-card">
    <h3>Ideas worth following</h3>
    <p class="quotes-intro">
      A collection about curiosity, play, and interesting questions—and how usefulness sometimes arrives later.
    </p>

    <section class="quotes-group" aria-labelledby="quotes-interesting-heading">
      <h4 id="quotes-interesting-heading">Because it seemed interesting</h4>
      <div class="quotes-grid">
        <blockquote class="quote-item">
          <p>“I guess I’ll invent a game.”</p>
          <footer>— Alfred Butts, inventor of <em>Scrabble</em></footer>
        </blockquote>
        <blockquote class="quote-item">
          <p>“Because it is there.”</p>
          <footer>— famously attributed to George Mallory when asked why he wanted to climb Mount Everest</footer>
        </blockquote>
        <blockquote class="quote-item">
          <p>“I don’t know. I thought it would be cool.”</p>
          <footer>— Will Wright, creator of <em>SimCity</em>, on his motivation</footer>
        </blockquote>
        <blockquote class="quote-item">
          <p>“Mostly because it seemed like a neat idea.”</p>
          <footer>— Ray Tomlinson, on why he invented email</footer>
        </blockquote>
        <blockquote class="quote-item">
          <p>“I did not know and I do not know why.”</p>
          <footer>— J.R.R. Tolkien, recalling the origin of <em>The Hobbit</em></footer>
        </blockquote>
        <blockquote class="quote-item">
          <p>“Nothing, I guess.”</p>
          <footer>— Heinrich Hertz, reportedly, when asked what would come from his work on electromagnetic waves</footer>
        </blockquote>
        <blockquote class="quote-item">
          <p>“I’m doing a (free) operating system (just a hobby, won’t be big and professional like GNU).”</p>
          <footer>— Linus Torvalds, announcing the project that became Linux in 1991</footer>
        </blockquote>
        <blockquote class="quote-item">
          <p>“I was looking for a ‘hobby’ programming project that would keep me occupied during the week around Christmas.”</p>
          <footer>— Guido van Rossum, on beginning what became Python</footer>
        </blockquote>
      </div>
    </section>

    <section class="quotes-group" aria-labelledby="quotes-research-heading">
      <h4 id="quotes-research-heading">Curiosity, usefulness, and pure research</h4>
      <div class="quotes-grid">
        <blockquote class="quote-item">
          <p>“The best kind of research is curiosity driven research.”</p>
          <footer>— Barry Marshall, Nobel laureate in medicine</footer>
        </blockquote>
        <blockquote class="quote-item">
          <p>“I have never done anything ‘useful’.”</p>
          <footer>— G. H. Hardy, <em>A Mathematician’s Apology</em></footer>
          <p class="quote-context">Hardy prized mathematics pursued for its own sake, especially number theory. The irony is that areas once seen as purely theoretical later became fundamental to cryptography and secure digital communication.</p>
        </blockquote>
        <blockquote class="quote-item">
          <p>“Thank God that number theory is unsullied by any application.”</p>
          <footer>— attributed to Leonard Eugene Dickson</footer>
          <p class="quote-context">Number theory is now central to public-key cryptography, encryption, digital signatures, and secure communication.</p>
        </blockquote>
        <blockquote class="quote-item">
          <p>“The sole end of science is the honor of the human mind.”</p>
          <footer>— Carl Gustav Jacob Jacobi, writing to Legendre in 1830</footer>
          <p class="quote-context">Jacobi was defending mathematics and science as intellectual ends in themselves, without requiring immediate practical justification.</p>
        </blockquote>
        <blockquote class="quote-item">
          <p>“The scientist does not study nature because it is useful; he studies it because he delights in it.”</p>
          <footer>— Henri Poincaré</footer>
          <p class="quote-context">For Poincaré, curiosity, understanding, and intellectual beauty were motivation enough; utility could follow later.</p>
        </blockquote>
      </div>
    </section>

    <section class="quotes-group" aria-labelledby="quotes-discovery-heading">
      <h4 id="quotes-discovery-heading">Thinking, questions, and discovery</h4>
      <div class="quotes-grid">
        <details class="quote-long">
          <summary>Arthur Schopenhauer on reading and thinking for oneself</summary>
          <blockquote>
            <p>“When we read, another person thinks for us: we merely repeat his mental process. It is the same as the pupil, in learning to write, following with his pen the lines that have been pencilled by the teacher. Accordingly, in reading, the work of thinking is, for the greater part, done for us. This is why we are consciously relieved when we turn to reading after being occupied with our own thoughts. But, in reading, our head is, however, really only the arena of some one else’s thoughts. And so it happens that if any one spends almost the whole day in reading, and by way of relaxation devotes the intervals to some thoughtless pastime, he gradually loses the capacity for thinking; just as a man who is always riding at last forgets how to walk. This is the case with very many learned persons: they have read themselves stupid. For to occupy every spare moment in reading, and to do nothing but read, is even more paralyzing to the mind than constant manual labor, which at least allows those engaged in it to follow their own thoughts. A spring never free from the pressure of some foreign body at last loses its elasticity; and so does the mind if other people’s thoughts are constantly forced upon it. Just as you can ruin the stomach and impair the whole body by taking too much nourishment, so you can overfill and choke the mind by feeding it too much. For the more you read, the fewer are the traces left by what you have read: the mind becomes like a tablet crossed over and over with writing. There is no time for rumination; and in no other way can you assimilate what you have read. If you read on and on without setting down your own thoughts, what has been read does not take root, but is for the most part lost. It is, in fact, just the same with mental as with bodily food: hardly the fifth part of what one takes is assimilated. The rest passes off in evaporation, respiration and the like.</p>
            <p>Reading is thinking with some one else’s head instead of one’s own. To think with one’s own head is always to aim at developing a coherent whole—a system, even though it be not a strictly complete one; and nothing hinders this so much as too strong a current of others’ thoughts, such as comes of continual reading.”</p>
            <footer>— Arthur Schopenhauer, “On Thinking for Oneself” / writings on reading and independent thought</footer>
          </blockquote>
        </details>

        <details class="quote-long">
          <summary>Donald Knuth on creativity and finding good questions</summary>
          <blockquote>
            <p>“And I think we should also try to guess what theorems are coming up; or, at least, to figure out how and why anybody would try to prove such theorems in the first place. We should imagine ourselves in the discoverer’s place. The creative part is really more interesting than the deductive part. Instead of concentrating just on finding good answers to questions, it’s more important to learn how to find good questions!</p>
            <p>You’ve got something there. I wish our teachers would give us problems like, ‘Find something interesting about x,’ instead of ‘Prove x.’</p>
            <p>Exactly. But teachers are so conservative, they’d be afraid of scaring off the ‘grind’ type of students who obediently and mechanically do all the homework. Besides, they wouldn’t like the extra work of grading the answers to nondirected questions.</p>
            <p>The traditional way is to put off all creative aspects until the last part of graduate school. For seventeen or more years, a student is taught examsmanship, then suddenly after passing enough exams in graduate school he’s told to do something original!</p>
            <p>Right. I doubt if many of the really original students have stuck around that long.</p>
            <p>Oh, I don’t know, maybe they’re original enough to find a way to enjoy the system. Like putting themselves into the subject, as we were saying. That would make the traditional college courses tolerable, maybe even fun.</p>
            <p>You always were an optimist. I’m afraid you’re painting too rosy a picture. But look, the rain has stopped, let’s lug this rock back to camp and see what it says.”</p>
            <footer>— Donald E. Knuth, <em>Surreal Numbers: How Two Ex-Students Turned On to Pure Mathematics and Found Total Happiness</em>, pp. 46–47.</footer>
          </blockquote>
        </details>

        <blockquote class="quote-item">
          <p>“An expert is a person who has made all the mistakes that can be made in a very narrow field.”</p>
          <footer>— Niels Bohr, commonly attributed</footer>
        </blockquote>
        <blockquote class="quote-item">
          <p>“The formulation of a problem is often more essential than its solution.”</p>
          <footer>— Albert Einstein and Leopold Infeld, <em>The Evolution of Physics</em></footer>
        </blockquote>
      </div>
    </section>
  </div>

  <div id="cool-stuff-panel" class="fun-panel fun-pdf-card">
    <div class="fun-pdf-header">
      <a class="btn btn--primary fun-page-button" href="/files/Cool_Stuff.pdf" target="_blank" rel="noopener">Open PDF in New Tab</a>
    </div>

    <iframe
      class="fun-pdf-frame"
      src="/files/Cool_Stuff.pdf#view=FitH"
      title="Cool Stuff PDF"
      loading="lazy">
    </iframe>
  </div>
</div>

<script>
  (function () {
    function randomizeFunPanelOrder(forceChange) {
      const container = document.getElementById("fun-panels");

      if (!container) return;

      const panels = Array.from(container.querySelectorAll(".fun-panel"));

      for (let i = panels.length - 1; i > 0; i--) {
        const randomIndex = Math.floor(Math.random() * (i + 1));
        [panels[i], panels[randomIndex]] = [panels[randomIndex], panels[i]];
      }

      panels.forEach((panel) => container.appendChild(panel));
    }

    function initializeFunPanelRandomizer() {
      const randomizeButton = document.getElementById("fun-randomize");

      randomizeFunPanelOrder();

      if (randomizeButton) {
        randomizeButton.addEventListener("click", randomizeFunPanelOrder);
      }
    }

    if (document.readyState === "loading") {
      document.addEventListener("DOMContentLoaded", initializeFunPanelRandomizer, { once: true });
    } else {
      initializeFunPanelRandomizer();
    }
  })();
</script>



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
  .fun-page-button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 0.35rem;
    border: 1px solid rgba(99, 102, 241, 0.32) !important;
    border-radius: 999px;
    background: linear-gradient(135deg, #4f46e5, #2b8aa0);
    background-color: #4f46e5;
    color: #ffffff !important;
    font-weight: 800;
    letter-spacing: 0.01em;
    text-decoration: none;
    box-shadow: 0 10px 22px rgba(79, 70, 229, 0.2);
    transition: transform 0.18s ease, box-shadow 0.18s ease, border-color 0.18s ease, background 0.18s ease;
  }

  .fun-page-button:hover,
  .fun-page-button:focus {
    border-color: rgba(245, 158, 11, 0.65) !important;
    background: linear-gradient(135deg, #4338ca, #24778a);
    background-color: #4338ca;
    color: #ffffff !important;
    transform: translateY(-1px);
    box-shadow: 0 14px 28px rgba(79, 70, 229, 0.26);
  }

  .fun-page-button:focus-visible,
  .genealogy-controls button:focus-visible {
    outline: 3px solid rgba(245, 158, 11, 0.65);
    outline-offset: 3px;
  }


  .fun-randomize-button {
    margin: 0.35rem 0 0.85rem;
    padding-inline: 1.05rem;
  }

  .fun-randomize-button::before {
    content: "↻";
    font-size: 1.05em;
    line-height: 1;
  }

  .fun-panel {
    margin-top: 0.75rem;
    margin-bottom: 1.2rem;
    padding: 0.85rem 1.1rem 1.05rem;
    border: 1px solid rgba(99, 102, 241, 0.28);
    border-left: 4px solid #6366f1;
    border-radius: 14px;
    background: linear-gradient(145deg, rgba(255, 255, 255, 0.95), rgba(99, 102, 241, 0.08));
    box-shadow: 0 14px 30px rgba(15, 23, 42, 0.12);
    color: var(--global-text-color);
  }

  .fun-panel h3 {
    margin-top: 0;
    margin-bottom: 0.65rem;
  }

  .economist-quiz-card h3 {
    margin-top: 0;
  }

  .sue-challis-card p {
    margin: 0 0 0.8rem;
    color: var(--global-text-color);
  }

  .sue-challis-accomplishments {
    margin: 0 0 0.8rem 1.25rem;
    color: var(--global-text-color);
  }

  .sue-challis-accomplishments li {
    margin-bottom: 0.3rem;
  }

  .sue-challis-links {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .quotes-card .quotes-intro {
    margin: 0 0 1rem;
  }

  .quotes-group + .quotes-group {
    margin-top: 1.4rem;
  }

  .quotes-group h4 {
    margin: 0 0 0.65rem;
    color: var(--global-text-color);
  }

  .quotes-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 0.75rem;
  }

  .quote-item,
  .quote-long {
    margin: 0;
    padding: 0.9rem 1rem;
    border: 1px solid rgba(99, 102, 241, 0.22);
    border-radius: 10px;
    background: rgba(255, 255, 255, 0.58);
    box-shadow: 0 6px 16px rgba(15, 23, 42, 0.06);
    color: var(--global-text-color);
  }

  .quote-item > p:first-child,
  .quote-long blockquote p {
    margin: 0 0 0.55rem;
    font-size: 1.02rem;
    line-height: 1.55;
  }

  .quote-item footer,
  .quote-long footer {
    font-size: 0.88rem;
    line-height: 1.45;
    opacity: 0.82;
  }

  .quote-context {
    margin: 0.7rem 0 0;
    padding-top: 0.65rem;
    border-top: 1px solid rgba(99, 102, 241, 0.16);
    font-size: 0.85rem;
    line-height: 1.5;
    opacity: 0.78;
  }

  .quote-long {
    grid-column: 1 / -1;
    padding: 0;
    overflow: hidden;
  }

  .quote-long summary {
    padding: 0.9rem 2.4rem 0.9rem 1rem;
    cursor: pointer;
    font-weight: 700;
    color: var(--global-text-color);
    transition: background-color 0.18s ease, color 0.18s ease;
  }

  .quote-long summary:hover {
    background: rgba(99, 102, 241, 0.1);
  }

  .quote-long summary:focus-visible {
    outline: 3px solid rgba(245, 158, 11, 0.65);
    outline-offset: -3px;
  }

  .quote-long[open] summary {
    border-bottom: 1px solid rgba(99, 102, 241, 0.18);
    background: rgba(99, 102, 241, 0.08);
  }

  .quote-long blockquote {
    margin: 0;
    padding: 1rem;
    border: 0;
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
    .quotes-grid {
      grid-template-columns: 1fr;
    }

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

  html[data-theme="dark"] .quote-item,
  html[data-theme="dark"] .quote-long {
    border-color: rgba(129, 140, 248, 0.3);
    background: rgba(15, 23, 42, 0.48);
    box-shadow: 0 6px 16px rgba(2, 6, 23, 0.24);
  }

  html[data-theme="dark"] .quote-context,
  html[data-theme="dark"] .quote-long[open] summary {
    border-color: rgba(129, 140, 248, 0.24);
  }

  html[data-theme="dark"] .quote-long summary:hover,
  html[data-theme="dark"] .quote-long[open] summary {
    background: rgba(129, 140, 248, 0.14);
  }

</style>
