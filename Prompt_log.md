# Prompt Log – Research Task 7: Ethical Implications of Decision Making

This file records the actual LLM prompts and responses used to support this assignment.

---

## Prompt 1
**Prompt:**  
“Summarize the 2024 F1 sprint results dataset into a short narrative highlighting the best drivers, most consistent teams, and relationship between starting grid and finishing position.”

**LLM Response (summary):**  
- Max Verstappen scored the most sprint points.  
- Red Bull was the most consistent team overall.  
- Positive correlation between grid position and final position.  
- Some podiums achieved from outside top 5.  

**Used/Modified:**  
Kept as basis for stakeholder report. Added uncertainty (bootstrap CIs) and validation via code.

---

## Prompt 2
**Prompt:**  
“Give me Python code in pandas to group sprint results by driver and team and calculate total points.”

**LLM Response (summary):**  
Provided `.groupby(["Driver"])["Points"].sum().sort_values()` and similar for teams.

**Used/Modified:**  
Directly used in analysis with slight edits for column naming consistency.

---

## Prompt 3
**Prompt:**  
“Suggest statistical methods to quantify uncertainty in descriptive claims (e.g., average improvement, correlation).”

**LLM Response (summary):**  
- Use bootstrap resampling for CIs.  
- Pearson/Spearman correlation with p-values.  
- Robustness checks by removing top performers.  

**Used/Modified:**  
Implemented bootstrap function in `analysis.py` and reported CIs.

---

## Prompt 4
**Prompt:**  
“Help me structure a stakeholder-facing report with executive summary, findings, recommendations, and ethical analysis.”

**LLM Response (summary):**  
Outlined sections: Title, Executive Summary, Background, Data/Methods, Findings, Recommendations (tiered), Ethical Concerns, Next Steps, Appendices.

**Used/Modified:**  
Followed structure almost exactly; expanded ethical section to include fairness and reproducibility.

---

## Prompt 5
**Prompt:**  
“What are best practices for bias/fairness checks in a sports dataset?”

**LLM Response (summary):**  
- Check representation across teams/drivers.  
- Look for subgroup disparities (rookie vs veteran).  
- Be cautious about interpreting small-sample subgroups.  

**Used/Modified:**  
Used representation check; acknowledged limited subgroup data available.

---

**Note:** All prompts/responses saved here for audit trail. Any edits were annotated in process log and in stakeholder report appendices.
