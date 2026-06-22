# Predicting Student Academic Performance and At-Risk Status Using Machine Learning and Deep Learning

## Problem Statement

Student academic underperformance and dropout represent significant challenges in educational institutions globally. Early identification of at-risk students enables timely intervention, improving retention rates and student outcomes. This project applies both classical machine learning and deep learning approaches to predict student academic performance and at-risk status using multi-modal educational data.

## Project Objectives

1. Develop interpretable machine learning models for student performance prediction
2. Compare classical ML (Scikit-learn) and deep learning (TensorFlow) approaches systematically
3. Engineer domain-specific features capturing academic and behavioral patterns
4. Conduct rigorous experiments with 7+ varied hyperparameter configurations
5. Provide actionable insights for educational policy and intervention strategies

## Dataset

**Source:** Student Academic Performance Dataset (UCI Machine Learning Repository)  
**Size:** 649 students, 33 features  
**Features:** Academic metrics, behavioral indicators, socioeconomic factors, engagement levels  
**Task:** Binary/Multi-class classification (Performance: High/Medium/Low or At-Risk: Yes/No)

## Methodology

### Classical Machine Learning Approaches
- Logistic Regression
- Random Forest Classifier
- Support Vector Machine (SVM)
- Gradient Boosting (XGBoost)

### Deep Learning Approaches
- Sequential API (Dense networks)
- Functional API (Multi-input architecture)
- Regularization techniques (Dropout, L2)
- Hyperparameter optimization

### Evaluation Metrics
- Accuracy, Precision, Recall, F1-Score
- Confusion Matrices & ROC-AUC curves
- Learning curves (train/validation loss)
- Feature importance analysis

## Project Structure

```
.
├── README.md                          # Project overview
├── data/
│   └── student_performance.csv        # Dataset (to download)
├── notebooks/
│   └── student_academic_performance.ipynb  # Main analysis notebook
├── config/
│   └── reproducibility.yaml           # Random seeds & hyperparameters
├── results/
│   ├── experiment_results.csv         # Experiments table
│   ├── confusion_matrices/            # Visualizations
│   ├── roc_curves/
│   └── learning_curves/
├── reports/
│   └── Academic_Report.docx           # 3500-5000 word report
└── video/
    └── demo_presentation.mp4          # 5-10 minute video
```

## Key Deliverables

✅ **Well-documented Jupyter notebook** with modular, reproducible code  
✅ **Comprehensive experiment table** (7+ experiments with detailed analysis)  
✅ **Academic report** (3500-5000 words, IEEE citations, <20% AI-generated)  
✅ **Professional demo video** (5-10 minutes with face visible)  
✅ **GitHub repository** with full reproducibility  

## Usage

1. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Download dataset:**
   - Visit [UCI ML Repository](https://archive.ics.uci.edu/ml/index.php)
   - Search "Student Academic Performance"
   - Place CSV in `data/` folder

3. **Run notebook:**
   - Open `notebooks/student_academic_performance.ipynb`
   - Execute cells top-to-bottom (seeds set for reproducibility)

4. **View results:**
   - Check `results/experiment_results.csv` for experiment table
   - Review learning curves and confusion matrices in `results/`

## Citation & References

All sources cited in IEEE format. Literature review includes 10+ peer-reviewed academic sources covering:
- Educational data mining
- Student retention prediction
- Deep learning in education
- Fairness and interpretability in ML

See Academic Report for full reference list.

## Author

[Your Name]  
ALU - Introduction to Machine Learning Summative Project  
June 2026

---

**GitHub Repository:** [Link to your repo]  
**Demo Video:** [Link to your video]
