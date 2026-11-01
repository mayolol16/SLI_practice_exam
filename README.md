# SL&I 3 Comprehensive Practice Exam Bank (240 Questions Total)

[![Live Exam Set 1](https://img.shields.io/badge/Exam%20Set%201-120%20Questions-38bdf8?style=for-the-badge&logo=googlechrome&logoColor=white)](https://mayolol16.github.io/SLI_practice_exam/)
[![Live Exam Set 2](https://img.shields.io/badge/Exam%20Set%202-120%20Questions-a855f7?style=for-the-badge&logo=googlechrome&logoColor=white)](https://mayolol16.github.io/SLI_practice_exam/exam2.html)
[![Course](https://img.shields.io/badge/Course-UB%20IMC%20543LEC%203%20(SL%26I%203)-10b981?style=for-the-badge)](#course-context)

Interactive, standalone examination web application and comprehensive study suite for **University at Buffalo Jacobs School of Medicine and Biomedical Sciences — Scientific Literacy & Inquiry (SL&I) Semester 3 Final Examination**.

---

## 🌐 Launch Interactive Exams (Live on GitHub Pages)

Access both exam blocks from any browser (desktop, tablet, mobile):

* 👉 **[Launch Practice Exam Set 1 (120 Questions)](https://mayolol16.github.io/SLI_practice_exam/)**
* 👉 **[Launch Practice Exam Set 2 (120 Questions)](https://mayolol16.github.io/SLI_practice_exam/exam2.html)**

*Both sets are also saved locally in `~/Downloads/` as `SLI_120Q_Interactive_Exam.html` (Set 1) and `SLI_120Q_Set2_Interactive_Exam.html` (Set 2) for offline access with one click.*

---

## 📊 Curricular Distribution (240 Questions Total)

Each 120-question set is calibrated to exactly 1/3 (40 questions) per core domain:

| Domain | Set 1 Count | Set 2 Count | Total | Key Topics Tested |
| :--- | :---: | :---: | :---: | :--- |
| **Behavioral Economics** | **40** | **40** | **80 Qs** | Risk aversion, Moral hazard (ex-ante vs. ex-post), Cost-sharing (deductibles, copays, coinsurance, OOP max), Tamblyn 2001 study, Adverse selection & Death spiral, ACA 3 Rs, Managed care models (HMO, PPO, POS, EPO), Capitation vs. FFS risk transfer, Medicare Parts A–D, Medicaid, EMTALA, and DRGs. |
| **Survival Analysis** | **40** | **40** | **80 Qs** | Time-to-event rationale, 4 Types of censoring (Right, Left, Interval, Administrative), Informative vs. non-informative censoring, Survivor function $S(t)$, Cumulative failure $F(t)$, Hazard rate $h(t)$ & 5 curve shapes, Kaplan-Meier product-limit calculations, Log-Rank hypothesis testing, Hazard Ratios (HR) interpretation, Cox Proportional Hazards regression, and KEYNOTE-522 trial analysis. |
| **Applied Biostatistics** | **40** | **40** | **80 Qs** | Clinical vs. statistical significance, MCID, Type I ($\alpha$) and Type II ($\beta$) errors, 4 levers of statistical power ($N$, effect size, $\alpha$, variability), Parametric vs. Nonparametric test selection (t-test, ANOVA, Mann-Whitney, Wilcoxon, Kruskal-Wallis, Chi-square, Fisher's exact), 2x2 Risk calculations (ARR, RRR, NNT, NNH, RR vs. OR), Skewness, Mean/SD vs. Median/IQR, Z-scores & 68-95-99.7 rule, Multiple lab testing flag rate ($1 - 0.95^k$), and Confounding vs. Effect modification. |
| **Total Practice Bank** | **120** | **120** | **240 Qs** | **Full 4x replication of the official 60-question final exam** |

---

## ⚡ Web Application Features

- **Tutor Mode vs. Exam Mode**: Immediate feedback and rationale on answer click, or timed block examination with score reveal on submission.
- **Detailed Distractor Breakdowns**: Every question includes a High-Yield Learning Objective Pearl, a comprehensive explanation, and an option-by-option rationale explaining why each incorrect distractor fails.
- **USMLE-Style Test Tools**:
  - **Cross-out / Strikethrough Tool** (`S` key or right-click) to eliminate choices.
  - **Text Highlighter** (`H` key) to mark critical stem details.
  - **Question Flagging** (`F` key) for bookmarking.
  - **Question Navigator Grid** (`G` key) with filters for Unanswered, Correct, Incorrect, and Flagged.
  - **Performance Scorecard** (`R` key) showing domain-by-domain accuracy and a **Targeted AI Review Prompt Generator** to drill weak topics in Gemini/ChatGPT.
- **Local Storage Persistence**: Independently saves exam progress, answers, flags, and timer for Set 1 and Set 2.

---

## 📁 Repository Contents

- [`index.html`](index.html) & [`SLI_120Q_Interactive_Exam.html`](SLI_120Q_Interactive_Exam.html): Practice Exam Set 1 (120 Questions).
- [`exam2.html`](exam2.html) & [`SLI_120Q_Set2_Interactive_Exam.html`](SLI_120Q_Set2_Interactive_Exam.html): Practice Exam Set 2 (120 Questions).
- [`SLI_Master_Exam_Study_Guide.md`](SLI_Master_Exam_Study_Guide.md): 210 KB master study bible synthesizing all lectures, official quizzes, formulas, and traps.
- [`notebook_sources/`](notebook_sources/): 7 modular session guides optimized for upload into Google NotebookLM for audio/video lecture generation.
- Raw lecture slide decks (`.pptx`), official study guide PDFs, and decompressed Anki deck (`SLI Exam.apkg`).
