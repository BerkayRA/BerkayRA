<h1 align="center">Berkay Adanalı</h1>

<p align="center">
  <b>AI Engineer</b> &nbsp;·&nbsp; backend developer & linguist by training &nbsp;·&nbsp; building sovereign AI: Turkish-first LLM tools, pipelines, and projects
</p>

<p align="center">
  <a href="https://github.com/BerkayRA"><img src="https://img.shields.io/badge/focus-Sovereign%20AI%20%C2%B7%20Turkish%20LLMs-c0392b" alt="focus" /></a>
  <img src="https://img.shields.io/badge/CS-%C3%97%20Linguistics-1f6feb" alt="cs x linguistics" />
  <img src="https://img.shields.io/badge/based%20in-Ankara%2C%20T%C3%BCrkiye-2da44e" alt="ankara" />
</p>

---

My main interest is **language**: how it's used, how it's structured, how it's modeled, how we (and our machines) play with it, and how we (and our machines) can do more of it ourselves, for our collective good.

🔭 **Currently:** **AI Engineer @ Mega Bilgisayar** *(April 2026 – present)* — Most of my work is **sovereign AI**: an on-premise **Turkish LLM** I built end to end: tokenizer → corpus → from-scratch model → demo. My private projects include building internal business intelligence and management tools, integrating and customizing open-source technologies into coherent, interoperable frameworks to replace external and proprietary product suites for our corporate clients, and research on building & using better LLM infrastructure. 

---

## Currently building — **Egemen** 🦅 (sovereign AI for Turkish, in iterations)

*Egemen* means "sovereign" in Turkish, and that's the whole brief: sovereign AI, meaning a Turkish language model whose tokenizer, corpus, weights, and serving all stay on-premise, built one iteration at a time. Each generation is meant to be small enough to train on hardware we actually have and honest enough to show its working.

**Egemen-124M — done, and [live in your browser](https://huggingface.co/spaces/BerkayRA/egemen-turkish-124m-demo).** A ~110M-parameter decoder trained from scratch for 300k steps on a single 8 GB GPU, with a 32k SentencePiece tokenizer. The demo runs entirely client-side (transformers.js + Pyodide, zero server compute) and has three tabs:
- **Model:** free-form Turkish generation.
- **Zaman Makinesi (Time Machine):** the same prompts sampled across training, so you can watch the model go from noise to fluent-but-wrong ("the capital of Türkiye is İstanbul…") to, eventually, Ankara.
- **Dilbilimsel Tokenizer:** the morphological analyzer from [turkish-tokenizer](https://github.com/BerkayRA/turkish-tokenizer), running the exact Python code in the browser.

Weights: [`BerkayRA/egemen-turkish-124m`](https://huggingface.co/BerkayRA/egemen-turkish-124m).

**Egemen-1.2B — training now.** A 10× scale-up, trained from scratch in FP8 on a single DGX Spark (Grace Blackwell) toward a ~30B-token budget, with a new 48k morphology-aware tokenizer. It's roughly a third of the way through. The Time Machine came along: 31 fixed prompts are sampled every 250 steps, so this run's growing-up is on the record too.

**Behind both: the corpus.** A curation pipeline with an HPLT v3 backbone across fifteen Turkish sources. It uses an LLM-as-teacher quality classifier, so we keep encyclopedic and long-form text and cut forum chatter. KVKK-compliant: the training data never leaves the building.

**Next:** continued pretraining of a strong open-weight base model on the same curated Turkish corpus (the fastest path to a genuinely useful assistant), followed by instruction and tool-use tuning. A larger from-scratch generation will follow as compute allows.

## Currently building — Turkish LLM suite

An exploratory project that spans multiple repos to build a Turkish NLP tool and eventually the **whole stack** for a Turkish LLM. I started with the tokenizer (first as a linguistic tool, then a tokenizer in the LLM sense) with the initial thesis that Turkish, as an agglutinative language, could be fragmented better with a bespoke tokenizer instead of generic English-tuned tokenizers. By building the tokenizer and corpus *first*, and I sought not to waste compute (which has been rather challenging to access in my current work premises) training on inflated per-token costs.

```
turkish-tokenizer  →  turkish-llm  →  turkish-corpus  →  turkish-llm-demo
 (morphology)         (tokenizer +     (HPLT pipeline:    (live training,
                       arch lab)        clean→dedup→blend)  chatbot, dashboard)
```

| Repo | What it is |
|------|------------|
| **[turkish-tokenizer](https://github.com/BerkayRA/turkish-tokenizer)** | Dependency-free Turkish morphological analyzer (root + ordered morphemes, UD-aligned) + a fertility metric. Pure Python stdlib. |
| **[turkish-llm](https://github.com/BerkayRA/turkish-llm)** | Tokenizer training/eval lab (SentencePiece Unigram, morpheme-aware BPE) + the from-scratch model architecture spec. |
| **[turkish-corpus](https://github.com/BerkayRA/turkish-corpus)** | HPLT-anchored corpus pipeline — Turkish-aware cleaning (ı/İ casing, KVKK PII scrubbing), MinHash dedup, token-budgeted blend. |
| **[turkish-llm-demo](https://github.com/BerkayRA/turkish-llm-demo)** | End-to-end on-prem demo: a ~110M transformer trained **live** on a self-built ~39B-token corpus, a QLoRA Turkish chatbot, a tokenizer-efficiency visualizer, and an executive dashboard — all on a single 8 GB GPU. |

<sub>You can find them together under the <a href="https://github.com/search?q=topic%3Aturkish-llm-suite+user%3ABerkayRA&type=repositories"><code>turkish-llm-suite</code></a> topic.</sub>

## Currently building — **[BerkayMakes Forge](https://berkaymakes.vercel.app)** & **Guild Hall** (NestJS · Next.js · Prisma · three.js · Socket.IO)

[BerkayMakes](https://instagram.com/berkaymakes) (est. 2023) is my solo tabletop gaming workshop where I design, build, and customize 3D-printed tabletop miniatures, props, dice, dice towers, decorative figurines, cosplay equipment, and various fantasy-inspired trinkets. I accept commissions via Instagram DMs and at events/conventions where I set up booths. However, as a passion project, I felt like the online presence of BerkayMakes demanded something with more character and flair than just an Instagram profile (which *does* have a lot of character — go check it out & reach out for some great minis!). 

I built the Forge to track commissions, chat with customers on specifics on our own chat platform, archive and display previous builds, and provide regular customers and the wider tabletop community with a livestream of my workspace.

What started as a few tabletop tools (a dice roller, an initiative tracker) has grown into **Guild Hall**, a proper multiplayer 3D tabletop simulator for D&D 5e. The GM opens a table and players join by invite link. Combat is rules-aware: initiative, conditions, concentration, reach, opportunity attacks, and saving throws, plus spellcasting with area effects and summons, an SRD monster bestiary, and animated 3D dice. The table has its own chat with roll commands, secret GM rolls, whispers, and GM moderation. 🎲

## Currently building — **Quotient** (NestJS · React · PostgreSQL + pgvector)

Quotient is a quote-to-cash platform that handles quotes, approvals, documents, and an opportunity pipeline, with a first-class BI layer and an agentic AI layer on top. It began as a greenfield rebuild of a bespoke internal quoting system: the kind of tool that fits one company perfectly and, for that exact reason, can't be sold to a second one. Turning it into a product means every hardcoded thing (user roles, the company's quote-number prefix, stages of a quote/opportunity, and the ERP) has to become configuration, which means tenant isolation has to be enforced by the database rather than remembered by the developer. Two commitments carry most of the weight during the rebuild. I chose to have English as the source language and Turkish as a locale rather than the other way round, so the project can be localized instead of translated. And the LLM never touches row-level business data or writes SQL: it emits a validated intermediate representation that a semantic layer compiles into parameterized queries, and rows reach the user through a deterministic renderer. The model proposes, a validator checks, a human approves, and the approval is the write operation. Same sovereignty instinct as the Turkish LLM work — the provider is pluggable and the default is on-prem.

## Currently building — **Ketum** 🤐 (Python · private for now)

*Ketum* is Turkish for "tight-lipped": someone you can trust with a secret. It's an anonymization and pseudonymization engine for Turkish-first enterprise text and the privacy layer of the sovereign AI stack, designed from the ground up to support **KVKK** (Türkiye's data-protection law) and **GDPR** compliance, and it has two jobs. It cleans LLM training corpora before they go anywhere near a model. And it sits between an on-prem assistant and a frontier model with web search, stripping the sensitive parts out of a prompt on the way out and putting them back into the answer on the way in.

The hard part is *consistency*, and Turkish makes it harder. The same person has to get the same alias across a whole document (or a whole corpus), or the text stops making sense. And because Turkish stacks suffixes onto names, swapping *Ayşe'ye* for an alias means re-harmonizing the suffix too, so the sentence stays grammatical. Underneath: format-preserving encryption (FF1) for IDs and numbers that still have to look valid, prefix-preserving IP anonymization (Crypto-PAn), defenses against Unicode look-alike tricks, and an NER layer (GLiNER + BERTurk). When a mention is ambiguous, it stays unlinked rather than guessed, and if sanitizing fails, nothing goes out: egress fails closed. It's built in small work packages, each of which has to survive an adversarial red-team review before it merges.

**Built around the law, not bolted on.** Every design decision maps back to KVKK and GDPR:
- **Data minimization (KVKK art. 4).** Only what a task needs leaves the system; everything else is aliased, tagged, or redacted.
- **Special-category data (KVKK art. 6).** Health, religion, union membership, biometrics, and criminal records are blocked or redacted by default.
- **Cross-border transfers (KVKK art. 9, as amended in 2024).** Sending a prompt to a foreign-hosted model is a transfer abroad, so every request leaves an audit trail that serves as the evidence for it.
- **Pseudonymization vs. anonymization.** Ketum is honest about the difference. As long as a re-identification key exists, aliased data is *still personal data* under both KVKK and GDPR; a corpus only moves toward anonymized once its keys are destroyed, and Ketum records that destruction as evidence.

It supports compliance rather than replacing a DPO or legal counsel, who still sign off on each deployment. And it follows its own rules: real data never leaves the building, so development runs on synthetic data only.

## Currently building — **Muallim** 🧑‍🏫 (Python · Manim · early research stage)

*Muallim* is an old Turkish word for "teacher." Snap a photo of a math question, get a short narrated video that solves it — either on a Khan Academy-style blackboard or as a 3Blue1Brown-style animation — in Turkish. I'm starting with LGS (the national high-school entrance exam).

Two findings shaped the design. First, open models are bad at writing free-form Manim code, so the LLM never writes animation code: it emits a constrained scene spec, and my own Manim templates render it. Second, there's no Turkish math verbalizer — nothing that reads a formula aloud the way a Turkish teacher would (the existing screen-reader tools have no Turkish). So I'm building one, with classroom and formal reading styles and suffixes that re-harmonize when they follow a formula, checked against a golden set that a tutor reviews. Around it: single-stroke handwriting with a moving pen tip for the blackboard theme, an open Turkish text-to-speech voice picked by bake-off, and automatic QA that transcribes the narration back to catch mispronunciations. A solution that can't be verified never becomes a video; it's shown as flagged text instead.

The render engine and narration work end to end; the verbalizer is in progress, with solving, verification, and photo input next. The goal is to run it all on self-hosted open models.

## 🛠️ Other things I'm building

- **[curated-ai-digest](https://github.com/BerkayRA/curated-ai-digest)** — a self-hosted, Claude-powered system that curates, writes, brands, and sends a weekly Turkish AI-news digest, with curation agents and an approval dashboard.
- **etch-a-chat** *(private, co-built with a collaborator)* — a text-free, privacy-focused instant messenger where all messages are in the form of doodles (hence the name evoking Etch A Sketch) with a WIP live, collaborative whiteboard room option (think old Google Jamboard).

## 🧠 Background

- 🎓 **B.A. Computer Science & Linguistics** (double major), Pomona College '20 — coursework across **Phonetics, Corpus Linguistics, Advanced Syntax, Machine Learning, and Field Methods**.
- 🧩 **Backend Developer & Technical Product Manager** @ Naylalabs — REST APIs on Node.js/NestJS across three international products; coordinated backend/frontend/DevOps to ship.
- ✍️ **Co-Founder, Lead Translator & Editor** @ BAYT Language & Editorial Services — TR↔EN translation/editorial for NGOs and consultancies (Argüden Governance Academy, the European Climate Foundation), and the official English subtitles for the documentary *Becoming Duru* (2020).

## 🧰 Tech Stack

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?logo=nodedotjs&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?logo=nestjs&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?logo=nextdotjs&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)

- **NLP / ML:** PyTorch · SentencePiece · datatrove · QLoRA / PEFT · Ollama · llama.cpp · morphological & corpus analysis (Praat, R)
- **Backend:** Node.js · NestJS · Express · Prisma · PostgreSQL · MongoDB · Redis · Docker
- **Languages:** Turkish & English (bilingual) · French (intermediate) · German (beginner) · Russian (beginner)

## 📫 Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-berkay--adanali-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/berkay-adanali)
[![Email](https://img.shields.io/badge/Email-b.adanali%40gmail.com-D14836?logo=gmail&logoColor=white)](mailto:b.adanali@gmail.com)
