# SL&I 3 Comprehensive Practice Exam Bank (360 Questions Total)

[![Live Exam Set 1](https://img.shields.io/badge/Exam%20Set%201-120%20Questions-38bdf8?style=for-the-badge&logo=googlechrome&logoColor=white)](https://mayolol16.github.io/SLI_practice_exam/)
[![Live Exam Set 2](https://img.shields.io/badge/Exam%20Set%202-120%20Questions-a855f7?style=for-the-badge&logo=googlechrome&logoColor=white)](https://mayolol16.github.io/SLI_practice_exam/exam2.html)
[![Live Exam Set 3](https://img.shields.io/badge/Exam%20Set%203-60%20Questions%20(Official%20Format)-10b981?style=for-the-badge&logo=googlechrome&logoColor=white)](https://mayolol16.github.io/SLI_practice_exam/exam3.html)
[![Live Exam Set 4](https://img.shields.io/badge/Exam%20Set%204-60%20Questions%20(Practice%20Exam)-f59e0b?style=for-the-badge&logo=googlechrome&logoColor=white)](https://mayolol16.github.io/SLI_practice_exam/exam4.html)
[![Course](https://img.shields.io/badge/Course-UB%20IMC%20543LEC%203%20(SL%26I%203)-ef4444?style=for-the-badge)](#course-context)

Interactive, standalone examination web applications and comprehensive study suite for **University at Buffalo Jacobs School of Medicine and Biomedical Sciences — Scientific Literacy & Inquiry (SL&I) Semester 3 Final Examination**.

---

## 🌐 Launch Interactive Exams (Live on GitHub Pages)

Access all four exam blocks from any browser (desktop, tablet, mobile):

* 👉 **[Launch Practice Exam Set 1 (120 Questions)](https://mayolol16.github.io/SLI_practice_exam/)**
* 👉 **[Launch Practice Exam Set 2 (120 Questions)](https://mayolol16.github.io/SLI_practice_exam/exam2.html)**
* 👉 **[Launch Practice Exam Set 3 (60 Questions - Official Exam Format)](https://mayolol16.github.io/SLI_practice_exam/exam3.html)**
* 👉 **[Launch Practice Exam Set 4 (60 Questions - Semester 3 Practice Exam)](https://mayolol16.github.io/SLI_practice_exam/exam4.html)**

*All four sets are also saved locally in `~/Downloads/` as `SLI_120Q_Interactive_Exam.html` (Set 1), `SLI_120Q_Set2_Interactive_Exam.html` (Set 2), `SLI_60Q_Set3_Interactive_Exam.html` (Set 3), and `SLI_60Q_Set4_Interactive_Exam.html` (Set 4) for offline access with one click.*

---

## 📊 Curricular Distribution (360 Questions Total)

Each exam set is calibrated to exactly 1/3 per core domain (40 Qs each in Sets 1 & 2; 20 Qs each in Sets 3 & 4):

| Domain | Set 1 (120Q) | Set 2 (120Q) | Set 3 (60Q) | Set 4 (60Q) | Total Questions | Key Topics Tested |
| :--- | :---: | :---: | :---: | :---: | :---: | :--- |
| **Behavioral Economics** | **40** | **40** | **20** | **20** | **120 Qs** | Risk aversion, Moral hazard (ex-ante vs. ex-post), Cost-sharing (deductibles, copays, coinsurance, OOP max), Tamblyn 2001 study, Adverse selection & Death spiral, ACA 3 Rs, Managed care models (HMO, PPO, POS, EPO), Capitation vs. FFS risk transfer, Medicare Parts A–D, Medicaid, EMTALA, and DRGs. |
| **Survival Analysis** | **40** | **40** | **20** | **20** | **120 Qs** | Time-to-event rationale, 4 Types of censoring (Right, Left, Interval, Administrative), Informative vs. non-informative censoring, Survivor function $S(t)$, Cumulative failure $F(t)$, Hazard rate $h(t)$ & 5 curve shapes, Kaplan-Meier product-limit calculations, Log-Rank hypothesis testing, Hazard Ratios (HR) interpretation, Cox Proportional Hazards regression, and KEYNOTE-522 trial analysis. |
| **Applied Biostatistics** | **40** | **40** | **20** | **20** | **120 Qs** | Clinical vs. statistical significance, MCID, Type I ($\alpha$) and Type II ($\beta$) errors, 4 levers of statistical power ($N$, effect size, $\alpha$, variability), Parametric vs. Nonparametric test selection (t-test, ANOVA, Mann-Whitney, Wilcoxon, Kruskal-Wallis, Chi-square, Fisher's exact), 2x2 Risk calculations (ARR, RRR, NNT, NNH, RR vs. OR), Skewness, Mean/SD vs. Median/IQR, Z-scores & 68-95-99.7 rule, Multiple lab testing flag rate ($1 - 0.95^k$), and Confounding vs. Effect modification. |
| **Total Practice Bank** | **120** | **120** | **60** | **60** | **360 Qs** | **Full 6x replication of the official 60-question final exam** |

---

## ⚡ Web Application Features

- **Tutor Mode vs. Exam Mode**: Immediate feedback and rationale on answer click, or timed block examination with score reveal on submission.
- **Detailed Distractor Breakdowns**: Every question includes a High-Yield Learning Objective Pearl, a comprehensive explanation, and an option-by-option rationale explaining why each incorrect distractor fails.
- **USMLE-Style Test Tools**:
  - **Cross-out / Strikethrough Tool** (`S` key or right-click) to eliminate choices.
  - **Text Highlighter** (`H` key) to mark critical stem details with floating tooltip, toolbar toggle, and click-to-remove.
  - **Question Flagging** (`F` key) for bookmarking.
  - **Right-Side Question Navigator Grid** (`G` key) with filters for Unanswered, Correct, Incorrect, and Flagged.
  - **Question-Changing Controls on Right**: Previous / Next buttons situated on the bottom-right for rapid single-hand navigation.
  - **No Giveaway Tags**: Domain and topic tags hidden from the question header while testing; revealed only in the explanation card after answering.
  - **Performance Scorecard** (`R` key) showing domain-by-domain accuracy and a **Targeted AI Review Prompt Generator** to drill weak topics in Gemini/ChatGPT.
- **Local Storage Persistence**: Independently saves exam progress, answers, flags, and timer for Set 1, Set 2, Set 3, and Set 4.

---

## 📁 Repository Contents

- [`index.html`](index.html) & [`SLI_120Q_Interactive_Exam.html`](SLI_120Q_Interactive_Exam.html): Practice Exam Set 1 (120 Questions).
- [`exam2.html`](exam2.html) & [`SLI_120Q_Set2_Interactive_Exam.html`](SLI_120Q_Set2_Interactive_Exam.html): Practice Exam Set 2 (120 Questions).
- [`exam3.html`](exam3.html) & [`SLI_60Q_Set3_Interactive_Exam.html`](SLI_60Q_Set3_Interactive_Exam.html): Practice Exam Set 3 (60 Questions - Official Exam Format).
- [`exam4.html`](exam4.html) & [`SLI_60Q_Set4_Interactive_Exam.html`](SLI_60Q_Set4_Interactive_Exam.html): Practice Exam Set 4 (60 Questions - Semester 3 Practice Exam).
- [`SL&I Semester 3 Practice Examination.md`](SL&I%20Semester%203%20Practice%20Examination.md): Raw markdown text of the official 60-question practice examination.
- [`SLI_Master_Exam_Study_Guide.md`](SLI_Master_Exam_Study_Guide.md): 210 KB master study bible synthesizing all lectures, official quizzes, formulas, and traps.
- [`notebook_sources/`](notebook_sources/): 7 modular session guides optimized for upload into Google NotebookLM for audio/video lecture generation.
- Raw lecture slide decks (`.pptx`), official study guide PDFs, and decompressed Anki deck (`SLI Exam.apkg`).
