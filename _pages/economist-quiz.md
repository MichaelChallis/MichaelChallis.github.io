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
      a famous economist fit, and why that result matches your seminar instincts.
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
      "Development",
      "Applied micro",
      "Theory",
      "Behavioral",
      "Political econ",
      "Labor",
      "History",
      "IO",
      "Econometrics",
      "Macro",
      "Finance"
    ];

    const economistDisplayNames = {
      "Development": "Development",
      "Applied micro": "Applied Micro",
      "Theory": "Theory",
      "Behavioral": "Behavioral",
      "Political econ": "Political Economy",
      "Labor": "Labor",
      "History": "History",
      "IO": "Industrial Organization",
      "Econometrics": "Econometrics",
      "Macro": "Macro",
      "Finance": "Finance"
    };

    const quizQuestions = [
      {
        id: "question-1",
        prompt: "Which would you rather do?",
        answers: [
          {
            label: "A",
            text: "Ask a big, important question, even if the answer is necessarily incomplete.",
            scores: {
              "Development": 3,
              "Behavioral": 1,
              "Political econ": 2,
              "Labor": 1,
              "History": 2,
              "Macro": 3,
              "Finance": 1
            }
          },
          {
            label: "B",
            text: "Ask a narrower question and answer it precisely.",
            scores: {
              "Applied micro": 3,
              "Theory": 2,
              "Behavioral": 1,
              "Labor": 1,
              "IO": 2,
              "Econometrics": 3,
              "Finance": 1
            }
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
            scores: {
              "Theory": 3,
              "Political econ": 2,
              "IO": 2,
              "Econometrics": 3,
              "Macro": 1,
              "Finance": 3
            }
          },
          {
            label: "B",
            text: "The identification strategy survives a hostile seminar.",
            scores: {
              "Development": 3,
              "Applied micro": 3,
              "Behavioral": 3,
              "Labor": 3,
              "History": 2,
              "Macro": 1
            }
          }
        ]
      },
      {
        id: "question-3",
        prompt: "If economics disappeared tomorrow, what would you become?",
        answers: [
          { label: "A", text: "A consultant", scores: { "Applied micro": 3 } },
          { label: "B", text: "A journalist", scores: { "History": 3 } },
          { label: "C", text: "Recruiter", scores: { "Labor": 3 } },
          { label: "D", text: "An investment banker", scores: { "Finance": 3 } },
          { label: "E", text: "A diplomat", scores: { "Political econ": 3 } },
          { label: "F", text: "Another job?!? Who else will pay me to solve puzzles?", scores: { "Theory": 3 } },
          { label: "G", text: "Merger and acquisition's lawyer", scores: { "IO": 3 } },
          { label: "H", text: "Central banker", scores: { "Macro": 3 } },
          { label: "I", text: "Psychological counsler", scores: { "Behavioral": 3 } },
          { label: "J", text: "Quantitative researcher", scores: { "Econometrics": 3 } }
        ]
      },
      {
        id: "seminar-question",
        prompt: "What is your favorite type of seminar question?",
        answers: [
          {
            label: "A",
            text: "“Is this identified?”",
            scores: { "Applied micro": 3, "Labor": 2, "Econometrics": 3 }
          },
          {
            label: "B",
            text: "“What is the mechanism?”",
            scores: { "Development": 3, "Theory": 3, "Behavioral": 3, "Political econ": 3 }
          },
          {
            label: "C",
            text: "“Can you microfound that?”",
            scores: { "IO": 3 }
          },
          {
            label: "D",
            text: "“What is the welfare implication?”",
            scores: { "Macro": 3, "Finance": 3 }
          },
          {
            label: "E",
            text: "“How is this economics?”",
            scores: {
              "Development": 1,
              "Applied micro": 1,
              "Labor": 2,
              "IO": 1,
              "Macro": 1,
              "Finance": 1
            }
          },
          {
            label: "F",
            text: "\"Do you have a qualitative evidence?\"",
            scores: { "History": 3 }
          }
        ]
      },
      {
        id: "question-5",
        prompt: "What is your ideal desk setup for getting work done?",
        answers: [
          {
            label: "A",
            text: "A clean desk, one notebook, one pen, no distractions.",
            scores: { "Theory": 1, "Econometrics": 3 }
          },
          {
            label: "B",
            text: "Two monitors, 47 tabs, Stata/R/Python open, and a half-finished coffee.",
            scores: {
              "Development": 1,
              "Applied micro": 2,
              "Political econ": 1,
              "Labor": 3,
              "Macro": 2,
              "Finance": 3
            }
          },
          {
            label: "C",
            text: "A whiteboard covered in equations that no one is allowed to erase.",
            scores: { "Theory": 2, "IO": 1, "Macro": 1 }
          },
          {
            label: "D",
            text: "A messy pile of books, papers, historical documents, and handwritten notes.",
            scores: { "Political econ": 2, "History": 3 }
          },
          {
            label: "E",
            text: "A café table, laptop, headphones, and the illusion that this counts as work-life balance.",
            scores: { "Behavioral": 3 }
          },
          {
            label: "F",
            text: "A spreadsheet, a calendar, and a terrifyingly organized to-do list.",
            scores: { "Development": 2, "Applied micro": 1, "IO": 2 }
          }
        ]
      },
      {
        id: "question-6",
        prompt: "Where do you do your best thinking?",
        answers: [
          {
            label: "A",
            text: "At the desk, after three uninterrupted hours.",
            scores: { "IO": 3, "Econometrics": 2, "Macro": 2, "Finance": 3 }
          },
          {
            label: "B",
            text: "On a walk, when you are supposed to be doing something else.",
            scores: { "Political econ": 1, "History": 3, "Macro": 1 }
          },
          {
            label: "C",
            text: "In the shower, where the perfect idea briefly appears and then disappears forever.",
            scores: { "Behavioral": 1 }
          },
          {
            label: "D",
            text: "During seminars, but only because you are quietly (or loudly) disagreeing with the speaker.",
            scores: { "Applied micro": 2, "Political econ": 2, "Labor": 3 }
          },
          {
            label: "E",
            text: "While talking to people outside academia.",
            scores: { "Development": 3, "Behavioral": 2 }
          },
          {
            label: "F",
            text: "In front of a whiteboard with someone who also thinks this is fun.",
            scores: { "Theory": 3, "Econometrics": 1 }
          }
        ]
      },
      {
        id: "question-7",
        prompt: "What kind of referee are you?",
        answers: [
          {
            label: "A",
            text: "“The question is important, but the design does not answer it.”",
            scores: { "Applied micro": 3, "Theory": 3 }
          },
          {
            label: "B",
            text: "“I enjoyed the paper, but I have concerns about interpretation.”",
            scores: { "Development": 3 }
          },
          {
            label: "C",
            text: "“The model is elegant, but the economics is unclear.”",
            scores: { "Macro": 3 }
          },
          {
            label: "D",
            text: "“The paper would benefit from a clearer welfare benchmark.”",
            scores: { "IO": 3 }
          },
          {
            label: "E",
            text: "“The setting is fascinating, but the contribution needs sharpening.”",
            scores: { "Behavioral": 3, "History": 3, "Finance": 3 }
          },
          {
            label: "F",
            text: "“I have 19 comments, most of which are minor.”",
            scores: {}
          },
          {
            label: "G",
            text: "“This is not economics.”",
            scores: { "Labor": 3 }
          },
          {
            label: "H",
            text: "“I am trying very hard to be nice.”",
            scores: { "Political econ": 3, "Econometrics": 3 }
          }
        ]
      },
      {
        id: "question-8",
        prompt: "At a conference dinner, what are you most likely doing?",
        answers: [
          { label: "A", text: "Asking someone about their data.", scores: { "Applied micro": 3 } },
          { label: "B", text: "Debating whether the mechanism is plausible.", scores: { "Development": 3 } },
          { label: "C", text: "Explaining a model on a napkin.", scores: { "Theory": 3 } },
          { label: "D", text: "Quietly networking with terrifying efficiency.", scores: { "Finance": 3 } },
          { label: "E", text: "Asking people what they are working on outside their main field.", scores: { "Behavioral": 3 } },
          { label: "F", text: "Having a long conversation about politics, history, or institutions.", scores: { "Political econ": 3, "History": 3 } },
          { label: "G", text: "Escaping early because tomorrow’s session starts at 9.", scores: { "Labor": 3, "IO": 3, "Econometrics": 3 } },
          { label: "H", text: "Accidentally starting a new coauthored project.", scores: { "Macro": 3 } }
        ]
      }
    ];

    const quizResults = {
      "Development": {
        famousFit: "Esther Duflo",
        explanation: "You want economics to answer big, important questions, but you still care whether the design can survive a hostile seminar. You are drawn to mechanisms, real-world institutions, and conversations outside academia. Your instinct is: “This question matters — now how do we identify it?”"
      },
      "Applied micro": {
        famousFit: "Joshua Angrist",
        explanation: "You like narrow questions that can be answered cleanly. You trust research when the empirical design is sharp, the data are credible, and someone can explain exactly what variation is doing the work. Your seminar question is probably: “Is this identified?”"
      },
      "Theory": {
        famousFit: "Kenneth Arrow",
        explanation: "You like clean logic, precise assumptions, and arguments that hold together from first principles. You are drawn to puzzles, models, strategic interaction, and the beauty of a result that feels inevitable once it is written down. Your instinct is to ask: “What is the structure underneath this?”"
      },
      "Behavioral": {
        famousFit: "Richard Thaler",
        explanation: "You think the most interesting economics starts when people stop behaving like perfectly rational agents. You like mechanisms, psychology, interpretation, and settings where human quirks actually matter. You are open to ideas from outside the standard economics toolkit."
      },
      "Political econ": {
        famousFit: "Daron Acemoglu",
        explanation: "You are interested in power, institutions, incentives, and why societies choose the policies they do. You like big questions, mechanisms, and long conversations about politics, history, or institutions. Your instinct is to ask how economic outcomes are shaped by rules, conflict, and authority."
      },
      "Labor": {
        famousFit: "David Card",
        explanation: "You are empirical, practical, and slightly ruthless about whether something counts as economics. You like data, identification, human behavior in markets, and seminar arguments where someone is quietly — or loudly — disagreeing with the speaker."
      },
      "History": {
        famousFit: "Douglass North",
        explanation: "You think economics makes more sense when it is put in historical context. You are drawn to institutions, long-run change, political order, and the question of why economies develop along different paths. You do not want history as decoration; you want history as evidence about how institutions shape economic life."
      },
      "IO": {
        famousFit: "Jean Tirole",
        explanation: "You like strategic behavior, firms, markets, and welfare. You are the person asking whether the incentives have been modeled properly and whether the benchmark makes sense. Your brain is happiest when market structure and strategic interaction are both on the table."
      },
      "Econometrics": {
        famousFit: "Guido Imbens",
        explanation: "You want precision, structure, and clean answers. You trust airtight logic, careful measurement, and designs that make the identifying variation explicit. You are not necessarily impressed by a big question unless the method can actually answer it."
      },
      "Macro": {
        famousFit: "Olivier Blanchard",
        explanation: "You are comfortable with big questions: growth, crises, inflation, policy, welfare, and the whole economy at once. You accept that answers may be incomplete, but you still want a model that clarifies the tradeoffs. Central banker energy."
      },
      "Finance": {
        famousFit: "Eugene Fama",
        explanation: "You are interested in risk, incentives, markets, and how information gets priced. You like questions where theory, data, and real-world stakes meet directly. You probably enjoy settings where small assumptions can have large consequences for valuation, behavior, and welfare."
      }
    };

    const form = document.getElementById("economist-quiz");
    const questionsContainer = document.getElementById("economist-quiz-questions");
    const message = document.getElementById("economist-quiz-message");
    const resultContainer = document.getElementById("economist-quiz-result");

    function escapeHtml(value) {
      return String(value).replace(/[&<>"]/g, function (character) {
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
              <span class="economist-answer-letter">${escapeHtml(answer.label)}</span>
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
        Object.entries(answer.scores).forEach(function ([type, value]) {
          if (Object.prototype.hasOwnProperty.call(totals, type)) {
            totals[type] += value;
          }
        });
      });

      return totals;
    }

    function chooseWinner(totals, seminarAnswer) {
      const highestScore = Math.max.apply(null, economistTypes.map(function (type) { return totals[type]; }));
      let tiedTypes = economistTypes.filter(function (type) { return totals[type] === highestScore; });

      if (tiedTypes.length > 1 && seminarAnswer) {
        const highestTieBreakScore = Math.max.apply(null, tiedTypes.map(function (type) { return seminarAnswer.scores[type] || 0; }));
        const seminarWinners = tiedTypes.filter(function (type) { return (seminarAnswer.scores[type] || 0) === highestTieBreakScore; });

        if (seminarWinners.length === 1) {
          return seminarWinners[0];
        }
      }

      return tiedTypes[0];
    }

    function showResult(type) {
      const result = quizResults[type];

      resultContainer.innerHTML = `
        <div class="economist-result-card">
          <p class="economist-result-label">Your economist type is</p>
          <h2>${escapeHtml(economistDisplayNames[type])}</h2>
          <dl class="economist-result-details">
            <div>
              <dt>Famous economist fit</dt>
              <dd>${escapeHtml(result.famousFit)}</dd>
            </div>
            <div>
              <dt>Why it fits</dt>
              <dd>${escapeHtml(result.explanation)}</dd>
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
