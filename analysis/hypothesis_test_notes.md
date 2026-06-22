# Hypothesis Test Notes
## Part 2: KPI Framework, Business Experiment Analysis & Decision Recommendation

**Student:** Bishakha Dey | **ID:** bitsom_ba_2511726

---

## 1. Null Hypothesis (H₀)
There is **no statistically significant difference** in the Paid Conversion Rate between the Control group (existing onboarding) and the Treatment group (new campaign experience).

> H₀: p_treatment = p_control

---

## 2. Alternate Hypothesis (H₁)
The Treatment group has a **significantly different** Paid Conversion Rate compared to the Control group.

> H₁: p_treatment ≠ p_control

---

## 3. Test Type
**Two-Proportion Z-Test — Two-Tailed**

- Two-tailed because we want to detect any difference (increase OR decrease)
- Z-test is appropriate because sample sizes are large (n > 30 in both groups)
- Both groups have binary outcomes (converted = 1, not converted = 0)

---

## 4. Significance Level
**α = 0.05 (95% confidence level)**

This is the industry standard for business A/B tests. It means we accept a 5% chance of incorrectly rejecting the null hypothesis (Type I error).

---

## 5. Metric Being Tested
**Primary Metric: Paid Conversion Rate**

- Definition: Number of users who converted to paid ÷ Total users in group
- Control Conversion Rate: 3.17% (22 out of 693 users)
- Treatment Conversion Rate: 6.99% (50 out of 715 users)

---

## 6. Reason for Choosing This Metric
Paid Conversion Rate is the **North Star Metric** for this experiment because:
- It directly measures the business objective (revenue generation)
- It is the final step in the conversion funnel
- It has a direct monetary impact on company growth
- Leadership's decision to launch depends on whether the campaign improves paid conversions
- All other metrics (landing page visits, trial starts, onboarding) are intermediate steps that lead to this outcome

---

## 7. Test Calculation Details

| Parameter | Value |
|---|---|
| Control group size (n_c) | 693 |
| Treatment group size (n_t) | 715 |
| Control conversions (x_c) | 22 |
| Treatment conversions (x_t) | 50 |
| Control conversion rate (p_c) | 0.0317 (3.17%) |
| Treatment conversion rate (p_t) | 0.0699 (6.99%) |
| Pooled proportion (p_pool) | 0.0514 |
| Standard Error (SE) | 0.01178 |
| **Z-Statistic** | **3.2640** |
| **P-Value** | **0.001099** |
| Critical Z (two-tailed, α=0.05) | ±1.96 |
| **Decision** | **REJECT H₀** |

---

## 8. Interpretation Logic

**Step 1:** Since p-value (0.001099) < α (0.05), we **reject the null hypothesis**.

**Step 2:** The Z-statistic (3.264) falls well outside the critical region (±1.96), confirming statistical significance.

**Step 3:** The treatment group shows a **2.2x higher conversion rate** (6.99% vs 3.17%).

**Step 4:** This result is statistically significant at the 99.9% confidence level (p < 0.001).

**Business Interpretation:**
The new onboarding and activation campaign has a **statistically significant positive impact** on paid conversions. The probability that this result occurred by random chance is only 0.11%, which is extremely low. This provides strong evidence that the treatment campaign should be launched to all users.

---

## 9. Secondary Test: Engagement Score (T-Test)

A two-sample independent t-test was also performed on engagement scores:
- Control mean: 59.9 | Treatment mean: 60.1
- Result: **NOT statistically significant** (p > 0.05)
- Interpretation: Engagement scores are similar between groups — the campaign does not hurt engagement

---

## 10. Guardrail Test: Refund Rate

- Control refund rate: 0.29% | Treatment refund rate: 0.14%
- Treatment shows LOWER refund rate — **no guardrail risk**
- The campaign improves conversions without increasing refunds
