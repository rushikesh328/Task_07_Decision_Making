# 🏎️ F1 Sprint Race Analysis – Research Tasks 7

This repository contains analysis, reports, and documentation for Research Tasks 7, using the **Formula 1 2024 Sprint Results dataset**.  
The project explores descriptive statistics, narrative generation, deepfake interview creation, and an ethical stakeholder-facing decision report.

---

## **Run analyses:**
   - Descriptive stats:
     ```bash
     python code/analysis.py
     ```
   - Generate uncertainty plots:
     ```bash
     python code/uncertainty_plots.py
     ```
   - Produce audio interview:
     ```bash
     python tts_generate.py --script script_example.txt        --voice_a en-US-JennyNeural --voice_b en-GB-RyanNeural        --out outputs/interview_mix.mp3
     ```

---

## Key Findings
- **Top driver:** Max Verstappen (highest sprint points, 38).  
- **Top team:** Red Bull Racing (most consistent performance).  
- **Correlation:** Starting grid strongly linked to finishing position (r ≈ 0.45, p < 0.01).  
- **Improvement vs Points:** Drivers gaining positions scored more points.  
- **Uncertainty:** Bootstrap CIs confirmed robustness; findings unchanged after sensitivity tests.  

---

## Recommendations (Tiered)
- **Low risk (operational):** Target sprint start training; practice tire strategy scenarios.  
- **Medium risk (investigatory):** Pilot alternative qualifying strategies; collect sector data.  
- **High risk:** Consider personnel adjustments only with multi-race validation.  

---

## ⚖️ Ethical Considerations
- **Privacy:** Data is public sports performance — low risk.  
- **Bias/Fairness:** Smaller teams underrepresented in podium finishes; risk of reinforcing existing dominance.  
- **Reproducibility:** All code, logs, and LLM prompts preserved for audit.  

---

## Reports & Figures
- [Stakeholder Report](report/stakeholder_report.md)  
- [Process Log](logs/process_log.md)  
- [Prompt Log](logs/prompt_log.md)  

Figures:  
- Driver Improvement CI
- Team Position CI

---

## Next Steps
- Extend analysis to **full race weekends** (not just sprints).  
- Validate with **FIA official stats**.  
- Collaborate with domain experts for strategy-specific insights.  
- Explore fairness-aware evaluation methods.  

---
