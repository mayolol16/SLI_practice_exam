# Session 3: Survival Analysis I – Introduction, Censoring, Survivor & Hazard Functions

> **Course:** Scientific Literacy & Inquiry (SL&I) – Semester 3  
> **Course Director:** Jennifer A. Campbell, PhD, MPH  
> **Instructor:** Raphael A. Fraser, PhD (Department of Medicine)  
> **USMLE Alignment:** Biostatistics, Epidemiology/Population Health & Medical Literature Interpretation (Survival analysis interpretation, time-to-event outcomes, censoring mechanisms)

---


---

## Curated Video Lectures for This Session
- **Introduction to Survival Analysis:** *Survival Analysis Part 1* — [Watch on YouTube](https://www.youtube.com/watch?v=Wo9RNcHM_bs).
- **Types of Censoring:** *Types of Censoring in Survival Analysis* — [Watch on YouTube](https://www.youtube.com/watch?v=L_ziqYhksG8). (Visual breakdown of right, left, interval, and administrative censoring).

## Session 3 Learning Objectives
By the end of this session, you must be able to:
1. **Define survival analysis** and explain its distinct necessity over linear and logistic regression for time-to-event clinical outcomes with variable follow-up durations.
2. **Identify and classify types of censored data**:
   - Right censoring (administrative, loss to follow-up, study termination).
   - Left censoring.
   - Interval censoring.
3. **Distinguish non-informative from informative censoring**, explain the fatal mathematical and clinical biases that arise when the non-informative censoring assumption is violated, and identify how to detect informative censoring in trials.
4. **Define and mathematically interpret the Survivor Function, $S(t) = P(T > t)$**, its core graphical properties, step-down nature, and clinical meaning.
5. **Define and interpret the Hazard Function, $h(t)$**, as an instantaneous failure rate (velocity) rather than a probability, understand its mathematical link to $S(t)$, and identify the **five canonical hazard shapes** along with their clinical medicine correlates:
   - Constant hazard.
   - Increasing hazard.
   - Decreasing hazard.
   - Bathtub-shaped hazard.
   - Unimodal (peaked) hazard.
6. **Code patient trial histories into time-to-event and binary status variables (Event = 1, Censored = 0)** using clinical trial vignettes (such as the KEYNOTE-522 trial).

---

## 1. Rationale and Foundations of Survival Analysis

### 1.1 What is Survival Analysis?
**Survival analysis** is the collection of statistical methods developed to analyze **time-to-event outcomes**:
- **Outcome Variable ($T$):** The elapsed time from a well-defined baseline starting point (e.g., date of trial randomization, surgical resection, or disease diagnosis) until the occurrence of a predefined clinical event.
- **The Event ("Failure"):** A binary outcome signifying an occurrence of interest. In clinical medicine, the event is frequently death (overall survival), disease recurrence/relapse, hospital readmission, myocardial infarction, or organ graft failure.
- **Terminology:**
  - $T$ = Survival time (duration).
  - Event = "Failure" (occurrence of the target endpoint).
  - Standard assumption: Each subject experiences at most one event of interest during the observation window.

### 1.2 Why Standard Statistical Methods Fail for Time-to-Event Data
Medical researchers cannot use ordinary statistical tests (like standard linear regression or logistic regression) to analyze survival data:

| Statistical Method | Why It Fails for Time-to-Event Clinical Data |
| :--- | :--- |
| **Linear Regression**<br>*(Ordinary Least Squares)* | **Cannot handle censored observations.** In any longitudinal trial, many patients remain alive at the conclusion of the study. We do not know their ultimate time of death—only that they survived at least until the end of the study. Excluding living patients introduces immense selection bias; arbitrarily assigning their survival time as the study duration drastically underestimates true survival. |
| **Logistic Regression** | **Ignores the timing of events.** Logistic regression converts the outcome into a binary variable (e.g., Died: Yes vs. No at 5 years). It treats a patient who suffered a fatal stroke on Day 2 of the trial identically to a patient who died of an unrelated event at Year 4.9. Furthermore, it cannot handle patients lost to follow-up at Month 6 whose final status at Year 5 is unknown. |
| **Two-Sample t-test** | Compares means between two groups; fails completely when follow-up times vary across subjects or when events have not yet occurred for everyone. |

### 1.3 Key Concept: Survival Time is Patient-Specific, NOT Calendar Time
- In clinical trials, patient enrollment is staggered over calendar months or years.
- In survival analysis, every patient's timeline is shifted so that **their own date of enrollment/randomization is defined as Time Zero ($t = 0$)**.
- Survival time ($T$) represents the duration of observation from that individual's $t = 0$.

```
Calendar Time:
Patient 1: Enrolled Jan 2021 ---------------------> Recurred July 2022 (T = 18 months)
Patient 2: Enrolled Aug 2021 -----------------------------------------> Alive at Dec 2023 (T = 28 months, Censored)
Patient 3: Enrolled Mar 2023 -------------> Recurred Sept 2023 (T = 6 months)

Analysis Time (All shifted to t = 0):
Patient 1: t=0 =========================> [EVENT at 18 mo]
Patient 2: t=0 ==========================================> [CENSORED at 28 mo]
Patient 3: t=0 ========> [EVENT at 6 mo]
```

---

## 2. Censoring: The Defining Feature of Survival Data

### 2.1 What is Censoring?
**Censoring** occurs when an investigator has **incomplete information about a subject's true survival time**. We know that the individual was event-free up to a certain time point $t$, but we do not know when (or if) the event occurred after that point.
- **Data Coding Convention:**
  - **Survival Time:** $T_i = \text{Time of event or time of last observation (censoring)} - \text{Entry time}$.
  - **Status Indicator:**
    $$\delta_i = \begin{cases} 1 & \text{if the patient experienced the event (Failure)} \\ 0 & \text{if the patient was censored (No event observed)} \end{cases}$$

### 2.2 The Four Types of Censoring

| Censoring Type | Definition | Clinical Trial Vignette Example |
| :--- | :--- | :--- |
| **Right Censoring**<br>*(Overwhelmingly Most Common)* | The patient's follow-up terminates before the event occurs. The true survival time is guaranteed to be **greater than** the observed follow-up time ($T > t$). | A patient enrolled in a 36-month oncology trial completes all 36 months without cancer recurrence. Her status is censored at $t = 36$ months. |
| **Administrative Censoring**<br>*(Subtype of Right Censoring)* | Occurs when the trial reaches its predefined calendar closing date (**data lock**). Patients enrolled late in the study who remain alive are administratively censored with short follow-up times. | Patient E enrolls in Month 20 of a study that locks data at Month 26. At data lock, she is disease-free. She is right-censored at 6 months purely because the trial ended. |
| **Left Censoring** | The event occurred **before** the subject entered the study or before observation began, but the exact calendar date of the event is unknown. ($T < t$). | An epidemiological study of Alzheimer's disease enrolls 70-year-olds. At baseline entry, a participant already exhibits cognitive impairment on testing, but neither the patient nor family knows the exact month or year the impairment began. |
| **Interval Censoring** | The event is known to have occurred **within a specific interval of time** between two scheduled examination visits, but the exact moment is unknown ($t_1 < T < t_2$). | In a clinical trial for asymptomatic diabetic retinopathy, retinal examinations occur at Month 12 and Month 24. At Month 12, the retina is normal; at Month 24, mild retinopathy is diagnosed. The event occurred between Months 12 and 24. |

### 2.3 Reasons for Right Censoring
Right censoring occurs for three universal reasons:
1. **The study ends (Administrative):** The protocol period concludes, and the participant is still alive and event-free.
2. **Loss to follow-up:** The participant stops attending study visits, changes phone numbers, or moves away, leaving their subsequent status unknown.
3. **Withdrawal of consent:** The participant chooses to exit the trial early for personal, non-medical reasons (e.g., job relocation).

### 2.4 Crucial Assumption: Non-Informative vs. Informative Censoring

#### 1. Non-Informative Censoring (The Mandatory Core Assumption)
- **Definition:** Censoring is non-informative if the reason for censoring is **completely unrelated to the patient's underlying risk of experiencing the event**.
- Stated mathematically: A patient who is censored at time $t$ has the exact same future risk of the event as a patient who remains under active follow-up at time $t$.
- *Valid Examples:* A participant moves to another country because their spouse accepted a new job; the study reaches its scheduled end date.

#### 2. Informative Censoring (The Fatal Threat to Validity)
- **Definition:** Informative censoring occurs when the reason a patient leaves the study is **directly correlated with their clinical prognosis or risk of failure**.
- *Clinical Vignette:* In an oncology trial, patients whose tumors are rapidly growing develop severe fatigue, nausea, and pain. Unable to travel to the academic center, they drop out of the trial. If the research team records them as "lost to follow-up / censored at Month 8," this is **informative censoring**.
- **The Catastrophic Bias of Informative Censoring:**
  - Because the sicker, highest-risk patients drop out and are censored, the study cohort that remains under observation appears artificially healthy.
  - **Result: True survival probability is massively overestimated, and drug toxicity is hidden.**
- **How to Investigate for Informative Censoring:**
  1. Meticulously document the explicit clinical reason for every patient dropout.
  2. Compare the baseline clinical characteristics (e.g., tumor stage, ECOG performance status, age) of patients who dropped out vs. those who completed follow-up. If dropouts were significantly sicker at baseline, censoring is informative.

---

## 3. Patient History Coding: The KEYNOTE-522 Clinical Trial Case

To master data coding for exams, examine the real-world structure of the landmark KEYNOTE-522 trial:
- **Trial Profile:** Schmid et al. (2024, NEJM). Phase 3 double-blind RCT; 1,174 patients with early-stage triple-negative breast cancer (TNBC) randomized 2:1 to Pembrolizumab + Chemotherapy ($n=784$) vs. Placebo + Chemotherapy ($n=390$).
- **Primary Endpoint:** Event-Free Survival (EFS) — time from randomization to first occurrence of local/distant recurrence, second primary cancer, death from any cause, or progression precluding surgery.

Consider five representative participants followed until trial data lock at Month 30:

| Participant | Enrollment | Clinical Course & Last Status | Follow-Up Time ($T$) | Event Status ($\delta$) | Classification |
| :--- | :---: | :--- | :---: | :---: | :--- |
| **Patient A** | Month 0 | Recurrence documented at Month 14 | **14 months** | **1 (Event)** | **Observed Failure** |
| **Patient B** | Month 0 | Disease-free at Month 22; alive at data lock (Month 30) | **30 months** | **0 (Censored)** | **Administrative Right Censoring** |
| **Patient C** | Month 3 | Missed clinic visit at Month 11; lost to all outreach | **8 months** (11 − 3) | **0 (Censored)** | **Loss to Follow-up** (Right Censored) |
| **Patient D** | Month 6 | Withdrew consent at Month 9 (relocated to another state) | **3 months** (9 − 6) | **0 (Censored)** | **Voluntary Withdrawal** (Non-informative) |
| **Patient E** | Month 20 | Disease-free at trial data lock (Month 26) | **6 months** (26 − 20) | **0 (Censored)** | **Administrative Right Censoring** |

*Exam Takeaway:* Only Patient A experienced the event ($\delta = 1$). Patients B, C, D, and E are all coded as censored ($\delta = 0$). Each censored patient contributes at-risk person-time up to the exact moment their follow-up ended, after which they are removed from the denominator of at-risk patients.

---

## 4. The Survivor Function, $S(t)$

### 4.1 Mathematical Definition
The **survivor function**, denoted $S(t)$, is the probability that an individual survives beyond a specified time $t$:
$$S(t) = P(T > t)$$
- Cumulative distribution function: $F(t) = P(T \le t)$ represents the probability that the event has occurred by time $t$.
- Therefore:
  $$S(t) = 1 - F(t)$$

### 4.2 Universal Mathematical Properties of $S(t)$
1. **Monotonically Non-Increasing:** As time progresses, $S(t)$ either decreases or remains horizontal; **it can NEVER increase**. Once someone experiences an event or time passes, survival probability cannot climb.
2. **Baseline Value:** At time $t = 0$ (the moment of randomization/study entry), no events have occurred. Therefore:
   $$S(0) = 1.0 \quad (100\%)$$
3. **End of Time:** As time approaches infinity ($t \to \infty$), $S(t) \to 0$, assuming that the event of interest eventually happens to everyone.
4. **Step-Down Function:** In empirical patient samples, $S(t)$ is plotted as a step function. The curve remains flat during periods between events, and drops vertically at the exact time an event occurs.

```
S(t)
1.0 |========    |        0.8 |         |===========    |                     0.6 |                      |==============    |                                     0.4 |                                      |==================...
    +------------------------------------------------------------> Time (t)
    0        t1           t2               t3
```

---

## 5. The Hazard Function, $h(t)$

### 5.1 What is the Hazard Function?
While $S(t)$ answers "What is the cumulative probability of surviving past year 5?", the **hazard function**, $h(t)$, answers:
> *"Given that a patient has survived up to today, what is their instantaneous rate of failing right now?"*

Mathematically:
$$h(t) = \lim_{\Delta t \to 0} \frac{P(t \le T < t + \Delta t \mid T \ge t)}{\Delta t}$$

### 5.2 Vital Distinction: Hazard is a RATE, NOT a Probability!
- **Hazard is an instantaneous failure rate (velocity)**, measured in events per person-unit of time (e.g., deaths per person-year).
- Because it is a rate and not a probability:
  - $h(t) \ge 0$ (it is non-negative).
  - **$h(t)$ HAS NO UPPER BOUND!** A hazard can be 1.5, 5.0, or 100.0. (Probabilities are strictly capped between 0 and 1; rates are not).
- Analogy: The hazard function is the **speedometer** of mortality. A speedometer reading of 80 mph tells you your instantaneous velocity right now; it does not mean you have driven 80 miles.

### 5.3 Mathematical Relationship Between $S(t)$ and $h(t)$
The hazard function represents the negative derivative of the log survivor function:
$$h(t) = -\frac{d \ln S(t)}{dt} = \frac{f(t)}{S(t)}$$
where $f(t)$ is the probability density function of failure times. Conversely, integrating the hazard function over time gives the **cumulative hazard function, $H(t)$**:
$$H(t) = \int_0^t h(u) du$$
$$S(t) = \exp(-H(t)) = e^{-H(t)}$$

---

## 6. The Five Canonical Shapes of Hazard Functions in Clinical Medicine

Examiners love asking you to match a clinical disease scenario to its corresponding hazard function curve:

```
    Constant                 Increasing                 Decreasing
 h(t) ^                   h(t) ^                     h(t) ^
      |                        |      /                   |       |------------            |     /                    |        |                        |    /                     |   \___________
      +------------> t         +-----------> t            +---------------> t

              Bathtub                             Unimodal (Peaked)
       h(t) ^                              h(t) ^
            | \          /                      |      /            |  \________/                       |     /              |                                   |    /    \___________
            +------------------> t              +---------------------> t
```

### 1. Constant Hazard ($h(t) = \lambda$)
- **Characteristics:** The instantaneous risk of failure is identical at every moment in time, regardless of how long the patient has already survived. The past history conveys zero predictive information (memoryless property / exponential distribution).
- **Clinical Medicine Example:**
  - Sudden cardiac death due to malignant ventricular arrhythmias in stable patients with severe ischemic cardiomyopathy.
  - Accidental death in healthy young individuals.
  - Radioactive isotope decay.

### 2. Increasing Hazard ($h(t)$ rises over time)
- **Characteristics:** The risk of failure accelerates as time advances. Indicates aging, cumulative physiological wear-and-tear, or progressive degeneration.
- **Clinical Medicine Example:**
  - Natural all-cause mortality as a function of chronological age.
  - Clinical deterioration in neurodegenerative diseases (e.g., Alzheimer's dementia, Parkinson's disease).
  - Structural mechanical failure of bioprosthetic aortic valves.

### 3. Decreasing Hazard ($h(t)$ falls over time)
- **Characteristics:** The risk of failure is front-loaded—highest immediately following a major event—and progressively declines as the patient recovers, heals, or stabilizes.
- **Clinical Medicine Example:**
  - Perioperative mortality and acute surgical complications in the days and weeks immediately following major cardiac bypass surgery (CABG) or liver resection.
  - Acute mortality following severe traumatic burn injuries.

### 4. Bathtub-Shaped Hazard (High Early $\to$ Low Plateau $\to$ High Late)
- **Characteristics:** High initial acute risk, followed by an extended intermediate period of low, stable hazard, followed by an increasing hazard in the late phase.
- **Clinical Medicine Example:**
  - **Solid Organ Transplantation (e.g., Renal or Cardiac Transplant):**
    - *Early Phase:* High hazard due to acute allograft rejection, surgical complications, and opportunistic infections.
    - *Intermediate Phase:* Low, stable hazard during successful immunosuppressive maintenance.
    - *Late Phase:* Rising hazard due to chronic allograft nephropathy/vasculopathy, progressive graft fibrosis, and long-term toxicities of immunosuppression (malignancy and cardiovascular disease).

### 5. Unimodal / Peaked Hazard (Rises to Peak $\to$ Declines)
- **Characteristics:** Instantaneous risk starts low, climbs rapidly to a distinct peak, and then gradually subsides.
- **Clinical Medicine Example:**
  - **Stroke Recurrence After a Transient Ischemic Attack (TIA):** The risk of recurrent stroke is highest during the first 48 hours to 30 days following an index TIA, after which the hazard declines to a lower chronic baseline rate.
  - Infection recurrence after acute abscess drainage.

---

## 7. The Three Primary Goals of Survival Analysis

Every survival analysis study aims to accomplish one or more of these three objectives:
1. **To estimate survivor and hazard functions from empirical patient data** (e.g., using the Kaplan-Meier product-limit method to determine the median survival time of a cohort).
2. **To compare survivor or hazard functions between two or more intervention groups** (e.g., using the non-parametric **Log-Rank test** to determine if survival curves differ significantly).
3. **To evaluate the multivariable relationship of prognostic explanatory variables (covariates) to survival time** (e.g., using **Cox Proportional Hazards multivariable regression** to adjust for patient age, disease stage, and comorbidities).

---

## 8. Session 3 High-Yield Active Learning Q&A & Quiz Bank

### Question 1: Study Design for Survival Analysis
**Vignette:** An epidemiological research team wants to evaluate clinical outcomes associated with mechanical thrombectomy for acute ischemic stroke. Which study design fundamentally requires survival analysis techniques?  
- A. A cross-sectional survey assessing functional disability scores at hospital discharge  
- B. A case-control study calculating the odds ratio of hypertension in stroke patients  
- C. A prospective cohort study tracking time from symptom onset until recurrent stroke or all-cause mortality over 3 years  
- D. A randomized trial comparing mean systolic blood pressure reductions between two antihypertensives at 6 weeks  
* **Correct Answer:** **C**  
* **Detailed Rationale:** Survival analysis is strictly required when the outcome of interest is **time until an event occurs** in a longitudinal cohort where follow-up lengths vary and subjects may be censored before the event occurs.

### Question 2: Nature of the Hazard Function
**Vignette:** In a phase 2 oncology trial, the estimated hazard of death for an experimental immunotherapy arm at Month 6 is reported as $h(6) = 1.25$ events per person-year. A junior research fellow claims this is impossible because probabilities cannot exceed 1.0. How should the principal investigator explain this result?  
- A. The result is a calculation error because survival probabilities must be between 0 and 1  
- B. The hazard function represents an instantaneous rate (velocity) rather than a probability, and therefore has no mathematical upper bound  
- C. The hazard represents cumulative mortality and must be divided by 100  
- D. The result reflects extreme informative censoring  
* **Correct Answer:** **B**  
* **Detailed Rationale:** The hazard function $h(t)$ is an instantaneous rate (events per unit of person-time), not a cumulative probability. Like speed (which can be 70 mph without requiring someone to travel 70 miles), a hazard rate can exceed 1.0.

### Question 3: Censoring Mechanism
**Vignette:** In a 5-year clinical trial evaluating renal transplantation outcomes, a participant relocates to Europe for employment at Year 2 with a functioning graft and is lost to subsequent follow-up. A second participant completes all 5 years of the study with a functioning graft. How should these two participants be classified?  
- A. Both are right-censored  
- B. Participant 1 is left-censored; Participant 2 is right-censored  
- C. Participant 1 is informatively censored; Participant 2 is interval-censored  
- D. Participant 1 is excluded from analysis; Participant 2 is an event  
* **Correct Answer:** **A**  
* **Detailed Rationale:** Right-censoring occurs whenever follow-up terminates before the event occurs. Participant 1 is right-censored at Year 2 due to loss to follow-up; Participant 2 is right-censored at Year 5 due to study termination (administrative censoring). Neither experienced the event.

### Question 4: Informative Censoring Bias
**Vignette:** A clinical trial evaluates an aggressive chemotherapy regimen for pancreatic adenocarcinoma. Patients who develop severe hepatic failure and intractable pain from disease progression frequently become too weak to attend study visits and drop out. If the trial investigators record these dropouts as standard censored observations, what impact will this have on the study findings?  
- A. It will underestimate the efficacy of the chemotherapy  
- B. It violates the non-informative censoring assumption and will falsely overestimate true patient survival  
- C. It increases the statistical power to detect treatment differences  
- D. It converts the hazard function into a unimodal distribution  
* **Correct Answer:** **B**  
* **Detailed Rationale:** Informative censoring occurs when dropout is linked to poor prognosis. Censoring the sickest patients removes them from the observed cohort, leaving an artificially healthy group that falsely inflates estimated survival probabilities.

### Question 5: Interpreting S(t)
**Vignette:** In a clinical trial of patients with multiple myeloma, the Kaplan-Meier estimated survivor function at $t = 36$ months is $S(36) = 0.65$. Which statement correctly interprets this metric?  
- A. 65% of patients experienced disease recurrence by 36 months  
- B. The instantaneous hazard of recurrence at 36 months is 0.65  
- C. The estimated probability that a patient remains alive and event-free beyond 36 months is 65%  
- D. Patients in the treatment arm survived 65% longer than control patients  
* **Correct Answer:** **C**  
* **Detailed Rationale:** By definition, $S(t) = P(T > t)$. $S(36) = 0.65$ means that an individual has a 65% probability of surviving event-free beyond 36 months.
