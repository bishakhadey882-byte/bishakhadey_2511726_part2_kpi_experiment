# bishakhadey_2511726_part2_kpi_experiment
# Part 2: KPI Framework, Business Experiment Analysis & Decision Recommendation

**Student:** Bishakha Dey

**Student ID:** bitsom_ba_2511726

**Repository:** bishakhadey_2511726_part2_kpi_experiment

**Date:** 2026-06-23

---

## 1. Business Context

A subscription-based digital product company launched a new onboarding and activation campaign to improve user conversion and early engagement. Users were divided into:
- **Control group:** Existing onboarding experience (693 users)
- **Treatment group:** New campaign experience (715 users)

**Business Decision Required:** Should the new campaign be launched to all users?

**Problem Statement:**
- What decision needs to be made? Whether to launch the new onboarding campaign to all users
- Who the decision impacts? Product team, marketing team, new users, and company revenue
- What metric should improve? Paid Conversion Rate (North Star Metric)
- What risks must be monitored? Refund rate, support ticket rate, revenue quality per converter
- What evidence is required? Statistically significant improvement in conversion with no guardrail violations

---

## 2. Dataset Description

| Property | Detail |
|---|---|
| File Name | campaign_experiment_data.xlsx |
| Total Records | 1,408 (raw) → 1,400 (after cleaning) |
| Columns | 16 |
| Control Group | 693 users |
| Treatment Group | 715 users |
| Experiment Period | January – May 2025 |

**Key columns:** user_id, experiment_group, region, device_type, traffic_source, plan_type, visited_landing_page, started_trial, completed_onboarding, converted_to_paid, revenue_30d, support_tickets_30d, refund_requested, days_to_convert, engagement_score

---

## 3. North Star Metric Selected

**✅ Paid Conversion Rate** — Percentage of users who convert from free/trial to paid subscription

- Why: Directly measures business revenue and growth
- Supporting metrics: Landing page visit rate, trial start rate, onboarding completion rate
- Guardrail metrics: Refund rate, support ticket rate, revenue quality
- Risk of blind optimization: Could lead to aggressive tactics that hurt long-term retention

---

## 4. KPI Tree Summary

**North Star:** Paid Conversion Rate

**Primary Drivers:**
1. Acquisition Driver → Landing Page Visit Rate + Trial Start Rate
2. Activation Driver → Onboarding Completion Rate + Engagement Score
3. Revenue Driver → Avg Revenue Per Converter + Days to Convert

**Guardrail Metrics:** Refund Rate | Support Ticket Rate | Revenue Quality | Segment-level Decline

KPI Tree saved as: `outputs/kpi_tree.png`

---

## 5. Experiment Analysis Approach

**Task 4 — Data Cleaning:**
- Removed 8 duplicate user_ids
- Filled 18 missing device_type values with "Unknown"
- Filled 24 missing traffic_source values with "Unknown"
- Filled 14 missing engagement_score values with group median
- Flagged revenue outliers (>3 standard deviations)
- Verified all binary columns (0/1 only)

**Task 5 — Experiment Summary:**
- Calculated all 9 required metrics for Control vs Treatment
- Performed segment-level breakdown by region, device type, traffic source, plan type
- Color-coded results (green = treatment better, red = treatment worse)

---

## 6. Hypothesis Test Summary

**Test:** Two-Proportion Z-Test (Two-Tailed)
**Metric:** Paid Conversion Rate
**H₀:** p_treatment = p_control (no difference)
**H₁:** p_treatment ≠ p_control (significant difference)
**α = 0.05**

| Result | Value |
|---|---|
| Control Rate | 3.17% (22/693) |
| Treatment Rate | 6.99% (50/715) |
| Z-Statistic | 3.264 |
| P-Value | 0.001099 |
| Decision | **REJECT H₀ — Statistically Significant** |

The treatment campaign produces **2.2x more conversions** than control, with 99.9% confidence.

---

## 7. Guardrail Metrics Considered

| Guardrail Metric | Control | Treatment | Risk? |
|---|---|---|---|
| Refund Rate | 0.29% | 0.14% | ✅ No Risk |
| Support Ticket Rate | 0.30 | 0.30 | ✅ Stable |
| Revenue Per Converter | $1,033 | $1,001 | ⚠️ Monitor |
| Segment-level Decline | — | None found | ✅ Safe |

---

## 8. Final Recommendation

### ✅ LAUNCH the campaign to ALL users

- Paid conversion rate improved by **+3.82 percentage points (+120% relative lift)**
- Result is statistically significant (p = 0.001, Z = 3.264)
- All funnel metrics improved
- No guardrail metric shows blocking risk
- All 4 regional segments benefit from treatment
- Average revenue per user increased by $26.20 (+67%)

---

## 9. Assumptions and Limitations

**Assumptions:**
- Missing device_type and traffic_source filled with "Unknown" for segment analysis
- Duplicate user_ids removed (kept first occurrence) — assumed data entry errors
- days_to_convert is NaN for non-converters — treated as valid missing data
- Revenue outliers (>3 std) were flagged but retained in analysis

**Limitations:**
- Long-term retention beyond 30 days not measured
- Slight decrease in revenue per converter ($1,033 → $1,001) needs monitoring
- Novelty effect possible — post-launch monitoring recommended
- 8 duplicate user_ids removed may represent edge cases

---

## 10. Screenshots Included

| File | Shows |
|---|---|
| `screenshots/summary_metrics.png` | Control vs Treatment summary table and funnel comparison chart |
| `screenshots/hypothesis_test_output.png` | Z-test results table and normal distribution visualization |
| `screenshots/kpi_tree_preview.png` | Full KPI tree with North Star, drivers, sub-drivers, and guardrails |

---

## Repository Structure

```
bishakhadey_bitsom_ba_2511726_part2_kpi_experiment/
├── data/
│   └── campaign_experiment_data.xlsx
├── analysis/
│   ├── experiment_analysis.xlsx
│   └── hypothesis_test_notes.md
├── outputs/
│   ├── kpi_tree.png
│   ├── experiment_summary.xlsx
│   └── recommendation_memo.md
├── screenshots/
│   ├── summary_metrics.png
│   ├── hypothesis_test_output.png
│   └── kpi_tree_preview.png
└── README.md

Note: Github automatically sorts the files alphabetically.
```
