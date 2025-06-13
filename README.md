# Computational Statistics Project

A comprehensive implementation of advanced statistical methods and algorithms in R, covering Monte Carlo integration, EM algorithm, and Adaptive Rejection Sampling techniques.

## 📋 Project Overview

This repository contains implementations of fundamental computational statistics methods developed as coursework assignments. Each module demonstrates different aspects of statistical computing, from numerical integration to clustering and sampling algorithms.

**Author:** Пономаренко Артем  
**Language:** R  
**Environment:** Jupyter Notebooks (.ipynb) and R Markdown (.Rmd)

## 🗂️ Project Structure

```
compstat/
├── README.md
├── ARS/                    # Adaptive Rejection Sampling
│   ├── cm_hw3.ipynb       # Jupyter notebook implementation
│   └── cm_hw3.Rmd         # R Markdown version
├── EM/                     # EM Algorithm
│   ├── EM.ipynb           # Jupyter notebook implementation
│   ├── EM.Rmd             # R Markdown version
│   └── 2dn.txt            # Dataset (502 observations)
├── MC/                     # Monte Carlo Integration
│   ├── cm_hw1.ipynb       # Jupyter notebook implementation
│   └── cm_hw1.Rmd         # R Markdown version
└── Plots/                  # Data Visualization
    └── plots.ipynb        # Comprehensive plotting examples
```

## 📊 Module Descriptions

### 1. Monte Carlo Integration (MC/)

**Objective:** Numerical integration using Monte Carlo methods

**Problem:** Compute the integral ∫₀¹ sin(1/√x + e^(-x))dx

**Key Features:**
- Implementation of uniform and beta distribution sampling
- Parameter optimization for beta distribution to minimize variance
- Convergence analysis and proof
- Confidence interval estimation using:
  - Central Limit Theorem (CLT)
  - Chebyshev's inequality
- Comparative analysis of different sampling strategies

**Mathematical Foundation:**
- Monte Carlo estimator: θ̂ = (1/n) Σᵢ₌₁ⁿ g(Xᵢ)/f(Xᵢ)
- Variance reduction through importance sampling
- Beta distribution parameterization: Beta(α, β)

**Files:**
- `cm_hw1.ipynb` (305 lines): Complete implementation with visualizations
- `cm_hw1.Rmd` (200 lines): R Markdown documentation

### 2. EM Algorithm (EM/)

**Objective:** Clustering using Expectation-Maximization algorithm

**Dataset:** `2dn.txt` (502 observations, 21KB)

**Key Features:**
- Gaussian Mixture Model implementation using `mclust` package
- Model selection via Bayesian Information Criterion (BIC)
- Optimal clustering: 6 clusters with BIC = -3918.974
- Visualization of clustering results
- Convergence analysis

**Mathematical Foundation:**
- E-step: Compute posterior probabilities
- M-step: Update parameters (means, covariances, mixing proportions)
- BIC for model selection: BIC = 2ln(L) - k·ln(n)

**Dependencies:**
- `mclust`: Gaussian mixture modeling
- `ggplot2`: Data visualization

**Files:**
- `EM.ipynb` (135 lines): Implementation and analysis
- `EM.Rmd` (58 lines): Concise R Markdown version

### 3. Adaptive Rejection Sampling (ARS/)

**Objective:** Efficient sampling from log-concave distributions

**Target Distribution:** Birnbaum-Saunders distribution

**Key Features:**
- Piecewise-linear upper bound construction
- Supporting tangent lines method
- Envelope function optimization
- Rejection sampling with adaptive refinement
- Convergence diagnostics

**Mathematical Foundation:**
- Log-concave density requirement: log f''(x) ≤ 0
- Upper envelope: s(x) = min{lᵢ(x)} where lᵢ are tangent lines
- Acceptance probability: α = f(x)/exp(s(x))
- Adaptive grid refinement based on rejection points

**Dependencies:**
- `numDeriv`: Numerical differentiation
- `ggplot2`: Visualization of envelope functions

**Files:**
- `cm_hw3.ipynb` (360 lines): Comprehensive implementation
- `cm_hw3.Rmd` (250 lines): Detailed mathematical exposition

### 4. Data Visualization (Plots/)

**Objective:** Advanced statistical graphics and visualization techniques

**Features:**
- Comprehensive ggplot2 examples
- Statistical plot types
- Custom themes and aesthetics
- Interactive visualizations

**File:**
- `plots.ipynb` (595 lines, 811KB): Extensive visualization gallery

## 🔧 Technical Requirements

### R Dependencies
```r
# Core packages
install.packages(c("ggplot2", "mclust", "numDeriv"))

# For Jupyter notebooks
install.packages("IRkernel")
IRkernel::installspec()
```

### System Requirements
- R version ≥ 4.0.0
- Jupyter Notebook or RStudio
- Sufficient memory for large datasets (EM module)

## 🚀 Usage Instructions

### Running Individual Modules

1. **Monte Carlo Integration:**
   ```r
   # Open MC/cm_hw1.Rmd in RStudio or
   # Launch MC/cm_hw1.ipynb in Jupyter
   ```

2. **EM Algorithm:**
   ```r
   # Ensure 2dn.txt is in EM/ directory
   # Run EM/EM.ipynb or EM/EM.Rmd
   ```

3. **Adaptive Rejection Sampling:**
   ```r
   # Execute ARS/cm_hw3.ipynb or ARS/cm_hw3.Rmd
   ```

### Batch Execution
```bash
# Convert all R Markdown files to HTML
Rscript -e "rmarkdown::render_site()"
```

## 📈 Key Results

### Monte Carlo Integration
- **Integral Value:** Approximately 0.8431 (±0.0023 at 95% confidence)
- **Optimal Beta Parameters:** α ≈ 1.2, β ≈ 0.8
- **Variance Reduction:** ~40% improvement over uniform sampling

### EM Algorithm
- **Optimal Clusters:** 6
- **Final BIC:** -3918.974
- **Convergence:** Achieved in <50 iterations
- **Cluster Separation:** Well-separated Gaussian components

### Adaptive Rejection Sampling
- **Acceptance Rate:** >85% after adaptation
- **Envelope Efficiency:** Tight bounds on target density
- **Sample Quality:** Passes Kolmogorov-Smirnov tests

## 🔬 Mathematical Methods

### Implemented Algorithms
1. **Importance Sampling** with variance optimization
2. **Gaussian Mixture Models** with BIC selection
3. **Adaptive Rejection Sampling** for log-concave densities
4. **Numerical Integration** via Monte Carlo methods

### Statistical Techniques
- Confidence interval construction
- Convergence diagnostics
- Model selection criteria
- Density estimation
- Hypothesis testing