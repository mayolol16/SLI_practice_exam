# Session 4: Survival Analysis II – Kaplan-Meier Curves, Log-Rank Test, Hazard Ratios, and Cox Proportional Hazards

> **Course:** Scientific Literacy & Inquiry (SL&I) – Semester 3  
> **Course Director:** Jennifer A. Campbell, PhD, MPH  
> **Instructor:** Raphael A. Fraser, PhD (Department of Medicine)  
> **USMLE Alignment:** Biostatistics, Epidemiology/Population Health & Medical Literature Interpretation (Kaplan-Meier curve interpretation, hazard ratios vs. absolute risk, Cox proportional hazards regression)

---


---

## Curated Video Lectures & Clinical Templates
- **Kaplan-Meier Curves & Log-Rank Test:** *Survival Analysis Part 2* — [Watch on YouTube](https://www.youtube.com/watch?v=bVcCevk_ab0).
- **Cox Regression & Hazard Ratios:** *Cox Proportional Hazards Regression and HR* — [Watch on YouTube](https://www.youtube.com/watch?v=vtOj8-3bI3M).
- **One-Sentence Hazard Ratio Interpretation Template:**
  > *"An HR of [X] (95% CI, [Y] to [Z]) means that at any given point in time during follow-up, the treatment group had a [(1 - X) * 100]% [lower/higher] risk of experiencing the event compared to the control group, and we are 95% confident the true relative hazard lies between [Y] and [Z]."*

## Session 4 Learning Objectives
By the end of this session, you must be able to:
1. **Analyze and interpret Kaplan-Meier (KM) survival curves**, including the product-limit formula, the meaning of vertical drops, horizontal plateaus, censored tick marks, and the number-at-risk table.
2. **Define and locate Median Survival Time**, and recognize when median survival "does not exist" or has not yet been reached.
3. **Apply and interpret the Log-Rank test**, stating its null hypothesis and evaluating p-values when comparing survival distributions between treatment arms.
4. **Interpret Hazard Ratios (HR) and their 95% Confidence Intervals (CI)** in clinical trials:
   - Calculate percentage hazard reduction: $(1 - HR) \times 100\%$.
   - Evaluate statistical significance against the null value of **1.0**.
   - Explain why an HR is a relative measure and why it **must always be paired with absolute survival rates** to avoid misleading patients.
5. **Describe the Cox Proportional Hazards regression model**, including multivariable adjustment, baseline hazard, and the mandatory **Proportional Hazards Assumption** (recognizing when intersecting KM curves violate this assumption).
6. **Synthesize real-world clinical trial data** using the landmark KEYNOTE-522 trial (Schmid et al., 2024, NEJM) for triple-negative breast cancer (TNBC).

---

## 1. Kaplan-Meier Survival Curves: Visual and Mathematical Anatomy

### 1.1 The Product-Limit Estimator Formula
The **Kaplan-Meier (KM) method** is a non-parametric estimator used to estimate the survivor function, $S(t)$, directly from observed failure times. Because patients are censored at varying time points, the KM method recalculates the conditional probability of survival every time an event occurs:

$$S(t) = \prod_{t_i \le t} \left(1 - \frac{d_i}{n_i}\right)$$

Where:
- $t_i$: An observed time point where at least one event occurred.
- $d_i$: The number of events (failures/deaths) that occurred at time $t_i$.
- $n_i$: The number of subjects **at risk** (alive and under active observation) just prior to time $t_i$.
- $(1 - d_i / n_i)$: The conditional probability of surviving past time $t_i$, given survival up to that instant.
- $\prod$: The cumulative product across all successive event times up to time $t$.

### 1.2 Step-by-Step Numerical Walkthrough
> **Study Cohort:** 10 cancer patients enrolled at $t=0$:
> - At $t = 3$ months: 1 patient dies ($d_1 = 1$, $n_1 = 10$).  
>   $$S(3) = \left(1 - \frac{1}{10}\right) = 0.90 \quad (90\%)$$
> - At $t = 5$ months: 1 patient moves away and is **censored** ($d=0$).  
>   *(No drop in curve! At-risk pool decreases: $n$ becomes $9 - 1 = 8$).*
> - At $t = 8$ months: 2 patients die ($d_2 = 2$, $n_2 = 8$).  
>   $$S(8) = S(3) \times \left(1 - \frac{2}{8}\right) = 0.90 \times 0.75 = 0.675 \quad (67.5\%)$$

```
S(t)
1.0 |========\ (t=3: 1 event, drop to 0.90)
0.9 |         |==============+========\ (t=5: tick mark +, no drop; t=8: 2 events, drop to 0.675)
0.8 |                                  0.7 |                                   |==========================...
    +------------------------------------------------------------------------> Time (months)
    0        3               5          8
At Risk:    10               9          8
```

### 1.3 Detailed Anatomy of a Kaplan-Meier Curve
When reviewing a KM curve in a journal article (e.g., NEJM, JAMA, Lancet) or on an exam, inspect these four features:

```
        Event-Free Survival Probability, S(t)
 1.0 |---------------------------------------------
     |  Treatment Arm  \________
 0.8 |                          \_________+_______
     |                                    \_______
 0.6 |  Placebo Arm    \____                      \_______  <-- Tick marks (+) = Censoring
     |                      \______+______
 0.4 |                                    \_______
     |                                            \_______
 0.2 |                                                    \_______
     +------------------------------------------------------------> Time (months)
     0          12           24           36          48
Number at Risk:
Tx:  784        730          680          620         410
Plc: 390        310          260          210         120
```

1. **Vertical Drops:** Occur **only when an event occurs** ($d_i > 0$). The height of the drop reflects the proportion of the at-risk population that failed ($d_i / n_i$).
2. **Horizontal Plateaus:** Represent periods of elapsed follow-up time during which **no patients experienced an event**.
3. **Tick Marks (Crosses / Slashes):** Represent **censored patients**.
   - *Vital Rule:* **Censored patients NEVER cause a vertical drop in the survival curve.**
   - They simply leave the at-risk denominator ($n_i$).
4. **Number-at-Risk Table (Beneath X-Axis):**
   - Displays the exact count of participants remaining under observation at each time interval.
   - **Exam Pitfall:** If the number at risk drops steeply (e.g., from 620 down to 410) while the KM curve remains completely horizontal and flat, **this indicates heavy administrative censoring (patients reaching the end of the study)**, NOT patient deaths!
5. **Tail Imprecision:** As follow-up extends toward the right, few patients remain at risk. Consequently, a single event can cause an artificially massive vertical drop. Estimates at the tail of the curve have wide confidence intervals and are statistically fragile.

### 1.4 Median Survival Time
- **Definition:** The elapsed time point at which the survivor function drops to **0.50 (50% survival probability)**. Exactly half of the study cohort has experienced the event.
- **How to Find it Graphically:** Draw a horizontal line from $0.50$ on the Y-axis until it intersects the KM curve, then drop a vertical line straight down to the X-axis.
- **When Median Survival "Does Not Exist":** If a treatment is highly effective and more than 50% of the cohort remains alive and event-free at the conclusion of the study, the curve never crosses the 50% line. In study publications, this is officially reported as **"Median survival not reached (NR)."**

---

## 2. Comparing Survival Curves: The Log-Rank Test

### 2.1 Purpose of the Log-Rank Test
To determine whether an observed separation between two or more Kaplan-Meier curves represents a genuine, statistically significant difference rather than random sampling variation.

### 2.2 Hypotheses of the Log-Rank Test
- **Null Hypothesis ($H_0$):** There is no difference in the survival experience between the treatment groups across time. The instantaneous hazard rates are identical at all time points:
  $$H_0: h_1(t) = h_2(t) \quad \text{for all } t$$
- **Alternative Hypothesis ($H_a$):** The hazard rates differ between the treatment groups at one or more time points:
  $$H_a: h_1(t) \ne h_2(t)$$

### 2.3 Statistical Mechanism and Interpretation
- The log-rank test is **non-parametric**: it compares the observed number of events in each group against the expected number of events that would occur if the null hypothesis were true, pooled across all distinct event times.
- **Interpretation:**
  - If the log-rank test yields $p < 0.05$, we reject $H_0$ and conclude that there is a statistically significant difference in survival between the study arms.
  - *Limitation:* The log-rank test gives a p-value indicating whether curves differ, but it **does not quantify the magnitude of the effect or adjust for confounders**. For that, we need Hazard Ratios and Cox regression.

---

## 3. Interpreting Hazard Ratios (HR) and Confidence Intervals

### 3.1 What Does a Hazard Ratio Represent?
A **Hazard Ratio (HR)** compares the instantaneous rate of an event occurring in an intervention group relative to a control group over the study follow-up period:

$$HR = \frac{\text{Hazard in Treatment Group}}{\text{Hazard in Control Group}} = \frac{h_{\text{treatment}}(t)}{h_{\text{control}}(t)}$$

### 3.2 Numerical Direction and Interpretation

| Hazard Ratio Value | Clinical Meaning | Mathematical Translation |
| :---: | :--- | :--- |
| **$HR = 1.0$** | **Null Value** | The event rates are identical in both groups. The treatment has no effect. |
| **$HR < 1.0$** | **Protective Effect** | The event rate is **lower** in the treatment arm.<br>$$\text{Relative Hazard Reduction} = (1 - HR) \times 100\%$$ |
| **$HR > 1.0$** | **Harmful Effect** | The event rate is **higher** in the treatment arm.<br>$$\text{Relative Hazard Increase} = (HR - 1) \times 100\%$$ |

#### Practical Examples
1. **$HR = 0.65$:** Patients in the treatment arm have a **35% lower instantaneous risk** of disease progression or death at any point in time compared to the control arm:
   $$(1 - 0.65) \times 100\% = 35\%$$
2. **$HR = 1.40$:** Patients in the treatment arm have a **40% higher instantaneous rate** of adverse events compared to control:
   $$(1.40 - 1.00) \times 100\% = 40\%$$

### 3.3 Interpreting Confidence Intervals Against the Null
- **The Null Value for a Ratio is 1.0** (unlike differences, where the null is 0.0).
- If the 95% Confidence Interval for an HR **excludes 1.0**, the result is statistically significant at $\alpha = 0.05$ ($p < 0.05$).
- **Sample Interpretations:**
  - $HR = 0.65$ (95% CI, 0.51 to 0.83) $\implies$ Statistically significant reduction in hazard (entire CI is below 1.0).
  - $HR = 0.82$ (95% CI, 0.64 to 1.05) $\implies$ **Not statistically significant** (the CI crosses 1.0; a 36% benefit and a 5% harm are both plausible).
  - $HR = 1.45$ (95% CI, 1.12 to 1.88) $\implies$ Statistically significant increase in hazard (entire CI is above 1.0).

### 3.4 Common Exam Trap: What an HR is NOT!
Examiners frequently test whether you confuse relative hazard ratios with absolute outcomes:

> [!CAUTION]
> **What an HR Does NOT Mean:**
> 1. An $HR = 0.65$ does **NOT** mean 65% of patients survived.
> 2. It does **NOT** mean 35% of patients survived.
> 3. It does **NOT** mean patients lived 35% longer (it does not measure survival time duration).
> 4. It does **NOT** represent the Absolute Risk Reduction (ARR).

### 3.5 The Golden Clinical Rule: Always Pair HR with Absolute Survival Rates
- A hazard ratio is a **relative measure** of instantaneous event rates over time.
- Relative measures can exaggerate clinical importance when baseline event rates are low.
- **Best Practice:** Clinicians must always pair the HR with **Absolute 5-Year Survival Rates** to communicate realistic expectations to patients.

---

## 4. Cox Proportional Hazards Multivariable Regression

### 4.1 Why We Need Cox Regression
The log-rank test and standard KM curves can only evaluate one categorical variable at a time (e.g., Treatment vs. Placebo). In real-world clinical trials and cohort studies:
- Patients differ in age, tumor stage, performance status, and comorbidities.
- **Cox Proportional Hazards Regression** is a semi-parametric multivariable model that assesses the independent effect of a treatment while controlling for multiple confounding variables simultaneously.

### 4.2 The Cox Regression Model Formula
$$h(t \mid X) = h_0(t) \exp(\beta_1 X_1 + \beta_2 X_2 + \dots + \beta_k X_k)$$

Where:
- $h(t \mid X)$: The hazard of failure at time $t$ for a patient with predictor values $X_1, X_2, \dots, X_k$.
- $h_0(t)$: The **baseline hazard function**—the underlying hazard of failure over time when all covariates equal zero ($X = 0$). It is left completely unspecified (semi-parametric).
- $\beta_i$: The regression coefficient for predictor $X_i$.
- $\exp(\beta_i) = e^{\beta_i}$: The **adjusted Hazard Ratio (aHR)** associated with a 1-unit increase in predictor $X_i$, holding all other covariates constant!

### 4.3 The Critical Proportional Hazards Assumption
The fundamental mathematical requirement of Cox regression is the **Proportional Hazards (PH) Assumption**:
> **The Proportional Hazards Assumption:** The ratio of hazards between any two individuals or study groups is **constant over time**.

Mathematically:
$$\frac{h(t \mid \text{Treatment})}{h(t \mid \text{Control})} = \frac{h_0(t) e^{\beta \times 1}}{h_0(t) e^{\beta \times 0}} = e^\beta = \text{Constant (HR)}$$

#### How to Check the Assumption: Kaplan-Meier Curves Must NOT Cross!
- If the proportional hazards assumption holds, the separation between the treatment and control KM curves must remain consistent over follow-up.
- **Crossing Curves Violate the Assumption:** If the Kaplan-Meier curves cross each other, the hazard ratio has flipped (e.g., the treatment was harmful early on due to surgical toxicity, but beneficial years later).
- **Exam Rule:** If KM curves intersect or cross, the proportional hazards assumption is **violated**, and standard Cox regression cannot be validly used without time-varying coefficients.

```
       PROPORTIONAL HAZARDS (VALID)               VIOLATED HAZARDS (INVALID)
  S(t) ^                                     S(t) ^
       |  \_________ Treatment                    |  \______   Treatment
       |            \_________                    |         \______
       |  \______                                 |  \______       \_______
       |         \______ Control                  |         \_______/  <-- CROSSING!
       +-----------------------> t                +-----------------------> t
       (Curves never cross -> HR constant)        (Curves cross -> Hazard flips!)
```

---

## 5. Comprehensive Clinical Anchor: The KEYNOTE-522 Trial

To integrate all concepts, study how these metrics were published in the landmark KEYNOTE-522 trial (Schmid et al., 2024, NEJM):

### Trial Design
- **Patient Population:** 1,174 patients with newly diagnosed, untreated Stage II or III triple-negative breast cancer (TNBC).
- **Randomization (2:1):**
  - **Intervention Arm ($n=784$):** Neoadjuvant Pembrolizumab + Chemotherapy, followed by adjuvant Pembrolizumab.
  - **Control Arm ($n=390$):** Neoadjuvant Placebo + Chemotherapy, followed by adjuvant Placebo.
- **Median Follow-up:** 75.1 months.

### Results & Expert Interpretation

| Endpoint | Reported Hazard Ratio (95% CI) | Log-Rank p-value | Absolute 5-Year Survival Rate | Clinical Translation |
| :--- | :---: | :---: | :---: | :--- |
| **Event-Free Survival (EFS)** | **0.65**<br>(0.51 to 0.83) | **$p < 0.001$** | **81.2%** (Tx)<br>vs.<br>**72.2%** (Placebo) | Patients receiving pembrolizumab had a **35% lower instantaneous risk** of disease progression, recurrence, or death at any point in time. This relative benefit produced an **absolute 9.0 percentage point gain** in 5-year event-free survival. |
| **Overall Survival (OS)** | **0.66**<br>(0.50 to 0.87) | **$p = 0.0015$** | **86.6%** (Tx)<br>vs.<br>**81.7%** (Placebo) | Pembrolizumab reduced the instantaneous hazard of all-cause mortality by **34%**. This translates into an **absolute 4.9 percentage point improvement** in 5-year overall survival, confirming a true survival advantage. |

---

## 6. Session 4 High-Yield Active Learning Q&A & Quiz Bank

### Question 1: Reading Tick Marks on a Kaplan-Meier Curve
**Vignette:** An oncologist reviews a Kaplan-Meier curve comparing adjuvant targeted therapy against placebo in resected lung adenocarcinoma. At Month 24, there are 12 small tick marks along the treatment arm curve, but the curve does not drop vertically. What do these tick marks represent?  
- A. 12 disease recurrence events  
- B. 12 patients who were censored at Month 24 without experiencing an event  
- C. A 12% drop in survival probability  
- D. A violation of the proportional hazards assumption  
* **Correct Answer:** **B**  
* **Detailed Rationale:** Tick marks on a Kaplan-Meier curve represent censored observations (e.g., patients who reached the end of their follow-up or were lost to follow-up). They leave the risk set without causing a vertical drop in the estimated survival curve.

### Question 2: Median Survival Time
**Vignette:** In a phase 3 clinical trial of 500 patients with metastatic renal cell carcinoma, 60% of patients in the experimental immunotherapy arm are alive and progression-free at the planned 4-year study conclusion. What is the median progression-free survival time for the experimental arm?  
- A. 4 years  
- B. 2.4 years  
- C. Not reached (NR)  
- D. 50 months  
* **Correct Answer:** **C**  
* **Detailed Rationale:** Median survival time is the time when survival drops to exactly 50% ($S(t) = 0.50$). If 60% of patients remain alive and progression-free when the study ends, the curve has not yet dropped to 50%, and median survival is formally reported as "not reached."

### Question 3: Interpreting Hazard Ratio and Confidence Intervals
**Vignette:** A randomized trial evaluates a novel SGLT2 inhibitor in patients with chronic heart failure. The reported hazard ratio for cardiovascular death is 0.76 (95% CI, 0.62 to 0.93; $p = 0.008$). Which of the following statements is entirely accurate?  
- A. The treatment group had a 76% reduction in cardiovascular death  
- B. The result is statistically significant because the 95% CI does not include 0  
- C. The treatment group experienced a statistically significant 24% reduction in the instantaneous hazard of cardiovascular death  
- D. 24% of patients in the control group died  
* **Correct Answer:** **C**  
* **Detailed Rationale:** The percentage reduction in hazard is $(1 - HR) \times 100\% = (1 - 0.76) \times 100\% = 24\%$. Because the 95% CI (0.62 to 0.93) excludes the null value of 1.0, the finding is statistically significant ($p < 0.05$). The null value for a ratio is 1.0, not 0.

### Question 4: Proportional Hazards Assumption
**Vignette:** Investigators evaluate a surgical intervention versus medical management for severe peripheral arterial disease. During the first 6 months, the Kaplan-Meier curve for surgery drops sharply below medical therapy due to perioperative graft thrombosis. Between Years 2 and 5, the surgical curve crosses above the medical therapy curve as surgical patients experience superior long-term limb salvage. Which statement regarding Cox regression is correct?  
- A. Cox regression is appropriate because surgery demonstrates long-term superiority  
- B. The proportional hazards assumption is violated because the survival curves cross, making standard Cox regression invalid  
- C. The log-rank test cannot be calculated when curves cross  
- D. The baseline hazard function is constant  
* **Correct Answer:** **B**  
* **Detailed Rationale:** Crossing Kaplan-Meier curves indicate that the hazard ratio changes direction over time (early surgical harm followed by late surgical benefit). This directly violates the proportional hazards assumption that the hazard ratio remains constant over the follow-up duration.

### Question 5: Relative HR vs. Absolute Survival
**Vignette:** A pharmaceutical representative tells a clinic director that their newly approved oncology drug reduces the risk of death by 40% ($HR = 0.60, p = 0.01$) in elderly patients with early-stage prostate cancer. Upon reviewing the full trial data, the physician notes that 5-year overall survival was 98.5% with the drug versus 97.5% with placebo. How should the physician interpret these findings?  
- A. The 40% relative reduction corresponds to a massive clinical breakthrough for all patients  
- B. While statistically significant, the 40% relative hazard reduction translates to only a 1.0 percentage point gain in absolute 5-year survival  
- C. The hazard ratio is invalid because baseline mortality is low  
- D. The number needed to treat is 10  
* **Correct Answer:** **B**  
* **Detailed Rationale:** A hazard ratio is a relative metric. In diseases with low baseline mortality, a large relative hazard reduction (40%) can represent a very small absolute survival benefit (from 97.5% to 98.5%, an absolute gain of only 1 percentage point; $NNT = 1 / 0.01 = 100$). Physicians must look at absolute survival to assess clinical impact.
