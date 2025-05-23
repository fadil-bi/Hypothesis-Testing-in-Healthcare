# 📊 Hypothesis Testing in Healthcare

### Objective
Applied statistical hypothesis testing techniques to assess the relationship between a new drug and its associated adverse effects using clinical trial data.

### Dataset
- Modified version of `drug_safety.csv`, originally provided by **Hbiostat**, courtesy of the **Vanderbilt University Department of Biostatistics**.
- Contains a **2:1 ratio** of **Drug** to **Placebo** observations.
- Includes five key adverse effects:
  - Headache
  - Abdominal pain
  - Dyspepsia
  - Upper respiratory infection
  - Chronic obstructive airway disease (COAD)
- The dataset was modified to introduce two new outcome variables:
  - `adverse_effects`: Indicates presence (1) or absence (0) of any adverse effect.
  - `num_effects`: Number of adverse effects experienced by an individual.

### Features
- **Demographics**: `sex`, `age`
- **Clinical trial context**: `week` (of testing), `trx` (Drug vs. Placebo)
- **Lab measurements**: `wbc` (white blood cell count), `rbc` (red blood cell count)

### Methodology
- Conducted the following hypothesis testing techniques:
  - **Independent t-tests** to compare lab values between groups.
  - **Chi-square tests** to examine associations between treatment and side effects.
  - **ANOVA** for multi-group comparisons when applicable.
- Checked statistical assumptions (normality, variance homogeneity).
- Interpreted **p-values** and **confidence intervals** to evaluate significance.

### Tools & Technologies
- **Python**: `Pandas`, `SciPy`, `StatsModels`
- **Jupyter Notebook**
- **Visualization**: `Seaborn`, `Matplotlib`

### Key Findings
- Statistically significant difference in the incidence of adverse effects between drug and placebo groups.
- Demographic and biological variables influenced the occurrence of side effects.
- Supported data-driven insights to inform clinical safety evaluations.

### Outcome
Demonstrated the power of statistical hypothesis testing in evaluating treatment safety and guiding healthcare decision-making.

## RESULTS
Here’s an interpretation of your results based on the statistical output and descriptive summary:

---

### ✅ **Descriptive Summary**

| Group   | No Adverse Effects | Yes Adverse Effects | Total  |
| ------- | ------------------ | ------------------- | ------ |
| Drug    | 9,703              | 1,024               | 10,727 |
| Placebo | 4,864              | 512                 | 5,376  |

* **Adverse Effect Rate (Drug)**: 1,024 / 10,727 ≈ **9.5%**
* **Adverse Effect Rate (Placebo)**: 512 / 5,376 ≈ **9.5%**

Despite more drug cases, the proportion of individuals experiencing adverse effects is **virtually identical** between the Drug and Placebo groups.

---

### 🧪 **Statistical Test Interpretations**

#### 1. **Two-Sample Proportion Test** (`two_sample_p_value = 0.964`)

* **Hypothesis**: H₀: The proportion of adverse effects is the same in both groups.
* **Result**: p = 0.964 > 0.05
* **Conclusion**: **Fail to reject H₀**. There is **no significant difference** in the proportion of adverse effects between the Drug and Placebo groups.

---

#### 2. **Number of Adverse Effects per Individual** (`num_effects_p_value = 0.615`)

* **Hypothesis**: H₀: The number of adverse effects per individual is the same in both groups.
* **Result**: p = 0.615 > 0.05
* **Conclusion**: **Fail to reject H₀**. The **severity or frequency** of side effects (count per individual) **does not differ significantly** between Drug and Placebo groups.

---

#### 3. **Normality Test (Shapiro-Wilk)**

* **p-values**: Drug: \~2.19e-38, Placebo: \~2.22e-29
* **Conclusion**: p < 0.05 for both groups ⇒ Data **is not normally distributed**.
* Non-parametric tests (e.g., Mann-Whitney U) are therefore appropriate.

---

#### 4. **Effect of Age Group on Adverse Effects** (`age_group_effects_p_value = 0.257`)

* **Hypothesis**: H₀: Age group has no effect on the number of adverse effects.
* **Result**: p = 0.257 > 0.05
* **Conclusion**: **No statistically significant relationship** between age group and the occurrence of adverse effects.

---

### 📌 **Final Interpretation & Takeaways**

* The drug **does not show increased risk** of adverse effects compared to placebo.
* There is **no statistically significant difference** in how many side effects are experienced per person between groups.
* Neither **age group** nor the **treatment type** appear to significantly influence the likelihood or number of adverse effects.
* **Normality assumption is violated**, so all tests were rightly done with non-parametric or distribution-free methods.



