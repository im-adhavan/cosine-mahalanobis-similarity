# Cosine Similarity vs Mahalanobis Distance  
### A Comparative Study of Similarity Measures in High-Dimensional Spaces

## Abstract
Similarity and distance measures are foundational tools in machine learning, pattern recognition, and statistical inference. This project presents a focused comparative analysis of **Cosine Similarity** and **Mahalanobis Distance**, examining their theoretical properties, geometric interpretations, and empirical behavior under correlated and uncorrelated feature settings.

Through controlled experiments and visual analysis, this work highlights when scale-invariant, angle-based similarity is sufficient, and when covariance-aware distance metrics provide fundamentally superior representations of structure in data.

---

## Motivation
In many machine learning pipelines, similarity is treated as a black-box operation. However, the choice of metric implicitly encodes strong assumptions about feature independence, scale, and geometry.

- **Cosine Similarity** assumes direction matters more than magnitude and ignores feature covariance.
- **Mahalanobis Distance** explicitly models feature correlations and rescales space accordingly.

Understanding the consequences of these assumptions is critical in domains such as:
- High-dimensional embeddings
- Speech and signal processing
- Anomaly detection
- Metric learning and representation learning

This repository aims to make those differences explicit, both mathematically and empirically.

---

## Theoretical Background

### Cosine Similarity
Cosine similarity measures the cosine of the angle between two vectors:
\[
\text{cosine}(x, y) = \frac{x \cdot y}{\|x\|\|y\|}
\]

Key properties:
- Scale-invariant
- Insensitive to magnitude
- Ignores feature correlations

Effective when vector direction encodes semantic meaning (e.g., embeddings).

---

### Mahalanobis Distance
Mahalanobis distance measures distance under a covariance-adjusted metric:
\[
d_M(x, y) = \sqrt{(x - y)^T \Sigma^{-1} (x - y)}
\]

Key properties:
- Accounts for feature variance and correlation
- Reduces to Euclidean distance when covariance is identity
- Statistically grounded in multivariate Gaussian theory

Essential when features are correlated or live in anisotropic spaces.

---

## Methodology
1. Data generation and preprocessing
2. Covariance estimation
3. Distance and similarity computation
4. Comparative visualization and analysis
5. Interpretation of geometric and statistical behavior

All experiments are implemented in a single, self-contained Jupyter notebook for clarity and reproducibility.

---

## Key Observations
- Cosine similarity performs well when magnitude is irrelevant and features are roughly independent.
- Mahalanobis distance significantly outperforms cosine-based measures when feature correlations exist.
- Ignoring covariance can lead to misleading similarity judgments in high-dimensional spaces.

These results reinforce the importance of metric choice as a modeling decision, not a technical detail.

---

## Repository Structure
.
├── cosinemahalanobi.ipynb # Main analysis notebook

├── requirements.txt # Python dependencies

├── .gitignore

└── README.md


---

## Reproducibility

### Installation
```bash
pip install -r requirements.txt
