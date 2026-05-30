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
      a famous economist fit, and the inner monologue you were probably already having during seminar.
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
    const economistTypes = [
      "Development Economist",
      "Applied Micro / Causal Inference Economist",
      "Economic Theorist",
      "Behavioral Economist",
      "Political Economy Economist",
      "Public Economist",
      "Health Economist",
      "Labor Economist",
      "Economic Historian",
      "Urban / Spatial Economist",
      "IO / Innovation Economist",
      "Econometrician / Methods Person"
    ];

    const quizQuestions = [
      {
        id: "question-1",
        prompt: "Which would you rather do?",
        answers: [
          {
            label: "A",
            text: "Ask a big, important question, even if the answer is necessarily incomplete.",
            scores: ["Development Economist", "Political Economy Economist", "Economic Historian", "Public Economist", "Urban / Spatial Economist"]
          },
          {
            label: "B",
            text: "Ask a narrower question and answer it precisely.",
            scores: ["Applied Micro / Causal Inference Economist", "Econometrician / Methods Person", "Economic Theorist", "IO / Innovation Economist", "Health Economist"]
          }
        ]
      },
      {
        id: "question-2",
        prompt: "What makes you trust a result?",
        answers: [
          { label: "A", text: "The logic is airtight.", scores: ["Economic Theorist", "Public Economist", "IO / Innovation Economist"] },
          { label: "B", text: "The assignment is randomized.", scores: ["Development Economist", "Health Economist", "Labor Economist", "Behavioral Economist"] },
          { label: "C", text: "The identification strategy survives a hostile seminar.", scores: ["Applied Micro / Causal Inference Economist", "Econometrician / Methods Person", "Political Economy Economist"] }
        ]
      },
      {
        id: "question-3",
        prompt: "If economics disappeared tomorrow, what would you become?",
        answers: [
          { label: "A", text: "A doctor", scores: ["Health Economist"] },
          { label: "B", text: "A journalist", scores: ["Political Economy Economist", "Economic Historian"] },
          { label: "C", text: "A social worker", scores: ["Development Economist", "Public Economist", "Labor Economist"] },
          { label: "D", text: "An investment banker", scores: ["IO / Innovation Economist", "Public Economist"] },
          { label: "E", text: "A diplomat", scores: ["Political Economy Economist", "Development Economist"] },
          { label: "F", text: "A startup founder", scores: ["IO / Innovation Economist", "Behavioral Economist"] },
          { label: "G", text: "An urban planner", scores: ["Urban / Spatial Economist"] },
          { label: "H", text: "A teacher", scores: ["Labor Economist", "Development Economist"] }
        ]
      },
      {
        id: "seminar-question",
        prompt: "What is your favorite type of seminar question?",
        answers: [
          { label: "A", text: "“Is this identified?”", scores: ["Applied Micro / Causal Inference Economist", "Econometrician / Methods Person"] },
          { label: "B", text: "“What is the mechanism?”", scores: ["Behavioral Economist", "Development Economist", "Political Economy Economist", "Labor Economist"] },
          { label: "C", text: "“Can you microfound that?”", scores: ["Economic Theorist", "IO / Innovation Economist"] },
          { label: "D", text: "“What is the welfare implication?”", scores: ["Public Economist"] },
          { label: "E", text: "“Where is the theory?”", scores: ["Economic Theorist", "Econometrician / Methods Person", "IO / Innovation Economist"] },
          { label: "F", text: "“How is this economics?”", scores: ["Economic Historian", "Political Economy Economist", "Behavioral Economist"] }
        ]
      },
      {
        id: "question-5",
        prompt: "What is your ideal desk setup for getting work done?",
        answers: [
          { label: "A", text: "A clean desk, one notebook, one pen, no distractions.", scores: ["Economic Theorist", "Econometrician / Methods Person", "Public Economist"] },
          { label: "B", text: "Two monitors, 47 tabs, Stata/R/Python open, and a half-finished coffee.", scores: ["Applied Micro / Causal Inference Economist", "Development Economist", "Health Economist", "Labor Economist"] },
          { label: "C", text: "A whiteboard covered in equations that no one is allowed to erase.", scores: ["Economic Theorist", "IO / Innovation Economist", "Econometrician / Methods Person"] },
          { label: "D", text: "A messy pile of books, papers, historical documents, and handwritten notes.", scores: ["Economic Historian", "Political Economy Economist"] },
          { label: "E", text: "A café table, laptop, headphones, and the illusion that this counts as work-life balance.", scores: ["Behavioral Economist", "Labor Economist", "Development Economist"] },
          { label: "F", text: "A spreadsheet, a calendar, and a terrifyingly organized to-do list.", scores: ["Public Economist", "IO / Innovation Economist", "Urban / Spatial Economist", "Applied Micro / Causal Inference Economist"] }
        ]
      },
      {
        id: "question-6",
        prompt: "Where do you do your best thinking?",
        answers: [
          { label: "A", text: "At the desk, after three uninterrupted hours.", scores: ["Econometrician / Methods Person", "Economic Theorist"] },
          { label: "B", text: "On a walk, when you are supposed to be doing something else.", scores: ["Behavioral Economist", "Economic Historian"] },
          { label: "C", text: "In the shower, where the perfect identification strategy briefly appears and then disappears forever.", scores: ["Applied Micro / Causal Inference Economist", "Econometrician / Methods Person", "Development Economist"] },
          { label: "D", text: "During seminars, but only because you are quietly disagreeing with the speaker.", scores: ["Economic Theorist", "IO / Innovation Economist", "Public Economist"] },
          { label: "E", text: "While talking to people outside academia.", scores: ["Development Economist", "Health Economist", "Labor Economist", "Political Economy Economist"] },
          { label: "F", text: "At 1 a.m., when the deadline has become real.", scores: ["Applied Micro / Causal Inference Economist", "IO / Innovation Economist", "Public Economist"] },
          { label: "G", text: "In front of a whiteboard with someone who also thinks this is fun.", scores: ["Economic Theorist", "IO / Innovation Economist", "Econometrician / Methods Person"] }
        ]
      },
      {
        id: "question-7",
        prompt: "What kind of referee are you?",
        answers: [
          { label: "A", text: "“The question is important, but the design does not answer it.”", scores: ["Applied Micro / Causal Inference Economist", "Econometrician / Methods Person"] },
          { label: "B", text: "“I enjoyed the paper, but I have concerns about interpretation.”", scores: ["Behavioral Economist", "Labor Economist", "Health Economist"] },
          { label: "C", text: "“The model is elegant, but the economics is unclear.”", scores: ["Economic Theorist", "IO / Innovation Economist"] },
          { label: "D", text: "“The paper would benefit from a clearer welfare benchmark.”", scores: ["Public Economist"] },
          { label: "E", text: "“The setting is fascinating, but the contribution needs sharpening.”", scores: ["Economic Historian", "Political Economy Economist", "Urban / Spatial Economist"] },
          { label: "F", text: "“I have 19 comments, most of which are minor.”", scores: ["Econometrician / Methods Person", "Applied Micro / Causal Inference Economist"] },
          { label: "G", text: "“This is not economics.”", scores: ["Economic Theorist", "Public Economist"] },
          { label: "H", text: "“I am trying very hard to be nice.”", scores: ["Development Economist", "Behavioral Economist", "Labor Economist"] }
        ]
      },
      {
        id: "question-8",
        prompt: "At a conference dinner, what are you most likely doing?",
        answers: [
          { label: "A", text: "Asking someone about their data.", scores: ["Applied Micro / Causal Inference Economist", "Econometrician / Methods Person", "Health Economist"] },
          { label: "B", text: "Debating whether the mechanism is plausible.", scores: ["Behavioral Economist", "Development Economist", "Political Economy Economist", "Labor Economist"] },
          { label: "C", text: "Explaining a model on a napkin.", scores: ["Economic Theorist", "IO / Innovation Economist"] },
          { label: "D", text: "Quietly networking with terrifying efficiency.", scores: ["IO / Innovation Economist", "Public Economist"] },
          { label: "E", text: "Asking people what they are working on outside their main field.", scores: ["Behavioral Economist", "Development Economist", "Urban / Spatial Economist"] },
          { label: "F", text: "Having a long conversation about politics, history, or institutions.", scores: ["Political Economy Economist", "Economic Historian"] },
          { label: "G", text: "Escaping early because tomorrow’s session starts at 9.", scores: ["Econometrician / Methods Person", "Applied Micro / Causal Inference Economist"] },
          { label: "H", text: "Accidentally starting a new coauthored project.", scores: ["IO / Innovation Economist", "Development Economist", "Labor Economist", "Urban / Spatial Economist"] }
        ]
      }
    ];

    const quizResults = {
      "Development Economist": {
        famousFit: "Esther Duflo",
        explanation: "You want economics to answer questions that matter in the real world: poverty, education, health, governance, and policy design. You are comfortable with messy settings, imperfect implementation, and the fact that the best question is not always the cleanest one.",
        innerMonologue: "But what would this actually change for people?"
      },
      "Applied Micro / Causal Inference Economist": {
        famousFit: "Joshua Angrist",
        explanation: "You believe a good paper begins with a sharp question and survives only if the design can defend itself. You care about clean variation, credible counterfactuals, and whether the coefficient means what the author says it means.",
        innerMonologue: "Interesting. But what is the identifying variation?"
      },
      "Economic Theorist": {
        famousFit: "Kenneth Arrow",
        explanation: "You like precision, abstraction, and arguments that are true because they have to be true. You are happiest when a complicated social problem becomes a clean model with assumptions, propositions, and implications.",
        innerMonologue: "This is intuitive, but can we prove it?"
      },
      "Behavioral Economist": {
        famousFit: "Richard Thaler",
        explanation: "You are interested in the gap between how people are supposed to behave and how they actually behave. You like mechanisms, mistakes, biases, norms, defaults, and all the ways real humans ruin elegant models.",
        innerMonologue: "But would people actually do that?"
      },
      "Political Economy Economist": {
        famousFit: "Daron Acemoglu",
        explanation: "You think economics is inseparable from power. You care about institutions, democracy, conflict, state capacity, elites, and the political constraints that shape economic outcomes.",
        innerMonologue: "Who has power here, and what do they want?"
      },
      "Public Economist": {
        famousFit: "James Mirrlees",
        explanation: "You care about welfare, redistribution, taxation, incentives, and how governments should design policy when people and firms respond strategically. You are the person asking whether the result changes the optimal policy rule.",
        innerMonologue: "What is the welfare benchmark?"
      },
      "Health Economist": {
        famousFit: "Amy Finkelstein",
        explanation: "You are drawn to questions where policy, insurance, public finance, and human vulnerability meet. You want to know how institutions shape health care access, medical spending, risk, and inequality.",
        innerMonologue: "What does this do to care, costs, and outcomes?"
      },
      "Labor Economist": {
        famousFit: "Claudia Goldin",
        explanation: "You care about work, wages, families, education, gender, inequality, and long-run changes in labor markets. You are interested in both institutions and people’s actual life choices.",
        innerMonologue: "How does this change people’s work and lives?"
      },
      "Economic Historian": {
        famousFit: "Douglass North",
        explanation: "You believe the present is impossible to understand without the past. You like archives, institutions, long-run change, historical shocks, and settings where the context is not noise but the point.",
        innerMonologue: "This makes more sense if we go back 150 years."
      },
      "Urban / Spatial Economist": {
        famousFit: "Edward Glaeser",
        explanation: "You think place matters. You care about cities, housing, migration, commuting, agglomeration, segregation, and how geography shapes opportunity.",
        innerMonologue: "Where is this happening, and why there?"
      },
      "IO / Innovation Economist": {
        famousFit: "Jean Tirole",
        explanation: "You are interested in firms, platforms, market power, competition, innovation, regulation, and strategic behavior. You like economics where everyone is optimizing and everyone is slightly terrifying.",
        innerMonologue: "What is the firm’s strategy, and what can the regulator actually do?"
      },
      "Econometrician / Methods Person": {
        famousFit: "James Heckman",
        explanation: "You care about what can be learned, what cannot be learned, and what assumptions are secretly doing all the work. You are interested in methods, selection, interpretation, and the structure behind estimates.",
        innerMonologue: "This estimate is only meaningful under which assumptions?"
      }
    };

    const form = document.getElementById("economist-quiz");
    const questionsContainer = document.getElementById("economist-quiz-questions");
    const message = document.getElementById("economist-quiz-message");
    const resultContainer = document.getElementById("economist-quiz-result");

    function escapeHtml(value) {
      return value.replace(/[&<>"]/g, function (character) {
        return { "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;" }[character];
      });
    }

    function getAnswerPoints(scores) {
      return scores.reduce(function (points, type, index) {
        points[type] = index === 0 ? 2 : 1;
        return points;
      }, {});
    }

    function renderQuestions() {
      questionsContainer.innerHTML = quizQuestions.map(function (question, questionIndex) {
        const answers = question.answers.map(function (answer, answerIndex) {
          const inputId = question.id + "-" + answer.label.toLowerCase();

          return `
            <label class="economist-answer-card" for="${inputId}">
              <input type="radio" id="${inputId}" name="${question.id}" value="${answerIndex}" />
              <span class="economist-answer-letter">${answer.label}</span>
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
      const totals = economistTypes.reduce(function (scores, type) {
        scores[type] = 0;
        return scores;
      }, {});

      selectedAnswers.forEach(function (answer) {
        const points = getAnswerPoints(answer.scores);
        Object.keys(points).forEach(function (type) {
          totals[type] += points[type];
        });
      });

      return totals;
    }

    function chooseWinner(totals, seminarAnswer) {
      const highestScore = Math.max.apply(null, economistTypes.map(function (type) { return totals[type]; }));
      let tiedTypes = economistTypes.filter(function (type) { return totals[type] === highestScore; });

      if (tiedTypes.length > 1 && seminarAnswer) {
        const tieBreakPoints = getAnswerPoints(seminarAnswer.scores);
        const highestTieBreakScore = Math.max.apply(null, tiedTypes.map(function (type) { return tieBreakPoints[type] || 0; }));
        const seminarWinners = tiedTypes.filter(function (type) { return (tieBreakPoints[type] || 0) === highestTieBreakScore; });

        if (highestTieBreakScore > 0) {
          tiedTypes = seminarWinners;
        }
      }

      return tiedTypes[0];
    }

    function showResult(type) {
      const result = quizResults[type];

      resultContainer.innerHTML = `
        <div class="economist-result-card">
          <p class="economist-result-label">Your economist type is</p>
          <h2>${escapeHtml(type)}</h2>
          <dl class="economist-result-details">
            <div>
              <dt>Famous economist fit</dt>
              <dd>${escapeHtml(result.famousFit)}</dd>
            </div>
            <div>
              <dt>Why it fits</dt>
              <dd>${escapeHtml(result.explanation)}</dd>
            </div>
            <div>
              <dt>Inner monologue</dt>
              <dd>“${escapeHtml(result.innerMonologue)}”</dd>
            </div>
          </dl>
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
      const seminarQuestionIndex = quizQuestions.findIndex(function (question) { return question.id === "seminar-question"; });
      const winner = chooseWinner(totals, selectedAnswers[seminarQuestionIndex]);

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
    --quiz-warm: #f59e0b;
    --quiz-text: var(--global-text-color);
    --quiz-muted: var(--global-text-color-light, #64748b);
  }

  .economist-quiz-hero,
  .economist-question-card,
  .economist-result-card {
    border: 1px solid rgba(99, 102, 241, 0.24);
    border-radius: 18px;
    background: linear-gradient(145deg, rgba(255, 255, 255, 0.98), rgba(238, 242, 255, 0.84));
    box-shadow: 0 14px 30px rgba(15, 23, 42, 0.11);
    color: var(--quiz-text);
  }

  .economist-quiz-hero {
    padding: 1.25rem 1.35rem;
    margin-bottom: 1.2rem;
  }

  .economist-quiz-hero h2 {
    margin: 0.15rem 0 0.55rem;
    color: var(--quiz-text);
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
    margin: 0 0 1rem;
    padding: 1rem;
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
    display: block;
    margin-bottom: 0.25rem;
    color: var(--quiz-warm);
  }

  .economist-answer-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
    gap: 0.7rem;
  }

  .economist-answer-card {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 0.65rem;
    align-items: start;
    min-height: 100%;
    margin: 0;
    padding: 0.85rem;
    border: 1px solid rgba(99, 102, 241, 0.22);
    border-radius: 14px;
    background: rgba(255, 255, 255, 0.78);
    cursor: pointer;
    transition: transform 0.16s ease, box-shadow 0.16s ease, border-color 0.16s ease, background 0.16s ease;
  }

  .economist-answer-card:hover,
  .economist-answer-card:focus-within {
    transform: translateY(-1px);
    border-color: rgba(79, 70, 229, 0.58);
    box-shadow: 0 9px 20px rgba(99, 102, 241, 0.16);
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

  .economist-answer-letter {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 2rem;
    height: 2rem;
    border-radius: 999px;
    background: rgba(99, 102, 241, 0.12);
    color: var(--quiz-accent-dark);
    font-weight: 800;
    transition: background 0.16s ease, color 0.16s ease, box-shadow 0.16s ease;
  }

  .economist-answer-text {
    color: var(--quiz-text);
    line-height: 1.45;
  }

  .economist-answer-card:has(input:checked) {
    border-color: var(--quiz-accent);
    background: linear-gradient(145deg, rgba(238, 242, 255, 0.95), rgba(255, 251, 235, 0.72));
    box-shadow: 0 10px 24px rgba(99, 102, 241, 0.2);
  }

  .economist-answer-card:has(input:checked) .economist-answer-letter {
    background: var(--quiz-accent);
    color: #ffffff;
    box-shadow: 0 6px 14px rgba(99, 102, 241, 0.32);
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
    font-weight: 700;
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
    padding: 1.25rem 1.35rem;
    border-left: 5px solid var(--quiz-accent);
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
    padding: 0.8rem 0.9rem;
    border-radius: 13px;
    background: rgba(255, 255, 255, 0.72);
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

    .economist-quiz-submit,
    .economist-retake {
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
  html[data-theme="dark"] .economist-result-details div {
    border-color: rgba(129, 140, 248, 0.3);
    background: rgba(15, 23, 42, 0.58);
  }

  html[data-theme="dark"] .economist-answer-card:has(input:checked) {
    border-color: rgba(129, 140, 248, 0.78);
    background: linear-gradient(145deg, rgba(49, 46, 129, 0.72), rgba(120, 53, 15, 0.34));
  }

  html[data-theme="dark"] .economist-quiz-message {
    color: #fbbf24;
  }
</style>
