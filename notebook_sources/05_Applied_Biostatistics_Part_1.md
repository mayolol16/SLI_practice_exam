# Session 5: Applied Biostatistics I – Hypothesis Testing, Errors, Power, Test Selection, and Clinical vs. Statistical Significance

> **Course:** Scientific Literacy & Inquiry (SL&I) – Semester 3  
> **Course Director:** Jennifer A. Campbell, PhD, MPH  
> **Instructor:** Sonia Sharma, PhD (Course Instructor)  
> **USMLE Alignment:** Biostatistics, Epidemiology/Population Health & Medical Literature Interpretation (Hypothesis testing, Type I & II errors, statistical power, test selection, confidence intervals, ARR, RRR, NNT)

---


---

## Curated Video Lectures & Study Design Distinctions
- **Hypothesis Testing & p-values:** *Biostatistics - Hypothesis Testing* — [Watch on YouTube](http://www.youtube.com/watch?v=75pQPB1RF50).
- **Statistical Power & Sample Size:** *Biostatistics - Statistical Power* — [Watch on YouTube](http://www.youtube.com/watch?v=lyMvsbiXT1c).
- **Relative Risk (RR) vs. Odds Ratio (OR) Study Design Rule:**
  - **Relative Risk (RR):** Strictly used in **Cohort Studies** and **Randomized Controlled Trials (RCTs)** where true incidence rates can be tracked over time.
    $$RR = \frac{a / (a + b)}{c / (c + d)}$$
  - **Odds Ratio (OR):** Strictly used in **Case-Control Studies** (where incidence cannot be directly measured) and in multivariable **Logistic Regression**.

## Session 5 Learning Objectives
By the end of this session, you must be able to:
1. **Formulate the Null ($H_0$) and Alternative ($H_a$) hypotheses** in words and symbols for clinical scenarios, and distinguish the exact patient consequences and ethical harms of **Type I ($\alpha$) vs. Type II ($\beta$) errors**.
2. **Define the p-value accurately**, refute common misconceptions, and explain why "absence of evidence is not evidence of absence."
3. **Predict how the Four Levers of Power** (sample size $n$, variability $SD$, significance level $\alpha$, and effect size $\Delta$) alter statistical power ($1 - \beta$) and confidence interval (CI) width.
4. **Select the correct statistical test** based on outcome variable type (continuous vs. categorical) and number/structure of study groups (independent vs. paired; 2 groups vs. $\ge 3$ groups).
5. **Interpret p-values and confidence intervals**, correctly identifying whether a CI crosses the null value (**0 for differences, 1.0 for ratios**).
6. **Distinguish statistical significance from clinical significance** using the **Minimal Clinically Important Difference (MCID)**, and calculate and interpret **Absolute Risk Reduction (ARR)**, **Relative Risk (RR)**, **Relative Risk Reduction (RRR)**, and **Number Needed to Treat (NNT)**.

---

## 1. The Core Clinical Framework: Two Questions for Every Paper

Whenever a clinician reads a newly published clinical trial or lab report, they must ask two separate questions:

```
                                  TWO CRITICAL QUESTIONS
                                             |
                  +--------------------------+--------------------------+
                  |                                                     |
          1. "IS IT REAL?"                                      2. "DOES IT MATTER?"
          (Statistical Inference)                               (Clinical Significance)
          - Could chance explain this result?                   - Will this change patient care?
          - Tools: Hypothesis testing, p-values,                - Tools: Effect size, MCID, ARR,
            confidence intervals, statistical power.              Number Needed to Treat (NNT).
```

### 1.1 Clinical Anchor: The Case of Ms. D
- **Patient Profile:** Ms. D is a 58-year-old woman with hypertension. Her seated blood pressure today is 138/84 mmHg on lisinopril 20 mg and amlodipine 5 mg daily, which she tolerates well without side effects.
- **The Dilemma:** She shows her physician a breaking news headline: *"New once-daily antihypertensive significantly lowers blood pressure in major global trial of 24,000 adults ($p < 0.001$)."*
- **Her Question:** *"Doctor, should I switch to this new pill?"*
- **The Clinical Lesson:** A massive sample size ($n = 24,000$) can make a minuscule, clinically irrelevant blood pressure difference (e.g., 0.8 mmHg) achieve $p < 0.001$. As a physician, you cannot switch her regimen until you evaluate: (1) Is the difference real? and (2) Does the magnitude of reduction achieve the **Minimal Clinically Important Difference (MCID)**?

---

## 2. Hypothesis Testing, Decision Matrix, and Errors

### 2.1 The Null and Alternative Hypotheses
- **Null Hypothesis ($H_0$):** Assumes there is **no true effect, no difference, or no association** between the study groups in the underlying population. Any observed difference in sample data is purely due to random chance or sampling error.
  - For differences in means: $H_0: \mu_1 - \mu_2 = 0$
  - For relative risks / hazard ratios: $H_0: RR = 1.0, \quad HR = 1.0$
- **Alternative Hypothesis ($H_a$):** Assumes that a **true effect, difference, or association exists** in the underlying population.
  - Two-sided alternative: $H_a: \mu_1 - \mu_2 \ne 0$
  - One-sided alternative: $H_a: \mu_1 - \mu_2 > 0$

### 2.2 What a p-value Actually Is (And What It Is NOT)
- **Accurate Definition:** The **p-value** is the probability of obtaining a test statistic at least as extreme as the one observed in the sample data, **assuming that the null hypothesis is true**.
- **Evidence Scale:** A small p-value ($p < 0.05$) provides strong evidence *against* $H_0$, leading us to reject the null hypothesis.

> [!CAUTION]
> **Universal Pitfalls Regarding p-values:**
> 1. A p-value is **NOT** the probability that the null hypothesis is true! (Data cannot tell you the probability of a hypothesis; that requires Bayesian prior probabilities).
> 2. A p-value is **NOT** the probability that the study result occurred "by chance alone."
> 3. $1 - p$ is **NOT** the probability that the drug works or that the alternative hypothesis is true.
> 4. A tiny p-value ($p < 0.0001$) does **NOT** indicate a large or clinically important treatment effect; it only indicates strong evidence that the effect is non-zero.

### 2.3 The 2x2 Decision Matrix: Type I vs. Type II Errors

```
                                      TRUTH IN THE POPULATION
                               H0 is Actually TRUE        H0 is Actually FALSE
                             (Drug does NOT work)           (Drug DOES work)
                         +--------------------------+--------------------------+
    Reject H0            |      TYPE I ERROR        |    CORRECT DECISION      |
    (Declare drug works) |      Probability = alpha |    Statistical Power     |
                         |                          |    Probability = 1 - beta|
DECISION                 +--------------------------+--------------------------+
IN STUDY    Fail to      |    CORRECT DECISION      |      TYPE II ERROR       |
    Reject H0            |   True Negative          |      Probability = beta  |
    (Declare no effect)  |   Probability = 1 - alpha|                          |
                         +--------------------------+--------------------------+
```

### 2.4 Patient Consequences and Ethical Harms of Errors
Medical licensing exams frequently present clinical scenarios asking: *"Who is harmed by this error?"*

| Error Type | Definition | Statistical Parameter | Clinical Scenario & Patient Harm |
| :--- | :--- | :---: | :--- |
| **Type I Error**<br>*(False Positive)* | Rejecting $H_0$ when $H_0$ is actually true. (Declaring a difference when none exists). | **$\alpha$**<br>(Conventionally set at **0.05**) | **Ineffective Drug Approved:** Patients are prescribed an ineffective medication, exposing them to financial costs, false hope, and potentially dangerous side effects for **zero therapeutic benefit**. |
| **Type II Error**<br>*(False Negative)* | Failing to reject $H_0$ when $H_0$ is actually false. (Missing a true clinical difference). | **$\beta$**<br>(Conventionally set at **0.10 to 0.20**) | **Effective Drug Abandoned:** An efficacious, potentially life-saving medication is shelved by the FDA or pharmaceutical sponsor, leaving patients without an effective therapy. |

### 2.5 "Fail to Reject" vs. "Accept the Null"
- **Absence of Evidence is NOT Evidence of Absence:** If a trial comparing an experimental cancer drug against standard care yields $p = 0.08$, you must **never** state: *"The trial proved the drug is ineffective."*
- A p-value of 0.08 simply indicates that the study had **insufficient evidence** to reject the null hypothesis. The trial may have been severely underpowered (too small a sample size) to detect a clinically meaningful difference.

---

## 3. Statistical Power and the Four Levers

### 3.1 What is Statistical Power?
**Statistical Power ($1 - \beta$)** is the probability of correctly rejecting the null hypothesis when a true effect actually exists in the population.
- Conventional target: **Power $\ge 80\%$** (corresponding to $\beta \le 0.20$), though high-stakes oncology trials often aim for **Power = 90%** ($\beta = 0.10$).

### 3.2 The Four Levers That Control Power and Confidence Interval Width
When designing a clinical trial, investigators manipulate four fundamental parameters:

```
                                  THE FOUR LEVERS OF POWER
                                             |
         +-----------------+-----------------+-----------------+-----------------+
         |                 |                 |                 |                 |
   1. Sample Size (n)   2. Effect Size (Δ)   3. Variability (SD)  4. Alpha Level (α)
      n ↑ => Power ↑       Δ ↑ => Power ↑       SD ↓ => Power ↑      α ↑ => Power ↑
      CI Width ↓           CI Width Unchanged   CI Width ↓           CI Width ↓
```

| Lever | Direction of Change | Effect on Power ($1 - \beta$) | Effect on 95% Confidence Interval Width | Mechanism / Formula Link |
| :--- | :---: | :---: | :---: | :--- |
| **1. Sample Size ($n$)** | **Increase ($n \uparrow$)** | **INCREASES** | **Narrows ($\downarrow$)** | Standard Error $SE = SD / \sqrt{n}$. As $n$ grows, $SE$ shrinks, producing tighter CIs and greater precision to detect differences. |
| **2. Target Effect Size ($\Delta$)** | **Larger ($\Delta \uparrow$)** | **INCREASES** | **Unchanged** | Massive clinical differences (e.g., 20 mmHg SBP drop) are far easier to distinguish from background noise than tiny differences (2 mmHg). |
| **3. Sample Variability ($SD$)** | **Decrease ($SD \downarrow$)** | **INCREASES** | **Narrows ($\downarrow$)** | Reducing measurement noise or adopting paired/crossover designs shrinks variance, reducing $SE$. |
| **4. Alpha Threshold ($\alpha$)** | **Increase (e.g., $0.01 \to 0.05$)** | **INCREASES** | **Narrows ($\downarrow$)** | Raising $\alpha$ lowers the evidentiary burden required to reject $H_0$, but directly increases the risk of a false positive (Type I error). |

---

## 4. Statistical Test Selection Guide

A staple of medical licensing exams is matching a clinical trial design to its appropriate statistical test:

```
                            STATISTICAL TEST SELECTION FLOWCHART
                                             |
                         What is the primary outcome variable?
                                             |
                 +---------------------------+---------------------------+
                 |                                                       |
        CONTINUOUS OUTCOME                                      CATEGORICAL OUTCOME
     (e.g., SBP, HbA1c, LDL)                                   (e.g., MI: Yes/No, Cured: Yes/No)
                 |                                                       |
     How many comparison groups?                             How many comparison groups?
                 |                                                       |
        +--------+--------+                                     +--------+--------+
        |                 |                                     |                 |
     2 Groups         ≥ 3 Groups                             2 Groups         ≥ 3 Groups
        |                 |                                     |                 |
  Are they paired?   ONE-WAY ANOVA                         CHI-SQUARE        CHI-SQUARE
        |           (F-statistic)                             TEST              TEST
   +----+----+                                              (Fisher's         (Contingency
   |         |                                               Exact if         Table)
 Independent Paired                                          counts < 5)
   |         |
 TWO-SAMPLE PAIRED
  t-TEST    t-TEST
```

### Detailed Summary Table of Tests

| Outcome Variable Type | Number of Groups / Design | Appropriate Statistical Test | Clinical Trial Example |
| :--- | :--- | :--- | :--- |
| **Continuous** | 2 Independent Groups | **Two-Sample (Independent) t-test** | Comparing mean HbA1c reduction between Metformin vs. Placebo in two separate cohorts. |
| **Continuous** | 2 Paired / Matched Groups | **Paired t-test** | Measuring seated SBP in the *same* 50 patients before and 12 weeks after starting an ACE inhibitor. |
| **Continuous** | $\ge 3$ Independent Groups | **One-Way ANOVA**<br>*(Analysis of Variance)* | Comparing mean serum LDL reductions among 4 different statin doses (10 mg, 20 mg, 40 mg, 80 mg). |
| **Categorical / Binary** | 2 or more Independent Groups | **Chi-Square ($\chi^2$) Test** | Comparing the proportion of patients suffering a 30-day myocardial infarction (Yes vs. No) between Aspirin vs. Control. |
| **Categorical / Binary** | 2 Groups with small counts ($< 5$) | **Fisher's Exact Test** | Comparing mortality in an extremely rare disease trial where one cell has only 2 events. |
| **Time-to-Event** | 2 or more Groups (with Censoring) | **Log-Rank Test** | Comparing Kaplan-Meier event-free survival curves in an oncology clinical trial. |

### The Multiple Comparisons Problem: Why ANOVA is Required
> **Exam Pitfall:** If an investigator has 4 treatment groups, why can't they just run separate two-sample t-tests between all pairs?
- Comparing 4 groups requires $\frac{4 \times 3}{2} = 6$ pairwise t-tests.
- If each individual test is evaluated at $\alpha = 0.05$, the probability of committing **at least one Type I error (false positive)** explodes:
  $$P(\text{At least one false positive}) = 1 - (1 - \alpha)^k = 1 - (0.95)^6 = 1 - 0.735 = \mathbf{0.265 \quad (26.5\%!)}$$
- **Running multiple t-tests massively inflates the family-wise false-positive rate.** One-Way ANOVA tests whether *any* group differs from the others in a single omnibus test, preserving $\alpha = 0.05$.

---

## 5. Interpreting Confidence Intervals Against the Null

### 5.1 Identifying the Correct Null Value
A confidence interval conveys both the precision of an estimate and statistical significance. However, you must identify the correct null value:

| Class of Measure | Metric Examples | True Null Value | Condition for Statistical Significance ($p < 0.05$) |
| :--- | :--- | :---: | :--- |
| **Difference Measures** | Mean Difference, Absolute Risk Reduction (ARR), Risk Difference | **0.0** | **The 95% Confidence Interval must NOT include 0.0** |
| **Ratio Measures** | Relative Risk (RR), Odds Ratio (OR), Hazard Ratio (HR) | **1.0** | **The 95% Confidence Interval must NOT include 1.0** |

### 5.2 Examples
1. *Mean SBP Difference:* $-4.2$ mmHg (95% CI, $-6.8$ to $-1.6$).  
   - Null value = 0.  
   - The CI is entirely below 0 $\implies$ **Statistically significant ($p < 0.05$)**.
2. *Relative Risk for Hip Fracture on PPI:* $RR = 1.25$ (95% CI, 0.96 to 1.62).  
   - Null value = 1.0.  
   - The CI crosses 1.0 $\implies$ **NOT statistically significant ($p \ge 0.05$)**.
3. *Hazard Ratio for Cardiovascular Death:* $HR = 0.78$ (95% CI, 0.65 to 0.94).  
   - Null value = 1.0.  
   - The CI is entirely below 1.0 $\implies$ **Statistically significant ($p < 0.05$)**.

---

## 6. Distinguishing Statistical vs. Clinical Significance

### 6.1 The Minimal Clinically Important Difference (MCID)
- **Definition:** The smallest change or benefit in a clinical outcome that patients or physicians perceive as worthwhile and that would mandate a change in clinical management.
- *Examples:*
  - In hypertension trials, cardiologists generally agree that an SBP reduction of at least **5.0 mmHg** is required to justify adding a second drug (MCID = 5 mmHg).
  - In lipid management, an LDL reduction of at least **10 mg/dL** is clinically meaningful (MCID = 10 mg/dL).

### 6.2 The Four Quadrants of Trial Interpretation

```
                                  95% CONFIDENCE INTERVAL VS. MCID
                                                 
             Case 1: Significant & Meaningful       |      Case 2: Significant but NOT Meaningful
             CI is entirely beyond the MCID         |      CI excludes 0, but falls short of MCID
             [-8.0 --------- -5.5]                  |      [-2.8 --------- -1.2]
             ---------------------|----------|----> |      ----------------|-------------|---->
                                 MCID        0      |                     MCID           0
                                (-5.0)              |                    (-10.0)
             ---------------------------------------+---------------------------------------
             Case 3: Inconclusive                   |      Case 4: Convincingly Negative
             CI spans across both 0 and the MCID    |      CI is tight and excludes both 0 and MCID
             [-6.6 -------------------- +0.4]       |      [-1.1 --------- +0.8]
             ------------|-------------------|----> |      ---|--------------------------|---->
                        MCID                 0      |        MCID                        0
                       (-5.0)                       |       (-5.0)
```

1. **Statistically Significant and Clinically Meaningful:** The point estimate and confidence interval exceed the MCID and exclude 0. (Definitive adoption of therapy).
2. **Statistically Significant but NOT Clinically Meaningful:** Occurs in massive trials (e.g., $n = 30,000$). The CI excludes 0 (so $p < 0.001$), but the entire CI lies below the MCID (e.g., lowering LDL by only 2 mg/dL when MCID is 10 mg/dL). **Do not adopt the treatment.**
3. **Inconclusive (Underpowered):** The CI is wide and spans across both 0 and the MCID (e.g., 95% CI, $-6.6$ to $+0.4$ mmHg, $p = 0.08$). A clinically meaningful benefit cannot be ruled out, nor can no effect. **More research needed.**
4. **Convincingly Negative:** The CI is narrow and excludes the MCID entirely, hugging 0. The drug definitively does not achieve a clinically meaningful benefit.

---

## 7. Measures of Effect: ARR, RR, RRR, and NNT

### 7.1 Core Definitions and Formulas
Suppose a 5-year randomized clinical trial evaluates a new drug to prevent myocardial infarction (MI):
- **Control Event Rate ($CER$):** Risk of event in unexposed/control group ($CER = \text{Events} / \text{Total Control}$).
- **Experimental Event Rate ($EER$):** Risk of event in treatment group ($EER = \text{Events} / \text{Total Treatment}$).

$$\boxed{\text{Absolute Risk Reduction (ARR)} = CER - EER}$$

$$\boxed{\text{Relative Risk (RR)} = \frac{EER}{CER}}$$

$$\boxed{\text{Relative Risk Reduction (RRR)} = \frac{CER - EER}{CER} = 1 - RR = \frac{\text{ARR}}{CER}}$$

$$\boxed{\text{Number Needed to Treat (NNT)} = \frac{1}{\text{ARR}} = \frac{1}{CER - EER}}$$

$$\boxed{\text{Number Needed to Harm (NNH)} = \frac{1}{\text{Absolute Risk Increase (ARI)}} = \frac{1}{EER - CER}}$$

### 7.2 Complete Mathematical Walkthrough
> **Trial Data:**
> - Control Arm: 5-year MI incidence = **4%** ($CER = 0.04$)
> - Treatment Arm: 5-year MI incidence = **3%** ($EER = 0.03$)
> - p-value = 0.01
>
> **1. Calculate Absolute Risk Reduction (ARR):**  
> $$ARR = 0.04 - 0.03 = 0.01 \quad (1.0\%)$$
>
> **2. Calculate Relative Risk (RR):**  
> $$RR = \frac{0.03}{0.04} = 0.75$$
>
> **3. Calculate Relative Risk Reduction (RRR):**  
> $$RRR = \frac{0.01}{0.04} = 0.25 \quad (25\%)$$  
> *(Notice how reporting "a 25% reduction in heart attacks" sounds dramatically more impressive than "a 1% absolute reduction!")*
>
> **4. Calculate Number Needed to Treat (NNT):**  
> $$NNT = \frac{1}{\text{ARR}} = \frac{1}{0.01} = \mathbf{100}$$
>
> **Clinical Translation for Patients:** *"You must treat 100 patients with this medication for 5 years to prevent one myocardial infarction."*
>
> *(Rule: Always round NNT UP to the next whole integer. E.g., if NNT = 23.1, report NNT = 24).*

---

## 8. Session 5 High-Yield Active Learning Q&A & Quiz Bank

### Question 1: Type I vs. Type II Error Identification
**Vignette:** Investigators evaluate a novel oral direct thrombin inhibitor against warfarin for stroke prevention in non-valvular atrial fibrillation. The trial concludes that the novel drug is significantly superior ($p = 0.03$). Over the next 5 years, three independent, larger phase 3 multicenter trials fail to demonstrate any difference between the two drugs. The conclusion of the original trial is best described as:  
- A. Type I error  
- B. Type II error  
- C. Confounding bias  
- D. Insufficient statistical power  
* **Correct Answer:** **A**  
* **Detailed Rationale:** A Type I error occurs when researchers reject the null hypothesis and declare a treatment difference when, in reality, no true difference exists in the population (a false-positive finding).

### Question 2: Levers of Statistical Power
**Vignette:** An academic medical center designs an RCT testing a novel SGLT2 inhibitor, with 12-week change in HbA1c as the primary continuous outcome. Which of the following protocol modifications would successfully increase the statistical power of the trial?  
- A. Decreasing the significance threshold $\alpha$ from 0.05 to 0.01  
- B. Increasing patient enrollment from 200 to 400 subjects  
- C. Broadening inclusion criteria so that baseline HbA1c exhibits wider variance  
- D. Reducing follow-up duration from 12 weeks to 3 weeks  
* **Correct Answer:** **B**  
* **Detailed Rationale:** Power ($1 - \beta$) increases when sample size ($n$) increases, because a larger $n$ shrinks the standard error ($SE = SD / \sqrt{n}$). Lowering $\alpha$ reduces power; increasing variability reduces power.

### Question 3: Accurate Interpretation of a p-value
**Vignette:** A clinical trial reports that an investigational PCSK9 inhibitor reduces LDL cholesterol compared with placebo with a p-value of 0.04. Which of the following statements represents the only correct interpretation?  
- A. There is a 4% probability that the null hypothesis is true  
- B. There is a 96% probability that the drug lowers LDL cholesterol  
- C. If the drug truly had no effect in the population, an LDL difference at least this large would be observed approximately 4% of the time due to random sampling variation  
- D. 4% of patients failed to respond to the drug  
* **Correct Answer:** **C**  
* **Detailed Rationale:** By definition, the p-value is the probability of observing data at least as extreme as the observed sample result assuming the null hypothesis ($H_0$) is strictly true. It is never the probability of the hypothesis itself.

### Question 4: Confidence Interval Crossing the Null
**Vignette:** A prospective cohort study of 4,000 elderly patients investigates whether long-term proton pump inhibitor (PPI) use increases hip fracture risk. The investigators report a Relative Risk of 1.25 (95% CI, 0.96 to 1.62). What is the correct scientific conclusion?  
- A. PPI therapy significantly increases the risk of hip fracture  
- B. The association is not statistically significant at $\alpha = 0.05$ because the 95% CI includes the null value of 1.0  
- C. The study p-value is less than 0.05  
- D. PPI therapy is definitively protective against fractures  
* **Correct Answer:** **B**  
* **Detailed Rationale:** For ratio measures (Relative Risk, Odds Ratio, Hazard Ratio), the null value representing "no association" is 1.0. Because the 95% CI (0.96 to 1.62) spans across 1.0, the finding is not statistically significant ($p \ge 0.05$).

### Question 5: Number Needed to Treat Calculation
**Vignette:** In a 5-year randomized trial of 10,000 patients with ischemic cardiomyopathy, an angiotensin receptor-neprilysin inhibitor (ARNI) reduces the risk of cardiovascular death from 10% in the control arm to 6% in the treatment arm ($p < 0.001$). How many patients must be treated with the ARNI for 5 years to prevent one cardiovascular death?  
- A. 4  
- B. 25  
- C. 40  
- D. 250  
* **Correct Answer:** **B**  
* **Detailed Rationale:**  
  1. $CER = 0.10$, $EER = 0.06$.  
  2. $ARR = CER - EER = 0.10 - 0.06 = 0.04 \quad (4\%)$.  
  3. $NNT = \frac{1}{ARR} = \frac{1}{0.04} = \mathbf{25}$.  
  Treating 25 patients for 5 years prevents 1 cardiovascular death.
