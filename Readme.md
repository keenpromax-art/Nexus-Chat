⚡ Nexus

AI Textbook Replicator & Multi-Mode Study Environment

Nexus is a dark-first, single-file Progressive Web Application (PWA) that turns any book or certification syllabus into an interactive, chapter-by-chapter AI tutoring curriculum. Combine instant book replication with 44+ specialized pedagogical response modes, interactive LaTeX formula sliders, and resilient multi-provider AI routing.

👉 Launch Live Web App: https://nexus-chat-473.pages.dev/

📖 Table of Contents

📚 The Dynamic Book Replicator ("Add Any Book")

🎛️ 44+ Pedagogical Response Modes

🚀 Quick Start

✨ Core Interactive Features

⌨️ Keyboard Shortcuts & Slash Commands

🏗️ Backend API Contract & Deployment

🔒 Privacy & Local Storage

📚 The Dynamic Book Replicator ("Add Any Book")

At the heart of Nexus is its Book Library & Custom Curriculum Engine (Alt + B). Instead of asking generic, ungrounded questions in a blank chat box, Nexus lets you study through the exact structural lens of any textbook, handbook, or exam syllabus.

1. Replicate Any Book into a Structured Curriculum

Type the title (and author/edition) of any book into the "Add a book" bar inside the Book Library and click Generate TOC:

High-Fidelity Structural Replica: Nexus instructs the AI to reconstruct a rigorous, 2-level Module (Chapter/Part) → Topic (Section/Concept) breakdown (6–20 chapters, 3–12 self-contained study units per chapter) matching the real book's structure and terminology.

Quality-Filtered Study Units: Automatically strips structural fluff ("Introduction", "Summary", "Bibliography"), merges near-duplicate sections, and retains substantive appendices, glossaries, and checklists.

Persistent Local Library: Generated books are saved directly to your browser's localStorage (nexus_custom_books) and behave identically to built-in curricula—searchable, expandable, and ready for sequential study.

2. Two-Stage AI Topic Prompting (Context-Aware Teaching)

Clicking a topic inside a book doesn't just paste a raw title into the chat. Nexus executes a two-stage AI pipeline:

Stage 1 — Context Disambiguation & Prompt Crafting: Real tables of contents often contain noisy labels, figure captions, or terse fragments. Stage 1 sends the clicked topic, its parent Book & Module title, every sibling topic in that chapter, and your currently active Response Mode to a specialized prompt-writer directive. It infers the exact underlying concept and crafts a rigorous, first-person study question.

Stage 2 — Deep Tutoring Execution: That tailored question is submitted to the main thread alongside a dedicated Study Reading Protocol (or Official Exam LOS Protocol for exam-flagged books), ensuring you get definitions, causal mechanics, worked examples, and neighbouring-topic connections.

3. Seamless Sequential Study ("Next Topic" Flow)

Once you start studying a topic from any built-in or custom-generated book, a contextual Next topic → pill appears right inside the message composer.

Step through an entire textbook or syllabus module-by-module, topic-by-topic, without reopening the library modal.

4. 19 Pre-Loaded Finance, Quantitative & Governance Curricula

Out of the box, Nexus ships with complete, ready-to-study outlines for 19 foundational texts and exams:

Professional Exams: CFA Program 2025 Level I (all 93 Modules & official Learning Outcome Statements), FRM Part I (Foundations of Risk Management, Quantitative Analysis, Financial Markets & Products, Valuation & Risk Models), IICA Corporate Governance Handbook, and Wall Street Prep Investment Banking Interview Guide.

Valuation & Accounting: Valuation (McKinsey, 5th Ed.), Narrative and Numbers (Aswath Damodaran), Financial Shenanigans (Schilit & Perler, 3rd Ed.), Financial Intelligence for Entrepreneurs (Berman & Knight).

Portfolios, Markets & Quant: Investments (Bodie, Kane & Marcus, 11th Ed.), Asset Management: A Systematic Approach to Factor Investing (Andrew Ang), Advanced Portfolio Management (Giuseppe Paleologo), The Intelligent Investor (Benjamin Graham & Jason Zweig).

Macroeconomics & Indian Markets: Macroeconomics (Olivier Blanchard, 9th Ed.), Principles for Navigating Big Debt Crises (Ray Dalio), Indian Economy (Ramesh Singh, 10th Ed.), Indian Financial System (M.Y. Khan, 10th Ed.).

🎛️ 44+ Pedagogical Response Modes

Nexus features 44+ single-active Response Modes (Alt + R or / slash commands) that fundamentally re-architect how the AI structures, reasons through, and formats its replies.

When you combine a Book Topic with a Response Mode, both Stage 1 (the question generator) and Stage 2 (the tutor) adapt—letting you turn any chapter of any book into Kaplan Schweser-style notes, interactive flashcards, sticky note boards, worked calculations, or Socratic dialogues.

📖 Study, Practice & Note-Taking Modes

Mode

Slash Command

How It Transforms the Response

Schweser Notes

/schwesernotes

Reconstructs the entire reading in the exact house style of Kaplan Schweser CFA Notes: STUDY SESSION, READING, EXAM FOCUS, numbered MODULE R.m blocks keyed to LOS, dense declarative prose, PROFESSOR'S NOTE callouts, MODULE QUIZ, KEY CONCEPTS, ANSWER KEY, and FORMULAS.

Sticky Note Mode

/sticky

Renders the topic into a visual corkboard of color-coded, tilted sticky notes (concept, formula, example, mistake, summary) connected by sequence arrows, with one-click saving to your global Notes panel.

Flashcards

/flashcards

Generates interactive click-to-reveal accordion flashcards (Front, Back, #tags) ordered from foundational definitions to advanced distinctions and common traps.

Cornell Notes

/cornellnotes

Formats the reply into a 3-part Cornell study sheet: Questions / Cues, Main Notes (mechanisms, formulas, distinctions), and a 2–4 sentence Summary.

One-Page Cheat Sheet

/onepagecheatsheet

Compresses the topic into a high-yield single-page reference with core rules, inline symbol definitions, compact tables, and rapid self-check prompts.

Zettelkasten / Obsidian

/zettelkasten

Breaks the topic into atomic (<100-word) self-contained notes with [[bidirectional wiki-links]], #tags, and a closing Map of Content (MoC).

Handwritten / Brain Dump

/braindump

Informal, shorthand study notes using sentence fragments, causal arrows (->), and quick groupings instead of formal textbook prose.

Practice Problems

/practiceproblems

Generates 3–5 self-contained, progressively harder practice problems without revealing solutions or hints so you can test yourself first.

Worked Solutions

/workedsolutions

Walks through problems step-by-step from given inputs and formula selection to intermediate arithmetic, final units, and the #1 common error to avoid.

Answer Check

/answercheck

Evaluates your submitted work (CORRECT, PARTIALLY CORRECT, or INCORRECT), pinpoints the first meaningful error, and provides a targeted repair.

Formula Deep Dive

/formuladeepdive

Lists every formula for the topic, defines every variable, derives it from first principles, and walks through a realistic numerical example.

Formula Sheet

/formulasheet

Compiles all relevant equations, variable definitions, units, and usage triggers into a clean reference sheet.

Concept Map

/conceptmap

Maps the 5–10 core concepts using visual Mermaid.js flowcharts, inline SVG diagrams, or structured outlines, highlighting the root dependency and most confused pair.

ASCII Diagram Mode

/asciidiagram

Renders a strict top-down ASCII box-and-branch tree diagram of the concept followed by a 2–3 sentence structural explanation.

Timeline / Sequence

/timelinesequence

Organizes events, causal chains, or process stages into a chronological/dependency table (What Happened, Why It Mattered, What Followed).

🧠 Guided Recall, Depth & Reasoning Modes

Mode

Slash Command

How It Transforms the Response

Concise Audio

/audioconcise

3–6 spoken-style sentences with zero markdown clutter or raw symbols—tuned for Nexus's Read Aloud (TTS) engine.

Standard

/standard

Direct, proportional, zero-ceremony answers that lead with the conclusion in plain language.

Mastery

/mastery

Exhaustive 6-stage breakdown: Core Idea → Causal Mechanism → Worked Example → Common Misconceptions → Connections → Check Understanding Question.

First Principles Mode

/firstprinciples

Strips the topic down to 3–6 irreducible axioms, separates assumptions from derivations, and rebuilds the concept layer-by-layer.

The "5 Whys" Interrogator

/fivewhys

Drills into the core premise through a visible causal chain (Why 1 -> Answer -> Why 2...) until reaching the structural root cause.

The 80/20 Pareto Guide

/pareto

Teaches only the highest-leverage 20% of concepts that unlock 80% of practical competence, explicitly listing what was skipped and why.

Guided Reading

/guidedreading

Breaks material into 3–5 stages, teaching one section at a time and pausing with a comprehension check before advancing.

Socratic Guide / Reading

/socratic · /socraticreading

Guides you to the insight by asking one targeted question per turn that adapts to your answers and exposes misconceptions.

Adaptive Difficulty

/adaptivedifficulty

Starts at medium difficulty and dynamically scales scaffolding up or down based on your demonstrated mastery.

Dependency Map

/dependencymap

Maps the 3–5 prerequisite concepts you must master before tackling the current topic, ordered in a clear learning sequence.

Glossary

/glossary

Generates an alphabetized, grouped glossary of the 8–15 most important terms, symbols, and definitions for the topic.

Case Study & Story Mode

/casestudy · /storymode

Embeds abstract concepts into realistic decision-making scenarios or character-driven narratives.

Deep Research & History

/deepresearch · /history

Either synthesizes sub-questions with explicit confidence/staleness flags (/deepresearch) or traces historical origins, turning points, and debates (/history).

ELI5, BLUF, Terse, Show Work

/eli5 · /bluf · /terse · /showwork

Calibrate tone and precision: child-friendly analogies (/eli5), executive bottom-line-up-front (/bluf), minimum word count (/terse), or full derivations for every number (/showwork).

🎓 Specialized Exam Prep Modes (CFA & IICA)

Mode

Slash Command

How It Transforms the Response

CFA Mode

/cfamode

Maps the topic to its CFA Topic Area, official LOS, and exam weight; teaches using strict CFA Institute terminology, worked examples, and trap analysis.

CFA Formula Navigator

/cfaformulanavigator

Lists every relevant CFA formula, required inputs, lookalike formulas, and step-by-step TI BA II Plus calculator keystrokes.

CFA Comparison Mode

/cfacomparison

Side-by-side comparison table of commonly confused CFA pairs, showing the exact exam keyword that signals which one applies.

CFA Calculation Walkthrough

/cfacalcwalkthrough

Solves a CFA-style quantitative problem step-by-step with bracketed BA II Plus keystrokes and common sign/compounding traps.

CFA Concept Distiller

/cfaconceptdistiller

Compresses any CFA topic into <250 words: Core Idea, The One Formula, The One Distinction, The One Trap, The One Application.

CFA Mock Vignette

/cfamockvignette

Generates a realistic 100–200 word practice vignette followed by 3–4 multiple-choice questions and a full distractor rationale.

CFA Distractor Analyzer

/cfadistractoranalyzer

Breaks down a multiple-choice question by explaining the exact wrong formula or misreading that produces each wrong option.

CFA Topic Connector

/cfatopicconnector

Traces how a concept links across all 10 CFA topic areas (e.g., how Fixed Income duration connects to Portfolio Management immunization).

IICA Modes (6 Modes)

/iicamode · /iicalegalnavigator · /iicacasestudy · /iicacompliancechecker · /iicaboardgovernance · /iicacsrethics

Tailored for Indian corporate law & governance: exact citations to the Companies Act 2013 (Sections 135, 149–177, Schedule IV) and SEBI LODR Regulations, board scenarios, compliance checks, and case studies.

🚀 Quick Start

Open the App: Visit nexus-chat-473.pages.dev (or install it as a standalone desktop/mobile app via your browser's Install App / Add to Home Screen prompt).

Configure an API Key (Optional if server keys are configured):

Open Menu (Alt + M) → Settings (S).

Select a provider (NVIDIA NIM, OpenRouter, or Groq) and paste your free API key—or paste a full Python/LangChain snippet and let Nexus auto-extract the key and model.

Add or Pick a Book & Choose a Mode:

Press Alt + B to open the Book Library—pick from the 19 built-in books or type any book title into "Add a book" and click Generate TOC.

Press Alt + R (or type / in the composer) to activate a mode like Schweser Notes (/schwesernotes), Sticky Note Mode (/sticky), or Mastery (/mastery), then click any topic to start studying.

✨ Core Interactive Features

Interactive Formula Explorer (fxCompile): Display-mode LaTeX equations (\[ ... \] or $$ ... $$) are automatically wrapped into interactive Formula Chips. Tapping any formula opens a full-screen Formula Explorer Sheet that compiles the LaTeX into a live JavaScript function with interactive sliders for every variable ($PV, FV, r, g, N, WACC$, etc.) and real-time substituted math rendering.

Multi-Provider AI Routing & Failover: Seamlessly switch between NVIDIA NIM, OpenRouter, and Groq (LPU). Store multiple API keys per provider in localStorage; if an active key hits a rate limit (429) or is rejected (401/403), Nexus automatically rotates to backup keys and fails over across providers.

Non-Destructive Conversation Branching: Every message is stored in a parent-linked tree ({ id, parentId, role, content }). Edit any user message, regenerate any reply, or branch from any point in the thread using the inline ‹ 1 / N › branch switcher.

Side Chat (Alt + S) & Global Notes (Alt + N): Open a stateless Side Chat beside your main thread to ask quick clarifying questions without polluting your main context or inheriting active modes, or pin cards to your persistent Global Notes scratchpad.

Dual-Engine Read Aloud (TTS): Listen to full responses—or highlight text and click Read from selection—using natural TTS.ai neural voices (via /api/tts) or your device's offline Web Speech Synthesis API.

⌨️ Keyboard Shortcuts & Slash Commands

Shortcut / Command

Action

Alt (tap)

Show floating keyboard shortcut cheat sheet

Alt + M

Open main menu (then press N for New Chat, B for Book Library, or S for Settings)

Alt + B

Open Book Library & Custom Book Generator modal

Alt + R

Open Response Modes modal

Alt + S / Alt + N

Toggle Side Chat panel / Toggle Global Notes panel

/newchat · /topics · /settings

Quick composer slash actions

/<mode>

Fuzzy-search and toggle any of the 44+ response modes (e.g., /schweser, /sticky, /cfa, /eli5)

🏗️ Backend API Contract & Deployment

Nexus is deployed on Cloudflare Pages at nexus-chat-473.pages.dev. While the entire frontend lives in a single zero-build index.html file, it communicates with three lightweight serverless endpoints:

├── index.html          # Complete single-file application (UI, CSS, 19 Books, 44+ Modes, Logic)
├── manifest.json       # PWA manifest
├── sw.js               # Service worker for offline app-shell caching
├── icons/              # PWA icons (favicon-16.png, favicon-32.png, apple-touch-icon.png)
└── functions/api/      # Serverless API routes (Cloudflare Pages Functions)
    ├── chat.js         # POST /api/chat   (relays OpenAI-compatible chat completions)
    ├── models.js       # GET  /api/models (fetches latest free model slugs)
    └── tts.js          # POST /api/tts    (proxies neural text-to-speech audio)


🔒 Privacy & Local Storage

All user state lives strictly in your browser's localStorage under the nexus_* namespace (nexus_custom_books, nexus_conversations, nexus_notes, nexus_key_list, nexus_last_modes). Nothing is sent to third-party servers except the AI provider you select via /api/chat. You can inspect storage counts, clear conversations while keeping your custom books and keys, or factory-reset the app anytime via Menu → Settings → Data.
