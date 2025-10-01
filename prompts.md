# 📋 Prompt Log: Formula 1 Sprint Race Analysis (2024 Season)

This file contains natural language questions tested with a large language model (LLM), model responses, and validation using Python.

---

### Prompt: Which driver earned the most sprint points overall?
✅ Answer: Max Verstappen with 38 points  
🧠 Model Accuracy: Correct  
🧪 Validation: `df.groupby("Driver")["Points"].sum().sort_values(ascending=False).head(1)`

---

### Prompt: Which team earned the most sprint points?
✅ Answer: Red Bull Racing Honda RBPT  
🧠 Model Accuracy: Correct  
🧪 Validation: `df.groupby("Team")["Points"].sum().sort_values(ascending=False).head(1)`

---

### Prompt: Which driver had the best average finishing position?
✅ Answer: Max Verstappen (lowest average position)  
🧠 Model Accuracy: Correct  
🧪 Validation:  
```python
df["Position"] = pd.to_numeric(df["Position"], errors="coerce")
df.groupby("Driver")["Position"].mean().sort_values().head(5)
```

---

### Prompt: Which team was the most consistent in sprint races?
✅ Answer: Team with lowest std deviation in finishing positions (e.g., Red Bull)  
🧠 Model Accuracy: Mostly correct  
🧪 Validation: `df.groupby("Team")["Position"].std().sort_values()`

---

### Prompt: Did starting grid position strongly impact final results?
✅ Answer: Yes, positive correlation found  
🧠 Model Accuracy: Correct if LLM mentions correlation strength  
🧪 Validation: `df["Starting Grid"].corr(df["Position"])` → produces correlation coefficient

---

### Prompt: Is there a correlation between improvement and sprint points?
✅ Answer: Yes, mild positive correlation (e.g., ~0.4)  
🧠 Model Accuracy: Acceptable if trend is mentioned  
🧪 Validation:  
```python
df["Improvement"] = df["Starting Grid"] - df["Position"]
df["Improvement"].corr(df["Points"])
```

---

### Prompt: Is there a correlation between starting grid and sprint points?
✅ Answer: Slight to moderate correlation expected  
🧠 Model Accuracy: Partially correct — depends on interpretation  
🧪 Validation: `df["Starting Grid"].corr(df["Points"])`

---

### Prompt: Does improvement in position lead to more points?
✅ Answer: Generally yes, as gaining places tends to score more points  
🧠 Model Accuracy: Acceptable if model links improvement with scoring  
🧪 Validation: Compare `Improvement` and `Points` with correlation and regression plot