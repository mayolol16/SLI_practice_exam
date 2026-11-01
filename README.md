# SL&I 3 Comprehensive Practice Exam & Study Suite

[![Live Exam Web App](https://img.shields.io/badge/Live%20Exam-Open%20Web%20App-38bdf8?style=for-the-badge&logo=googlechrome&logoColor=white)](https://mayolol16.github.io/SLI_practice_exam/)
[![Questions](https://img.shields.io/badge/Questions-120%20Total%20(40%20per%20domain)-10b981?style=for-the-badge)](#question-distribution)
[![Course](https://img.shields.io/badge/Course-UB%20IMC%20543LEC%203%20(SL%26I%203)-a855f7?style=for-the-badge)](#course-context)

Interactive, standalone examination web application and comprehensive study suite for **University at Buffalo Jacobs School of Medicine and Biomedical Sciences — Scientific Literacy & Inquiry (SL&I) Semester 3 Final Examination**.

---

## 🌐 Live Web Application

Access the exam from any desktop, tablet, or phone browser:
👉 **[Launch Interactive Exam (120 Questions)](https://mayolol16.github.io/SLI_practice_exam/)**

Alternatively, clone this repository and double-click `index.html` or `SLI_120Q_Interactive_Exam.html` to run completely offline.

---

## 📊 Question Distribution (120 Questions)

The practice exam doubles the official 60-question final exam blueprint with exactly **40 questions per domain**:

| Domain | Count | Key Curricular Topics Tested |
| :--- | :---: | :--- |
| **Behavioral Economics** | **40** (Q1–Q40) | Sessions 1 & 2: Risk aversion, Moral hazard (ex-ante vs. ex-post), Cost-sharing (deductibles, copays, coinsurance, OOP max), Tamblyn 2001 study, Adverse selection & Death spiral, ACA 3 Rs, Managed care models (HMO, PPO, POS, EPO), Capitation vs. FFS risk transfer, Medicare Parts A–D, Medicaid, EMTALA, and DRGs. |
| **Survival Analysis** | **40** (Q41–Q80) | Sessions 3 & 4: Time-to-event rationale, 4 Types of censoring (Right, Left, Interval, Administrative), Informative vs. non-informative censoring, Survivor function $S(t)$, Cumulative failure $F(t)$, Hazard rate $h(t)$ & 5 curve shapes, Kaplan-Meier product-limit calculations, Log-Rank hypothesis testing, Hazard Ratios (HR) interpretation, Cox Proportional Hazards regression, and KEYNOTE-522 trial analysis. |
| **Applied Biostatistics** | **40** (Q81–Q120) | Sessions 5 & 6: Clinical vs. statistical significance, MCID, Type I ($\alpha$) and Type II ($\beta$) errors, 4 levers of statistical power ($N$, effect size, $\alpha$, variability), Parametric vs. Nonparametric test selection (t-test, ANOVA, Mann-Whitney, Wilcoxon, Kruskal-Wallis, Chi-square, Fisher's exact), 2x2 Risk calculations (ARR, RRR, NNT, NNH, RR vs. OR), Skewness, Mean/SD vs. Median/IQR, Z-scores & 68-95-99.7 rule, Multiple lab testing flag rate ($1 - 0.95^k$), and Confounding vs. Effect modification. |

---

## ⚡ Web App Features

- **Tutor Mode vs. Exam Mode**: Immediate rationale upon clicking an option vs. timed block with score reveal on submission.
- **Detailed Distractor Breakdowns**: Every question includes a high-yield takeaway pearl, a comprehensive explanation, and an option-by-option rationale explaining why each incorrect distractor fails.
- **USMLE-Style Test Tools**:
  - **Cross-out / Strikethrough Tool** (`S` key or right-click) to eliminate choices.
  - **Text Highlighter** (`H` key) to mark critical stem details.
  - **Question Flagging** (`F` key) for bookmarking.
  - **Question Navigator Grid** (`G` key) with filters for Unanswered, Correct, Incorrect, and Flagged.
  - **Performance Scorecard** (`R` key) showing domain-by-domain accuracy and a **Targeted AI Review Prompt Generator** to drill weak topics in Gemini/ChatGPT.
- **Offline & Local Storage**: Auto-saves exam progress, answers, flags, and timer in your browser.

---

## 📁 Repository Contents

- [`index.html`](index.html) & [`SLI_120Q_Interactive_Exam.html`](SLI_120Q_Interactive_Exam.html): Standalone interactive exam application.
- [`SLI_Master_Exam_Study_Guide.md`](SLI_Master_Exam_Study_Guide.md): 210 KB master study bible synthesizing all lectures, official quizzes, formulas, and traps.
- [`notebook_sources/`](notebook_sources/): 7 modular session guides optimized for upload into Google NotebookLM for audio/video lecture generation.
  - `01_Behavioral_Economics_Part_1.md`
  - `02_Behavioral_Economics_Part_2.md`
  - `03_Survival_Analysis_Part_1.md`
  - `04_Survival_Analysis_Part_2.md`
  - `05_Applied_Biostatistics_Part_1.md`
  - `06_Applied_Biostatistics_Part_2.md`
  - `07_Formula_Sheet_and_Quiz_Bank.md`
- Raw lecture slide decks (`.pptx`), official study guide PDFs, and decompressed Anki deck (`SLI Exam.apkg`).
