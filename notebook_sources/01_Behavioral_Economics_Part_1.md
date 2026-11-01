# Session 1: Healthcare Economics & Financing I – Risk, Moral Hazard, and Adverse Selection

> **Course:** Scientific Literacy & Inquiry (SL&I) – Semester 3  
> **Course Director:** Jennifer A. Campbell, PhD, MPH  
> **Instructor:** Obinna Ekwunife, PhD (Division of Population Health, Department of Medicine)  
> **USMLE Alignment:** Systems-Based Practice (Cost awareness, risk-benefit analysis in patient care, healthcare policy, and economics)

---


---

## Curated Video Lectures for This Session
- **Calculating Patient Responsibility:** *How to Calculate Patient and Payer Responsibility (Copay vs Coinsurance vs Deductible)* by Ask The Biller® — [Watch on YouTube](http://www.youtube.com/watch?v=SdYPzcQPWOw). (Walks through deductibles, coinsurance percentages, and hitting out-of-pocket maximums).
- **Adverse Selection & Moral Hazard Mechanics:** *Health Econ. - Moral Hazard and Adverse Selection* by Joseph Shinn — [Watch on YouTube](http://www.youtube.com/watch?v=LdOx3Abd13g). (Maps out a multi-round adverse selection death spiral mathematically starting at 0:37, and explains demand curve shifts under moral hazard).

## Session 1 Learning Objectives
By the end of this session, you must be able to:
1. **Explain the need for healthcare insurance** using the statistical properties of medical spending (uncertainty, variability, and right-skewness), and describe the primary financial purpose of insurance (risk pooling and consumption smoothing).
2. **Explain moral hazard** (ex-ante vs. ex-post), identify patient-side cost-sharing mechanisms (deductibles, copayments, coinsurance, out-of-pocket maximums), distinguish behavioral responses (own-price, cross-price, and offset effects), cite empirical evidence (Tamblyn et al., 2001), and analyze supply-side controls (gatekeeping, managed care, capacity control).
3. **Evaluate adverse selection and risk selection** (adverse selection vs. favorable selection/cream-skimming), demonstrate how information asymmetry and community rating trigger the insurance "death spiral" using a Willingness-to-Pay (WTP) table, explain primary vs. secondary risk, and evaluate regulatory solutions (guaranteed issue, individual mandate, ACA 3 Rs, risk adjustment, reinsurance, risk corridors) and insurer counter-tactics (adverse tiering, Jacobs & Sommers, 2015).
4. **Articulate the two fundamental tradeoffs of health insurance:**
   - *Tradeoff 1:* Financial Protection vs. Moral Hazard.
   - *Tradeoff 2:* Market Competition vs. Adverse Selection.

---

## 1. The Fundamental Need for Health Care Insurance

### 1.1 The Unique Nature of Healthcare Expenditures
In most economic markets (e.g., buying groceries, electronics, clothing), consumer expenditures are predictable and discretionary. Healthcare is fundamentally different due to three distinct statistical characteristics:
1. **Uncertainty:** Illness and acute trauma strike randomly. An individual cannot predict whether, when, or what type of illness will afflict them in a given year.
2. **Extreme Variability:** Healthcare costs range from minor ($20 for a brief consultation) to catastrophic (>$200,000 for a severe burn, coronary bypass, premature infant intensive care, or cancer immunotherapy).
3. **Right-Skewed Distribution (Skewness > 0):**
   - If you plot the distribution of healthcare expenditures across the population, it does **not** follow a normal bell curve.
   - It is severely **right-skewed**: The vast majority of people spend very little or nothing in a given calendar year (the tall peak near zero on the left), while a tiny minority (approximately 5% of individuals) accounts for over 50% of all national healthcare spending (the long, heavy tail extending far to the right).

```
   Relative
   Frequency
       ^
       |  *
       |  **
       |  ***
       |  ****
       |  *****
       |  ******
       |  *******   <-- Most people: $0 to $1,000/year
       |  ********
       |  *********
       |  *******************-------------------> Long Right Tail (Top 5% incur bills > $100k)
       +---------------------------------------------> Healthcare Expenditure ($)
          Mode  Median     Mean (Mean is pulled far to the right!)
```

### 1.2 Why Saving and Borrowing Fail as Solutions
Because health spending is right-skewed and unpredictable:
- **Personal Savings Fail:** You cannot budget or save for an unpredictable $150,000 intensive care stay out of regular wages. The target is too large and the timing is completely unknown.
- **Borrowing / Credit Fails:** In the event of catastrophic illness or disability, an individual’s earning potential collapses. Commercial lenders will not loan hundreds of thousands of dollars to an incapacitated patient with no guaranteed repayment capacity.
- **The Only Viable Solution is Insurance:** Pooling financial resources across a large group of people to protect against ruinous losses.

### 1.3 What Insurance Actually Does (And Does Not Do)
- **What it DOES:**
  - **Spreads financial risk** across both healthy and sick individuals.
  - **Transfers money:** From the healthy to the sick, and across time for a single individual (paying premiums during healthy years to draw benefits when sick).
  - **Achieves "Consumption Smoothing":** It reduces the variance of disposable income across time. Instead of having $50,000 of income in Year 1 and negative $80,000 in Year 2 due to a hospital bill, the individual pays a steady, predictable premium each year, leaving their living standard ("consumption") stable and unperturbed by medical catastrophe.
- **What it DOES NOT Do:**
  - Insurance **does not ensure a return to health**. Having an insurance card does not magically eradicate cellular damage or cure chronic illness.
  - Therefore, health insurance should more accurately be conceptualized as **"Healthcare Cost Insurance."** Its primary purpose is purely financial.

### 1.4 Terminology of Premiums and Willingness to Pay (WTP)
To master health economics questions, you must distinguish between four distinct components:
1. **Expected Healthcare Cost ($E[C]$):** The probability of illness multiplied by the cost of treatment ($\sum p_i 	imes 	ext{Cost}_i$). In insurance economics, this is called the **Actuarially Fair Premium (AFP)**. If an insurer only charged the AFP, their expected profit would be zero, covering only pure medical claims.
2. **Loading Cost:** The markup added by insurance companies to cover administrative expenses, claims processing, underwriting, marketing, IT infrastructure, provider contracting, regulatory compliance, executive compensation, and profit margins.
   $$\text{Actual Premium Charged} = \text{Actuarially Fair Premium (Expected Claims)} + \text{Loading Cost}$$
3. **Risk Premium:** The extra dollar amount *above* expected healthcare costs that a risk-averse person is willing to pay simply to eliminate uncertainty and sleep peacefully at night.
4. **Willingness to Pay (WTP):** The maximum total dollar amount an individual is willing to pay for an insurance policy:
   $$\text{WTP} = \text{Expected Healthcare Cost} + \text{Risk Premium}$$
   *Decision Rule:* A consumer will purchase insurance if and only if:
   $$\text{Premium} \le \text{WTP}$$

### 1.5 Primary vs. Secondary Risk and Risk Pool Size
- **Primary Risk:** The individual consumer's risk of suffering an unexpected, costly health event.
- **Secondary Risk:** The insurer's financial risk that actual average claims in the risk pool will deviate from their estimated expected claims (the risk of being wrong about the forecast).
- **The Law of Large Numbers:**
  - As the number of enrollees ($N$) in a risk pool expands, the variance of the average claim declines rapidly:
    $$\text{Standard Error of the Mean Claim} = \frac{\sigma}{\sqrt{N}}$$
  - **Larger risk pool $\implies$ Dramatically lower secondary risk.** The insurer faces far fewer surprises, enabling stable, predictable pricing.
  - **Loading Costs Decline with Group Size:** Administrative overhead is largely fixed. Spreading fixed costs over 5,000 employees yields a loading fee of only ~6.5% of benefits, compared to a crushing 70% loading fee for a single individual buying a non-group policy!

---

## 2. Moral Hazard and Cost Sharing

### 2.1 What is Moral Hazard?
**Moral hazard** refers to behavioral distortions that occur when individuals do not bear the full financial consequences of their actions. In healthcare:
> *Healthcare Moral Hazard:* The excess consumption of medical care that occurs because insurance coverage reduces the out-of-pocket price at the point of care below its true market cost.

### 2.2 Ex Ante vs. Ex Post Moral Hazard
Medical licensing exams frequently test this distinction using clinical vignettes:

| Concept | Timing | Mechanism | Classical Exam Clinical Vignette |
| :--- | :--- | :--- | :--- |
| **Ex Ante Moral Hazard** | **Before** the health event occurs | Insurance alters health-related behaviors, increasing the probability that an illness or injury occurs. | A 27-year-old man purchases full-coverage health insurance and decides to take up backcountry cliff-jumping or stops adhering to a diabetic diet, knowing "if anything happens, the hospital is fully covered." |
| **Ex Post Moral Hazard** | **After** the illness or injury occurs | Lower out-of-pocket prices cause the patient to consume more healthcare services than they would have if paying full price. | A 30-year-old woman with a mild tension headache demands an elective brain MRI and multiple specialist visits because her plan has a $10 copayment. |

### 2.3 Price Elasticity of Demand in Healthcare
- Price elasticity measures how much the quantity demanded changes when price changes ($%\Delta Q / %\Delta P$).
- **Discretionary / Elective Services (High Price Elasticity):** Comfort care, elective cosmetic procedures, physical therapy for mild aches, brand-name vs. generic drugs. **Moral hazard is highly pronounced here.**
- **Urgent / Life-Saving Services (Low Price Elasticity / Inelastic):** Insulin for type 1 diabetes, acute appendectomy, antibiotics for septic shock, trauma surgery. **Moral hazard is very low here** because nobody undergoes emergency heart surgery just because it is cheap.

### 2.4 Patient-Side Cost Sharing: Mechanisms & Calculations
To restrain ex-post moral hazard, insurers make patients pay a portion of the bill. You must know these four structures:
1. **Deductible:** A fixed dollar amount the patient must pay 100% out of pocket before the insurance company pays a single dollar.
2. **Copayment (Copay):** A flat dollar fee paid at the time a service is delivered (e.g., $25 per office visit, $15 per prescription).
3. **Coinsurance:** A fixed percentage of the allowable bill that the patient pays *after* the deductible has been satisfied (e.g., 20% coinsurance).
4. **Stop-Loss / Out-of-Pocket Maximum (OOP Max):** The maximum cumulative amount the patient can be required to pay in a plan year for covered services (deductibles + copays + coinsurance). Once the OOP Max is reached, the insurer pays 100% of all subsequent covered expenses.

#### Comprehensive Calculation Walkthrough
> **Scenario:** John incurs a $25,000 in-network hospital bill. His insurance plan has:
> - Annual Deductible: **$2,000**
> - Coinsurance: **20%**
> - Out-of-Pocket Maximum: **$5,000**
>
> *Question: How much does John pay out of pocket, and how much does the insurer pay?*
>
> **Step 1: Apply the Deductible.**  
> John pays the first **$2,000**.  
> Remaining bill to split: $\$25,000 - \$2,000 = \$23,000$.  
> Running out-of-pocket total: **$2,000**.
>
> **Step 2: Calculate Coinsurance.**  
> John is responsible for 20% of the remaining $23,000:  
> $$0.20 \times \$23,000 = \$4,600$$  
> Tentative total out-of-pocket spending:  
> $$	ext{Deductible} + 	ext{Coinsurance} = \$2,000 + \$4,600 = \$6,600$$
>
> **Step 3: Check Against the Out-of-Pocket Maximum.**  
> John's plan caps his annual out-of-pocket spending at **$5,000**.  
> Because the calculated $6,600 exceeds his $5,000 cap:  
> - **John pays exactly $5,000.**  
> - **Insurer pays the rest:** $\$25,000 - \$5,000 = \mathbf{\$20,000}$.

### 2.5 Economic Effects of Cost Sharing: Own-Price, Cross-Price, and Offset Effects
1. **Own-Price Effect:** Increasing the out-of-pocket cost of a specific service reduces its utilization.  
   *Example:* Raising the prescription copay for an inhaler from $10 to $40 causes the patient to refill the inhaler less frequently.
2. **Cross-Price Effect:** Changing the price of one healthcare service alters the utilization of a separate, related service.  
   *Example:* Raising prescription drug copays causes patients to cancel routine outpatient follow-up visits with their primary care physician.
3. **Offset Effect (Crucial Clinical Concept):** When patient cost-sharing leads to cutbacks on medically necessary or preventive care, causing disease exacerbation, preventable hospitalizations, and dramatically higher downstream costs.  
   *Example:* A heart failure patient skips their $30/month furosemide copay to save money, develops acute pulmonary edema, and requires a $25,000 ICU admission.

### 2.6 Landmark Study: Tamblyn et al. (2001, JAMA)
- **Background:** In August 1996, the government of Quebec, Canada reformed its provincial drug insurance. Welfare recipients and low-income seniors (who previously paid $0 for all prescriptions) were subjected to a 25% coinsurance rate up to a cap, followed by a $100 deductible in January 1997.
- **Hypothesis of Policy Makers:** Increasing cost sharing would save public money by discouraging frivolous, non-essential drug consumption.
- **Empirical Findings:**
  1. Beneficiaries slashed their use of non-essential medications (e.g., mild analgesics, sedatives).
  2. **Crucially, beneficiaries also slashed their use of essential life-saving medications** (e.g., insulin, beta-blockers, ACE inhibitors, anti-asthmatics, anticoagulants).
  3. **Severe Offset Effects Occurred:** Reductions in essential drugs produced an immediate, dose-dependent surge in serious adverse events (cardiac arrests, strokes, deaths) and emergency department visits.
- **Clinical & Policy Takeaway:** Patients lack the pharmacological expertise to differentiate between high-value essential medicines and low-value symptomatic relief. Cost sharing is a blunt instrument that harms vulnerable populations.

### 2.7 Supply-Side Controls to Combat Moral Hazard
Instead of forcing patients to pay at the point of care, health systems can control moral hazard from the provider/supply side:
1. **Gatekeeping:** A primary care physician (PCP) acts as the coordinator. Patients cannot self-refer to specialists or order advanced imaging (MRIs) without an explicit PCP referral.
2. **Managed Care:** Insurers implement utilization management, mandatory prior authorizations, clinical practice guidelines, and restricted provider networks.
3. **Capacity Control (Queuing / Supply Constraints):** Used in single-payer systems (such as Canada and the UK National Health Service). The system restricts the overall supply of physical capital (number of MRI scanners, operating rooms, ICU beds) and specialists.
   - There is zero cost-sharing at the point of care, so money is not the barrier.
   - **Waiting times (queuing)** serve as the non-monetary rationing mechanism to deter frivolous utilization.

### 2.8 The First Fundamental Tradeoff of Health Insurance
$$\boxed{\text{Financial Protection (Generous Coverage)} \iff \text{Moral Hazard (Excessive Utilization & Cost)}}$$
- Expanding coverage shields patients from catastrophic financial distress and promotes peace of mind.
- However, the more comprehensive and generous the insurance, the lower the out-of-pocket price at the point of care, which fuels moral hazard, encourages unnecessary care, and raises total healthcare costs for society.

---

## 3. Risk Selection, Adverse Selection, and the Death Spiral

### 3.1 Understanding Risk Selection
Insurers' profitability is determined almost entirely by the underlying health status of their risk pool:
- Healthy members pay premiums and consume few resources (high profit).
- Chronically ill members generate claims that dwarf their premiums (losses).
- **Risk Selection:** The process by which an insurance plan ends up enrolling a non-random group of either healthy or sick beneficiaries.
  - **Adverse Selection:** Disproportionate enrollment of sicker, high-cost individuals into a plan.
  - **Favorable Selection ("Cream-Skimming" / "Cherry-Picking"):** Insurers deliberately design plans and marketing to attract healthier, low-cost individuals while repelling the sick.

### 3.2 Necessary Preconditions for Risk Selection
Risk selection occurs whenever three conditions coexist:
1. **Consumer Choice:** Individuals have the freedom to choose among different insurance plans or opt out entirely.
2. **Asymmetric Information:** Individuals possess private, superior knowledge about their own health status, family history, and future medical intentions than the insurer possesses.
3. **Cost Mismatch:** Premiums are set based on community or average risk, rather than reflecting the exact risk of each individual enrollee.

### 3.3 The Lemons Principle and The Insurance Death Spiral (Worked Example)
The "Death Spiral" is a classic exam question. You must understand the mathematical step-by-step unraveling of a voluntary insurance market:

#### The Scenario
Suppose a population consists of 5 risk-averse individuals with differing expected annual healthcare costs. Each person is willing to pay their expected cost plus a risk premium:

| Person | Expected Healthcare Cost | Risk Premium | Willingness to Pay (WTP) |
| :---: | :---: | :---: | :---: |
| **1 (Healthy)** | $10 | $1 | **$11** |
| **2 (Low Risk)** | $50 | $6 | **$56** |
| **3 (Moderate Risk)** | $100 | $15 | **$115** |
| **4 (High Risk)** | $150 | $25 | **$175** |
| **5 (Severe Chronic)** | $250 | $50 | **$300** |
| **Total** | **$560** | — | — |
| **Average (Mean)** | **$112** | — | — |

#### Round 1: Community-Rated Average Premium
- The insurer calculates the average expected cost of the entire group: $\$560 / 5 = \mathbf{\$112}$.
- The insurer sets the Year 1 Premium at **$112**.
- *Who decides to buy?*
  - Person 1 ($WTP = $11): **Declines** (Premium $112 > $11).
  - Person 2 ($WTP = $56): **Declines** (Premium $112 > $56).
  - Person 3 ($WTP = $115): **Buys** (Premium $112 \le $115).
  - Person 4 ($WTP = $175): **Buys** (Premium $112 \le $175).
  - Person 5 ($WTP = $300): **Buys** (Premium $112 \le $300).
- *Insurer Financial Result in Round 1:*
  - Enrollees = 3 (Persons 3, 4, 5).
  - Total Revenue = $3 	imes \$112 = \mathbf{\$336}$.
  - Total Actual Claims = $\$100 + \$150 + \$250 = \mathbf{\$500}$.
  - **Insurer Loss = $\$336 - \$500 = -\mathbf{\$164}$ (Deficit!).**

#### Round 2: The Insurer Adjusts Premium Upward
- To cover the $500 in claims from the remaining 3 enrollees, the insurer raises the premium to the new average:  
  $$\text{New Premium} = \frac{\$500}{3} = \mathbf{\$167}$$
- *Who buys at $167?*
  - Person 3 ($WTP = $115): **Drops out!** (Premium $167 > $115).
  - Person 4 ($WTP = $175): **Buys**.
  - Person 5 ($WTP = $300): **Buys**.
- *Insurer Financial Result in Round 2:*
  - Enrollees = 2 (Persons 4 and 5).
  - Total Revenue = $2 	imes \$167 = \mathbf{\$334}$.
  - Total Actual Claims = $\$150 + \$250 = \mathbf{\$400}$.
  - **Insurer Loss = $\$334 - \$400 = -\mathbf{\$66}$ (Deficit continues!).**

#### Round 3: The Market Collapses (Death Spiral)
- The insurer raises the premium again: $\$400 / 2 = \mathbf{\$200}$.
- Person 4 ($WTP = $175) drops out!
- Only Person 5 remains. The premium must be increased to over $250.
- Eventually, no risk pooling occurs, premiums explode, and the market collapses.
- **Definition of Death Spiral:** The vicious cycle in which healthy enrollees flee a risk pool due to rising average premiums, leaving a progressively sicker, more expensive pool that forces further premium increases until the plan fails.

### 3.4 Regulatory Policies to Combat Adverse Selection
How can a health system prevent adverse selection?
1. **Universal Single-Payer Coverage:** Everyone is automatically enrolled in one universal pool (e.g., Medicare for all, Canadian Medicare). Without voluntary opt-outs, adverse selection is mathematically impossible.
2. **Employer-Sponsored Group Coverage:** Enrolling employees automatically as a condition of employment broadens the risk pool to include young, healthy workers who would not otherwise buy coverage.
3. **The Affordable Care Act (ACA) Three-Legged Stool:**
   - *Leg 1 (Guaranteed Issue & Community Rating):* Insurers are barred from denying coverage or charging higher premiums based on pre-existing conditions. (Note: On its own, this worsens adverse selection!).
   - *Leg 2 (Individual Mandate):* Required every citizen to maintain insurance or pay a tax penalty, forcing healthy individuals to stay in the pool.
   - *Leg 3 (Premium Subsidies):* Income-based tax credits to ensure coverage is affordable for low- and middle-income families.

### 3.5 The ACA "3 Rs" Risk Mitigation Framework
To stabilize the individual insurance marketplaces and protect insurers against adverse selection, the ACA established three specific programs:

| Mechanism | Duration | Operational Definition & Target | Exam Trigger Cue |
| :--- | :--- | :--- | :--- |
| **Risk Adjustment** | **Permanent** | Redistributes money from plans with healthier-than-average enrollees to plans with sicker-than-average enrollees. Net transfer sum is zero. | "Zero-sum transfer between plans based on enrollee clinical risk scores" |
| **Reinsurance** | Temporary (2014–2016) | Partially reimburses insurers when an individual enrollee incurs exceptionally high, catastrophic medical expenses. | "Government subsidizes extraordinarily expensive individual cases" |
| **Risk Corridors** | Temporary (2014–2016) | Government shares risk with insurers by cushioning unexpected large profits or losses against a predefined target corridor. | "Protects insurers from unexpected major losses/gains in new exchange" |

### 3.6 Insurer Counter-Tactics: Adverse Tiering (Jacobs & Sommers, 2015, NEJM)
- Even under ACA regulations prohibiting denial of coverage for pre-existing conditions, insurers sought ways to achieve **favorable selection (cream-skimming)**.
- **Adverse Tiering:** Placing all medications used to treat a specific high-cost chronic illness into the highest specialty cost-sharing tier (requiring 30% to 50% coinsurance), even when cheap generic equivalents exist.
- **Empirical Demonstration:** Jacobs & Sommers (2015) analyzed 2014 ACA marketplace plans in Florida. They found that multiple insurers placed 100% of HIV antiretroviral therapies onto specialty tiers.
  - A patient with HIV faced out-of-pocket medication costs of over $4,000 per year in these plans compared to $1,000 in competitor plans.
  - **Incentive:** Sicker patients with HIV avoided these plans, effectively steering high-cost chronic patients onto competitor plans while the offending insurer cream-skimmed healthy enrollees.
- **Remedies:** Regulatory formularies, price transparency, and establishing statutory caps on monthly out-of-pocket spending for protected drug classes.

### 3.7 The Second Fundamental Tradeoff of Health Insurance
$$\boxed{\text{Market Competition & Choice} \iff \text{Adverse Selection & Risk Segmentation}}$$
- Providing consumers with many competing insurance options and plan designs maximizes individual choice and market competition.
- However, widespread consumer choice paired with information asymmetry directly enables risk selection and adverse selection death spirals. Mitigating selection requires standardized benefit designs, mandatory coverage, or single universal pools that inevitably restrict market choice and competition.

---

## 4. Session 1 High-Yield Active Learning Q&A & Quiz Bank

### Question 1: Primary Purpose of Health Insurance
**Vignette:** A 45-year-old healthy accountant asks why he should pay $450 every month for insurance when he rarely visits a doctor. Which of the following is the primary financial rationale for health insurance?  
- A. To guarantee superior physical health outcomes  
- B. To reduce the variance of disposable income across time by pooling catastrophic risk  
- C. To eliminate all primary health risks  
- D. To ensure equal access to experimental interventions  
* **Correct Answer:** **B**  
* **Detailed Rationale:** The primary purpose of insurance is financial consumption smoothing. Because medical spending is right-skewed and unpredictable, insurance pools risk to reduce the variance of income and shield against catastrophic debt. It does not eliminate primary disease risk or guarantee biological cure.

### Question 2: Ex Ante vs. Ex Post Moral Hazard
**Vignette:** A 28-year-old software engineer enrolls in an employer's comprehensive health plan with zero deductible. Within two weeks, he takes up extreme downhill mountain biking without wearing protective body armor, stating "my orthopedic surgery is covered 100%." Which concept best describes this behavior?  
- A. Ex post moral hazard  
- B. Ex ante moral hazard  
- C. Favorable risk selection  
- D. Adverse tiering  
* **Correct Answer:** **B**  
* **Detailed Rationale:** Ex ante moral hazard represents changes in risk-taking behavior *before* an event occurs because the individual knows they do not bear the full financial penalty of potential injury. Ex post moral hazard occurs *after* injury/illness occurs (e.g. overusing therapy).

### Question 3: Out-of-Pocket Expense Calculation
**Vignette:** A patient is admitted for an emergency appendectomy resulting in a total covered hospital charge of $16,000. Her health insurance policy has an annual deductible of $1,000, coinsurance of 20%, and an out-of-pocket maximum of $3,000. How much will the patient pay out of pocket for this hospitalization?  
- A. $1,000  
- B. $3,000  
- C. $4,000  
- D. $4,200  
* **Correct Answer:** **B**  
* **Detailed Rationale:**  
  1. Patient pays first $1,000 (Deductible). Remaining bill = $\$16,000 - \$1,000 = \$15,000$.  
  2. Coinsurance = $20\% 	imes \$15,000 = \$3,000$.  
  3. Tentative out-of-pocket total = $\$1,000 + \$3,000 = \$4,000$.  
  4. Compare with Out-of-Pocket Maximum ($3,000). The patient's spending is capped at $3,000. (The insurer pays $\$16,000 - \$3,000 = \$13,000$).

### Question 4: Offset Effects of Cost Sharing
**Vignette:** A provincial health authority increases prescription drug copayments for low-income elderly patients from $2 to $25 per prescription. Within 6 months, prescription refill rates for antihypertensives drop by 30%, and emergency department admissions for hypertensive crises and strokes increase by 40%. This phenomenon is best classified as:  
- A. Own-price elasticity  
- B. An offset effect  
- C. Supply-side gatekeeping  
- D. Actuarial loading  
* **Correct Answer:** **B**  
* **Detailed Rationale:** An offset effect occurs when cutting back on necessary medical care due to higher patient cost-sharing results in worsened clinical outcomes and more expensive downstream healthcare utilization (e.g., ED visits, hospitalizations), offsetting the initial intended savings (Tamblyn et al., 2001).

### Question 5: Adverse Tiering
**Vignette:** An insurer offering plans on an ACA exchange places all disease-modifying therapies for multiple sclerosis into a "Tier 5 Specialty" tier requiring 40% coinsurance, while other chronic drugs remain on Tier 2 with flat $15 copays. Which of the following best describes the insurer's motivation?  
- A. To implement reinsurance  
- B. To engage in favorable selection by discouraging patients with multiple sclerosis from enrolling  
- C. To eliminate ex-ante moral hazard  
- D. To reduce loading fees  
* **Correct Answer:** **B**  
* **Detailed Rationale:** Adverse tiering is an insurer strategy to deter patients with expensive chronic diseases from enrolling in their plan (favorable selection / cream-skimming), steering them toward competitor plans (Jacobs & Sommers, 2015).
