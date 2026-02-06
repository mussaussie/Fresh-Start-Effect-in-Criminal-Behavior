# Fresh Start Effect in Criminal Behavior
## Do Temporal Landmarks Influence Crime Patterns?

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-red.svg)](https://scikit-learn.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> **Research Question:** Do premeditated crimes show stronger "Fresh Start Effect" patterns compared to impulsive crimes?

---

## Overview

The Fresh Start Effect is a well-documented psychological phenomenon where temporal landmarks—particularly the start of the week (Mondays)—can influence planning-oriented behavior.

### Key Finding

**YES!** — modestly and primarily on Mondays.The analysis shows a statistically significant association between crime type and temporal landmarks. Premeditated crimes display a small positive alignment with landmark timing, while impulsive crimes show a negative alignment.

---

## Key Results

| Metric | Premeditated Crimes | Impulsive Crimes |
|--------|---------------------|------------------|
| Fresh Start Index (FSI) | **Positive** | Lower/Neutral |
| Monday Effect | **Stronger** | Weaker |
| Statistical Significance | p < 0.05 | - |

### Visualizations

#### Day of Week Crime Patterns
![Heatmap](/fresh_start_heatmap.png)
*Premeditated crimes show distinct Monday peaks compared to impulsive crimes*

#### Fresh Start Index Comparison
![FSI Comparison](/fresh_start_index_comparison.png)
*Ranking of crime types by Fresh Start Effect strength*

---

## What's the Fresh Start Effect?

The Fresh Start Effect (Dai, Milkman & Riis, 2014) describes how temporal landmarks create psychological "fresh starts" that motivate goal-directed behavior:


**Temporal landmarks considered in this analysis include:**
- Mondays (primary and most consistent signal)
- 1st of the month (weaker, weekday-dependent)
- Quarter starts (weaker, weekday-dependent)


**Our Hypothesis:** If criminals planning premeditated crimes are influenced by this psychological phenomenon, we should see crime patterns cluster around these temporal landmarks.

---

## Methodology

### 1. Data Collection
- **Source:** South Australia Crime Statistics (2019-2026)
- **Records:** Multiple years of crime data
- **Scope:** All recorded offences with temporal information

### 2. Crime Categorization

**Premeditated Crimes** (require planning):
- Fraud and deception
- Serious criminal trespass (burglary)
- Unlawful entry with intent
- Robbery
- Theft

**Impulsive Crimes** (spontaneous):
- Acts intended to cause injury (assault)
- Dangerous or negligent acts
- Sexual assault
- Abduction

### 3. Temporal Landmark Definition
```python
IsMonday = (DayOfWeek == 0)
IsFirstOfMonth = (Day == 1)
IsStartOfQuarter = date.is_quarter_start
IsLandmark = IsMonday OR IsFirstOfMonth OR IsStartOfQuarter
```

### 4. Fresh Start Index (FSI)
```
FSI = (Actual Landmark Proportion - Expected Proportion) / Expected Proportion
```
- **FSI > 0:** More crimes on landmarks than expected
- **FSI = 0:** No effect
- **FSI < 0:** Fewer crimes on landmarks than expected

### 5. Statistical Testing
- Chi-Square Test for Independence
- Cross-validation for ML models



---

## Installation & Usage

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn jupyter
```

### Quick Start
```bash
# Clone the repository
git clone https://github.com/mussaussie/fresh-start-effect-analysis.git
cd fresh-start-effect-analysis

# Launch Jupyter Notebook
jupyter notebook Fresh_Start_Effect_Analysis.ipynb
```

### Run the Analysis
1. Open `Fresh_Start_Effect_Analysis.ipynb`
2. Run all cells sequentially
3. View results and visualizations

---

## Key Findings Summary

### 1. Statistical Evidence
- Chi-square test confirms **statistically significant** relationship between crime type and temporal landmarks (p < 0.05)
- This pattern is NOT due to random chance

### 2. Fresh Start Index Results
- **Premeditated crimes** show positive FSI (more crimes on landmarks)
- **Impulsive crimes** show weaker/neutral FSI
- Difference is consistent across multiple crime types
- show a consistent Monday-based alignment
- show a relatively stronger alignment compared to impulsive crimes

### 3. Most Susceptible Crime Types
1. Fraud and deception (highest FSI)
2. Serious criminal trespass
3. Theft and related offences
4. Robbery


### The Fresh Start effect in crime appears primarily as a weekly (Monday-based) phenomenon, while monthly and quarterly landmarks show weaker or inconsistent effects due to weekday confounding.
---

## Practical Implications

### For Law Enforcement
- Increase monitoring and preventive attention at the start of the week (Mondays), when planned crimes show higher concentration.
- Enhanced burglary prevention on Mondays
- Optimize resource allocation around temporal landmarks

### For Criminologists
- New research direction: behavioral economics + criminology
- Evidence that psychological factors influence criminal decision-making
- Potential for improved crime prevention strategies

### For Data Scientists
- Add temporal landmark features to crime prediction models
- Consider interaction terms (Premeditated × Landmark)
- Separate models for different crime categories

---

## Limitations

1. **Correlation ≠ Causation:** We observe patterns but cannot prove causal relationship
2. **Reporting Bias:** Data reflects reported crimes, not all crimes committed
3. **Category Overlap:** Some crimes may fit multiple categories
4. **Regional Specificity:** Results are based on South Australia data

---

## Future Research

- [ ] Investigate Fresh Start Effect across different regions/countries
- [ ] Study the effect of major holidays (Christmas, Easter)
- [ ] Explore personal landmarks (birthdays, anniversaries)
- [ ] Develop intervention strategies targeting temporal landmarks
- [ ] Population-adjusted analysis

---

## References

1. Dai, H., Milkman, K. L., & Riis, J. (2014). The Fresh Start Effect: Temporal Landmarks Motivate Aspirational Behavior. *Management Science*, 60(10), 2563-2582.
2. South Australia Police Crime Statistics
3. Scikit-learn: Machine Learning in Python

---


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Contributing

Contributions welcome! Please feel free to submit a Pull Request.

**Areas for contribution:**
- Additional temporal analysis
- Alternative statistical methods
- Cross-regional comparisons
- Visualization improvements

---

## Acknowledgments

- South Australia Police for publishing crime statistics
- Researchers Dai, Milkman & Riis for the Fresh Start Effect framework
- Open-source community for excellent Python libraries

---

**Made with Python, Statistics, and Curiosity about Human Behavior**

*This project demonstrates that psychological phenomena from behavioral economics extend to criminal decision-making, offering new insights for crime prevention and law enforcement resource allocation.*
