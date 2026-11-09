<div align="center">

<img src="docs/banner.png" alt="banner" width="720"/>

# JuChang Hardware Exam Bank

** 1552+ Real Written-Test Questions · Verified Answers · AI-Ready · Bilingual **

*From real exam questions to a structured knowledge system — your one-stop open-source prep kit for hardware engineering hiring tests*

[![License](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-orange)](./LICENSE)
[![Questions](https://img.shields.io/badge/Questions-1552%2B-red)](#-bank-overview)
[![Sets](https://img.shields.io/badge/Sets-27-blue)](#-bank-overview)
[![AI Ready](https://img.shields.io/badge/AI--Ready-Markdown%20Structured-9cf)](#-quick-start)
[![Languages](https://img.shields.io/badge/Lang-%E4%B8%AD%E6%96%87%20%7C%20English-success)](./README.md)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)](#-contributing)

[简体中文](./README.md) | **English**

</div>

---

> 📢 **What is this?** An open-source collection of real written-test questions for the **Hardware General / Board Development** role at a leading Chinese telecom equipment vendor (community nickname: "**JuChang / 菊厂**"). Questions come from candidate recollections across past years, with answers verified question-by-question, explanations written/rewritten, and knowledge-point tags added — optimized for **AI-powered retrieval** and **systematic review**.
>
> ⚠️ This repository is **not affiliated with** any company. For learning purposes only — commercial use is prohibited. If any content infringes your rights, please open an Issue and we will remove it promptly.

## 📖 Table of Contents

- [Why this repo](#-why-this-repo)
- [Bank overview](#-bank-overview)
- [Quick start](#-quick-start)
- [Knowledge system](#-knowledge-system)
- [Quality assurance](#-quality-assurance)
- [Repository layout](#-repository-layout)
- [Contributing](#-contributing)
- [Disclaimer](#-disclaimer)

## 💡 Why This Repo

Pain points of preparing for hardware hiring tests:

1. **Real questions are scattered** — often with no answers, or with wrong answers everywhere;
2. The real exam **draws questions randomly** from a large pool — coverage determines hit rate, so scattered practice is inefficient;
3. Most existing material is **not AI-friendly** — messy formats make it hard for LLMs to locate and answer precisely.

This repository turns 27 real exam sets into **structured Markdown**: every question follows one uniform schema (question stem / options / answer / explanation / knowledge tags), so AI assistants can Grep the exact original question and answer it precisely. A companion knowledge system supports systematic review.

> In one sentence: **turn question drilling into data engineering.**

## 📊 Bank Overview

| Item | Value |
|---|---|
| Domain | Hardware General · Board Development (campus/intern exams, 2020–2024) |
| Sets | 27 |
| Questions | **1552** (single-choice / multi-select / true-false) |
| Per question | Answer + Explanation + Topic tags |

**Topic tag system** (11 categories, filterable):

`Components` `Analog Circuits` `Digital Circuits` `Signal Integrity` `PCB Design` `Power Design` `EMC` `Test & Measurement` `RF & Microwave` `Bus Protocols` `Others`

**Topic weight in real exams** (by frequency): SI > Power > Components > Digital & Buses > Test & Measurement > EMC > Analog > RF

## 🚀 Quick Start

### 1) Feed it to your AI (recommended)

Point any file-aware AI (Claude Code, Cursor, Copilot, etc.) at the `bank/` directory:

```text
# Retrieve original questions
Search bank/ for "twisted-ring counter", return all matching questions with answers & explanations

# Filter by tag
List all questions tagged "Signal Integrity" as a practice sheet

# Mock exam
Randomly pick 40 questions from bank/ (26 single + 10 multi + 4 T/F),
quiz me, grade me, and explain my mistakes
```

Uniform schema — zero friction for LLM parsing:

```markdown
### Q12. To convert a voltage signal into a proportional current signal,
which feedback topology should be introduced?
- **A.** Shunt-series (current-shunt) negative feedback
- **B.** Voltage-shunt negative feedback
- **C.** Voltage-series negative feedback
- **D.** Current-series negative feedback
- **Answer**: D
- **Explanation**: V→I conversion requires a stable output current ...
- **Tags**: Analog Circuits | Power Design
```

### 2) Drill it yourself

Open any set under `bank/` (`Set01.md` … `Set28.md`). Answers sit right below each question; use `knowledge/` to review the underlying concepts behind your mistakes.

## 📚 Knowledge System

[`knowledge/00-core-knowledge-overview.md`](./knowledge/00-核心知识点总览.md) is the recommended entry point:

- Core conclusions across 10 major topics + exam tactics + 6 categories of classic traps (absolute-wording traps, direction traps, fixed calculation patterns …)
- Per-set summaries: high-frequency topics and pitfalls of each set
- *Hardware Design Handbook Distilled*: condensed from a classic (159-page) hardware design handbook widely circulated in the industry, preserving concrete design spec values (5-1-5 rule, impedance formula, grounding / filtering / surge-protection parameters, TTL/CMOS interface essentials, etc.)

## ✅ Quality Assurance

- **Three-stage pipeline**: text extraction → structured rebuild → question-by-question professional verification (analog / digital / SI / PI / EMC / RF / test cross-review)
- **Errata log**: red/green marks in the circulating versions were **candidates' own answers, not official keys** (sampled error rate ≈ 25%) — all corrected per engineering principles, with correction notes preserved; known errors in the original bank (skin effect, RC time constant, hex comparison, etc.) fixed
- **Transparent uncertainty**: ~60 questions carry a `（存疑 / uncertain）` mark with justification notes — never silent guessing

## 📂 Repository Layout

```text
.
├── bank/                          # Question bank (27 sets, 1552 questions)
│   ├── 菊厂硬件通用、单板开发（第01套）.md   # Set 01
│   ├── ...
│   └── 菊厂校招实习硬件通用（高频、电磁兼容、测试）（第28套）.md
├── knowledge/                     # Knowledge system
│   ├── 00-核心知识点总览.md        # ← recommended entry
│   ├── 菊厂硬件设计手册精华.md     # classic design handbook, distilled (spec values)
│   └── 分套摘要-第XX-XX套.md      # per-set summaries
├── docs/                          # Logo & banner
├── .github/ISSUE_TEMPLATE/        # correction issue template
├── LICENSE                        # CC BY-NC-SA 4.0
├── README.md                      # 简体中文
└── README_EN.md                   # this file
```

> Note: question files are named in Chinese (set titles are quoted verbatim from the exam headers). Topic tags inside every question are in Chinese as well — AI retrieval works regardless; English tags may be added by PR.

## 🤝 Contributing

All contributions welcome:

- 🐛 **Corrections**: found a wrong answer/explanation? Open an Issue with set name + question number
- ✍️ **Explanations**: some older questions lack explanations — contributions appreciated
- 🌍 **Translations**: translate README / knowledge docs into more languages
- 📦 **New sets**: format new question sets following the existing schema

## 🔍 Keywords

`hardware interview` `hardware written test` `board development` `signal integrity` `SI PI EMC` `PCB interview questions` `power design` `analog digital circuits` `campus recruitment` `硬件笔试` `硬件面试` `校招真题` `菊厂` `single board development` `RF interview` `test measurement`

## ⭐ Support

If this repo helps you, please give it a **Star** ⭐ — that's the biggest motivation for continued updates!

## 📄 Disclaimer

1. All content consists of **candidate-recalled and community-compiled versions** circulated online, for learning and research only;
2. Not affiliated with, endorsed, or sponsored by any company; company references use community nicknames;
3. **Commercial use is strictly prohibited** (selling, paid groups, app bundling, etc.); redistribution must link back to this repository;
4. If any content infringes your rights, open an Issue or contact the maintainer — verified requests will be removed immediately.

<div align="center">

**Made with ❤️ by the community · For the community**

</div>
