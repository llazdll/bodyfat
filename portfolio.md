title: Human Body Structure Analysis with PCA and EFA 
description: Multivariate analysis of human body measurement data using Principal Component Analysis (PCA) and Exploratory Factor Analysis (EFA) to uncover hidden structures related to body fat, body size, and physical characteristics.
category: Data Science
role: Data Scientist / Statistical Analyst
year: 2026  
status: completed
stack:
- R
- Statistics
- PCA
- Exploratory Factor Analysis
- psych
- Data Visualization  
features:
- Correlation analysis and covariance matrix
- Bartlett's test for factor analysis suitability
- Dimensionality reduction with Principal Component Analysis
- Component selection using Kaiser Criterion and Scree Plot
- Latent factor extraction with Maximum Likelihood Factor Analysis
- Interpretation of Factor Loadings and biological structures

demo: https://llazdll.github.io/bodyfat/
github: https://github.com/llazdll/bodyfat
image: https://storage.googleapis.com/kaggle-datasets-images/1408058/2332711/1864edb79bfd4e883d0682926af447ce/dataset-cover.jpg?t=2021-06-14-12-26-25
featured: true  
stars: 0

---

# Human Body Structure Analysis with PCA and EFA

This project is a **multivariate statistical analysis** of body measurement data from **252 individuals**, aiming to identify hidden structures related to **body fat, overall body size, muscular structure, and skeletal characteristics**.

In this project, relationships between anthropometric variables were first examined. Then, **Principal Component Analysis (PCA)** was used to reduce data dimensions, followed by **Exploratory Factor Analysis (EFA)** to extract latent factors influencing physical characteristics.

---

## ✨ Key Highlights

- Correlation analysis to identify relationships between body measurement variables.
- Confirmation of data suitability for factor analysis using **Bartlett's Test of Sphericity** (χ² = 3673.05, p &lt; 0.001).
- Extraction of **2 principal components** explaining over **76.6%** of the total variance.
- Identification of **Component 1** as a representative of overall body size and fat-related features.
- Extraction of **6 latent factors** using Maximum Likelihood Estimation.
- Scientific interpretation of Factor Loadings to identify various body structures.

---

## 📊 Key Results


| Analysis           | Result                     |
| ------------------ | -------------------------- |
| Bartlett's Test    | χ² = 3673.05, p &lt; 0.001 |
| PCA Components     | 2                          |
| Explained Variance | 76.68%                     |
| EFA Factors        | 6                          |
| Estimation Method  | Maximum Likelihood         |


- **PCA Component 1** explains approximately **67.9%** of the data variance.
- The **first two components** collectively explain approximately **76.6%** of the total variance.
- Variables `weight`, `abdomen`, `chest`, and `hip` have the most significant impact on the main data structure.
- Factor analysis revealed that **body size, musculature, skeletal structure, and limb characteristics** have interpretable latent dimensions.

---

## 🖼️ Analysis Visualizations

### Scree Plot



### PCA Variable Vector Plot



---

## 🔗 Links

- [View Full Project Analysis on GitHub](https://github.com/llazdll/bodyfat)
- [Direct Access to Main Notebook](https://github.com/llazdll/bodyfat/blob/main/Body_fat.ipynb)

---

## 🛠 Technologies

- **Programming Language:** R
- **Platform:** Google Colab (R Kernel)
- **Packages Used:** `psych`

---

## 📁 Project Structure

```
.
├── Body_fat.ipynb              # Main notebook (Google Colab - R)
├── dataset/
│   └── bodyfat.csv             # Dataset file
├── vector.png                  # PCA vector plot
├── pca_screan_plot.png         # PCA scree plot
└── README.md
```

---

## 📚 References

- Jolliffe, I. T. (2002). *Principal Component Analysis*.
- Hair, J. F. et al. *Multivariate Data Analysis*.
- Revelle, W. (2024). *psych: Procedures for Psychological, Psychometric, and Personality Research*.