# Marketing A/B Test Analysis — Do Ads Actually Drive Conversions?

## 📌 Project Overview
This project analyses a real-world marketing A/B test to determine 
whether digital advertisements significantly outperform a neutral 
Public Service Announcement (PSA) in driving user conversions.

The analysis goes beyond a simple pass/fail hypothesis test — it 
investigates **when** ads work best, **how many** ads drive optimal 
conversion, and translates all statistical findings into concrete 
business recommendations.

**Tools Used:** Python (Pandas, SciPy, Statsmodels, Seaborn, 
Matplotlib)  
**Dataset:** Marketing A/B Testing Dataset — Kaggle  
**Techniques:** Hypothesis Testing, Two-Proportion Z-Test, 
Exploratory Data Analysis, Customer Segmentation

---

## Business Question
A marketing team ran a campaign showing digital ads to ~564,000 
users, while a holdout group of ~23,500 users saw a neutral PSA 
instead. The core questions are:

1. Do the ads significantly outperform the PSA in conversion rate?
2. Which days and hours do ads convert best?
3. Does ad frequency affect conversion — is there an ad fatigue 
   effect?

---

## Dataset
- **Total users:** 588,101
- **Ad group:** 564,577 users (96%)
- **PSA group:** 23,524 users (4%)
- **Key columns:** test group, converted, total ads, 
  most ads day, most ads hour

The 96/4 split reflects a common industry **holdout group 
strategy** — companies maintain a small control group to measure 
ad effectiveness without significantly disrupting normal business 
operations.

---

##  Methodology

### 1. Data Quality Check
- Verified zero missing values and no duplicate records
- Confirmed correct data types across all columns

### 2. Hypothesis Test — Two-Proportion Z-Test
**Null Hypothesis (H₀):** There is no significant difference 
between the conversion rates of the ad and PSA groups  
**Alternative Hypothesis (H₁):** The ad group converts at a 
significantly higher rate than the PSA group  
**Significance Level:** α = 0.05

### 3. Exploratory Analysis
- Conversion rate by day of week
- Conversion rate by hour of day
- Ad frequency vs conversion rate (fatigue analysis)

---

##  Key Findings

### Core Result — Ads Work
| Group | Users | Conversions | Conversion Rate |
|-------|-------|-------------|-----------------|
| Ad    | 564,577 |  14,423   |   2.55% |
| PSA   | 23,524  |  420      |   1.79% |

- **Z-statistic:** 7.37
- **P-value:** <0.0001
- **Result:** Reject H₀ — ads significantly outperform the PSA
- **Relative uplift:** 42.8% higher conversion rate vs PSA
- **Business impact:** ~4,300 additional conversions, representing 
  ~€215,000 in incremental revenue (assuming €50 avg order value)

### Timing Insights
- **Best days:** Monday (3.25%) and Tuesday (3.00%)
- **Worst days:** Saturday (2.11%) and Thursday (2.16%)
- **Peak hours:** 4pm-5pm (3.10%) and 8pm-9pm (3.00%)
- **Dead zones:** 2am-3am (under 1.00%)

### Ad Frequency Insights
| Ads Seen | Conversion Rate |
|----------|----------------|
| 1-5 | 0.25% |
| 6-20 | 0.49-0.84% |
| 21-50 | 2.92% |
| 51-100 | 11.63% |
| 101-200 | **17.68% (peak)** |
| 201-500 | 15.37% |

Conversion rises strongly with frequency up to ~200 ads, consistent 
with the **mere exposure effect** from behavioural economics — 
repeated brand exposure builds familiarity and purchase intent.

---

## Limitations
- **Selection bias in frequency analysis:** High ad frequency users 
  are likely highly engaged platform users by nature — their higher 
  conversion rates may partly reflect pre-existing purchase intent 
  rather than ad exposure alone
- **No user purchase history:** The dataset does not contain
  customer info so unable to distinguish new vs 
  returning customers — frequency strategy likely differs 
  significantly between these segments
- **Holdout group imbalance:** The 96/4 split, while valid given 
  large sample sizes, reflects an observational design rather than 
  a perfectly randomised controlled experiment

---

## ✅ Business Recommendations

1. **Continue the ad campaign** — statistical evidence strongly 
   supports ads driving meaningful incremental conversions with 
   near-zero probability of random chance

2. **Shift budget toward Monday-Tuesday, 3pm-6pm** — conversion 
   rates peak at 3.25% and 3.10% respectively during these windows

3. **Reduce spend during 12am-4am** — conversion rates drop below 
   1% during these hours, representing largely wasted budget

4. **Investigate low-frequency users (1-20 ads)** — converting at 
   under 1%, increasing their ad exposure represents the largest 
   untapped conversion opportunity in the current campaign

5. **Conduct follow-up segmentation by new vs returning users** — 
   frequency requirements likely differ significantly between 
   first-time and repeat customers; a dedicated frequency-capping 
   experiment per segment would sharpen these recommendations

