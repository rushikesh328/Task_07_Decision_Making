# Process Log – Research Task 7: Ethical Implications of Decision Making

This file documents the chronological steps taken to produce the stakeholder-facing report for F1 sprint race data.

---

## 1. Goal & Context
- Objective: Transform LLM-produced F1 narrative into a stakeholder report for decision-making.
- Stakeholder chosen: Formula 1 Team Principal.
- Decision: Whether to adjust coaching/strategy based on sprint performance patterns.
- Risk level: Medium (operational + reputational).

---

## 2. Data Provenance
- Dataset: `Formula1_2024season_sprintResults.csv` (from GitHub F1 repo).
- Collector: Publicly scraped race statistics.
- Privacy concerns: Low (sports performance data, already public).
- Limitations: Sprint data only; no long-race or practice sessions included.

---

## 3. Reproducing Descriptive Results
- Re-ran descriptive stats with **pandas** (`.describe()`, `.value_counts()`, `.nunique()`).
- Grouped by driver and team to compute total sprint points.
- Verified Max Verstappen had highest sprint points, Red Bull led teams.
- Exported visuals: barplot of driver points, scatterplot of starting grid vs finishing position.

---

## 4. Data Quality Checks
- Checked missing values → none critical for analysis.
- Verified ranges for `Position` and `Starting Grid`.
- Converted categorical columns consistently.
- Found some NaNs in secondary fields → dropped safely.

---

## 5. Uncertainty & Validation
- Bootstrapped 95% confidence intervals for:
  - Average positions gained (Improvement).
  - Team mean finishing position.
- Pearson correlation: Starting Grid vs Finishing Position → r ≈ 0.45, p < 0.01.
- Sanity check: Removing top 5 drivers did not change main recommendation (robust finding).

---

## 6. Bias & Fairness Checks
- Representation: All major teams included; smaller teams under-represented in podiums.
- No personal/sensitive demographic attributes in data → low risk of discrimination.
- Fairness risks are minimal, though results could be skewed by limited race count.

---

## 7. Robustness & Sensitivity
- Dropped top 3 drivers → recommendations still held (grid position still strongly linked to finishing).
- Normalized metrics (z-scores) → rankings of consistent teams unchanged.

---

## 8. Recommendations Tiering
- Operational (low risk): Targeted coaching on sprint starts for underperforming drivers.
- Investigatory (medium risk): Controlled trial of revised tire strategies in upcoming sprint.
- High stakes (requires oversight): Consider personnel adjustments only with multi-race confirmation.

---

## 9. Ethics & Transparency
- All LLM-generated text clearly labeled in report.
- Every claim traced back to code/statistical validation.
- Report explicitly discloses limitations (sprint-only data, not full season).

---

## 10. Final Deliverables
- `stakeholder_report.md` — polished report.
- `logs/prompt_log.md` — full LLM transcript & edits.
- `code/analysis.py` — reproducible stats + bootstrap CI functions.
- `report/figs/` — supporting visuals.

