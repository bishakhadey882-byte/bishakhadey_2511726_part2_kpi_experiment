# Recommendation Memo
## Campaign Experiment Analysis — Onboarding & Activation Campaign

**To:** Leadership / Product Team
**From:** Bishakha Dey, Business Analyst
**Student ID:** bitsom_ba_2511726
**Date:** 2026-06-21
**Subject:** Launch Recommendation — New Onboarding Campaign

---

## 1. Executive Summary

A controlled A/B experiment was conducted to evaluate a new onboarding and activation campaign for our subscription-based digital product. The experiment ran from January to May 2025 with **1,408 users** split into Control (693) and Treatment (715) groups.

**Recommendation: ✅ LAUNCH the new campaign to all users.**

The treatment campaign produced a **2.2x improvement in paid conversion rate** (3.17% → 6.99%), which is statistically significant at the 99.9% confidence level. No guardrail metrics show meaningful risk.

---

## 2. North Star Metric

**Selected North Star Metric: Paid Conversion Rate**

- **Definition:** Percentage of users who convert from free/trial to paid subscription
- **Why this is the North Star:** It directly measures revenue generation and business growth. All other metrics (landing page visits, trial starts, onboarding completions) are upstream drivers that ultimately lead to paid conversion. A company's survival depends on converting users to paying customers.
- **Risk of blind optimization:** If optimized blindly, the company might use aggressive tactics (heavy discounts, pressure tactics) that inflate short-term conversions but hurt long-term retention and brand reputation. That is why guardrail metrics like refund rate and support ticket rate must be monitored alongside.

---

## 3. KPI Tree Explanation

The KPI tree shows how Paid Conversion Rate breaks down into three primary drivers:

**Acquisition Driver** (getting users to the product)
- Landing Page Visit Rate: Did users engage with the first touchpoint?
- Trial Start Rate: Did they take the next step?

**Activation Driver** (getting users to experience value)
- Onboarding Completion Rate: Did users complete the onboarding flow?
- Average Engagement Score: Are users actively engaging?

**Revenue Driver** (converting engaged users to paying customers)
- Average Revenue Per Converter: Quality of conversions
- Average Days to Convert: Speed of conversion funnel

**3 Guardrail Metrics monitored:** Refund Rate, Support Ticket Rate, Revenue Quality

---

## 4. Experiment Result Summary

| Metric | Control | Treatment | Change |
|---|---|---|---|
| Users | 693 | 715 | +22 |
| Landing Page Visit Rate | 63.6% | 72.6% | +9.0% ✅ |
| Trial Start Rate | 25.1% | 29.1% | +4.0% ✅ |
| Onboarding Completion Rate | 15.6% | 21.3% | +5.7% ✅ |
| **Paid Conversion Rate** | **3.17%** | **6.99%** | **+3.82% ✅** |
| Avg Revenue Per User | $39.3 | $65.5 | +$26.2 ✅ |
| Refund Rate | 0.29% | 0.14% | -0.14% ✅ |
| Support Ticket Rate | 0.30 | 0.30 | 0.00 ✅ |
| Avg Engagement Score | 59.9 | 60.1 | +0.2 ✅ |

The treatment group improved on **every single primary metric** while maintaining or improving all guardrail metrics.

---

## 5. Hypothesis Test Interpretation

**Test Performed:** Two-Proportion Z-Test (Two-Tailed)
**Metric:** Paid Conversion Rate
**H₀:** No difference between Control and Treatment
**H₁:** There is a significant difference

| Result | Value |
|---|---|
| Z-Statistic | 3.264 |
| P-Value | 0.001099 |
| Significance Level (α) | 0.05 |
| Decision | **REJECT H₀** |

**Interpretation:** The probability that this result occurred by random chance is only 0.11%. This means we are 99.89% confident the treatment campaign genuinely improves paid conversions. The result is statistically significant.

---

## 6. Guardrail Analysis

We evaluated 3 guardrail metrics to ensure the campaign does not cause harm:

**Refund Rate:**
- Control: 0.29% | Treatment: 0.14%
- Status: ✅ **No Risk** — Refund rate is actually LOWER in treatment. Users are more satisfied.

**Support Ticket Rate:**
- Control: 0.30 tickets/user | Treatment: 0.30 tickets/user
- Status: ✅ **Stable** — No increase in support load. Campaign does not confuse users.

**Revenue Quality (Avg Revenue Per Converter):**
- Control: $1,033 | Treatment: $1,001
- Status: ⚠️ **Monitor** — Slight decrease ($32 less per converter). This may be because treatment attracts more price-sensitive users who choose lower plans. Not alarming but worth tracking post-launch.

**Overall Guardrail Verdict:** No guardrail metric creates a blocking risk for launch.

---

## 7. Segment-Level Insight

Analysis across 4 segments (Region, Device Type, Traffic Source, Plan Type) reveals:

- **Region:** Treatment outperforms Control in all 4 regions (North, South, East, West). No regional segment shows decline.
- **Device Type:** Improvement is strongest on Mobile (+4.1% conversion lift) — the new campaign may be especially well-designed for mobile users.
- **Traffic Source:** Paid Search and Email segments show the highest conversion lift with treatment.
- **Plan Type:** Free plan users show the biggest improvement in converting to paid — exactly the target segment.

No segment shows a negative impact from the treatment campaign.

---

## 8. Final Recommendation

### ✅ LAUNCH the new campaign to ALL users

**Rationale:**
1. Paid conversion rate improved by **2.2x** (statistically significant, p=0.001)
2. Every funnel metric improved (landing page → trial → onboarding → conversion)
3. No guardrail metric shows harmful impact
4. All regional and demographic segments benefit from the treatment
5. Average revenue per user increased by $26.20 (+67%)

**Alternative options considered:**
- **Do not launch:** Not recommended — strong statistical evidence supports the campaign
- **Launch only for selected segment:** Not needed — all segments show improvement
- **Continue testing:** Not needed — result is already significant at 99.9% confidence with 1,400+ users

---

## 9. Risks and Limitations

1. **Experiment duration:** The experiment ran for ~5 months. Long-term retention impact beyond 30 days is unknown.
2. **Revenue quality:** Avg revenue per converter is slightly lower in treatment ($1,001 vs $1,033). Monitor whether treatment users have lower LTV (lifetime value).
3. **Novelty effect:** Some of the conversion lift may be due to the excitement of a new experience. Monitor conversion rates 30/60/90 days post-launch.
4. **Missing data:** 18 records had missing device_type and 24 had missing traffic_source — filled with "Unknown" which may slightly affect segment analysis.
5. **Duplicate users:** 8 duplicate user_ids were found and removed. If these represent legitimate multiple sign-ups, removal may slightly undercount certain segments.

---

## 10. Next Steps

1. **Immediate (Week 1):** Begin rollout of new campaign to 100% of new users
2. **Short-term (Month 1):** Monitor paid conversion rate, refund rate, and support tickets daily during rollout
3. **Medium-term (Month 2-3):** Measure 60-day and 90-day retention of converted users from both groups
4. **Revenue tracking:** Compare average revenue per user and LTV between original Control and Treatment cohorts at 6 months
5. **Segment optimization:** Given Mobile shows strongest lift, consider further mobile-specific optimizations
6. **Iteration:** Use these results as baseline — run the next experiment to improve onboarding completion rate from 21.3% further
