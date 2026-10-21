# ⚡ Nexus

**Turn any textbook or exam syllabus into an interactive, AI-tutored curriculum.**

Nexus is a dark-first, single-file Progressive Web App. Type a book title, get a chapter-by-chapter study plan, then learn each topic through 44+ response modes: Schweser-style notes, flashcards, Socratic dialogue, worked calculations, and more.

**[Launch the app →](https://nexus-chat-473.pages.dev/)**

<!-- Add a screenshot or short GIF here: Book Library → topic click → Schweser Notes output -->

---

## Contents

- [Why Nexus](#why-nexus)
- [Quick start](#quick-start)
- [Book Library](#book-library)
- [Response modes](#response-modes)
- [Core features](#core-features)
- [Keyboard shortcuts & commands](#keyboard-shortcuts--commands)
- [Architecture & self-hosting](#architecture--self-hosting)
- [Privacy & storage](#privacy--storage)

---

## Why Nexus

A blank chat box gives you generic answers. Nexus grounds the AI in the structure of a real book or syllabus, then lets you choose *how* it teaches.

| Without Nexus | With Nexus |
|---|---|
| "Explain duration" | Click *Duration* inside your CFA Fixed Income module; the AI knows the chapter, sibling topics, and exam context |
| One response style | Switch between notes, flashcards, practice problems, or Socratic questioning in one keystroke |
| Static formulas | Tap any equation to open live sliders and see results update |
| One API key, one failure point | Multiple keys and providers with automatic failover |

---

## Quick start

1. **Open** [nexus-chat-473.pages.dev](https://nexus-chat-473.pages.dev/). To install it as an app, use your browser's *Install App* / *Add to Home Screen* option.
2. **Add an API key** (optional if the deployment has server-side keys): `Alt + M` → **Settings**. Choose NVIDIA NIM, OpenRouter, or Groq and paste a free key. You can also paste a full Python/LangChain snippet and Nexus will extract the key and model.
3. **Pick a book**: press `Alt + B` and choose a built-in book, or type any title into **Add a book** and click **Generate TOC**.
4. **Pick a mode**: press `Alt + R` (or type `/` in the composer), for example `/schwesernotes`, `/sticky`, or `/mastery`.
5. **Click any topic** to start studying.

---

## Book Library

Open with `Alt + B`.

### Add any book

Enter a title (with author or edition if useful) and click **Generate TOC**. Nexus asks the AI to rebuild the book as a two-level outline:

- **6–20 modules** (chapters or parts)
- **3–12 self-contained topics** per module
- Terminology and structure matched to the real book

Generated outlines are filtered for quality: filler such as "Introduction", "Summary", and "Bibliography" is removed, near-duplicates are merged, and substantive appendices, glossaries, and checklists are kept.

Custom books are saved in your browser (`nexus_custom_books`) and behave exactly like built-in ones: searchable, expandable, and ready for sequential study.

### Two-stage topic prompting

Clicking a topic does more than paste its title into the chat.

1. **Disambiguate and craft.** Real tables of contents are full of terse fragments and figure captions. Stage 1 sends the clicked topic, its book and module, all sibling topics, and your active mode to a prompt-writer. It infers the underlying concept and writes a precise, first-person study question.
2. **Teach.** Stage 2 submits that question to the main thread with a **Study Reading Protocol** (or an **Official Exam LOS Protocol** for exam-flagged books), so you get definitions, causal mechanics, worked examples, and links to neighbouring topics.

### Next-topic flow

After you start a topic, a **Next topic →** pill appears in the composer. Step through a whole book without reopening the library.

### Built-in curricula

| Category | Books & exams |
|---|---|
| **Professional exams** | CFA Program 2025 Level I (93 modules with official LOS) · FRM Part I · IICA Corporate Governance Handbook · Wall Street Prep Investment Banking Interview Guide |
| **Valuation & accounting** | *Valuation* (McKinsey, 5th ed.) · *Narrative and Numbers* (Damodaran) · *Financial Shenanigans* (Schilit & Perler, 3rd ed.) · *Financial Intelligence for Entrepreneurs* (Berman & Knight) |
| **Portfolios, markets & quant** | *Investments* (Bodie, Kane & Marcus, 11th ed.) · *Asset Management* (Ang) · *Advanced Portfolio Management* (Paleologo) · *The Intelligent Investor* (Graham & Zweig) |
| **Macro & Indian markets** | *Macroeconomics* (Blanchard, 9th ed.) · *Principles for Navigating Big Debt Crises* (Dalio) · *Indian Economy* (Ramesh Singh, 10th ed.) · *Indian Financial System* (M.Y. Khan, 10th ed.) |

---

## Response modes

Only one mode is active at a time. Open the picker with `Alt + R`, or type `/` and fuzzy-search. When you pair a book topic with a mode, **both** the question generator and the tutor adapt.

### Notes & reference

| Mode | Command | What you get |
|---|---|---|
| Schweser Notes | `/schwesernotes` | Kaplan Schweser house style: Study Session, Reading, Exam Focus, numbered Modules keyed to LOS, Professor's Notes, Module Quiz, Key Concepts, Answer Key, Formulas |
| Sticky Notes | `/sticky` | Corkboard of colour-coded, tilted notes (concept, formula, example, mistake, summary) joined by arrows; one-click save to Global Notes |
| Flashcards | `/flashcards` | Click-to-reveal cards (front, back, tags) ordered from definitions to traps |
| Cornell Notes | `/cornellnotes` | Cues, main notes, and a 2–4 sentence summary |
| One-Page Cheat Sheet | `/onepagecheatsheet` | Core rules, symbol definitions, compact tables, self-check prompts |
| Zettelkasten | `/zettelkasten` | Atomic notes under 100 words with `[[wiki-links]]`, tags, and a Map of Content |
| Brain Dump | `/braindump` | Informal shorthand with fragments and causal arrows |
| Glossary | `/glossary` | 8–15 key terms, grouped and alphabetized |

### Practice & calculation

| Mode | Command | What you get |
|---|---|---|
| Practice Problems | `/practiceproblems` | 3–5 progressively harder problems, no hints or solutions |
| Worked Solutions | `/workedsolutions` | Inputs → formula choice → arithmetic → units → the #1 common error |
| Answer Check | `/answercheck` | Verdict (correct / partially / incorrect), first meaningful error, targeted fix |
| Formula Deep Dive | `/formuladeepdive` | Every formula, every variable defined, derivation, numerical example |
| Formula Sheet | `/formulasheet` | Equations, variables, units, and when to use each |

### Visual maps

| Mode | Command | What you get |
|---|---|---|
| Concept Map | `/conceptmap` | 5–10 core concepts as Mermaid, SVG, or outline; root dependency and most-confused pair highlighted |
| ASCII Diagram | `/asciidiagram` | Top-down box-and-branch tree plus a short explanation |
| Timeline / Sequence | `/timelinesequence` | What happened, why it mattered, what followed |
| Dependency Map | `/dependencymap` | 3–5 prerequisites in learning order |

### Guided learning & reasoning

| Mode | Command | What you get |
|---|---|---|
| Standard | `/standard` | Direct, proportional answers that lead with the conclusion |
| Mastery | `/mastery` | Core idea → mechanism → worked example → misconceptions → connections → check question |
| First Principles | `/firstprinciples` | 3–6 axioms, assumptions separated from derivations, rebuilt layer by layer |
| 5 Whys | `/fivewhys` | Visible causal chain down to the structural root |
| 80/20 Pareto | `/pareto` | The vital 20%, with what was skipped and why |
| Guided Reading | `/guidedreading` | 3–5 stages with a comprehension check before advancing |
| Socratic | `/socratic` · `/socraticreading` | One adaptive question per turn that surfaces misconceptions |
| Adaptive Difficulty | `/adaptivedifficulty` | Starts at medium; scaffolding scales with your answers |
| Case Study / Story | `/casestudy` · `/storymode` | Concepts embedded in decision scenarios or narratives |
| Deep Research / History | `/deepresearch` · `/history` | Sub-question synthesis with confidence flags, or origins, turning points, and debates |
| Tone controls | `/eli5` · `/bluf` · `/terse` · `/showwork` | Plain analogies, bottom-line-first, minimum words, or full derivations |

### Exam prep: CFA

| Mode | Command | What you get |
|---|---|---|
| CFA Mode | `/cfamode` | Topic area, official LOS, exam weight, CFA Institute terminology, trap analysis |
| Formula Navigator | `/cfaformulanavigator` | Formulas, inputs, lookalikes, TI BA II Plus keystrokes |
| Comparison | `/cfacomparison` | Side-by-side table of commonly confused pairs and the exam keyword that distinguishes them |
| Calculation Walkthrough | `/cfacalcwalkthrough` | Step-by-step solution with keystrokes and sign/compounding traps |
| Concept Distiller | `/cfaconceptdistiller` | Under 250 words: core idea, one formula, one distinction, one trap, one application |
| Mock Vignette | `/cfamockvignette` | 100–200 word vignette, 3–4 MCQs, full distractor rationale |
| Distractor Analyzer | `/cfadistractoranalyzer` | The exact error behind each wrong option |
| Topic Connector | `/cfatopicconnector` | How a concept links across all 10 CFA topic areas |

### Exam prep: IICA (Indian corporate governance)

Six modes: `/iicamode` · `/iicalegalnavigator` · `/iicacasestudy` · `/iicacompliancechecker` · `/iicaboardgovernance` · `/iicacsrethics`. They cite the Companies Act 2013 (e.g. Section 135, Sections 149–177, Schedule IV) and SEBI LODR Regulations, and cover board scenarios, compliance checks, and case studies.

### Audio

| Mode | Command | What you get |
|---|---|---|
| Concise Audio | `/audioconcise` | 3–6 spoken-style sentences with no symbols or markdown, tuned for Read Aloud |

---

## Core features

- **Interactive Formula Explorer.** Display-mode LaTeX (`\[ … \]` or `$$ … $$`) becomes a tappable Formula Chip. It opens a full-screen sheet that compiles the equation into a live JavaScript function with a slider for every variable (PV, FV, r, g, N, WACC, …) and real-time rendered math.
- **Multi-provider routing and failover.** NVIDIA NIM, OpenRouter, and Groq. Store several keys per provider; on a 429 (rate limit) or 401/403 (rejected key), Nexus rotates to a backup key and then fails over across providers.
- **Non-destructive branching.** Messages form a parent-linked tree. Edit any message, regenerate any reply, and switch between versions with the inline `‹ 1 / N ›` control.
- **Side Chat** (`Alt + S`). A stateless panel for quick clarifications that doesn't touch your main context or inherit the active mode.
- **Global Notes** (`Alt + N`). A persistent scratchpad; pin cards or sticky notes from any response.
- **Read Aloud.** Listen to a full response, or select text and choose *Read from selection*. Uses TTS.ai neural voices via `/api/tts`, or your device's offline Web Speech API.
- **Installable and offline-capable.** A service worker caches the app shell.

---

## Keyboard shortcuts & commands

| Shortcut / command | Action |
|---|---|
| `Alt` (tap) | Show shortcut cheat sheet |
| `Alt + M` | Main menu (then `N` New Chat, `B` Book Library, `S` Settings) |
| `Alt + B` | Book Library & custom book generator |
| `Alt + R` | Response Modes |
| `Alt + S` | Toggle Side Chat |
| `Alt + N` | Toggle Global Notes |
| `/newchat` · `/topics` · `/settings` | Composer shortcuts |
| `/<mode>` | Fuzzy-search and toggle any mode (e.g. `/schweser`, `/sticky`, `/cfa`, `/eli5`) |

---

## Architecture & self-hosting

The whole frontend is one zero-build `index.html`, backed by three small Cloudflare Pages Functions.

```
├── index.html          # UI, CSS, built-in books, modes, and logic
├── manifest.json       # PWA manifest
├── sw.js               # Service worker (offline app-shell caching)
├── icons/              # PWA icons
└── functions/api/
    ├── chat.js         # POST /api/chat    OpenAI-compatible chat relay
    ├── models.js       # GET  /api/models  latest free model slugs
    └── tts.js          # POST /api/tts     neural text-to-speech proxy
```

**Run locally**

```bash
npx wrangler pages dev .
```

**Deploy**

1. Connect the repo to Cloudflare Pages (build command: none; output directory: repo root).
2. Optionally add server-side provider keys as Pages environment variables so users don't need their own. See `functions/api/chat.js` for the expected variable names.

---

## Privacy & storage

- Your data lives in your browser's `localStorage` under the `nexus_*` namespace: `nexus_custom_books`, `nexus_conversations`, `nexus_notes`, `nexus_key_list`, `nexus_last_modes`.
- Prompts are sent to the AI provider you select through `/api/chat`. If you use Read Aloud with neural voices, the text being read is sent to the TTS provider through `/api/tts`. Offline Web Speech keeps audio on-device.
- API keys are stored unencrypted in `localStorage`, so use keys you can revoke and avoid shared computers.
- Manage everything under **Menu → Settings → Data**: inspect storage, clear conversations (keeping books and keys), or factory-reset.
