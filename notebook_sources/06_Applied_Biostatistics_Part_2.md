# Session 6: Applied Biostatistics II – Data Distributions, Normal Curve, Z-Scores, Correlation, and Multivariable Regression

> **Course:** Scientific Literacy & Inquiry (SL&I) – Semester 3  
> **Course Director:** Jennifer A. Campbell, PhD, MPH  
> **Instructor:** Sonia Sharma, PhD (Course Instructor)  
> **USMLE Alignment:** Biostatistics, Epidemiology/Population Health & Medical Literature Interpretation (Data distributions, skewness, z-scores, SD vs. SE, correlation, linear vs. logistic vs. Cox regression, multivariable confounding adjustment)

---


---

## Curated Video Lectures for This Session
- **Distributions, Skewness, & Normal Curve:** *Biostatistics - Data Distributions* — [Watch on YouTube](http://www.youtube.com/watch?v=7ymCiLPP9os).
- **Correlation & Multivariable Regression:** *Biostatistics - Correlation & Regression* — [Watch on YouTube](http://www.youtube.com/watch?v=NRw8pNn-WmM).

## Session 6 Learning Objectives
By the end of this session, you must be able to:
1. **Classify a distribution's shape** (symmetric/normal, positive/right skew, negative/left skew), relate the relative positions of the **mean, median, and mode**, and select the appropriate summary statistics (**Mean & SD vs. Median & IQR**).
2. **Apply the Normal Curve and 68-95-99.7 Empirical Rule**, calculate and interpret **z-scores**, explain clinical **reference ranges** (central 95%), and calculate the probability of false-positive flags in automated lab panels:
   $$P(\ge 1 \text{ false flag in } k \text{ tests}) = 1 - (0.95)^k$$
3. **Differentiate Standard Deviation (SD) from Standard Error of the Mean (SE)** regarding what each measures, how each behaves as sample size $n$ increases, and why displaying Mean $\pm$ SE can mislead readers.
4. **Interpret the Pearson correlation coefficient ($r$) and coefficient of determination ($r^2$)**, and identify the **four distinct ways correlation misleads** (correlation $\ne$ causation, non-linear/curvilinear relationships where $r \approx 0$, outlier distortion, and restriction of range).
5. **Interpret linear regression output**: regression slope ($\beta$), intercept, $R^2$, and explain why predicting outside the range of data (**extrapolation**) is invalid.
6. **Evaluate multivariable regression and confounding adjustment**, explaining why an adjusted estimate drops compared to an unadjusted estimate, and recognizing residual confounding.
7. **Match the regression model to the clinical outcome type:**
   - Continuous outcome $\implies$ **Linear Regression** (reports $\beta$, null = 0).
   - Binary outcome (yes/no) $\implies$ **Logistic Regression** (reports Odds Ratio [OR], null = 1.0).
   - Time-to-event outcome with censoring $\implies$ **Cox Proportional Hazards Regression** (reports Hazard Ratio [HR], null = 1.0).

---

## 1. Distribution Shapes and Summary Statistics

### 1.1 The Three Fundamental Distribution Shapes
When continuous medical data are graphed on a histogram, their symmetry and tail behavior dictate how they must be summarized:

```
     SYMMETRIC (NORMAL)             POSITIVE (RIGHT) SKEW            NEGATIVE (LEFT) SKEW
           ^                                 ^                                 ^
          / \                               / \                               /          /   \                             /   \                             /           /     \                           /     \                           /            /       \                         /       \                         /             /         \                       /         \------                 /              +-----------+                     +-----------------+               +-----------+
   Mode = Median = Mean               Mode < Median < Mean             Mean < Median < Mode
   (Tail equally balanced)            (Long tail extends RIGHT)        (Long tail extends LEFT)
```

### 1.2 Mathematical Relationship of Mean, Median, and Mode

| Distribution Shape | Visual Direction of Tail | Mathematical Order of Central Tendency | Clinical Examples | Best Summary Measures |
| :--- | :--- | :---: | :--- | :--- |
| **Symmetric**<br>*(Normal Bell Curve)* | Tails are balanced on both sides | $$\mathbf{\text{Mean} = \text{Median} = \text{Mode}}$$ | - Serum sodium in healthy adults<br>- Adult male height<br>- Seated systolic blood pressure in homogeneous cohorts | **Mean and Standard Deviation (SD)** |
| **Positive Skew**<br>*(Right Skew)* | Long tail stretches to the **RIGHT** (toward high positive values) | $$\mathbf{\text{Mode} < \text{Median} < \text{Mean}}$$ | - Hospital length of stay (LOS)<br>- Annual healthcare expenditures ($)<br>- Serum C-reactive protein (CRP)<br>- Serum triglycerides | **Median and Interquartile Range (IQR)**<br>*(IQR $= Q_3 - Q_1$)* |
| **Negative Skew**<br>*(Left Skew)* | Long tail stretches to the **LEFT** (toward low values) | $$\mathbf{\text{Mean} < \text{Median} < \text{Mode}}$$ | - Age at death in industrialized nations (most die in 70s–90s; small number of premature deaths pull mean down) | **Median and Interquartile Range (IQR)** |

### 1.3 Why the Mean is Pulled Toward the Tail
- The **mean is non-robust**: It incorporates the numerical value of every single observation. Extreme values (outliers) in the tail exert a massive leverage effect, pulling the mean in the direction of the tail.
- The **median is resistant / robust**: It depends only on the rank order of observations (the 50th percentile). Extreme values in the tail do not alter the median.
- **Exam Rule:** Whenever medical data are skewed, the **median and IQR** must be reported to describe a "typical" patient, because the mean is distorted by extreme outliers!

---

## 2. The Normal Curve, Z-Scores, Reference Ranges, and Lab Testing

### 2.1 The 68-95-99.7 Empirical Rule
For any continuous variable that follows a normal distribution with mean $\mu$ and standard deviation $\sigma$:
- **68.2%** of all observations lie within **$\mu \pm 1\sigma$** (1 SD of the mean).
- **95.4%** (conventionally **95%**) of observations lie within **$\mu \pm 1.96\sigma$** (approximately **$\pm 2$ SD**).
- **99.7%** of observations lie within **$\mu \pm 3\sigma$** (3 SD of the mean).

```
                            THE NORMAL DISTRIBUTION
                                     |
                                  95.4% (±2 SD)
                            +-----------------------+
                            |     68.2% (±1 SD)     |
                            |   +---------------+   |
                            |   |               |   |
      2.1%      13.6%       |   | 34.1% | 34.1% |   |       13.6%      2.1%
     (0.1%)   +---------+   |   |       |       |   |   +---------+   (0.1%)
   +--------+ |         |   |   |       |       |   |   |         | +--------+
---|--------|-|---------|---|---|-------|-------|---|---|---------|-|--------|--->
  -3σ      -2σ         -1σ             μ               +1σ       +2σ        +3σ
```

### 2.2 Z-Scores: Quantifying Deviation
A **z-score** measures how many standard deviations an individual patient's value ($x$) lies above or below the population mean ($\mu$):

$$\boxed{z = \frac{x - \mu}{\sigma}}$$

#### Clinical Example (TopHat Check A2 Walkthrough)
> **Problem:** Serum sodium in healthy adults is approximately normally distributed with mean $\mu = 140$ mEq/L and standard deviation $\sigma = 2$ mEq/L. A patient's serum sodium is measured at **134 mEq/L**. What is this patient's z-score?  
>
> $$z = \frac{134 - 140}{2} = \frac{-6}{2} = \mathbf{-3.0}$$
>
> **Interpretation:** The patient's sodium is **3.0 standard deviations below the mean**. In a normal distribution, values $\le -3$ SD occur in less than **0.15%** of healthy individuals. This represents severe, clinically significant hyponatremia requiring immediate medical evaluation.

### 2.3 Clinical Reference Ranges: The Inherent 5% Flag Rate
- In clinical pathology laboratories, the **reference range ("normal range")** for any blood test is formally defined as the **central 95% of healthy individuals** (spanning from $\mu - 2\sigma$ to $\mu + 2\sigma$).
- **Mathematical Inevitability:**
  - By deliberate definition, **5% of completely healthy people fall OUTSIDE the reference range!**
  - **2.5%** of healthy people fall below the lower reference limit.
  - **2.5%** of healthy people fall above the upper reference limit.

### 2.4 The Multiple Testing Problem in Lab Panels (Ms. D's Case)
When an automated comprehensive metabolic panel (CMP) or lab battery tests $k$ separate analytes simultaneously, each with a 5% chance of falling outside the reference range by chance alone ($\alpha = 0.05$):

$$\boxed{P(\ge 1 \text{ false flag in } k \text{ independent tests}) = 1 - (1 - \alpha)^k = 1 - (0.95)^k}$$

#### The Clinical Dilemma of Ms. D
- Ms. D's routine annual panel ran **20 automated blood tests**.
- All 19 tests were completely normal, except her alanine aminotransferase (ALT) returned at **44 U/L** (reference range: 7–40 U/L), flagged with an **"H" (High)**.
- *What was the probability that a completely healthy person would have at least one test flagged in a 20-test panel?*
  $$P(\ge 1 \text{ flag}) = 1 - (0.95)^{20} = 1 - 0.3585 = \mathbf{0.6415 \quad (64.2\%!)}$$
- **Clinical Action:** In an asymptomatic patient, there is a **64% probability of at least one abnormal flag purely due to random biological fluctuation**.
- **Physician Advice:** Do *not* order an immediate $3,000 abdominal CT or liver biopsy! Evaluate the patient in clinical context (alcohol intake, medications), and simply repeat the test in 4 to 8 weeks to determine if a true clinical trend exists.

---

## 3. Standard Deviation (SD) vs. Standard Error of the Mean (SE)

A classic USMLE and SL&I exam concept is differentiating what SD and SE measure and how they behave as sample size ($n$) increases:

| Dimension | Standard Deviation (SD) | Standard Error of the Mean (SE) |
| :--- | :--- | :--- |
| **What does it measure?** | **The dispersion / variability of INDIVIDUAL patient measurements** around the sample mean. | **The precision of the ESTIMATED SAMPLE MEAN** as an estimate of the true population mean. |
| **Formula** | $$SD = \sqrt{\frac{\sum (x_i - \bar{x})^2}{n - 1}}$$ | $$SE = \frac{SD}{\sqrt{n}}$$ |
| **Behavior as $n$ Increases** | **Does NOT shrink toward zero.** As $n$ grows, SD stabilizes around the true population standard deviation ($\sigma$). | **SHRINKS TOWARD ZERO.** As $n \to \infty$, $SE \to 0$. |
| **Clinical Interpretation** | About **95% of individual patients** in the study have values falling within:  
$$\mathbf{\text{Mean} \pm 2 \times SD}$$ | We are **95% confident that the true population mean** lies within the confidence interval:  
$$\mathbf{\text{Mean} \pm 1.96 \times SE}$$ |

### The "Tidy Error Bar" Deception in Medical Literature
- Authors sometimes present graphs showing error bars as $\text{Mean} \pm \text{SE}$ rather than $\text{Mean} \pm \text{SD}$.
- Because $SE = SD / \sqrt{n}$, dividing by $\sqrt{400} = 20$ makes the error bar **20 times smaller**!
- This gives the false visual impression that individual patients had remarkably uniform responses, when in reality individual patient variability (SD) was massive.

---

## 4. Correlation: Measuring Linear Associations

### 4.1 Pearson ($r$) vs. Spearman ($\rho$) Correlation
- **Pearson Product-Moment Correlation ($r$):** Parametric statistic measuring the strength and direction of a **linear relationship** between two continuous, roughly normally distributed variables.
  - Scale: Ranges strictly from **$-1.0$ to $+1.0$**.
  - Sign: Indicates direction ($+$ means both variables rise together; $-$ means as one rises, the other falls).
  - Magnitude: Indicates how tightly data points cluster around a straight line ($|r| = 1.0$ is a perfect straight line; $r = 0.0$ indicates no linear association).
- **Spearman Rank Correlation ($\rho$):** Non-parametric equivalent based on the rank order of data. Used when:
  1. Data are ordinal (e.g., pain scale 1 to 10).
  2. Data are severely skewed.
  3. The relationship is non-linear but monotonic.
  4. Extreme outliers are present.

### 4.2 Coefficient of Determination ($r^2$ or $R^2$)
- Defined as the square of the correlation coefficient.
- **Meaning:** Represents the **proportion of total variance in the dependent variable that is explained by its linear relationship with the predictor**.
- *Example:* If the correlation between physical exercise and HbA1c is $r = -0.30$:
  $$r^2 = (-0.30)^2 = 0.09 \quad (9\%)$$
  Only **9% of the variance** in HbA1c is explained by exercise; the remaining 91% is driven by genetics, diet, medications, and age.

### 4.3 The Four Distinct Ways Correlation ($r$) Misleads (High-Yield!)

```
                   FOUR WAYS CORRELATION COEFFICIENTS MISLEAD
                                       |
     +-----------------+---------------+---------------+-----------------+
     |                 |                               |                 |
1. Correlation ≠    2. r ≈ 0 Does NOT Mean         3. Outlier         4. Restriction
   Causation           "No Relationship"              Distortion         of Range
   (Confounding)       (Non-linear / Curvilinear)     (False r)          (Deflated r)
```

1. **Correlation is NOT Causation:** Confounding variables or reverse causality frequently generate high correlations.  
   *Classic Medical Example:* In early epidemiological studies, coffee consumption correlated positively with pancreatic cancer ($r = +0.35$). However, individuals who drank heavy amounts of coffee were also far more likely to smoke cigarettes. After adjusting for tobacco smoking, the correlation between coffee and cancer vanished!
2. **$r \approx 0$ Does NOT Mean "No Relationship":** Pearson $r$ tests **strictly for linear (straight-line) relationships**.  
   *Classic Medical Example:* The relationship between Body Mass Index (BMI) and all-cause mortality is **J-shaped / U-shaped**: mortality is elevated in severely underweight individuals, lowest in normal-weight individuals (BMI 22–25), and elevated in severe obesity. A straight line fitted through a U-shaped curve yields **$r \approx 0.0$**, despite a profound biological relationship!
3. **Outliers Severely Distort $r$:** A single extreme outlier far in the corner of a scatter plot can create a strong artificial correlation ($r = 0.80$) in a dataset where no association exists, or can destroy a true correlation.
4. **Restriction of Range:** If an investigator samples only a narrow, restricted slice of the predictor variable (e.g., assessing the correlation between MCAT scores and medical school licensing exam performance only among admitted Harvard medical students), the measured correlation will appear artificially weak.

---

## 5. Linear Regression: Quantifying the Relationship

### 5.1 Simple Linear Regression Equation
$$\hat{Y} = \beta_0 + \beta_1 X$$

Where:
- $\hat{Y}$: The predicted mean value of the continuous dependent variable.
- $\beta_0$: The **Y-intercept** (the predicted value of $Y$ when $X = 0$).
- $\beta_1$: The **Regression Slope**—the expected change in the mean of $Y$ for every **1-unit increase** in predictor $X$.

### 5.2 Hypothesis Testing for the Regression Slope
- **Null Hypothesis:** $H_0: \beta_1 = 0$ (The slope is zero; $X$ does not predict $Y$).
- **Null Value:** **0.0**.
- If the 95% Confidence Interval for $\beta_1$ excludes 0.0, the slope is statistically significant ($p < 0.05$).

### 5.3 The Danger of Extrapolation Outside the Data
- Regression equations are empirically valid **only within the observed range of predictor values** in the study sample.
- **Extrapolation:** Using a regression equation to predict outcomes for predictor values far outside the observed study range. Extrapolation is clinically and scientifically invalid because physiological relationships become non-linear at extreme ranges.

---

## 6. Multivariable Regression and Confounding Adjustment

### 6.1 Unadjusted (Crude) vs. Adjusted Estimates
- **Unadjusted (Crude) Slope:** Measures the raw association between predictor $X$ and outcome $Y$. It mixes the true effect of $X$ with the effects of all other confounding variables that travel alongside $X$.
- **Adjusted Slope:** The estimated change in outcome $Y$ per 1-unit increase in $X$, **holding all other included covariates constant** ("controlling for" age, BMI, renal function).

### 6.2 The SALT-Check Study: Deconstructing Confounding
In a cross-sectional study of 2,400 hypertensive adults investigating dietary sodium (measured by 24-hour urinary sodium) and systolic blood pressure (SBP):

| Predictor | Model 1: Unadjusted $\beta$ (95% CI) | Model 2: Adjusted $\beta$ (95% CI) |
| :--- | :---: | :---: |
| **Sodium (per 1 g/day)** | **4.2** (3.5 to 4.9) | **2.1** (1.4 to 2.8) |
| **Age (per 10 years)** | — | **4.8** (3.9 to 5.7) |
| **BMI (per 5 kg/m²)** | — | **2.6** (1.7 to 3.5) |
| **eGFR < 60 mL/min (Yes vs. No)** | — | **3.4** (1.2 to 5.6) |
| **Physical Activity (per 60 min/wk)** | — | **$-0.3$** ($-0.9$ to $0.3$) |
| **Model $R^2$** | **0.06** (6%) | **0.22** (22%) |

#### Key Analytical Lessons
1. **Why did the sodium coefficient drop from 4.2 to 2.1?**  
   - Older patients and patients with higher BMIs consumed more sodium and also had stiffer arteries and poorer renal function.
   - Age, BMI, and impaired renal function were **confounding the crude association**. Half of the raw SBP difference was driven by age and weight, not sodium itself!
2. **Interpreting the Adjusted Sodium Coefficient:**  
   - *"Holding age, BMI, kidney function, and physical activity constant, each additional 1 g/day of dietary sodium is independently associated with an average 2.1 mmHg higher systolic blood pressure."*
3. **Interpreting Physical Activity:**  
   - The 95% CI ($-0.9$ to $+0.3$) spans across 0.0 ($p > 0.05$). Physical activity was **not a statistically significant independent predictor** of SBP in this adjusted model.
4. **Statistical Significance vs. Low $R^2$:**  
   - In Model 1, sodium has $p < 0.001$, yet $R^2 = 0.06$.  
   - *How can both be true?* In a large sample ($n=2,400$), we can be extremely certain that the slope is not zero ($p < 0.001$), even though sodium explains only 6% of the overall variation in blood pressure!
5. **Residual Confounding:** Observational multivariable regression can only adjust for variables that were explicitly measured. It **cannot rule out unmeasured residual confounding** (e.g., genetic variations, socioeconomic status, stress).

---

## 7. Model Matching Matrix: Selecting the Right Regression Model

Medical licensing exams regularly present a research scenario and ask you to select the correct regression architecture:

| Clinical Outcome Variable | Outcome Type | Appropriate Regression Model | Parameter Reported | Null Value | Clinical Example |
| :--- | :--- | :--- | :---: | :---: | :--- |
| **Continuous**<br>*(Quantitative measurement)* | Interval or ratio scale | **Linear Regression** | **Slope ($\beta$)** | **0.0** | Predicting seated SBP, HbA1c reduction, or serum LDL cholesterol. |
| **Binary**<br>*(Dichotomous: Yes / No)* | Categorical (0 or 1) | **Logistic Regression** | **Adjusted Odds Ratio (aOR)** | **1.0** | Predicting 30-day hospital readmission, mortality (alive vs. dead), or uncontrolled BP ($\ge 140/90$). |
| **Time-to-Event**<br>*(With Censoring)* | Survival duration until failure | **Cox Proportional Hazards Regression** | **Adjusted Hazard Ratio (aHR)** | **1.0** | Predicting time to cancer recurrence, time to stroke, or time to all-cause death. |

---

## 8. Clinical Case Conclusion: Answering Ms. D's Questions

### Question 1: *"My labs flagged something... ALT 44 (reference 7–40). Is something wrong with my liver?"*
- **Physician Answer:** *"Ms. D, your annual panel checked 20 individual tests. When we run 20 tests at once, a healthy person has about a 64% chance of having at least one test flag slightly outside the normal range purely by biological chance. Your ALT is only slightly above the reference boundary. We will repeat the test in 6 weeks and monitor the trend. There is no cause for alarm."*

### Question 2: *"How much would cutting salt help? I eat 5 g of sodium a day. If I cut it in half, how much will my BP drop?"*
- **Physician Answer:** *"Ms. D, you currently consume 5 g/day. Halving your intake means reducing it by 2.5 g/day. Based on our adjusted regression model ($\beta = 2.1$ mmHg per 1 g/day):*
  $$\text{Predicted SBP Drop} = 2.5 \text{ g/day} \times 2.1 \text{ mmHg/g} = \mathbf{5.25 \text{ mmHg}}$$
  *Because 5.25 mmHg meets the Minimal Clinically Important Difference (MCID) of 5 mmHg, halving your sodium intake is a clinically meaningful lifestyle modification that could allow you to avoid needing a third blood pressure medication."*

---

## 9. Session 6 High-Yield Active Learning Q&A & Quiz Bank

### Question 1: Skewed Distributions
**Vignette:** In a study of 500 patients hospitalized with community-acquired pneumonia, the hospital length of stay (LOS) has a mean of 6.8 days, a median of 4.0 days, and a mode of 3.0 days. Which of the following statements is correct?  
- A. The distribution is negatively skewed; a few short stays pull the mean down  
- B. The distribution is positively skewed; a few prolonged stays pull the mean upward, so the median and IQR best describe a typical patient's stay  
- C. The mean and standard deviation should be reported because $n = 500$ is large  
- D. Length of stay follows a normal distribution  
* **Correct Answer:** **B**  
* **Detailed Rationale:** When $\text{Mode} < \text{Median} < \text{Mean}$ ($3 < 4 < 6.8$), the distribution is positively (right) skewed. A small number of patients with complicated hospital stays (e.g., 30+ days in the ICU) pull the mean far to the right. For skewed data, the median and IQR provide the most accurate representation of a typical patient.

### Question 2: Pearson Correlation and Explained Variance
**Vignette:** In a cohort of 1,200 adults with prediabetes, the correlation between weekly physical activity (hours) and fasting plasma glucose (mg/dL) is $r = -0.40$ ($p < 0.001$). What proportion of the variation in fasting plasma glucose is explained by physical activity?  
- A. 40%  
- B. 20%  
- C. 16%  
- D. 4%  
* **Correct Answer:** **C**  
* **Detailed Rationale:** The proportion of variance explained is given by the coefficient of determination, $r^2$.  
$$r^2 = (-0.40)^2 = 0.16 \quad (16\%)$$  
16% of the variance in glucose is explained by physical activity; 84% is driven by other factors.

### Question 3: Curvilinear Associations
**Vignette:** An epidemiologist evaluates the association between serum 25-hydroxyvitamin D levels and all-cause mortality. Very low vitamin D levels are associated with high mortality, intermediate levels with low mortality, and excessively high toxic levels with increased hypercalcemic mortality. The Pearson correlation coefficient is calculated as $r = 0.02$ ($p = 0.65$). How should this be interpreted?  
- A. Vitamin D levels have no biological relationship with mortality  
- B. Pearson correlation evaluates strictly linear associations and fails to detect the true U-shaped non-linear relationship  
- C. The study suffered from informative censoring  
- D. A logistic regression would yield an odds ratio of 0  
* **Correct Answer:** **B**  
* **Detailed Rationale:** Pearson correlation measures only linear associations. A U-shaped or J-shaped relationship can produce $r \approx 0.0$ because the downward slope on the left cancels out the upward slope on the right.

### Question 4: Confounding in Multivariable Regression
**Vignette:** A study reports that unadjusted linear regression shows each additional 12-oz can of sugar-sweetened soda per day is associated with an SBP increase of 3.8 mmHg ($p < 0.001$). When the model is adjusted for patient body weight, total daily caloric intake, and age, the regression coefficient drops to 1.1 mmHg ($p = 0.12$). What is the best scientific explanation for this change?  
- A. The initial study was a Type II error  
- B. Body weight and caloric intake confounded the crude relationship between soda and blood pressure  
- C. Linear regression cannot be used when coefficients change  
- D. Adjusting for covariates always eliminates statistical power  
* **Correct Answer:** **B**  
* **Detailed Rationale:** When an adjusted regression coefficient drops substantially compared to the unadjusted coefficient, it proves that the newly added variables were confounding the crude association. Soda drinkers tended to have higher body weight and higher caloric intake, which were responsible for most of the observed blood pressure elevation.

### Question 5: Logistic Regression Odds Ratio Interpretation
**Vignette:** In the SALT-Check study, multivariable logistic regression evaluates the odds of uncontrolled hypertension (SBP $\ge 140$ or DBP $\ge 90$ mmHg). High sodium intake (>4 g/day vs. $\le 4$ g/day) has an adjusted Odds Ratio ($aOR$) of 1.35 (95% CI, 1.12 to 1.63). Coffee consumption ($\ge 3$ cups/day vs. $<3$ cups/day) has an $aOR$ of 0.92 (95% CI, 0.74 to 1.14). Which statement is correct?  
- A. High sodium intake causes a 35% increase in blood pressure  
- B. High sodium intake is independently associated with 35% higher odds of uncontrolled hypertension; the coffee estimate is not statistically significant  
- C. Both associations are statistically significant  
- D. Coffee consumption significantly lowers the odds of uncontrolled hypertension by 8%  
* **Correct Answer:** **B**  
* **Detailed Rationale:** For sodium, $aOR = 1.35$ with a 95% CI (1.12 to 1.63) excluding 1.0, indicating a statistically significant 35% increase in odds of uncontrolled BP. For coffee, the 95% CI (0.74 to 1.14) spans across 1.0, meaning the association is not statistically significant ($p \ge 0.05$).
