# 🌍 World Happiness Report Analysis (2005–2021)

**CS 133: Introduction to Data Visualization**  
San Jose State University | Spring 2025  
Author: Bushra Naveed

---

## Overview

This project analyzes global happiness data from 2005 to 2021 to uncover what socioeconomic and emotional factors most strongly predict national well-being. Using a dataset of 2,089 records across 165+ countries, we explore how wealth, social support, life expectancy, freedom, and government trust relate to happiness scores.

The project combines exploratory data visualization with machine learning regression models to identify the strongest predictors of happiness.

---

## Dataset

**Source:** [World Happiness Dataset (2005–2021)](https://raw.githubusercontent.com/csbfx/cs133/main/world_happiness_2005-2021.csv)

| Column | Description | Scale |
|---|---|---|
| Country | Country name | — |
| Year | Survey year | 2005–2021 |
| Happiness | Life ladder score | 0–10 |
| Wealth | Log GDP per capita | ~5–12 |
| Social Support | Proportion with social support | 0–1 |
| Life Expectancy | Healthy life expectancy at birth | ~6–75 yrs |
| Freedom | Perceived freedom of choice | 0–1 |
| Generosity | Charitable donations (scaled) | 0–1 |
| Perceived Corruption | Corruption perception | 0–1 |
| Positive Affect | Frequency of positive emotions | 0–1 |
| Negative Affect | Frequency of negative emotions | 0–1 |
| Trust in Government | Confidence in government | 0–1 |

> The dataset is publicly available via the link above. Place it in the `data/` folder as `world_happiness_2005-2021.csv` before running the notebook.

---

## Project Structure

```
world-happiness-analysis/
├── README.md
├── requirements.txt
├── data/
│   └── world_happiness_2005-2021.csv   ← download from link above
├── notebooks/
│   └── world_happiness_analysis.ipynb  ← main analysis notebook
├── visualizations/
│   └── *.png                           ← exported charts
└── reports/
    └── CS133_World_Happiness_Report.pdf
```

---

## Key Findings

- **Wealth, Social Support, and Life Expectancy** are the strongest predictors of happiness (correlations of 0.79, 0.71, and 0.72 respectively).
- **Trust in Government** showed near-zero correlation with happiness across most countries.
- **Nordic countries** (Finland, Denmark, Iceland) consistently ranked highest in happiness from 2017–2021.
- Countries with high social support score about **1–1.5 points higher** on the happiness scale than low-support countries.
- Freedom amplifies the positive effects of wealth and health on happiness.

---

## Machine Learning Models

Four regression models were trained to predict happiness scores:

| Model | R² Score | MSE |
|---|---|---|
| Linear Regression | 0.779 | 0.281 |
| KNN Regressor | 0.680 | 0.407 |
| Decision Tree Regressor | 0.738 | 0.334 |
| **Random Forest Regressor** | **0.888** | **0.143** |

**Random Forest** was the best-performing model, validated with 5-fold cross-validation (avg CV R² = 0.862).

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/world-happiness-analysis.git
   cd world-happiness-analysis
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download the dataset and place it in `data/`:
   ```
   https://raw.githubusercontent.com/csbfx/cs133/main/world_happiness_2005-2021.csv
   ```

4. Open and run the notebook:
   ```bash
   jupyter notebook notebooks/world_happiness_analysis.ipynb
   ```

   Or open directly in [Google Colab](https://colab.research.google.com/drive/1O2wOxVzBzZMH8bc0ZXl-rTUf5QzLjRGF?usp=sharing).

---

## References

- [Dataset](https://raw.githubusercontent.com/csbfx/cs133/main/world_happiness_2005-2021.csv)
- [Project Presentation (Google Slides)](https://docs.google.com/presentation/d/1XXyCFKxorkFgHFJPZ38JJN0-XaPfU5slc1A5NS0CiYU/edit?usp=sharing)
- [Google Colab Notebook](https://colab.research.google.com/drive/1O2wOxVzBzZMH8bc0ZXl-rTUf5QzLjRGF?usp=sharing)
- [World Happiness Report](https://worldhappiness.report/)
