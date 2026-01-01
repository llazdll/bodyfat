# Body Fat Measurement Analysis using PCA & EFA

This project analyzes human body measurement data to uncover the latent structure of variables related to **body fat, body size, and body shape** using multivariate statistical techniques in **R**.

---

## Dataset

The dataset contains body measurements from **252 individuals**.  
After preprocessing, the following variables were used:

- weight  
- height  
- neck  
- chest  
- abdomen  
- hip  
- thigh  
- knee  
- ankle  
- biceps  
- forearm  
- wrist  

The first three columns of the original dataset were removed, and only numeric variables were retained.

---

## Requirements

R packages used in this project:

    install.packages("psych")
    library(psych)

Execution environment: **Google Colab (R kernel)**

---

## Preliminary Analysis

### Covariance and Correlation Matrices

- Covariance and correlation matrices were computed.
- Strong correlations were observed among several variables (e.g., abdomen, chest, hip).

### Bartlett’s Test of Sphericity

    cortest.bartlett(bodyfat_corr, n = 252)

- p-value ≈ 0  
- The null hypothesis is rejected.

This confirms that the data is suitable for PCA and factor analysis.

---

## Principal Component Analysis (PCA)

PCA was performed using the **correlation matrix**:

    pca <- princomp(bodyfat, cor = TRUE)

### Variance Explained

| Component | Proportion of Variance | Cumulative Variance |
|----------|------------------------|---------------------|
| PC1 | 67.9% | 67.9% |
| PC2 | 8.7% | 76.6% |

---

## Determining the Number of Components

Three criteria were used:

1. **Kaiser Criterion (eigenvalue > 1)** → 2 components  
2. **Cumulative variance difference** → dominant contribution from early components  
3. **Scree plot** → clear elbow after PC2  

**Final decision:** retain **2 principal components**.

---

## PCA Biplot Interpretation

### High Correlation (Overlapping Vectors)

- abdomen & chest  
- biceps & hip  
- wrist & ankle  

### Near Independence (≈ 90° Angles)

- height vs weight  
- abdomen vs height  
- wrist vs knee  

### Highest Contributions

- PC1: weight, chest  
- PC2: height, forearm  

### Component Naming

- **PC1:** Body Fat / Body Size  
- **PC2:** Body Shape  

---

## Exploratory Factor Analysis (EFA)

EFA was performed using **Maximum Likelihood Estimation**:

    factanal(
      covmat = bodyfat_cov,
      factors = 6,
      method  = "mle",
      n.obs   = 252
    )

The first acceptable model (p-value > 0.05) occurred at **6 factors**, so six latent factors were retained.

---

## Factor Interpretation

### Factor 1 – Body Fat & Overall Size

- abdomen (0.868)  
- chest (0.837)  
- weight (0.733)  
- hip (0.728)  

Represents overall body fat and size.

---

### Factor 2 – Muscularity & Proportions

- biceps (0.658)  
- forearm (0.630)  
- thigh (0.418)  

Represents muscular structure and proportions.

---

### Factor 3 – Skeletal Structure & Height

- height (0.866)  
- wrist (0.831)  

Represents skeletal size and body height.

---

### Factor 4 – Mixed Body Features

- neck  
- knee  
- hip  

Represents distributed upper and lower body characteristics.

---

### Factor 5 – Secondary Lower-Body Structure

- knee (0.651)  
- hip (0.453)  

Represents lower-impact structural features.

---

### Factor 6 – Extremities

- wrist  
- forearm  
- ankle  

Represents hand and foot dimensions.

---

## Visualizations

- Scree Plot  
- PCA Biplot  
- Factor Loading Plots  

(All figures are included in the repository.)

---

## Conclusion

- PCA shows that **2 principal components** explain most of the variance.
- EFA reveals **6 meaningful latent factors** related to fat distribution, muscularity, skeletal structure, and extremities.
- Body width-related measurements are strong indicators of body fat distribution.

---

## Author

Analysis and implementation by **llazdll**

---

## License

This project is intended for **educational and academic purposes**.
