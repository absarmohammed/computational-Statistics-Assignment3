# Computational Statistics Assignment 3

## Overview

This repository contains solutions to four computational statistics problems covering Monte Carlo integration, stratified sampling, bootstrap analysis, and hypothesis testing simulations.

## Project Structure

```
computational Statistics Assignment3/
├── notebooks/
│   └── main.ipynb          # Main Jupyter notebook with all solutions
├── data/
│   └── faithful.csv        # Old Faithful geyser dataset
├── artifacts/
│   ├── bootstrap_histogram.png
│   ├── type1_error_plot.png
│   └── question_snipped/   # Problem statement images
└── README.md
```

## Problems Solved

### Problem 1: Monte Carlo Integration with Control Variates

**Objective**: Estimate the integral I = ∫₀¹ xe^(-x²)dx using control variates for variance reduction.

**Key Results**:

- Analytical expectations calculated for three control variates
- Best control variate selected based on correlation analysis (n=5,000)
- Variance reduction achieved: ~85-90%
- Efficiency gain: ~7x improvement over standard Monte Carlo

### Problem 2: Stratified Sampling

**Objective**: Estimate I = ∫₀¹ sin(πx)/(1+x)dx comparing two stratification strategies.

**Approaches**:

- **Plan A**: 10 equal intervals with equal allocation
- **Plan B**: 5 equal strata with proportional allocation based on variance

**Key Results**:

- Both plans significantly reduce variance compared to standard MC
- Plan A shows superior performance with ~95% variance reduction
- Demonstrates importance of stratification in numerical integration

### Problem 3: Bootstrap Analysis of Correlation

**Objective**: Analyze correlation between eruption time and waiting time in Old Faithful geyser data.

**Methods**:

- Original correlation: ~0.90 (strong positive)
- 10,000 bootstrap samples generated
- 90% confidence interval computed
- Standard error and bias estimated

**Key Findings**:

- Very small bias (~0.0001)
- Narrow confidence interval indicating stable estimate
- Bootstrap distribution approximately normal

### Problem 4: Type I Error Simulation

**Objective**: Test t-test robustness under non-normal distributions.

**Distributions Tested**:

1. **χ²(1)**: Highly right-skewed
2. **Uniform(0,2)**: Symmetric but non-normal
3. **Exponential(rate=1)**: Right-skewed

**Sample Sizes**: n ∈ {10, 30, 50, 100}

**Key Findings**:

- Uniform distribution: Excellent performance across all sample sizes
- Skewed distributions: Type I error inflation for small n, convergence for large n
- Central Limit Theorem effect clearly visible
- Recommendation: Use n ≥ 30 for skewed distributions

## Requirements

### Python Libraries

```python
numpy
matplotlib
pandas
seaborn
scipy
```

### Installation

```bash
pip install numpy matplotlib pandas seaborn scipy
```

## Usage

1. **Open the Jupyter Notebook**:

   ```bash
   jupyter notebook notebooks/main.ipynb
   ```

2. **Run All Cells**: Execute cells sequentially from top to bottom

3. **View Results**:
   - Numerical results displayed in console output
   - Visualizations saved to `artifacts/` directory

## Expected Runtime

- Problem 1: ~1 second
- Problem 2: ~2 seconds
- Problem 3: ~3 seconds
- Problem 4: ~60-90 seconds (10,000 replications × 3 distributions × 4 sample sizes)

**Total**: Approximately 1.5-2 minutes for complete execution

## Key Concepts Demonstrated

1. **Variance Reduction Techniques**

   - Control variates method
   - Stratified sampling
   - Optimal allocation strategies

2. **Resampling Methods**

   - Bootstrap sampling
   - Confidence interval estimation
   - Bias and standard error calculation

3. **Hypothesis Testing**

   - Type I error rate analysis
   - Robustness of parametric tests
   - Effect of sample size on test performance

4. **Simulation Studies**
   - Monte Carlo methods
   - Numerical integration
   - Statistical inference validation

## Results Interpretation

### Monte Carlo Integration

- Control variates provide substantial variance reduction
- Best control variate: f₃(x) = e^(-x) with correlation ~0.93
- Efficiency gain allows for accurate estimates with fewer samples

### Stratified Sampling

- Proper stratification crucial for variance reduction
- Equal allocation (Plan A) outperformed proportional allocation (Plan B)
- Both methods superior to standard Monte Carlo

### Bootstrap Analysis

- Strong positive correlation (0.90) between eruption time and waiting time
- Bootstrap distribution stable with minimal bias
- Confidence interval: [0.886, 0.915]

### Type I Error Simulation

- T-test robust for symmetric distributions even with small samples
- Skewed distributions require larger samples (n≥30) for nominal error rate
- Sample size more important than distributional shape for large n

## References

- Rizzo, M. L. (2019). Statistical Computing with R (2nd ed.)
- Efron, B., & Tibshirani, R. J. (1994). An Introduction to the Bootstrap
- Ross, S. M. (2013). Simulation (5th ed.)

## Author

Course: CM 3430 Computational Statistics

## License

This project is for educational purposes.
