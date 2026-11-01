# Session 7: Master Exam Formula Sheet, Common Traps, Self-Check Checklist, Curated Video Library, and Complete 45-Question Official Quiz Bank

> **Course:** Scientific Literacy & Inquiry (SL&I) – Semester 3 Final Exam Review  
> **Course Director:** Jennifer A. Campbell, PhD, MPH  
> **Exam Date & Time:** November 4, 2026 (1:00–2:30 PM). Approximately 60 Single-Best-Answer Questions (~20 on Behavioral Economics, ~20 on Survival Analysis, ~20 on Biostatistics).

---

## 1. Master Formula Sheet

You may use a basic calculator during the examination. Practice calculating every single one of these formulas by hand until it is automatic:

| Formula | Mathematical Notation | Primary Clinical / Economic Purpose | Example Calculation |
| :--- | :--- | :--- | :--- |
| **1. Patient Out-of-Pocket Expense** | $$\text{OOP} = \text{Deductible} + [\text{Coinsurance \%} \times (\text{Bill} - \text{Deductible})]$$<br>*(Subject to: $\text{OOP} \le \text{OOP Max}$)* | Calculate patient financial responsibility for a covered medical bill. | Bill = $10,000, Ded = $1,000, Coinsurance = 20%, OOP Max = $2,500.<br>Ded = $1,000. Remainder = $9,000. 20% of $9,000 = $1,800. Tentative = $2,800.<br>**Patient pays $2,500 (capped at OOP Max).** |
| **2. Willingness to Pay (WTP)** | $$\text{WTP} = \text{Expected Healthcare Cost} + \text{Risk Premium}$$ | Determine whether a consumer purchases an insurance plan (Buys iff $\text{Premium} \le \text{WTP}$). | Expected cost = $100, Risk premium = $15.<br>$\text{WTP} = \$115$. If premium is $112, consumer buys. If $120, declines. |
| **3. Premium Charged by Insurer** | $$\text{Premium} = \text{Actuarially Fair Premium (Expected Claims)} + \text{Loading Cost}$$ | Distinguish pure claims costs from administrative markups and profit. | Expected claims = $5,000, Loading = $500.<br>$\text{Premium} = \$5,500$. |
| **4. Patient Survival Time** | $$T_i = \text{Event/Censoring Date} - \text{Study Entry Date}$$ | Code patient duration in survival analysis from their own baseline. | Entered Month 3, recurred Month 11.<br>$$T = 11 - 3 = 8 \text{ months}, \quad \delta = 1$$. |
| **5. Z-Score (Normal Curve)** | $$z = \frac{x - \mu}{\sigma}$$ | Determine how many standard deviations an individual patient value lies from the mean. | Sodium = 134, $\mu = 140, \sigma = 2$.<br>$$z = (134 - 140) / 2 = -3.0$$.<br>Hemoglobin = 11.0, $\mu = 13.5, \sigma = 1.0$.<br>$$z = (11.0 - 13.5) / 1.0 = -2.5$$. |
| **6. Standard Error of the Mean (SE)** | $$SE = \frac{SD}{\sqrt{n}}$$ | Measure the precision of the estimated sample mean. Shrinks as $n$ grows! | $SD = 20, n = 100$.<br>$$SE = 20 / \sqrt{100} = 20 / 10 = 2.0$$. |
| **7. 95% Confidence Interval for Mean** | $$95\% \text{ CI} \approx \text{Mean} \pm 1.96 \times SE$$ | Plausible range containing the true population mean. | Mean = 140 mmHg, $SE = 2.0$.<br>$$95\% \text{ CI} = 140 \pm (1.96 \times 2.0) = 136.08 \text{ to } 143.92 \approx 136 \text{ to } 144$$. |
| **8. Absolute Risk Reduction (ARR)** | $$ARR = \text{Control Event Rate (CER)} - \text{Treatment Event Rate (EER)}$$ | Measure absolute clinical benefit of an intervention. | Control MI = 4% (0.04), Tx MI = 3% (0.03).<br>$$ARR = 0.04 - 0.03 = 0.01 \quad (1.0\%)$$. |
| **9. Relative Risk (RR)** | $$RR = \frac{a / (a + b)}{c / (c + d)} = \frac{EER}{CER}$$ | Measure relative probability of an event in exposed/treated vs. unexposed. (Used in **cohort studies and RCTs**). | $$RR = 0.03 / 0.04 = 0.75$$. |
| **10. Relative Risk Reduction (RRR)** | $$RRR = \frac{CER - EER}{CER} = 1 - RR = \frac{ARR}{CER}$$ | Measure proportional reduction in event rate relative to baseline. | $$RRR = 0.01 / 0.04 = 0.25 \quad (25\%)$$. |
| **11. Number Needed to Treat (NNT)** | $$NNT = \frac{1}{ARR} = \frac{1}{CER - EER}$$<br>*(Always round UP to next whole integer!)* | Number of patients who must receive treatment for a specified time to prevent 1 adverse event. | $$ARR = 0.01$. $NNT = 1 / 0.01 = 100$ patients treated for 5 years. |
| **12. Number Needed to Harm (NNH)** | $$NNH = \frac{1}{\text{Absolute Risk Increase (ARI)}} = \frac{1}{EER - CER}$$ | Number of patients treated before 1 adverse side effect is caused. | Control bleed = 1%, Tx bleed = 2%.<br>$$ARI = 0.01$. $NNH = 1 / 0.01 = 100$$. |
| **13. Multiple Lab Testing Probability** | $$P(\ge 1 \text{ false flag in } k \text{ tests}) = 1 - (1 - \alpha)^k = 1 - (0.95)^k$$ | Calculate probability of at least one abnormal flag in an automated panel of $k$ independent tests. | For 12 tests ($k=12$):<br>$$1 - (0.95)^{12} \approx 1 - 0.540 = 0.46 \quad (46\%)$$.<br>For 20 tests ($k=20$):<br>$$1 - (0.95)^{20} \approx 1 - 0.358 = 0.642 \quad (64.2\%)$$. |
| **14. Coefficient of Determination ($r^2$)** | $$r^2 = (r)^2$$ | Proportion of total variance in outcome explained by its linear relationship with predictor. | $r = 0.70 \implies r^2 = 0.49$ (49% explained).<br>$r = -0.30 \implies r^2 = 0.09$ (9% explained). |
| **15. Regression Slope Prediction** | $$\Delta \hat{Y} = \beta_1 \times \Delta X$$ | Predict change in continuous outcome for a given change in predictor. (Intercept does NOT enter difference!). | $\beta = 0.08$ per 1 kg/m² BMI. For $\Delta BMI = 10$:<br>$\Delta HbA1c = 10 \times 0.08 = 0.8$ percentage points. |
| **16. Relative Hazard Reduction** | $$\text{Reduction} = (1 - HR) \times 100\%$$ | Translate a Hazard Ratio into percentage risk reduction over follow-up. | $HR = 0.65 \implies (1 - 0.65) \times 100\% = 35\%$ lower hazard.<br>$HR = 1.30 \implies (1.30 - 1) \times 100\% = 30\%$ higher hazard. |

---

## 2. High-Yield Clinical Mnemonics & Flashcard Hooks

- **Medicare Parts A, B, C, D:**
  - **Part A:** **inpAtient** care $\implies$ Hospital stays, hospice, skilled nursing, home health. (Funded by 2.9% FICA payroll tax).
  - **Part B:** **Basic / outpatient** care $\implies$ Doctor visits, outpatient clinics, durable medical equipment, lab tests, ambulances. (Funded by monthly premiums + general revenues).
  - **Part C:** **Company / Commercial** care $\implies$ **Medicare Advantage** (private HMOs/PPOs bundling A+B+D with out-of-pocket maximums).
  - **Part D:** **Drugs** $\implies$ Outpatient prescription pharmaceutical formularies with mandatory protected classes.
- **Medicaid:** **State-funded & means-tested** for low-income, pregnancy, children, and disabled. The #1 payer of **long-term nursing home custodial care** in the US!
- **CHIP:** **Children's Health Insurance Program** $\implies$ For families who make *too much* to qualify for Medicaid, but *not enough* to afford private health insurance for their kids.
- **COBRA:** **"Unemployed But Keep My Coverage"** $\implies$ Allows workers to keep employer group health plan for up to 18–36 months after job loss, but employee pays 102% of the premium (super expensive!).
- **Study Designs: Relative Risk (RR) vs. Odds Ratio (OR):**
  - **Relative Risk (RR):** Strictly used in **Cohort Studies** and **Randomized Controlled Trials (RCTs)** where true cumulative disease incidence can be measured.
  - **Odds Ratio (OR):** Strictly used in **Case-Control Studies** (where incidence cannot be directly measured) and reported in **Logistic Regression**.
- **One-Sentence Hazard Ratio Interpretation Template:**
  > *"An HR of [X] (95% CI, [Y] to [Z]) means that at any given point in time during follow-up, the treatment group had a [(1 - X) * 100]% [lower/higher] risk of experiencing the event compared to the control group, and we are 95% confident the true relative hazard lies between [Y] and [Z]."*

---

## 3. Curated High-Yield Video Library

| Topic | Video Title & Instructor | Direct URL | High-Yield Timestamps & Focus Areas |
| :--- | :--- | :--- | :--- |
| **Patient Cost Sharing** | *How to Calculate Patient and Payer Responsibility* by Ask The Biller® | [YouTube Link](http://www.youtube.com/watch?v=SdYPzcQPWOw) | Step-by-step math of deductibles, coinsurance %, and hitting out-of-pocket maximums. |
| **Adverse Selection & Moral Hazard** | *Health Econ. - Moral Hazard and Adverse Selection* by Joseph Shinn | [YouTube Link](http://www.youtube.com/watch?v=LdOx3Abd13g) | Multi-round adverse selection death spiral table (starts at 0:37); demand curve shifts under moral hazard. |
| **Medicare Breakdown** | *Medicare Explained: Parts A, B, C, & D* | [YouTube Link](https://www.youtube.com/watch?v=t3gRoYNFY3s) | Clear distinctions between Traditional Medicare vs. Medicare Advantage and coverage gaps. |
| **Survival Analysis I** | *Introduction to Survival Analysis* | [YouTube Link](https://www.youtube.com/watch?v=Wo9RNcHM_bs) | Time-to-event outcomes, right vs. left vs. interval censoring, non-informative assumption. |
| **Survival Analysis II** | *Kaplan-Meier Curves & Log-Rank Test* | [YouTube Link](https://www.youtube.com/watch?v=bVcCevk_ab0) | Reading step-downs, tick marks, number at risk, and comparing groups. |
| **Censoring Types** | *Types of Censoring in Survival Analysis* | [YouTube Link](https://www.youtube.com/watch?v=L_ziqYhksG8) | Right vs. left vs. interval vs. administrative censoring visual diagrams. |
| **Cox Regression & Hazard Ratios** | *Cox Proportional Hazards Regression and HR* | [YouTube Link](https://www.youtube.com/watch?v=vtOj8-3bI3M) | Multivariable adjustment, checking proportional hazards assumption (crossing curves). |
| **Biostatistics Core I** | *Hypothesis Testing and p-Values* | [YouTube Link](http://www.youtube.com/watch?v=75pQPB1RF50) | $H_0$ vs. $H_a$, Type I vs. Type II errors, who gets hurt in clinical medicine. |
| **Biostatistics Core II** | *Statistical Power and Sample Size* | [YouTube Link](http://www.youtube.com/watch?v=lyMvsbiXT1c) | The 4 levers of power: sample size, effect size, variability, alpha. |
| **Biostatistics Core III** | *Distributions, Skewness, and Central Tendency* | [YouTube Link](http://www.youtube.com/watch?v=7ymCiLPP9os) | Mean/SD vs. Median/IQR, visual tail behavior, z-scores on the normal curve. |
| **Biostatistics Core IV** | *Correlation and Linear vs. Logistic Regression* | [YouTube Link](http://www.youtube.com/watch?v=NRw8pNn-WmM) | Pearson $r$, Spearman $ho$, $R^2$, slope $eta$, odds ratios, and confounding adjustment. |

---

## 4. The 10 Critical Exam Traps (From Faculty Study Guide)

Examiners deliberately construct question stems around these ten classic misunderstandings:

1. **The Null Value Trap (Ratios vs. Differences):**
   - *Trap:* Declaring a ratio measure (RR, OR, HR) statistically significant because "the CI does not include 0."
   - *Correction:* The null value for ratios is **1.0**! The null value for differences (e.g., SBP difference) is **0.0**. Always check whether the measure is a difference or a ratio first.
2. **"Fail to Reject" vs. "No Effect" Trap:**
   - *Trap:* Reading a non-significant result ($p = 0.08$) as proof that "the drug has no effect."
   - *Correction:* Absence of evidence is not evidence of absence. A non-significant result may simply mean the trial was underpowered. Evaluate the confidence interval against the Minimal Clinically Important Difference (MCID).
3. **Misleading Patients with RRR:**
   - *Trap:* Telling a patient their risk of a heart attack is reduced by "25%" (Relative Risk Reduction) when their true risk only dropped from 4% to 3% (Absolute Risk Reduction of 1%).
   - *Correction:* Always communicate **Absolute Risk Reduction (ARR)** and **Number Needed to Treat (NNT)** with an explicit time frame (e.g., "1 out of 100 patients treated for 5 years will avoid an MI").
4. **The Test Selection Trap (Categorical vs. Continuous):**
   - *Trap:* Choosing One-Way ANOVA simply because a trial has 3 study groups, even though the outcome is binary (Yes/No cured).
   - *Correction:* ANOVA is strictly for **continuous** outcomes (means). If the outcome is categorical/proportions, you must use a **Chi-Square test** regardless of the number of groups!
5. **The Correlation Slope & Causation Trap:**
   - *Trap:* Treating a correlation coefficient $r$ as a regression slope $eta$, or concluding that a small p-value ($p < 0.001$) proves causation.
   - *Correction:* Correlation measures linear clustering strength, not rate of change (slope). Confounding variables easily produce statistically significant correlations without causal links.
6. **The Hazard Rate Trap:**
   - *Trap:* Believing that a hazard $h(t)$ is a probability that cannot exceed 1.0, or that a Hazard Ratio of 0.65 means "65% of patients survived."
   - *Correction:* A hazard is an instantaneous **rate (velocity)** that has no upper bound. An $HR = 0.65$ means a **35% lower instantaneous event rate** at any point in time. It conveys nothing about the absolute proportion surviving.
7. **The Composite Endpoint / Death Classification Trap:**
   - *Trap:* Counting an accidental death (e.g., motor vehicle collision) as "censored" in an oncology trial.
   - *Correction:* If the trial endpoint includes "Overall Survival (OS)" or defines Event-Free Survival (EFS) to include "death from any cause," **any death—including trauma or infection—is coded as an EVENT ($\delta = 1$)**, NOT as censored!
8. **The Regression Extrapolation Trap:**
   - *Trap:* Using a regression equation derived from dietary sodium intakes between 1.5 and 6.0 g/day to predict blood pressure in a patient consuming 10 g/day.
   - *Correction:* Predictions are valid strictly within the observed range of study data. Extrapolation outside the empirical range is invalid.
9. **The Within-Arm Trap:**
   - *Trap:* Claiming a drug works because patients improved from baseline to Month 6 within the treatment arm.
   - *Correction:* Within-arm improvement can be driven entirely by the placebo effect, regression to the mean, or natural disease resolution. A treatment effect is proven **only by comparing the difference between the treatment arm and the control arm**.
10. **The Behavioral Economics Definitions Trap:**
    - *Trap:* Confusing ex-ante with ex-post moral hazard, or confusing own-price effects with cross-price effects.
    - *Correction:*
      - **Ex-ante:** Risky behavior *before* illness strikes because insurance covers costs.
      - **Ex-post:** Excess healthcare utilization *after* illness strikes due to low copays.
      - **Own-price:** Higher drug copay $\implies$ fewer refills of that drug.
      - **Cross-price:** Higher drug copay $\implies$ fewer primary care office visits.

---

## 5. Faculty Self-Check Exam Checklist & Master Answers

Tick each item only when you can answer it completely from memory:

### Part I: Behavioral Economics
- [x] **Explain why saving cannot replace insurance, using the shape of health spending:**  
  *Answer:* Health spending is severely right-skewed and unpredictable. Most people spend little, but a tiny fraction incur catastrophic bills (>$100k). Individuals cannot save enough out of wages for unpredictable catastrophic losses, nor can incapacitated sick patients borrow large sums.
- [x] **Classify a scenario as ex ante or ex post moral hazard:**  
  *Answer:* Ex ante occurs *before* illness/injury (e.g., cliff diving or stopping diet because care is covered). Ex post occurs *after* illness strikes (e.g., demanding elective MRIs or extra visits because copays are only $10).
- [x] **Calculate out-of-pocket cost with a deductible, coinsurance, and out-of-pocket max:**  
  *Answer:* $	ext{OOP} = 	ext{Deductible} + [	ext{Coinsurance} 	imes (	ext{Bill} - 	ext{Deductible})]$, capped at OOP Max.
- [x] **Tell own-price, cross-price, and offset effects apart in a vignette:**  
  *Answer:* Own-price = price of Drug A rises $\implies$ use of Drug A falls. Cross-price = price of Drug A rises $\implies$ use of Doctor Visits falls. Offset effect = cutting essential meds $\implies$ disease exacerbation, ED visits, and hospitalizations that increase total costs.
- [x] **Work a death-spiral table for two rounds:**  
  *Answer:* Round 1: Premium set at pool average cost. Healthy individuals whose WTP < premium decline. Sicker enrollees buy, causing actual claims to exceed revenue (insurer loss). Round 2: Insurer raises premium to new average of remaining enrollees. Moderate-risk members drop out. Process repeats until pool collapses.
- [x] **Match each remedy to the problem it solves:**  
  *Answer:* Guaranteed Issue + Mandate eliminates underwriting while keeping healthy people in pool; Risk Adjustment redistributes funds between plans based on enrollee health scores; Reinsurance covers catastrophic individual cases; Risk Corridors cushions unexpected insurer profits/losses.
- [x] **State both fundamental tradeoffs with an example:**  
  *Answer:* Tradeoff 1: Financial Protection vs. Moral Hazard (Generous zero-deductible coverage protects patients but causes overutilization). Tradeoff 2: Competition vs. Adverse Selection (Allowing many plan choices fosters competition but triggers risk selection and death spirals).
- [x] **Summarize Tamblyn 2001 and Jacobs & Sommers 2015:**  
  *Answer:* Tamblyn (2001) showed drug cost-sharing in Quebec caused patients to cut both essential and non-essential drugs, sparking a dose-dependent increase in ED visits and death (offset effects). Jacobs & Sommers (2015) showed insurers placed 100% of HIV drugs onto high specialty tiers (adverse tiering) to deter sick patients from enrolling (favorable risk selection).

### Part II: Survival Analysis
- [x] **Code survival time and status from patient stories:**  
  *Answer:* Survival time = Event/Censoring time minus Entry time. Status: Event = 1, Censored = 0.
- [x] **Name the censoring type in a scenario and say whether it is informative:**  
  *Answer:* Right censoring = follow-up ends before event (study end, lost to follow-up, withdrawal). Non-informative if leaving is unrelated to disease risk (e.g. job relocation); Informative if leaving is linked to disease severity (e.g. sickest patients drop out due to cancer progression, biasing survival upward).
- [x] **Interpret $S(t)$ and explain the steps, tick marks, and number at risk on a KM curve:**  
  *Answer:* $S(t) = P(T > t)$. Vertical steps occur only when events happen. Tick marks represent censored patients (who leave risk set without dropping curve). Steep drops in number at risk with a flat curve indicate administrative censoring, not deaths.
- [x] **Explain why a hazard can exceed 1 and match a clinical pattern to its hazard shape:**  
  *Answer:* Hazard is an instantaneous velocity/rate (events per person-time), not a probability. Shapes: Constant = sudden cardiac death; Increasing = aging/Alzheimer's; Decreasing = post-op surgical complications; Bathtub = organ transplant; Unimodal = stroke risk after TIA.
- [x] **Decide whether a given death counts as an event for EFS or OS:**  
  *Answer:* If the endpoint is Overall Survival or defines EFS to include "death from any cause," every death (even accidental or unrelated) counts as an Event ($\delta = 1$).
- [x] **Interpret an HR and its CI in one sentence:**  
  *Answer:* "An EFS HR of 0.65 (95% CI, 0.51–0.83) indicates that at any point in time during follow-up, treated patients experienced a statistically significant 35% lower instantaneous risk of disease progression or death compared to control."

### Part III: Biostatistics
- [x] **Write $H_0$ and $H_a$ and describe who is harmed by Type I vs. Type II error:**  
  *Answer:* $H_0$: No effect; $H_a$: An effect exists. Type I error ($lpha$, false positive) harms patients by prescribing an ineffective drug with side effects and financial costs for no benefit. Type II error ($eta$, false negative) harms patients by abandoning an effective drug.
- [x] **Predict how $n$, SD, $lpha$, and target effect change power and CI width:**  
  *Answer:* Power increases with larger $n$, larger effect size, lower SD, or higher $lpha$. 95% CI width narrows with larger $n$ or lower SD ($SE = SD / \sqrt{n}$).
- [x] **Pick the right test from outcome type and comparison:**  
  *Answer:* Continuous, 2 independent groups = Two-sample t-test; Continuous, paired = Paired t-test; Continuous, $\ge 3$ groups = One-Way ANOVA; Categorical/Proportions = Chi-square test (or Fisher's exact if cell < 5); Time-to-event with censoring = Log-rank test.
- [x] **Interpret a p-value and say whether a CI crosses the correct null value:**  
  *Answer:* p-value is probability of data this extreme assuming $H_0$ is true. Differences: null is 0. Ratios (RR, OR, HR): null is 1.0. CI excluding null means $p < 0.05$.
- [x] **Classify a result into one of the four significance categories using the MCID:**  
  *Answer:* 1. Significant & Meaningful (CI beyond MCID). 2. Significant but NOT Meaningful (huge sample, CI excludes 0 but short of MCID). 3. Inconclusive (CI spans 0 and MCID). 4. Convincingly Negative (CI tight around 0, excludes MCID).
- [x] **Calculate ARR, RRR, and NNT and explain to a patient:**  
  *Answer:* $ARR = CER - EER$; $RRR = ARR / CER$; $NNT = 1 / ARR$ (rounded up). Patient explanation: "Treating 100 patients for 5 years prevents 1 heart attack."
- [x] **Choose mean/SD or median/IQR from distribution shape; calculate z-score:**  
  *Answer:* Normal/symmetric = Mean & SD. Skewed (right or left) = Median & IQR (mean is distorted by tail). Z-score: $z = (x - \mu) / \sigma$.
- [x] **Tell SD from SE and calculate both ranges for a sample:**  
  *Answer:* SD measures individual patient variation (does not shrink with $n$). 95% of patients = $	ext{Mean} \pm 2 	ext{SD}$. SE measures precision of sample mean ($SE = SD / \sqrt{n}$, shrinks with $n$). 95% CI for mean = $	ext{Mean} \pm 1.96 	ext{SE}$.
- [x] **Interpret $r$, $r^2$, regression slope, $R^2$, and adjusted vs. unadjusted estimates:**  
  *Answer:* $r$ = direction/strength of straight line ($-1$ to $+1$). $r^2$ / $R^2$ = share of variance explained. Slope $eta$ = change in mean $Y$ per 1-unit increase in $X$. Unadjusted $eta$ mixes exposure with confounders; adjusted $eta$ isolates independent association holding covariates constant.
- [x] **Match linear, logistic, and Cox regression to outcome and name null values:**  
  *Answer:* Continuous $\implies$ Linear ($eta$, null = 0). Binary $\implies$ Logistic (OR, null = 1.0). Time-to-event with censoring $\implies$ Cox Proportional Hazards (HR, null = 1.0).
- [x] **Answer both of Ms. D's questions in one sentence each:**  
  *Answer:* Question 1 (ALT 44): In a 20-test panel, a healthy individual has a 64% chance of at least one abnormal flag by chance, so we will monitor the trend rather than ordering an invasive workup. Question 2 (Halving salt): Cutting sodium by 2.5 g/day is predicted to lower SBP by ~5.25 mmHg based on adjusted regression, achieving a clinically meaningful improvement.

---

## 6. Complete 45-Question Official Quiz Bank with Rationales

### Part A: Healthcare Economics UB Learns Official Quiz (20 Questions)

1. **Question 1:** A 45-year-old man with no significant medical history is concerned about unexpected medical expenses. He asks his physician why people need health insurance. Which of the following best explains the primary financial purpose of health insurance?  
   - A. To ensure equal access to all treatments  
   - B. To reduce the variance of income by protecting against unpredictable costs  
   - C. To guarantee better health outcomes for enrollees  
   - D. To eliminate the risk of illness  
   * **Answer:** **B**  
   * **Rationale:** Health insurance primarily protects individuals from unpredictable, potentially catastrophic medical expenses by pooling risk across many people, thereby reducing financial uncertainty (consumption smoothing) rather than guaranteeing health outcomes or eliminating illness.

2. **Question 2:** A 30-year-old woman with private health insurance chooses to see her doctor for multiple minor complaints because her co-pay is only $10 per visit. This is an example of which of the following?  
   - A. Ex ante moral hazard  
   - B. Ex post moral hazard  
   - C. Risk selection  
   - D. Loading cost  
   * **Answer:** **B**  
   * **Rationale:** Ex post moral hazard occurs after obtaining insurance, when lower out-of-pocket costs encourage greater use of healthcare services. The low copay makes the patient more likely to seek care for minor complaints.

3. **Question 3:** A 27-year-old man with health insurance decides to start skydiving because he knows that emergency care will be covered if he is injured. This behavior reflects which concept?  
   - A. Ex post moral hazard  
   - B. Adverse selection  
   - C. Ex ante moral hazard  
   - D. Capacity control  
   * **Answer:** **C**  
   * **Rationale:** Ex ante moral hazard refers to engaging in riskier behavior before an event occurs because insurance reduces the financial consequences of illness or injury. Skydiving is an example of increased risk-taking after obtaining coverage.

4. **Question 4:** A 65-year-old woman needs surgery costing $20,000. Her insurance policy requires her to pay the first $2,000 before coverage begins. This $2,000 payment is best described as which of the following?  
   - A. Premium  
   - B. Deductible  
   - C. Coinsurance  
   - D. Co-pay  
   * **Answer:** **B**  
   * **Rationale:** A deductible is the amount a patient must pay out of pocket before insurance begins paying for covered services.

5. **Question 5:** A 54-year-old man with health insurance is responsible for paying 20% of his $10,000 hospital bill after meeting his deductible. What type of cost-sharing is this?  
   - A. Premium  
   - B. Deductible  
   - C. Co-pay  
   - D. Coinsurance  
   * **Answer:** **D**  
   * **Rationale:** Coinsurance is a percentage of the cost of covered services that the patient pays after meeting the deductible.

6. **Question 6:** A 70-year-old woman in Quebec was receiving free prescriptions before a 1996 reform that introduced coinsurance and deductibles. After the reform, she cut back on both essential and non-essential medications and later required hospitalization for heart failure. This demonstrates which of the following unintended consequences of cost-sharing?  
   - A. It improves efficiency by eliminating unnecessary care  
   - B. It may reduce use of essential medications, worsening outcomes  
   - C. It prevents adverse selection in the insurance pool  
   - D. It ensures patients always make rational medication choices  
   * **Answer:** **B**  
   * **Rationale:** Cost-sharing can reduce unnecessary care, but it may also discourage patients from taking high-value medications, leading to poorer health outcomes and potentially more expensive hospitalizations (offset effects).

7. **Question 7:** A 40-year-old man tells his physician that he prefers comprehensive health insurance that covers all costs, even minor services. Which of the following is the first fundamental tradeoff of health insurance this preference highlights?  
   - A. More coverage protects against large risks but increases unnecessary care use  
   - B. Broader coverage reduces risk selection but increases premiums  
   - C. Larger risk pools reduce loading costs but limit patient choice  
   - D. Expanding coverage decreases secondary risk but increases primary risk  
   * **Answer:** **A**  
   * **Rationale:** The first major tradeoff in health insurance is that broader coverage provides better financial protection but also increases the likelihood of moral hazard by reducing the cost of seeking care.

8. **Question 8:** A 33-year-old woman in Canada is told she will have to wait 3 months for an elective knee surgery despite having no cost-sharing at the point of service. This waiting time is an example of which of the following strategies to limit moral hazard?  
   - A. Risk corridors  
   - B. Gatekeeping  
   - C. Capacity control  
   - D. Risk adjustment  
   * **Answer:** **C**  
   * **Rationale:** Capacity control limits utilization by restricting the supply of services, such as through waiting lists, rather than charging patients at the point of care.

9. **Question 9:** An insurance plan offers free gym memberships, which results in more healthy individuals enrolling compared to sicker individuals. This is best described as which of the following?  
   - A. Adverse selection  
   - B. Favorable risk selection  
   - C. Ex ante moral hazard  
   - D. Ex post moral hazard  
   * **Answer:** **B**  
   * **Rationale:** Favorable risk selection occurs when healthier individuals are disproportionately attracted to a health plan, lowering average healthcare costs for the insurer.

10. **Question 10:** A 56-year-old man pays $500 per month for his health insurance. His expected healthcare costs for the year are $6,000. The portion of his premium that equals his expected claims is referred to as which of the following?  
    - A. Loading cost  
    - B. Actuarially fair premium  
    - C. Risk premium  
    - D. Stop-loss  
    * **Answer:** **B**  
    * **Rationale:** The actuarially fair premium equals the expected healthcare costs of the insured before administrative expenses, profit, and other loading costs are added.

11. **Question 11:** A 29-year-old patient with HIV buys an ACA marketplace plan. The insurer places all HIV medications, including generics, in the highest cost-sharing tier. This practice is best described as:  
    - A. Adverse selection  
    - B. Risk adjustment  
    - C. Adverse tiering  
    - D. Reinsurance  
    * **Answer:** **C**  
    * **Rationale:** Adverse tiering places expensive medications used by patients with specific conditions into the highest cost-sharing tiers, discouraging those patients from enrolling or remaining in the plan.

12. **Question 12:** A 47-year-old woman with diabetes chooses an ACA exchange plan. To protect insurers from very high costs for patients like her, the ACA created a mechanism that pays insurers when they cover unusually expensive individuals. This is known as:  
    - A. Risk corridors  
    - B. Reinsurance  
    - C. Risk adjustment  
    - D. Capacity control  
    * **Answer:** **B**  
    * **Rationale:** Reinsurance protects insurers against exceptionally high-cost enrollees by reimbursing part of those expenses, reducing financial risk.

13. **Question 13:** A 34-year-old uninsured man applies for coverage through an ACA marketplace. He learns that plans cannot deny him coverage for pre-existing conditions, and that his premiums may be reduced with tax credits. These provisions were designed primarily to address which of the following?  
    - A. Loading costs  
    - B. Moral hazard  
    - C. Adverse selection  
    - D. Secondary risk  
    * **Answer:** **C**  
    * **Rationale:** ACA provisions such as guaranteed issue and premium tax credits were designed to reduce adverse selection by encouraging both healthy and sick individuals to participate in the insurance market.

14. **Question 14:** A 59-year-old man joins a large employer-sponsored health plan with thousands of employees. Compared to buying an individual plan, this large group insurance will primarily reduce which of the following?  
    - A. Primary risk  
    - B. Secondary risk  
    - C. Adverse selection  
    - D. Loading costs  
    * **Answer:** **B**  
    * **Rationale:** Large employer groups reduce secondary (financial) risk by spreading unpredictable healthcare costs across many individuals, making expenses more predictable.

15. **Question 15:** A 42-year-old woman compares premiums across multiple ACA exchange plans. Some plans lose money if they attract many high-cost enrollees. To protect against extreme financial losses and gains, the ACA introduced which of the following mechanisms?  
    - A. Risk corridors  
    - B. Reinsurance  
    - C. Stop-loss provisions  
    - D. Gatekeeping  
    * **Answer:** **A**  
    * **Rationale:** Risk corridors were designed to limit extreme insurer gains and losses during the early years of the ACA marketplaces by sharing financial risk with the government.

16. **Question 16:** Which is a key advantage of group employer-based insurance in reducing adverse selection?  
    - A. It requires risk-adjusted premiums  
    - B. All employees are automatically covered  
    - C. It excludes high-risk individuals  
    - D. It offers universal public coverage  
    * **Answer:** **B**  
    * **Rationale:** Automatic enrollment through employer-sponsored coverage broadens the risk pool by including healthier individuals who might otherwise remain uninsured, reducing adverse selection.

17. **Question 17:** A disadvantage of employer-based insurance is:  
    - A. It encourages overuse of preventive care  
    - B. It restricts employee mobility between jobs  
    - C. It increases insurer competition  
    - D. It reduces adverse selection  
    * **Answer:** **B**  
    * **Rationale:** Employer-sponsored insurance can create "job lock," where employees are reluctant to change jobs because they would lose their health insurance.

18. **Question 18:** Compared with an HMO, a PPO typically:  
    - A. Requires referrals for specialists  
    - B. Offers no out-of-network coverage  
    - C. Costs more but allows out-of-network care  
    - D. Is more restrictive in provider choice  
    * **Answer:** **C**  
    * **Rationale:** PPOs generally have higher premiums than HMOs but provide greater flexibility by allowing out-of-network care without requiring referrals.

19. **Question 19:** Which best describes an EPO?  
    - A. Requires a referral for all specialist visits  
    - B. Allows out-of-network coverage at higher costs  
    - C. Requires use of in-network providers but no referrals  
    - D. Offers the most flexible provider choice  
    * **Answer:** **C**  
    * **Rationale:** EPOs require members to use in-network providers (except emergencies) but typically do not require referrals for specialty care.

20. **Question 20:** A point-of-service (POS) plan is best described as:  
    - A. A high-deductible plan with HSA  
    - B. A hybrid of HMO and PPO  
    - C. An indemnity insurance product  
    - D. A catastrophic-only insurance  
    * **Answer:** **B**  
    * **Rationale:** POS plans combine features of HMOs and PPOs by encouraging coordinated in-network care while allowing out-of-network services at higher cost.

---

### Part B: Survival Analysis UB Learns Official Quiz (10 Questions)

1. **Question 1: When to Use Survival Analysis**  
   Which of the following study designs would most appropriately require survival analysis techniques?  
   - A) A cross-sectional survey of current smoking prevalence  
   - B) A case-control study of past infection and cancer  
   - C) A longitudinal study measuring time to hospitalization  
   - D) A randomized trial comparing cholesterol levels at 6 months  
   * **Answer:** **C) A longitudinal study measuring time to hospitalization**  
   * **Explanation:** Survival analysis is used when the outcome is time until an event, and not just event status or levels of a continuous variable.

2. **Question 2: Interpreting the Hazard Function**  
   A clinical trial compares a new chemotherapy regimen with standard treatment in patients with advanced lung cancer. The hazard function for the new treatment group remains flat over time, while the control group’s hazard increases steadily. Which of the following best describes the implication of this hazard pattern for the treatment group?  
   - A) Patients are at increasing risk of failure over time  
   - B) Patients are at constant risk of failure over time  
   - C) The treatment leads to delayed onset of risk  
   - D) There is no failure observed in the treatment group  
   * **Answer:** **B) Patients are at constant risk of failure over time**  
   * **Explanation:** A flat hazard function implies a constant risk per unit time, which is characteristic of the exponential distribution and often assumed in simple survival models.

3. **Question 3: Censoring Mechanism**  
   In a survival study of kidney transplant patients, some participants are lost to follow-up, and some are still alive at the end of the study period. What type of censoring is this most consistent with?  
   - A) Left censoring  
   - B) Interval censoring  
   - C) Informative censoring  
   - D) Right censoring  
   * **Answer:** **D) Right censoring**  
   * **Explanation:** Right censoring occurs when the event of interest has not occurred by the end of the observation period or when a participant is lost to follow-up.

4. **Question 4: Informative vs. Non-informative Censoring**  
   In a survival analysis of patients with HIV, those who become too ill to return for follow-up are censored. Which type of censoring does this represent?  
   - A) Right censoring  
   - B) Non-informative censoring  
   - C) Informative censoring  
   - D) Left censoring  
   * **Answer:** **C) Informative censoring**  
   * **Explanation:** If the reason for censoring is related to the likelihood of the event (e.g., being too ill), it violates the non-informative assumption and biases results.

5. **Question 5: Left Censoring**  
   Which of the following scenarios illustrates left censoring?  
   - A) A patient is lost to follow-up before experiencing the event.  
   - B) A patient enrolls in a study and has the event after 12 months.  
   - C) A patient had the event before entering the study, but the exact time is unknown.  
   - D) A patient did not have the event before the study ended.  
   * **Answer:** **C) A patient had the event before entering the study, but the exact time is unknown.**  
   * **Explanation:** Left censoring occurs when the event has already happened before observation begins, but its timing is not known.

6. **Question 6: Interpretation of the Survivor Function**  
   A survival function $S(t) = 0.70$ at $t = 12$ months in a cancer study indicates:  
   - A) The event rate is 70% at 12 months  
   - B) 70% of patients had the event by 12 months  
   - C) The hazard at 12 months is 0.70  
   - D) 70% of patients are expected to survive beyond 12 months  
   * **Answer:** **D) 70% of patients are expected to survive beyond 12 months**  
   * **Explanation:** $S(t)$ represents the probability of surviving beyond time $t$.

7. **Question 7: Survivor Function at $t = 0$**  
   What is the value of the survival function $S(t)$ at time $t = 0$, assuming no events have occurred at baseline?  
   - A) 0  
   - B) 0.5  
   - C) 1  
   - D) Undefined  
   * **Answer:** **C) 1**  
   * **Explanation:** At $t = 0$, all individuals are alive or event-free, so $S(0) = 1$.

8. **Question 8: Nature of the Hazard Function**  
   Which of the following best defines the hazard function?  
   - A) The number of events per unit time  
   - B) The total risk accumulated by time $t$  
   - C) The instantaneous event rate at time $t$ given survival until $t$  
   - D) The proportion of censored observations at time $t$  
   * **Answer:** **C) The instantaneous event rate at time $t$ given survival until $t$**  
   * **Explanation:** The hazard function captures the conditional risk of failure in a tiny interval, given survival up to that time.

9. **Question 9: Main Goal of Survival Analysis**  
   Which of the following best describes the main goal of survival analysis in clinical research?  
   - A) To estimate the correlation between exposure and binary outcome  
   - B) To compare means across two treatment groups  
   - C) To estimate and compare the time until occurrence of a specific event  
   - D) To maximize sensitivity and specificity of a diagnostic test  
   * **Answer:** **C) To estimate and compare the time until occurrence of a specific event**  
   * **Explanation:** Survival analysis focuses on time-to-event data, accounting for censoring and the distribution of event times.

10. **Question 10: Handling Censored Data in Analysis**  
    In a cancer trial, a patient withdraws consent and stops all follow-up 10 months into a 3-year study, with no event observed up to that point. How should this patient's data be handled in the survival analysis?  
    - A. Excluded from the analysis entirely, since their eventual outcome is unknown  
    - B. Treated as an event at 10 months, since that's when they left the study  
    - C. Censored at 10 months, contributing at-risk time up to that point  
    - D. Censored at 3 years, the end of the study  
    * **Answer:** **C) Censored at 10 months, contributing at-risk time up to that point**  
    * **Explanation:** Right-censoring means follow-up ended before the event of interest occurred. The patient contributes at-risk time up to their last known point (10 months) but is not counted as an event, and is not simply dropped from the dataset.

---

### Part C: Applied Biostatistics Part 2 UB Learns Official Quiz (Mark Youssef's 15 Questions with 100% Score & Official Feedback)

1. **Question 1: Confounding in Logistic Regression**  
   A case-control study examines alcohol ($\ge 2$ drinks/day) and lung cancer. The crude odds ratio is 1.8 (95% CI, 1.4 to 2.3). After adjusting for pack-years of smoking in a logistic regression, the adjusted odds ratio is 1.05 (95% CI, 0.85 to 1.30). What is the best interpretation?  
   - A. Alcohol is an independent risk factor for lung cancer  
   - B. The adjusted result must be a Type II error because adjustment reduces power  
   - C. Smoking confounded the crude association; after accounting for it, no significant association remains  
   - D. Smoking is an effect modifier of the alcohol–lung cancer association  
   - E. Adjusting for smoking introduced bias into the estimate  
   * **Correct Answer:** **C) Smoking confounded the crude association; after accounting for it, no significant association remains**  
   * **Official UB Learns Feedback:** The estimate moved from 1.8 to about 1.0 once smoking was included, and the adjusted CI includes 1. That pattern is classic confounding. Effect modification would mean the association differs across smoking strata, which a single adjusted OR does not show.

2. **Question 2: Non-Linearity and Pearson Correlation**  
   A cohort study of 20,000 adults finds a Pearson correlation of $r = 0.01$ ($p = 0.16$) between BMI and all-cause mortality. A plot of mortality by BMI category shows higher mortality at both very low and very high BMI, with the lowest mortality at a BMI of about 22–25. What is the best conclusion?  
   - A. Higher BMI protects against death  
   - B. Pearson $r$ measures only linear association; a J-shaped relationship can produce an $r$ near 0  
   - C. A Spearman correlation would necessarily show a strong positive relationship  
   - D. The study was too small to detect a relationship  
   - E. BMI is unrelated to mortality  
   * **Correct Answer:** **B) Pearson $r$ measures only linear association; a J-shaped relationship can produce an $r$ near 0**  
   * **Official UB Learns Feedback:** Risk rises at both ends, so a straight line fits poorly and $r$ is near 0 even though the relationship is strong. Always look at the scatter plot before interpreting $r$.

3. **Question 3: Time-to-Event Regression Model Matching**  
   A cohort study follows 8,000 postmenopausal women for up to 10 years until their first hip fracture; women lost to follow-up are censored. Long-term proton pump inhibitor use has an adjusted hazard ratio of 1.30 (95% CI, 1.10 to 1.54), adjusted for age, BMI, and corticosteroid use. Which statement is correct?  
   - A. Logistic regression was used; PPI users had 30% higher odds of fracture  
   - B. Linear regression was used; PPI users had their fracture 1.3 years earlier  
   - C. Cox proportional hazards regression was used; PPI users had a 30% higher hazard of hip fracture at any point during follow-up, and the association is statistically significant  
   - D. Cox regression was used; the association is not significant because the CI does not include 0  
   - E. Kaplan–Meier analysis was used; 30% of PPI users had a fracture  
   * **Correct Answer:** **C) Cox proportional hazards regression was used; PPI users had a 30% higher hazard of hip fracture at any point during follow-up, and the association is statistically significant**  
   * **Official UB Learns Feedback:** Time-to-event data with censoring and covariates call for Cox regression, which reports hazard ratios. The null value for an HR is 1, and the CI excludes 1, so the association is significant. This directly links to the survival analysis in Sessions 3–4.

4. **Question 4: Extrapolation in Linear Regression**  
   A linear regression developed in adults aged 40 to 70 years predicts eGFR from age: $\text{eGFR} = 130 - 0.9 \times \text{age}$. A clinician uses it to estimate eGFR for a 22-year-old and a 95-year-old. What is the main problem?  
   - A. Extrapolation beyond the range of data used to build the model  
   - B. Confounding  
   - C. The slope is negative  
   - D. $R^2$ was not reported  
   - E. Type I error  
   * **Correct Answer:** **A) Extrapolation beyond the range of data used to build the model**  
   * **Official UB Learns Feedback:** A regression equation describes the relationship only within the range of the data. Outside ages 40 to 70 the relationship may be different, so these predictions are unreliable.

5. **Question 5: Multiple Testing in Laboratory Chemistry Panels**  
   A healthy 25-year-old has a 12-test chemistry panel. Each test's reference range is the central 95% of healthy people. Assuming the tests are independent, what is the probability that at least one result is flagged as abnormal?  
   - A. 5%  
   - B. 34%  
   - C. 26%  
   - D. 46%  
   - E. 12%  
   * **Correct Answer:** **D) 46%**  
   * **Official UB Learns Feedback:** $P(\text{all 12 normal}) = 0.95^{12} \approx 0.54$, so $P(\text{at least one flagged}) \approx 1 - 0.54 = 0.46 \quad (46\%)$. A single mildly abnormal value in a healthy person is often expected; interpret it in clinical context.

6. **Question 6: Non-Parametric Correlation for Skewed Data**  
   Investigators examine the relationship between pain severity on a 0–10 numeric rating scale and daily opioid dose (morphine milligram equivalents) in 120 postoperative patients. Opioid dose is heavily right-skewed with several extreme values. Which measure of association is most appropriate?  
   - A. Spearman rank correlation  
   - B. One-way ANOVA  
   - C. Paired t-test  
   - D. Chi-square test  
   - E. Pearson correlation  
   * **Correct Answer:** **A) Spearman rank correlation**  
   * **Official UB Learns Feedback:** Spearman's $\rho$ uses ranks, so it suits ordinal data, skewed distributions, and outliers. Pearson $r$ assumes two continuous, roughly normal variables and is sensitive to extreme values.

7. **Question 7: Coefficient of Determination ($r^2$)**  
   In 300 adults, waist circumference and CT-measured visceral fat area are correlated: $r = 0.70$ ($p < 0.001$). Which statement is correct?  
   - A. The relationship is weak because $r$ is below 0.80  
   - B. A larger waist circumference causes more visceral fat  
   - C. About 49% of the variation in visceral fat area is explained by its linear relationship with waist circumference  
   - D. 70% of the variation in visceral fat is explained by waist circumference  
   - E. Each 1-cm increase in waist circumference raises visceral fat area by 0.70 cm²  
   * **Correct Answer:** **C) About 49% of the variation in visceral fat area is explained by its linear relationship with waist circumference**  
   * **Official UB Learns Feedback:** $r^2 = 0.70^2 = 0.49$. $r$ is not a slope (E), correlation does not prove causation (B), and $r = 0.70$ is a strong correlation.

8. **Question 8: Predicting Differences from a Regression Slope**  
   In 600 adults with type 2 diabetes, a linear regression of HbA1c (%) on BMI gives a slope of $\beta = 0.08$ per 1 kg/m² (95% CI, 0.05 to 0.11) and an intercept of 4.9. Two patients differ in BMI by 10 kg/m². What is the predicted difference in their mean HbA1c?  
   - A. 8.0 percentage points  
   - B. 4.9 percentage points  
   - C. 0.11 percentage points  
   - D. 0.8 percentage points  
   - E. 0.08 percentage points  
   * **Correct Answer:** **D) 0.8 percentage points**  
   * **Official UB Learns Feedback:** The slope is the change in mean outcome per 1-unit change in the predictor: $10 \times 0.08 = 0.8$ percentage points. The intercept does not enter a difference between two patients.

9. **Question 9: Model Selection for Binary Multivariable Outcome**  
   A hospital wants to identify which factors predict 30-day readmission (yes/no), examining age, number of medications, primary diagnosis, and discharge day of the week at the same time. Which analysis is most appropriate?  
   - A. One-way ANOVA  
   - B. Multiple logistic regression  
   - C. Pearson correlation  
   - D. Multiple linear regression  
   - E. Cox proportional hazards regression  
   * **Correct Answer:** **B) Multiple logistic regression**  
   * **Official UB Learns Feedback:** The outcome is binary and there are several predictors, so multiple logistic regression is appropriate; it reports adjusted odds ratios. Linear regression is for continuous outcomes and Cox regression for time-to-event outcomes.

10. **Question 10: Z-Score Calculation on the Normal Curve**  
    Hemoglobin in healthy adult women is approximately normal, with a mean of 13.5 g/dL and an SD of 1.0 g/dL. A 34-year-old woman has a hemoglobin of 11.0 g/dL. What is her z-score?  
    - A. -11  
    - B. -5.0  
    - C. +2.5  
    - D. -1.0  
    - E. -2.5  
    * **Correct Answer:** **E) -2.5**  
    * **Official UB Learns Feedback:** $z = (\text{value} - \text{mean}) / SD = (11.0 - 13.5) / 1.0 = -2.5$. She is 2.5 SDs below the mean; under 1% of healthy women are this low.

11. **Question 11: Statistical Significance vs. Low Explained Variance ($R^2$)**  
    In a registry of 50,000 adults, a linear regression of SBP on daily step count gives $\beta = -0.4$ mmHg per 1,000 steps (95% CI, $-0.5$ to $-0.3$), $p < 0.001$, $R^2 = 0.02$. Which conclusion is best?  
    - A. Step count is a strong predictor of SBP because $p < 0.001$  
    - B. Each additional 1,000 steps causes a 0.4 mmHg drop in SBP  
    - C. 2% of participants had lower SBP when they walked more  
    - D. The association is not statistically significant because $R^2$ is small  
    - E. The association is statistically significant, but step count explains only about 2% of the variation in SBP, and the effect per 1,000 steps is small  
    * **Correct Answer:** **E) The association is statistically significant, but step count explains only about 2% of the variation in SBP, and the effect per 1,000 steps is small**  
    * **Official UB Learns Feedback:** With $n = 50,000$, even a small, weak association is statistically significant. $R^2 = 0.02$ means step count explains little of the variation in SBP. Observational data do not establish causation.

12. **Question 12: Tail Probabilities Under the Normal Curve**  
    Fasting plasma glucose in healthy adults is approximately normally distributed with a mean of 90 mg/dL and an SD of 8 mg/dL. Approximately what percentage of healthy adults have a fasting glucose above 106 mg/dL?  
    - A. 47.5%  
    - B. 16%  
    - C. 5%  
    - D. 32%  
    - E. 2.5%  
    * **Correct Answer:** **E) 2.5%**  
    * **Official UB Learns Feedback:** 106 mg/dL is the $\text{mean} + 2 \text{ SD}$ ($90 + 2 \times 8 = 106$). About 95% of values lie within $\pm 2$ SD, so 5% lie outside, split equally between the two tails: 2.5% above and 2.5% below.

13. **Question 13: Confounding in Observational Epidemiology**  
    A cross-sectional study of 5,000 adults finds that people who carry a cigarette lighter have a much higher prevalence of lung cancer than people who do not. What is the most likely explanation for this association?  
    - A. Measurement Bias  
    - B. Selection Bias  
    - C. Confounding by Cigarette Smoking  
    - D. Type I Error  
    - E. Reverse Causation  
    * **Correct Answer:** **C) Confounding by Cigarette Smoking**  
    * **Official UB Learns Feedback:** Smoking is associated with both carrying a lighter and lung cancer, and it is not on the causal path between them. A confounder can create a strong correlation with no causal link.

14. **Question 14: Standard Error and Confidence Interval for the Sample Mean**  
    A random sample of 100 patients with hypertension has a mean SBP of 140 mmHg and an SD of 20 mmHg. Which range is the approximate 95% confidence interval for the population mean SBP?  
    - A. 138 to 142 mmHg  
    - B. 120 to 160 mmHg  
    - C. 136 to 144 mmHg  
    - D. 100 to 180 mmHg  
    * **Correct Answer:** **C) 136 to 144 mmHg**  
    * **Official UB Learns Feedback:** $SE = SD / \sqrt{n} = 20 / \sqrt{100} = 20 / 10 = 2.0$. The $95\% \text{ CI} \approx 140 \pm 1.96 \times 2 \approx 136$ to $144$ mmHg. The range 100 to 180 ($\pm 2$ SD) describes where about 95% of individual patients fall, not the precision of the sample mean.

15. **Question 15: Skewed Distributions and Summary Measures**  
    A lipid clinic reports fasting triglycerides for 1,000 adults: mean 185 mg/dL, median 140 mg/dL, mode 120 mg/dL. Which statement best describes the distribution and how to summarize it?  
    - A. Positively skewed; report the median and interquartile range (IQR)  
    - B. Negatively skewed; report the mean and SD  
    - C. Normally distributed; report the mean and SD  
    - D. Positively skewed; report the mode and range  
    - E. Negatively skewed; report the median and IQR  
    * **Correct Answer:** **A) Positively skewed; report the median and interquartile range (IQR)**  
    * **Official UB Learns Feedback:** $\text{Mode} < \text{Median} < \text{Mean}$ ($120 < 140 < 185$) means a long right tail: a few very high values pull the mean up. For skewed data, the median and IQR describe a typical patient better than the mean and SD.
