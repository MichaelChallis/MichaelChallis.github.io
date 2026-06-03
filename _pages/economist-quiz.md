---
layout: archive
title: "What Type of Economist Should I Be?"
permalink: /economist-quiz/
author_profile: true
---

<div class="economist-quiz-page">
  <section class="economist-quiz-hero" aria-labelledby="quiz-title">
    <p class="economist-quiz-kicker">A highly scientific personality instrument, probably</p>
    <h2 id="quiz-title">What Type of Economist Should I Be?</h2>
    <p>
      Choose the answer that sounds most like you. When you are done, the quiz will match you with an economist type,
      a famous economist fit, and a short result blurb about your seminar instincts.
    </p>
  </section>

  <form id="economist-quiz" class="economist-quiz" novalidate>
    <div id="economist-quiz-questions"></div>

    <div class="economist-quiz-actions">
      <button type="submit" class="btn btn--primary economist-quiz-submit">Get my result</button>
      <p id="economist-quiz-message" class="economist-quiz-message" role="alert" aria-live="polite"></p>
    </div>
  </form>

  <section id="economist-quiz-result" class="economist-result" aria-live="polite" hidden></section>
</div>

<script>
  (function () {
    const outcomeOrder = [
      "development",
      "appliedMicro",
      "theory",
      "behavioral",
      "politicalEconomy",
      "labor",
      "history",
      "io",
      "econometrics",
      "macro",
      "finance"
    ];

    const quizResults = {
      development: {
        label: "Development",
        famousEconomist: "Esther Duflo",
        blurb: "You want economics to answer big, important questions, but you still care whether the design can survive a hostile seminar. You are drawn to mechanisms, real-world institutions, and conversations outside academia. Your instinct is: “This question matters — now how do we identify it?”"
      },
      appliedMicro: {
        label: "Applied Micro",
        famousEconomist: "Joshua Angrist",
        blurb: "You like narrow questions that can be answered cleanly. You trust research when the empirical design is sharp, the data are credible, and someone can explain exactly what variation is doing the work. Your seminar question is probably: “Is this identified?”"
      },
      theory: {
        label: "Theory",
        famousEconomist: "Kenneth Arrow",
        blurb: "You like clean logic, precise assumptions, and arguments that hold together from first principles. You are drawn to puzzles, models, strategic interaction, and the beauty of a result that feels inevitable once it is written down. Your instinct is to ask: “What is the structure underneath this?”"
      },
      behavioral: {
        label: "Behavioral",
        famousEconomist: "Richard Thaler",
        blurb: "You think the most interesting economics starts when people stop behaving like perfectly rational agents. You like mechanisms, psychology, interpretation, and settings where human quirks actually matter. You are open to ideas from outside the standard economics toolkit."
      },
      politicalEconomy: {
        label: "Political Economy",
        famousEconomist: "Daron Acemoglu",
        blurb: "You are interested in power, institutions, incentives, and why societies choose the policies they do. You like big questions, mechanisms, and long conversations about politics, history, or institutions. Your instinct is to ask how economic outcomes are shaped by rules, conflict, and authority."
      },
      labor: {
        label: "Labor",
        famousEconomist: "David Card",
        blurb: "You are empirical, practical, and slightly ruthless about whether something counts as economics. You like data, identification, human behavior in markets, and seminar arguments where someone is quietly — or loudly — disagreeing with the speaker."
      },
      history: {
        label: "History",
        famousEconomist: "Douglass North",
        blurb: "You think economics makes more sense when it is put in historical context. You are drawn to institutions, long-run change, political order, and the question of why economies develop along different paths. You do not want history as decoration; you want history as evidence about how institutions shape economic life."
      },
      io: {
        label: "Industrial Organization",
        famousEconomist: "Jean Tirole",
        blurb: "You like strategic behavior, firms, markets, and welfare. You are the person asking whether the incentives have been modeled properly and whether the benchmark makes sense. Your brain is happiest when market structure and strategic interaction are both on the table."
      },
      econometrics: {
        label: "Econometrics",
        famousEconomist: "Guido Imbens",
        blurb: "You want precision, structure, and clean answers. You trust airtight logic, careful measurement, and designs that make the identifying variation explicit. You are not necessarily impressed by a big question unless the method can actually answer it."
      },
      macro: {
        label: "Macro",
        famousEconomist: "Olivier Blanchard",
        blurb: "You are comfortable with big questions: growth, crises, inflation, policy, welfare, and the whole economy at once. You accept that answers may be incomplete, but you still want a model that clarifies the tradeoffs. Central banker energy."
      },
      finance: {
        label: "Finance",
        famousEconomist: "Eugene Fama",
        blurb: "You are interested in risk, incentives, markets, and how information gets priced. You like questions where theory, data, and real-world stakes meet directly. You probably enjoy settings where small assumptions can have large consequences for valuation, behavior, and welfare."
      }
    };

    const quizQuestions = [
      {
        id: "question-1",
        prompt: "Which would you rather do?",
        answers: [
          {
            label: "A",
            text: "Ask a big, important question, even if the answer is necessarily incomplete.",
            scores: { development: 3, behavioral: 1, politicalEconomy: 2, labor: 1, history: 2, macro: 3, finance: 1 }
          },
          {
            label: "B",
            text: "Ask a narrower question and answer it precisely.",
            scores: { appliedMicro: 3, theory: 2, behavioral: 1, labor: 1, io: 2, econometrics: 3, finance: 1 }
          }
        ]
      },
      {
        id: "question-2",
        prompt: "What makes you trust a result?",
        answers: [
          {
            label: "A",
            text: "The logic is airtight.",
            scores: { theory: 3, politicalEconomy: 2, io: 2, econometrics: 3, macro: 1, finance: 3 }
          },
          {
            label: "B",
            text: "The identification strategy survives a hostile seminar.",
            scores: { development: 3, appliedMicro: 3, behavioral: 3, labor: 3, history: 2, macro: 1 }
          }
        ]
      },
      {
        id: "question-3",
        prompt: "If economics disappeared tomorrow, what would you become?",
        answers: [
          { label: "A", text: "A consultant", scores: { appliedMicro: 3 } },
          { label: "B", text: "A journalist", scores: { history: 3 } },
          { label: "C", text: "Recruiter", scores: { labor: 3 } },
          { label: "D", text: "An investment banker", scores: { finance: 3 } },
          { label: "E", text: "A diplomat", scores: { politicalEconomy: 3 } },
          { label: "F", text: "Another job?!? Who else will pay me to solve puzzles?", scores: { theory: 3 } },
          { label: "G", text: "Merger and acquisition's lawyer", scores: { io: 3 } },
          { label: "H", text: "Central banker", scores: { macro: 3 } },
          { label: "I", text: "Psychological counsler", scores: { behavioral: 3 } },
          { label: "J", text: "Quantitative researcher", scores: { econometrics: 3 } }
        ]
      },
      {
        id: "question-4",
        prompt: "What is your favorite type of seminar question?",
        answers: [
          { label: "A", text: "“Is this identified?”", scores: { appliedMicro: 3, labor: 2, econometrics: 3 } },
          { label: "B", text: "“What is the mechanism?”", scores: { development: 3, theory: 3, behavioral: 3, politicalEconomy: 3 } },
          { label: "C", text: "“Can you microfound that?”", scores: { io: 3 } },
          { label: "D", text: "“What is the welfare implication?”", scores: { macro: 3, finance: 3 } },
          { label: "E", text: "“How is this economics?”", scores: { development: 1, appliedMicro: 1, labor: 2, io: 1, macro: 1, finance: 1 } },
          { label: "F", text: "\"Do you have a qualitative evidence?\"", scores: { history: 3 } }
        ]
      },
      {
        id: "question-5",
        prompt: "What is your ideal desk setup for getting work done?",
        answers: [
          { label: "A", text: "A clean desk, one notebook, one pen, no distractions.", scores: { theory: 1, econometrics: 3 } },
          { label: "B", text: "Two monitors, 47 tabs, Stata/R/Python open, and a half-finished coffee.", scores: { development: 1, appliedMicro: 2, politicalEconomy: 1, labor: 3, macro: 2, finance: 3 } },
          { label: "C", text: "A whiteboard covered in equations that no one is allowed to erase.", scores: { theory: 2, io: 1, macro: 1 } },
          { label: "D", text: "A messy pile of books, papers, historical documents, and handwritten notes.", scores: { politicalEconomy: 2, history: 3 } },
          { label: "E", text: "A café table, laptop, headphones, and the illusion that this counts as work-life balance.", scores: { behavioral: 3 } },
          { label: "F", text: "A spreadsheet, a calendar, and a terrifyingly organized to-do list.", scores: { development: 2, appliedMicro: 1, io: 2 } }
        ]
      },
      {
        id: "question-6",
        prompt: "Where do you do your best thinking?",
        answers: [
          { label: "A", text: "At the desk, after three uninterrupted hours.", scores: { io: 3, econometrics: 2, macro: 2, finance: 3 } },
          { label: "B", text: "On a walk, when you are supposed to be doing something else.", scores: { politicalEconomy: 1, history: 3, macro: 1 } },
          { label: "C", text: "In the shower, where the perfect idea briefly appears and then disappears forever.", scores: { behavioral: 1 } },
          { label: "D", text: "During seminars, but only because you are quietly (or loudly) disagreeing with the speaker.", scores: { appliedMicro: 2, politicalEconomy: 2, labor: 3 } },
          { label: "E", text: "While talking to people outside academia.", scores: { development: 3, behavioral: 2 } },
          { label: "F", text: "In front of a whiteboard with someone who also thinks this is fun.", scores: { theory: 3, econometrics: 1 } }
        ]
      },
      {
        id: "question-7",
        prompt: "What kind of referee are you?",
        answers: [
          { label: "A", text: "“The question is important, but the design does not answer it.”", scores: { appliedMicro: 3, theory: 3 } },
          { label: "B", text: "“I enjoyed the paper, but I have concerns about interpretation.”", scores: { development: 3 } },
          { label: "C", text: "“The model is elegant, but the economics is unclear.”", scores: { macro: 3 } },
          { label: "D", text: "“The paper would benefit from a clearer welfare benchmark.”", scores: { io: 3 } },
          { label: "E", text: "“The setting is fascinating, but the contribution needs sharpening.”", scores: { behavioral: 3, history: 3, finance: 3 } },
          { label: "F", text: "“I have 19 comments, most of which are minor.”", scores: {} },
          { label: "G", text: "“This is not economics.”", scores: { labor: 3 } },
          { label: "H", text: "“I am trying very hard to be nice.”", scores: { politicalEconomy: 3, econometrics: 3 } }
        ]
      },
      {
        id: "question-8",
        prompt: "At a conference dinner, what are you most likely doing?",
        answers: [
          { label: "A", text: "Asking someone about their data.", scores: { appliedMicro: 3 } },
          { label: "B", text: "Debating whether the mechanism is plausible.", scores: { development: 3 } },
          { label: "C", text: "Explaining a model on a napkin.", scores: { theory: 3 } },
          { label: "D", text: "Quietly networking with terrifying efficiency.", scores: { finance: 3 } },
          { label: "E", text: "Asking people what they are working on outside their main field.", scores: { behavioral: 3 } },
          { label: "F", text: "Having a long conversation about politics, history, or institutions.", scores: { politicalEconomy: 3, history: 3 } },
          { label: "G", text: "Escaping early because tomorrow’s session starts at 9.", scores: { labor: 3, io: 3, econometrics: 3 } },
          { label: "H", text: "Accidentally starting a new coauthored project.", scores: { macro: 3 } }
        ]
      }
    ];

    const form = document.getElementById("economist-quiz");
    const questionsContainer = document.getElementById("economist-quiz-questions");
    const message = document.getElementById("economist-quiz-message");
    const resultContainer = document.getElementById("economist-quiz-result");

    function escapeHtml(value) {
      return value.replace(/[&<>"]/g, function (character) {
        return { "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;" }[character];
      });
    }

    function renderQuestions() {
      questionsContainer.innerHTML = quizQuestions.map(function (question, questionIndex) {
        const answers = question.answers.map(function (answer, answerIndex) {
          const inputId = question.id + "-" + answer.label.toLowerCase();

          return `
            <label class="economist-answer-card" for="${inputId}">
              <input type="radio" id="${inputId}" name="${question.id}" value="${answerIndex}" />
              <span class="economist-answer-text">${escapeHtml(answer.text)}</span>
            </label>
          `;
        }).join("");

        return `
          <fieldset class="economist-question-card">
            <legend>
              <span class="economist-question-number">Question ${questionIndex + 1}</span>
              ${escapeHtml(question.prompt)}
            </legend>
            <div class="economist-answer-grid">${answers}</div>
          </fieldset>
        `;
      }).join("");
    }

    function getSelectedAnswers() {
      return quizQuestions.map(function (question) {
        const selected = form.querySelector(`input[name="${question.id}"]:checked`);
        return selected ? question.answers[Number(selected.value)] : null;
      });
    }

    function scoreAnswers(selectedAnswers) {
      const totals = outcomeOrder.reduce(function (scores, outcome) {
        scores[outcome] = 0;
        return scores;
      }, {});

      selectedAnswers.forEach(function (answer) {
        Object.keys(answer.scores).forEach(function (outcome) {
          if (Object.prototype.hasOwnProperty.call(totals, outcome)) {
            totals[outcome] += answer.scores[outcome] || 0;
          }
        });
      });

      return totals;
    }

    function chooseWinner(totals) {
      return outcomeOrder.reduce(function (winner, outcome) {
        return totals[outcome] > totals[winner] ? outcome : winner;
      }, outcomeOrder[0]);
    }

    function showResult(outcome) {
      const result = quizResults[outcome];
      const shareUrl = window.location.href.split("#")[0];
      const shareText = `I got ${result.label} on the What Type of Economist Should I Be? quiz.`;
      const encodedShareText = encodeURIComponent(shareText);
      const encodedShareUrl = encodeURIComponent(shareUrl);

      resultContainer.innerHTML = `
        <div class="economist-result-card">
          <p class="economist-result-label">Your economist type is</p>
          <h2>${escapeHtml(result.label)}</h2>
          <dl class="economist-result-details">
            <div>
              <dt>Famous economist fit</dt>
              <dd>${escapeHtml(result.famousEconomist)}</dd>
            </div>
            <div>
              <dt>Why it fits</dt>
              <dd>${escapeHtml(result.blurb)}</dd>
            </div>
          </dl>
          <div class="economist-share" aria-label="Share your quiz result">
            <p class="economist-share-title">Share your result</p>
            <div class="economist-share-actions">
              <a class="btn economist-share-link" href="https://twitter.com/intent/tweet?text=${encodedShareText}&url=${encodedShareUrl}" target="_blank" rel="noopener">Post on X</a>
              <a class="btn economist-share-link" href="https://www.facebook.com/sharer/sharer.php?u=${encodedShareUrl}" target="_blank" rel="noopener">Facebook</a>
              <a class="btn economist-share-link" href="https://www.linkedin.com/sharing/share-offsite/?url=${encodedShareUrl}" target="_blank" rel="noopener">LinkedIn</a>
            </div>
          </div>
          <button type="button" class="btn btn--primary economist-retake">Retake quiz</button>
        </div>
      `;
      resultContainer.hidden = false;

      resultContainer.querySelector(".economist-retake").addEventListener("click", function () {
        form.reset();
        resultContainer.hidden = true;
        resultContainer.innerHTML = "";
        message.textContent = "";
        form.scrollIntoView({ behavior: "smooth", block: "start" });
      });
      resultContainer.scrollIntoView({ behavior: "smooth", block: "start" });
    }

    form.addEventListener("submit", function (event) {
      event.preventDefault();

      const selectedAnswers = getSelectedAnswers();

      if (selectedAnswers.some(function (answer) { return answer === null; })) {
        message.textContent = "Please answer every question before getting your result.";
        resultContainer.hidden = true;
        return;
      }

      const totals = scoreAnswers(selectedAnswers);
      const winner = chooseWinner(totals);

      message.textContent = "";
      showResult(winner);
    });

    renderQuestions();
  })();
</script>

<style>
  .economist-quiz-page {
    --quiz-accent: #6366f1;
    --quiz-accent-dark: #4f46e5;
    --quiz-accent-soft: #eef2ff;
    --quiz-warm: #f59e0b;
    --quiz-warm-soft: #fff7ed;
    --quiz-rose: #ec4899;
    --quiz-text: var(--global-text-color);
    --quiz-muted: var(--global-text-color-light, #64748b);
    position: relative;
    isolation: isolate;
  }

  .economist-quiz-page::before {
    content: "";
    position: absolute;
    inset: -1rem -0.75rem auto;
    height: 18rem;
    border-radius: 999px;
    background:
      radial-gradient(circle at 20% 30%, rgba(245, 158, 11, 0.22), transparent 34%),
      radial-gradient(circle at 74% 20%, rgba(99, 102, 241, 0.22), transparent 36%),
      radial-gradient(circle at 52% 78%, rgba(236, 72, 153, 0.12), transparent 42%);
    filter: blur(8px);
    opacity: 0.9;
    pointer-events: none;
    z-index: -1;
  }

  .economist-quiz-hero,
  .economist-question-card,
  .economist-result-card {
    border: 1px solid rgba(99, 102, 241, 0.2);
    border-radius: 22px;
    background:
      linear-gradient(145deg, rgba(255, 255, 255, 0.96), rgba(238, 242, 255, 0.82)),
      radial-gradient(circle at top right, rgba(245, 158, 11, 0.16), transparent 35%);
    box-shadow: 0 18px 42px rgba(15, 23, 42, 0.12);
    color: var(--quiz-text);
  }

  .economist-quiz-hero {
    position: relative;
    overflow: hidden;
    padding: 1.6rem 1.7rem;
    margin-bottom: 1.25rem;
  }

  .economist-quiz-hero::after {
    content: "";
    position: absolute;
    right: -3rem;
    top: -3rem;
    width: 10rem;
    height: 10rem;
    border-radius: 50%;
    background: linear-gradient(135deg, rgba(99, 102, 241, 0.18), rgba(245, 158, 11, 0.16));
    pointer-events: none;
  }

  .economist-quiz-hero h2 {
    position: relative;
    margin: 0.15rem 0 0.65rem;
    color: var(--quiz-text);
    font-size: clamp(1.65rem, 3.6vw, 2.45rem);
    line-height: 1.08;
  }

  .economist-quiz-hero p:last-child {
    margin-bottom: 0;
  }

  .economist-quiz-kicker,
  .economist-result-label,
  .economist-question-number {
    display: inline-block;
    margin: 0;
    color: var(--quiz-accent-dark);
    font-size: 0.78rem;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  .economist-question-card {
    position: relative;
    margin: 0 0 1.15rem;
    padding: 1.15rem;
    overflow: hidden;
  }

  .economist-question-card::before {
    content: "";
    position: absolute;
    inset: 0 auto 0 0;
    width: 0.28rem;
    background: linear-gradient(180deg, var(--quiz-accent), var(--quiz-warm));
  }

  .economist-question-card legend {
    width: 100%;
    margin-bottom: 0.8rem;
    color: var(--quiz-text);
    font-size: 1.05rem;
    font-weight: 700;
    line-height: 1.35;
  }

  .economist-question-number {
    display: inline-flex;
    width: fit-content;
    margin-bottom: 0.45rem;
    padding: 0.2rem 0.55rem;
    border-radius: 999px;
    background: rgba(245, 158, 11, 0.13);
    color: #b45309;
  }

  .economist-answer-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(245px, 1fr));
    gap: 0.8rem;
  }

  .economist-answer-card {
    position: relative;
    display: flex;
    align-items: center;
    min-height: 100%;
    margin: 0;
    padding: 1rem 3.1rem 1rem 1rem;
    border: 1px solid rgba(99, 102, 241, 0.18);
    border-radius: 16px;
    background:
      linear-gradient(180deg, rgba(255, 255, 255, 0.9), rgba(248, 250, 252, 0.76));
    cursor: pointer;
    box-shadow: 0 8px 22px rgba(15, 23, 42, 0.06);
    transition: transform 0.16s ease, box-shadow 0.16s ease, border-color 0.16s ease, background 0.16s ease;
  }

  .economist-answer-card::after {
    content: "";
    position: absolute;
    right: 1rem;
    top: 50%;
    width: 1.15rem;
    height: 1.15rem;
    border: 2px solid rgba(99, 102, 241, 0.35);
    border-radius: 999px;
    background: rgba(255, 255, 255, 0.86);
    box-shadow: inset 0 0 0 0.22rem rgba(255, 255, 255, 0.92);
    transform: translateY(-50%);
    transition: background 0.16s ease, border-color 0.16s ease, box-shadow 0.16s ease;
  }

  .economist-answer-card:hover,
  .economist-answer-card:focus-within {
    transform: translateY(-2px);
    border-color: rgba(79, 70, 229, 0.5);
    box-shadow: 0 14px 28px rgba(99, 102, 241, 0.15);
  }

  .economist-answer-card input {
    position: absolute;
    inline-size: 1px;
    block-size: 1px;
    overflow: hidden;
    clip: rect(0 0 0 0);
    clip-path: inset(50%);
    white-space: nowrap;
  }


  .economist-answer-text {
    color: var(--quiz-text);
    line-height: 1.5;
  }

  .economist-answer-card:has(input:checked) {
    border-color: rgba(99, 102, 241, 0.7);
    background:
      linear-gradient(145deg, rgba(238, 242, 255, 0.98), rgba(255, 251, 235, 0.82));
    box-shadow: 0 14px 30px rgba(99, 102, 241, 0.2);
  }

  .economist-answer-card:has(input:checked)::after {
    border-color: var(--quiz-accent);
    background: var(--quiz-accent);
    box-shadow: inset 0 0 0 0.25rem #ffffff, 0 0 0 0.18rem rgba(99, 102, 241, 0.13);
  }

  .economist-quiz-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 0.8rem;
    align-items: center;
    margin: 1rem 0 1.25rem;
  }

  .economist-quiz-submit,
  .economist-retake {
    border-radius: 999px;
    font-weight: 800;
    box-shadow: 0 10px 22px rgba(99, 102, 241, 0.2);
  }

  .economist-quiz-message {
    min-height: 1.35rem;
    margin: 0;
    color: #b45309;
    font-weight: 700;
  }

  .economist-result {
    margin-top: 1rem;
  }

  .economist-result-card {
    padding: 1.45rem 1.55rem;
    border-left: 6px solid var(--quiz-accent);
  }

  .economist-result-card h2 {
    margin: 0.15rem 0 0.95rem;
    color: var(--quiz-text);
  }

  .economist-result-details {
    display: grid;
    gap: 0.85rem;
    margin: 0 0 1.1rem;
  }

  .economist-result-details div {
    padding: 0.95rem 1rem;
    border: 1px solid rgba(99, 102, 241, 0.12);
    border-radius: 15px;
    background: rgba(255, 255, 255, 0.76);
  }

  .economist-result-details dt {
    margin-bottom: 0.25rem;
    color: var(--quiz-accent-dark);
    font-size: 0.78rem;
    font-weight: 800;
    letter-spacing: 0.06em;
    text-transform: uppercase;
  }

  .economist-result-details dd {
    margin: 0;
    color: var(--quiz-text);
    line-height: 1.5;
  }

  .economist-share {
    margin: 0 0 1.1rem;
    padding: 1rem;
    border: 1px solid rgba(99, 102, 241, 0.14);
    border-radius: 16px;
    background:
      linear-gradient(145deg, rgba(238, 242, 255, 0.74), rgba(255, 247, 237, 0.62));
  }

  .economist-share-title {
    margin: 0 0 0.7rem;
    color: var(--quiz-accent-dark);
    font-size: 0.82rem;
    font-weight: 800;
    letter-spacing: 0.07em;
    text-transform: uppercase;
  }

  .economist-share-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 0.55rem;
  }

  .economist-share-link {
    border-radius: 999px;
    border: 2px solid #4338ca !important;
    background: #ffffff;
    background-color: #ffffff;
    color: #312e81 !important;
    font-size: 0.82rem;
    font-weight: 800;
    text-decoration: none;
    box-shadow: 0 8px 18px rgba(67, 56, 202, 0.18);
  }

  .economist-share-link:hover,
  .economist-share-link:focus {
    border-color: #312e81 !important;
    background: #4338ca;
    background-color: #4338ca;
    color: #ffffff !important;
    transform: translateY(-1px);
  }

  .economist-share-link:focus-visible {
    outline: 3px solid #f59e0b;
    outline-offset: 3px;
  }

  @media (max-width: 640px) {
    .economist-quiz-hero,
    .economist-question-card,
    .economist-result-card {
      border-radius: 14px;
    }

    .economist-quiz-hero,
    .economist-result-card {
      padding: 1rem;
    }

    .economist-question-card {
      padding: 0.9rem;
    }

    .economist-answer-grid {
      grid-template-columns: 1fr;
    }

    .economist-quiz-actions {
      align-items: stretch;
      flex-direction: column;
    }

    .economist-share-actions {
      flex-direction: column;
    }

    .economist-quiz-submit,
    .economist-retake,
    .economist-share-link {
      width: 100%;
    }
  }

  html[data-theme="dark"] .economist-quiz-hero,
  html[data-theme="dark"] .economist-question-card,
  html[data-theme="dark"] .economist-result-card {
    border-color: rgba(129, 140, 248, 0.34);
    background: linear-gradient(145deg, rgba(30, 41, 59, 0.86), rgba(55, 48, 163, 0.32));
    box-shadow: 0 14px 30px rgba(2, 6, 23, 0.48);
  }

  html[data-theme="dark"] .economist-answer-card,
  html[data-theme="dark"] .economist-result-details div,
  html[data-theme="dark"] .economist-share {
    border-color: rgba(129, 140, 248, 0.3);
    background: rgba(15, 23, 42, 0.58);
  }

  html[data-theme="dark"] .economist-answer-card::after {
    border-color: rgba(129, 140, 248, 0.52);
    background: rgba(15, 23, 42, 0.88);
    box-shadow: inset 0 0 0 0.22rem rgba(15, 23, 42, 0.92);
  }

  html[data-theme="dark"] .economist-answer-card:has(input:checked) {
    border-color: rgba(129, 140, 248, 0.78);
    background: linear-gradient(145deg, rgba(49, 46, 129, 0.72), rgba(120, 53, 15, 0.34));
  }

  html[data-theme="dark"] .economist-answer-card:has(input:checked)::after {
    background: #a5b4fc;
    border-color: #c7d2fe;
    box-shadow: inset 0 0 0 0.25rem rgba(15, 23, 42, 0.96), 0 0 0 0.18rem rgba(129, 140, 248, 0.16);
  }

  html[data-theme="dark"] .economist-share-link {
    border-color: #c7d2fe !important;
    background: #eef2ff;
    background-color: #eef2ff;
    color: #1e1b4b !important;
    box-shadow: 0 10px 24px rgba(165, 180, 252, 0.24);
  }

  html[data-theme="dark"] .economist-share-link:hover,
  html[data-theme="dark"] .economist-share-link:focus {
    border-color: #fde68a !important;
    background: #fbbf24;
    background-color: #fbbf24;
    color: #111827 !important;
  }

  html[data-theme="dark"] .economist-quiz-message {
    color: #fbbf24;
  }
</style>
