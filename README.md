<h1 align="center">Berkay Adanalı</h1>

<p align="center">
  <b>AI Engineer</b> &nbsp;·&nbsp; backend developer & linguist by training &nbsp;·&nbsp; building Turkish-first LLM tools, pipelines, and projects
</p>

<p align="center">
  <a href="https://github.com/BerkayRA"><img src="https://img.shields.io/badge/focus-Turkish%20LLMs-c0392b" alt="focus" /></a>
  <img src="https://img.shields.io/badge/CS-%C3%97%20Linguistics-1f6feb" alt="cs x linguistics" />
  <img src="https://img.shields.io/badge/based%20in-Ankara%2C%20T%C3%BCrkiye-2da44e" alt="ankara" />
</p>

---

My main interest is **language**: how it's used, how it's structured, how it's modeled, how we (and our machines) play with it, and how we (and our machines) can do more of it ourselves, for our collective good.

🔭 **Currently:** **AI Engineer @ Mega Bilgisayar** *(April 2026 – present)* — Most of my work involves a sovereign, on-premise **Turkish LLM** I built end to end: tokenizer → corpus → from-scratch model → demo. My private projects include building internal business intelligence and management tools, integrating and customizing open-source technologies into coherent, interoperable frameworks to replace external and proprietary product suites for our corporate clients, and research on building & using better LLM infrastructure. 

---

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

## Currently building — **[BerkayMakes Forge](https://berkaymakes.vercel.app)** (NestJS · Next.js · Prisma)

[BerkayMakes](https://instagram.com/berkaymakes) (est. 2023) is my solo tabletop gaming workshop where I design, build, and customize 3D-printed tabletop miniatures, props, dice, dice towers, decorative figurines, cosplay equipment, and various fantasy-inspired trinkets. I accept commissions via Instagram DMs and at events/conventions where I set up booths. However, as a passion project, I felt like the online presence of BerkayMakes demanded something with more character and flair than just an Instagram profile (which *does* have a lot of character — go check it out & reach out for some great minis!). 

I built the BerkayMakes Forge to track commissions, chat with customers on specifics on our own chat platform, archive and display previous builds, and provide regular customers and the wider tabletop community with a livestream of my workspace and several digital tabletop gaming tools. Check out the Tavern for a dice roller, initiative tracker, and name generator. 🎲

## 🛠️ Other things I'm building

- **[curated-ai-digest](https://github.com/BerkayRA/curated-ai-digest)** — a self-hosted, Claude-powered system that curates, writes, brands, and sends a weekly Turkish AI-news digest, with curation agents and an approval dashboard.

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
