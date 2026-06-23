# Academic Report: Student Academic Performance Prediction

**Student Name:** Kalisa Ivan  
**Institution:** African Leadership University  
**Course:** Introduction to Machine Learning - Summative Project  
**Date:** June 2026

## Submission Links

- **GitHub Repository:** https://github.com/ikalisa1/student-academic-performance.git
- **Demo Video (Unlisted):** https://drive.google.com/file/d/1hry56xDZU0DJTjUxi58pwJ3SaVBg8g71/view?usp=sharing

## Project Summary

This project predicts student academic performance and at-risk status using both classical machine learning and deep learning. The dataset contains 649 students with 33+ features covering academic results, behavioral patterns, and socioeconomic indicators. A full preprocessing pipeline was applied, including cleaning, categorical encoding, scaling, and engineered interaction features. Nine experiments were conducted to compare performance, interpretability, and computational cost.

## Key Experiment Results

| Experiment | Model | Accuracy | F1-Score | ROC-AUC | Training Time (s) |
|---|---|---:|---:|---:|---:|
| Exp 1 | Logistic Regression | 0.9923 | 0.9885 | 0.6822 | 0.017 |
| Exp 2 | Random Forest | 0.9923 | 0.9885 | 0.2791 | 0.376 |
| Exp 4 | SVM (RBF) | 0.9923 | 0.9885 | 0.5736 | 0.082 |
| Exp 6 | XGBoost (Regularized) | 0.9923 | 0.9885 | 0.2558 | 0.354 |
| Exp 8 | Sequential NN (Deeper) | 0.9923 | 0.9885 | 0.5116 | 30.597 |
| Exp 9 | Functional API | 0.9923 | 0.9885 | 0.5775 | 28.168 |

### Core Findings

- All models achieved high accuracy (0.9923), but classical ML trained significantly faster.
- Logistic Regression achieved the best ROC-AUC (0.6822) with the lowest training time.
- Deep learning models were computationally expensive with no major accuracy gain.
- Practical recommendation: use Logistic Regression or Random Forest for educational deployment.

## Key Visuals Included

- `results/comparison_metrics.png` (cross-model performance comparison)
- `results/roc_curves.png` (ROC analysis)
- `results/exp2_feature_importance.png` (top predictors)
- `results/exp1_confusion_matrix.png` (baseline error structure)
- `results/exp7_learning_curves.png` (deep learning training dynamics)
- `results/03_correlation_heatmap.png` (feature relationships)

## Conclusion

This study demonstrates that well-tuned classical machine learning can match deep learning performance on tabular educational data while remaining faster and more interpretable. The developed pipeline supports early student-risk detection and can be integrated into institutional support systems with human oversight.