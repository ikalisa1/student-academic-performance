# Experiment Plan: Student Academic Performance Prediction

## Overview

This document outlines 7+ systematically designed experiments comparing classical ML and deep learning approaches. Each experiment is incremental, with clear justification and documented hyperparameter choices.

---

## Experiment Structure

| Exp # | Approach | Model | Hyperparameters | Purpose | Notes |
|-------|----------|-------|-----------------|---------|-------|
| 1 | Classical ML | Logistic Regression | C=1.0, penalty='l2', max_iter=1000 | Baseline, interpretable | Simple linear classifier |
| 2 | Classical ML | Random Forest | n_estimators=100, max_depth=10, min_samples_split=5 | Feature importance, ensemble | Moderate complexity |
| 3 | Classical ML | Random Forest | n_estimators=200, max_depth=15, min_samples_split=3 | Improved RF performance | Increased complexity |
| 4 | Classical ML | SVM | C=1.0, kernel='rbf', gamma='scale' | Non-linear decision boundary | Medium complexity |
| 5 | Classical ML | XGBoost | n_estimators=100, max_depth=5, learning_rate=0.1 | Gradient boosting baseline | Strong baseline |
| 6 | Classical ML | XGBoost | n_estimators=200, max_depth=7, learning_rate=0.05 | Optimized XGBoost | Regularized variant |
| 7 | Deep Learning | Sequential (Dense) | 128→64→32→2 layers, dropout=0.3, lr=0.001 | Basic neural network | TensorFlow Sequential API |
| 8 | Deep Learning | Sequential (Dense) | 256→128→64→32→2 layers, dropout=0.5, lr=0.001 | Deeper architecture | Increased capacity |
| 9 | Deep Learning | Functional Multi-Input | Separate embeddings for categorical/numeric, lr=0.001 | Advanced architecture | TensorFlow Functional API |

---

## Experiment Design Rationale

### Progression & Justification

**Experiments 1-2: Classical ML Baselines**
- Simple Logistic Regression establishes interpretable baseline
- Random Forest introduces non-linearity and feature selection
- **Why:** Per Romero & Ventura [1], EDM studies benefit from simple→complex progression

**Experiment 3: RF Hyperparameter Tuning**
- Increases max_depth (10→15) and decreases min_samples_split (5→3)
- Allows deeper trees, more complex feature interactions
- **Why:** Explores bias-variance trade-off; based on validation loss curves from Exp 2

**Experiment 4: Non-Linear SVM**
- RBF kernel captures non-linear relationships
- Provides alternative to tree-based ensemble methods
- **Why:** Thai-Nghe et al. [4] found SVM competitive on student data

**Experiments 5-6: Gradient Boosting**
- XGBoost as strong baseline with feature importance interpretation
- Exp 6 reduces learning_rate (0.1→0.05) and increases n_estimators (100→200)
- **Why:** Regularization to prevent overfitting; per Chen & Pandey [7]

**Experiments 7-8: Deep Learning Architecture**
- Sequential API with progressively deeper networks
- Dropout regularization (0.3→0.5) prevents overfitting
- **Why:** Per Bengio et al. [9], representation learning benefits from depth + regularization

**Experiment 9: Functional Multi-Input API**
- Separate preprocessing branches for categorical and numeric features
- Custom embedding layers for categorical variables
- **Why:** Demonstrates advanced TensorFlow knowledge; tailored to mixed data types

---

## Hyperparameter Justification

### Learning Rate (Deep Learning)
- **Choice: 0.001** - Standard default from Keras documentation
- **Rationale:** Balances convergence speed vs. local minima risk

### Dropout Rates (Deep Learning)
- **Exp 7: 0.3** - Conservative, minimal information loss
- **Exp 8: 0.5** - Moderate regularization per Srivastava et al.
- **Rationale:** Test regularization strength; typical range is 0.2-0.5

### Tree Depth (Classical ML)
- **RF Exp 2: max_depth=10** - Default depth for 649 samples
- **RF Exp 3: max_depth=15** - ~1.5x increase to explore capacity
- **Rationale:** Rule of thumb: max_depth ≈ log₂(n_samples) + 2-3; formula suggests ~10-12

### C Parameter (SVM & Logistic Regression)
- **Choice: 1.0** - Default inverse regularization strength
- **Rationale:** Neutral starting point; can tune based on cross-validation performance

---

## Dataset Splits & Validation Strategy

**All experiments use:**
- Train/Test split: 80/20, stratified by target class
- Cross-validation: 5-fold stratified K-fold for hyperparameter tuning
- Random state: Set to 42 (see config/reproducibility.yaml)

**Rationale:** Per Kabakchieva [5], stratification essential for imbalanced education data; 5-fold balances computational cost vs. robust estimates.

---

## Expected Metrics Output

For each experiment, record:
- **Training accuracy/loss** (per epoch for DL, per fold for classical ML)
- **Validation accuracy/loss** (same)
- **Test accuracy, precision, recall, F1-score**
- **Confusion matrix** (for error analysis)
- **ROC-AUC, precision-recall curve AUC**
- **Feature importance** (for interpretable models)
- **Training time** (minutes)

---

## Interpretation Framework

### For Each Experiment:
1. **Why did performance change?** Reference hyperparameter choices
2. **Underfitting vs. overfitting?** Analyze train/validation loss divergence
3. **Which classes are confused?** Inspect confusion matrix
4. **Is this better than baseline?** Quantify improvement %

### Comparative Analysis:
- Classical ML vs. Deep Learning: Which generalizes better on test set?
- Within-approach comparison: Does deeper/more complex = better?
- Trade-offs: Accuracy vs. interpretability vs. computational cost

---

## Reproducibility Checklist

- [ ] Random seeds set in config/reproducibility.yaml
- [ ] Dataset split logic documented with random state
- [ ] Hyperparameters listed for all 9 experiments
- [ ] Code cells output learning curves, confusion matrices, metrics
- [ ] Results logged to results/experiment_results.csv automatically
- [ ] No manual metric computation; sklearn/TensorFlow metrics only

---

## References

[1] C. Romero and S. Ventura, "Educational data mining and learning analytics," *IEEE Trans. Learn. Technol.*, 2020.
[4] N. Thai-Nghe, T. Janecek, and P. Haddawy, "A comparative analysis of techniques," *FIE 2007*.
[5] D. Kabakchieva, "Student performance prediction," *IJCSMR*, vol. 2, 2013.
[7] J. Chen and B. Pandey, "Academic performance analysis," *ICCES 2020*.
[9] Y. Bengio et al., "Representation learning: A review," *IEEE TPAMI*, vol. 35, 2013.
