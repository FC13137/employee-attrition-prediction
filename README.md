# Employee Attrition Prediction

A machine learning project for predicting employee attrition using various classification algorithms.

## 📋 Project Overview

This project implements multiple machine learning models to predict employee attrition (whether an employee will leave the company) based on various employee attributes and work-related features.

**Student**: Chenzi Fang (ID: 2036451)  
**Course**: INT303 Assignment 2  
**Institution**: XJTLU

## 🎯 Objective

Build and compare different machine learning models to predict employee attrition, evaluating their performance with and without PCA (Principal Component Analysis) dimensionality reduction.

## 📊 Dataset

The dataset contains employee information including:
- Demographics (Age, Gender, Marital Status)
- Job-related features (Department, Job Role, Job Level)
- Work-life balance metrics
- Compensation and benefits
- Performance ratings
- **Target variable**: Attrition (Yes/No)

## 🔧 Data Preprocessing

1. **Removed constant columns**: `EmployeeCount`, `Over18`, `StandardHours`
2. **Handled missing values**: Dropped rows with missing values
3. **Removed duplicates**: Eliminated duplicate records
4. **Feature encoding**:
   - One-Hot Encoding: `Gender`, `JobRole`, `EducationField`, `Department`, `BusinessTravel`, `MaritalStatus`
   - Manual encoding: `OverTime` (Yes/No → 1/0), `Over18` (Y/N → 1/0)
5. **Feature scaling**: Standardized features using `StandardScaler`

## 🤖 Models Implemented

### Without PCA
- **Decision Tree Classifier**
- **Support Vector Machine (SVM)**
- **Random Forest Classifier**
- **K-Nearest Neighbors (KNN)**
- **Naive Bayes** (low accuracy, noted in code)
- **Neural Network (MLP)**
- **AdaBoost Classifier**
- **Gradient Boosting Classifier**

### With PCA (n_components=25)
All models above were also trained on PCA-reduced features (25 principal components) for comparison.

## 🔍 Model Optimization

- **GridSearchCV**: Used for hyperparameter tuning
- **Cross-Validation**: 5-fold KFold cross-validation for model evaluation
- **Performance Metrics**: Accuracy scores and confusion matrices

## 📈 Results

Models are evaluated using:
- Cross-validation accuracy scores
- Confusion matrices for visualization
- Comparison between original features and PCA-reduced features

## 📁 Project Structure

```
.
├── chenzi-fang-2036451.ipynb    # Main notebook with all code
├── A2-data/                      # Dataset folder (not uploaded)
│   ├── train.csv
│   ├── test.csv
│   └── sample_submission.csv
├── Diagram/                      # Project diagrams
│   ├── Framework.drawio
│   └── Framwork.drawio.png
└── README.md                     # This file
```

## 🚀 Usage

1. Open `chenzi-fang-2036451.ipynb` in Jupyter Notebook or Kaggle
2. Ensure the dataset is in the correct path (`/kaggle/input/int303-a2/` for Kaggle)
3. Run all cells sequentially
4. The notebook will:
   - Load and preprocess the data
   - Train multiple models with optimal hyperparameters
   - Evaluate models with cross-validation
   - Generate predictions and save to `submission.csv`

## 📦 Requirements

```python
pandas
numpy
scikit-learn
matplotlib
seaborn
imbalanced-learn  # for RandomOverSampler (if used)
```

## 📝 Notes

- GridSearchCV code sections are commented out as they take a long time to run
- Optimal parameters were found separately and stored in dictionaries
- The final submission uses Gradient Boosting predictions
- PCA analysis shows that 25 components capture sufficient variance

## 📄 License

This project is for educational purposes (INT303 Assignment 2).

## 👤 Author

**Chenzi Fang**  
Student ID: 2036451  
XJTLU

