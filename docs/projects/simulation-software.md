# 🔬 Scientific Computing & Mathematical Modeling

[![ScienceDirect](https://img.shields.io/badge/ScienceDirect-Published_Paper-orange?style=flat)](https://www.sciencedirect.com/science/article/abs/pii/S0021967325001049)

!!! abstract "Publication Overview"
    The foundation of any robust Artificial Intelligence model is mathematical rigor and the ability to model complex phenomena from noisy data. In this section, I present my work focused on mechanistic modeling and algorithmic optimization, published in the **Journal of Chromatography A (Elsevier, 2025)**[cite: 3].

    This project exemplifies the application of advanced joint parameter estimation techniques and *overfitting* mitigation to solve real process engineering problems[cite: 3], acting as the technical bridge between my Industrial Biotechnology background and my role as a Machine Learning Engineer.

---

## 📄 The Scientific Paper

**Title:** *Microplate approach to resin screening and parameter estimation applied to chromatography column modeling of gradient elution operation*[cite: 3]
**Authors:** Felipe Coelho Vieira, Willian Kopp, Felipe Fernando Furlan, Thiago Faggion de Pádua, Marcelo Perencin de Arruda Ribeiro[cite: 3]
**Publication Date:** April 12, 2025[cite: 3]

### The Computational and Business Challenge
Chromatographic separation process development is notoriously data-intensive and consumes significant time and material resources[cite: 3]. Using phenomenological (mechanistic) models to simulate and optimize these processes often hits a snag in obtaining precise estimates for the model's parameters[cite: 3].

In the traditional approach (inverse method), parameters are estimated by trying to find the best fit (*best fit*) directly from the chromatogram, but this method suffers from high parameter correlation, which increases uncertainty and harms confidence in model predictions[cite: 3].

### The Algorithmic Solution (Joint Estimation)
To solve parameter uncertainty and optimize data usage, we developed and proposed a new algorithmic method:

* **Data Integration (Data Fusion):** The study introduces a joint estimation procedure that integrates noisy microplate screening data (*batch data*) with data from a single column experiment[cite: 3].
* **Optimization Pipeline:** Initial estimates of equilibrium isotherm parameters were derived from screening data and then refined by incorporating chromatogram data to simultaneously estimate mass transport parameters[cite: 3].
* ***Overfitting* Prevention:** We used advanced mathematical techniques, applying weighted least squares (*weighted least squares*) together with the *l-curve method* to define an appropriate weighting matrix[cite: 3]. Results showed that the use of the L-curve effectively mitigated model *overfitting*[cite: 3].

---

## ⚙️ Technical Translation: From Biotechnology to AI/MLOps

Although the application domain of this article is fine chemistry and bioharma, the solution architecture reflects fundamental principles of **Machine Learning Engineering**:

| Scientific Concept | Equivalent in Machine Learning / AI |
|---------------------|---------------------------------------|
| **Parameter Estimation** | Model Training / Weight Optimization (Gradient Descent). |
| **l-curve method** | Regularization (L1/L2) and *Hyperparameter Tuning* to prevent *overfitting*. |
| **Weighted Least Squares** | Definition of custom *Loss Functions* (Cost Functions). |
| **Phenomenological Modeling** | *First-Principles* predictive modeling (White-box models). |

!!! success "Results and Predictive Accuracy"
    The effectiveness of our method was rigorously validated. While the isolated use of equilibrium parameters predicted a retention volume with an error of $8.9\%$ relative to experimental results, **the prediction using our joint estimation reduced the error to only $0.8\%$ in the best scenario**[cite: 3]. This proves our mathematical modeling's ability to capture the real signal of the system, ignoring noise and ensuring extreme accuracy[cite: 3].

---

## 🧠 My Role and Technical Leadership

According to the official contribution statement (*CRediT authorship contribution statement*) of the article, my work on the project encompassed[cite: 3]:

* **Conceptualization & Methodology:** Conception of the solution architecture and algorithmic methodology design[cite: 3].
* **Formal Analysis & Data Curation:** Raw data processing, formal analysis, and *outliers* removal to ensure the integrity of the *datasets* that fed the models[cite: 3].
* **Project Administration & Resources:** Project management and funding resource acquisition[cite: 3].