# SL&I 3 Comprehensive Practice Exam Bank (420 Questions Total)

[![Live Exam Set 1](https://img.shields.io/badge/Exam%20Set%201-120%20Questions-38bdf8?style=for-the-badge&logo=googlechrome&logoColor=white)](https://mayolol16.github.io/SLI_practice_exam/)
[![Live Exam Set 2](https://img.shields.io/badge/Exam%20Set%202-120%20Questions-a855f7?style=for-the-badge&logo=googlechrome&logoColor=white)](https://mayolol16.github.io/SLI_practice_exam/exam2.html)
[![Live Exam Set 3](https://img.shields.io/badge/Exam%20Set%203-60%20Questions%20(Official%20Format)-10b981?style=for-the-badge&logo=googlechrome&logoColor=white)](https://mayolol16.github.io/SLI_practice_exam/exam3.html)
[![Live Exam Set 4](https://img.shields.io/badge/Exam%20Set%204-60%20Questions%20(Practice%20Exam)-f59e0b?style=for-the-badge&logo=googlechrome&logoColor=white)](https://mayolol16.github.io/SLI_practice_exam/exam4.html)
[![Live In-House Exam](https://img.shields.io/badge/In--House%20Exam-60%20Questions%20(Quizzes%20%26%20Lectures)-ec4899?style=for-the-badge&logo=googlechrome&logoColor=white)](https://mayolol16.github.io/SLI_practice_exam/inhouse.html)
[![Course](https://img.shields.io/badge/Course-UB%20IMC%20543LEC%203%20(SL%26I%203)-ef4444?style=for-the-badge)](#course-context)

Interactive, standalone examination web applications and comprehensive study suite for **University at Buffalo Jacobs School of Medicine and Biomedical Sciences — Scientific Literacy & Inquiry (SL&I) Semester 3 Final Examination**.

---

## 🌐 Launch Interactive Exams (Live on GitHub Pages)

Access all five exam blocks from any browser (desktop, tablet, mobile):

* 👉 **[Launch Practice Exam Set 1 (120 Questions)](https://mayolol16.github.io/SLI_practice_exam/)**
* 👉 **[Launch Practice Exam Set 2 (120 Questions)](https://mayolol16.github.io/SLI_practice_exam/exam2.html)**
* 👉 **[Launch Practice Exam Set 3 (60 Questions - Official Exam Format)](https://mayolol16.github.io/SLI_practice_exam/exam3.html)**
* 👉 **[Launch Practice Exam Set 4 (60 Questions - Semester 3 Practice Exam)](https://mayolol16.github.io/SLI_practice_exam/exam4.html)**
* 👉 **[Launch In-House Exam (60 Questions - Quizzes & Lecture Questions)](https://mayolol16.github.io/SLI_practice_exam/inhouse.html)**

*All five sets are also saved locally in `~/Downloads/` as `SLI_120Q_Interactive_Exam.html` (Set 1), `SLI_120Q_Set2_Interactive_Exam.html` (Set 2), `SLI_60Q_Set3_Interactive_Exam.html` (Set 3), `SLI_60Q_Set4_Interactive_Exam.html` (Set 4), and `SLI_60Q_InHouse_Interactive_Exam.html` (In-House) for instant one-click offline access.*

---

## 📊 Curricular Distribution (420 Questions Total)

Each exam set is calibrated to match the official **UB Jacobs School of Medicine SL&I Semester 3** curricular blueprint:

| Domain | Set 1 | Set 2 | Set 3 | Set 4 | In-House | Total | Core Tested Competencies |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Healthcare Economics & Financing** | 40 | 40 | 20 | 20 | 20 | **140 Qs** | Moral hazard (ex ante vs. ex post), Adverse selection & death spirals, Cost-sharing mechanics (deductible, coinsurance, copay, stop-loss), Own/cross-price & offset effects, Risk adjustment vs. Risk corridors vs. Reinsurance (ACA 3Rs), Managed care plans (HMO, PPO, EPO, POS), and Tax subsidies. |
| **Survival Analysis** | 40 | 40 | 20 | 20 | 10 | **130 Qs** | Time-to-event outcomes, Censoring types (right, left, interval, informative vs. non-informative), Survivor function $S(t)$, Hazard function $h(t)$, Kaplan-Meier product-limit estimation, Log-rank test, Cox proportional hazards regression, and Hazard ratios ($HR$). |
| **Applied Biostatistics** | 40 | 40 | 20 | 20 | 30 | **150 Qs** | Hypothesis testing errors (Type I $\alpha$ vs. Type II $\beta$), Power ($1-\beta$), Test selection (t-tests, ANOVA, Mann-Whitney, Wilcoxon, Kruskal-Wallis, Chi-square, Fisher's exact), 2x2 Risk calculations (ARR, RRR, NNT, NNH, RR vs. OR), Skewness, Mean/SD vs. Median/IQR, Z-scores & 68-95-99.7 rule, Multiple lab testing flag rate ($1 - 0.95^k$), and Confounding vs. Effect modification. |
| **Total Practice Bank** | **120** | **120** | **60** | **60** | **60** | **420 Qs** | **Full 7x replication of the official 60-question final exam** |

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
- **Header Switcher**: 5-way switcher navigation bar connecting all sets seamlessly across both GitHub Pages and local offline mirrors.
- **Local Storage Persistence**: Independently saves exam progress, answers, flags, and timer for all five sets.

---

## 📁 Repository Contents

- [`index.html`](index.html) & [`SLI_120Q_Interactive_Exam.html`](SLI_120Q_Interactive_Exam.html): Practice Exam Set 1 (120 Questions).
- [`exam2.html`](exam2.html) & [`SLI_120Q_Set2_Interactive_Exam.html`](SLI_120Q_Set2_Interactive_Exam.html): Practice Exam Set 2 (120 Questions).
- [`exam3.html`](exam3.html) & [`SLI_60Q_Set3_Interactive_Exam.html`](SLI_60Q_Set3_Interactive_Exam.html): Practice Exam Set 3 (60 Questions - Official Exam Format).
- [`exam4.html`](exam4.html) & [`SLI_60Q_Set4_Interactive_Exam.html`](SLI_60Q_Set4_Interactive_Exam.html): Practice Exam Set 4 (60 Questions - Semester 3 Practice Exam).
- [`inhouse.html`](inhouse.html) & [`SLI_60Q_InHouse_Interactive_Exam.html`](SLI_60Q_InHouse_Interactive_Exam.html): In-House Practice Exam (60 Questions - Quizzes & Lectures).
- [`SLI_Master_Exam_Study_Guide.md`](SLI_Master_Exam_Study_Guide.md): 55-page master curricular study manual covering all learning objectives, formulas, and distractor traps.
- `notebook_sources/`: High-yield markdown lecture modules, formula sheets, and curated video guide.

---

## 🏫 Course Context

- **Course:** IMC 543LEC 3 — Scientific Literacy & Inquiry (SL&I) - Semester 3
- **Institution:** University at Buffalo, Jacobs School of Medicine and Biomedical Sciences
- **Course Director:** Jennifer A. Campbell, PhD, MPH
- **Exam Format:** ~60 Single-Best-Answer Multiple-Choice Questions (1/3 Behavioral Economics, 1/3 Survival Analysis, 1/3 Biostatistics).
