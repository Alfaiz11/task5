# Task 5

# Heart Disease Classification with Decision Trees and Random Forests

This project focuses on classifying the presence of heart disease using the Heart Disease dataset. Two classification models are explored — **Decision Tree** and **Random Forest** — along with proper data preprocessing, EDA, and performance evaluation.

---

## Dataset

- **Source**: https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset
- **File**: `heart.csv`
- **Target Variable**: `target` (1 = presence of heart disease, 0 = absence)

---

## Data Preprocessing & EDA

- Checked for nulls, data types, and class balance.
- Explored feature distributions via histograms.
- Analyzed feature relationships with a correlation heatmap.
- Dataset was split into train/test sets using an 80-20 ratio.

---

##  Decision Tree Classifier

- Trained a `DecisionTreeClassifier` on the training set.
- Visualized the tree structure.
- Evaluated with accuracy, classification report, and confusion matrix.
- Observed signs of **overfitting** in deeper trees.

---

## Overfitting Control

- Plotted accuracy vs. `max_depth`.
- Found optimal depth around **3**, where test accuracy was high and train/test gap was small.
- Pruned the tree by setting `max_depth=3` to balance bias and variance.

---

## Random Forest Classifier

- Trained a `RandomForestClassifier` with 100 trees.
- Initial model showed **perfect accuracy**.
- Re-evaluated using `max_depth` tuning.
- Final model used `max_depth=5`, which balanced performance and generalization.

---

## Cross-Validation and Feature Importance

- Performed 5-fold cross-validation on the final Random Forest.
- Reported mean accuracy and standard deviation.
- Plotted feature importances:
  - Top features: `cp`, `thal`, `ca`, `oldpeak`, `chol`, etc.

---

## Evaluation Metrics

| Model            | Accuracy (Test Set) | Cross-Validated Accuracy |
|------------------|---------------------|---------------------------|
| Decision Tree    | ~85% (depth=3)      | ~85%                      |
| Random Forest    | ~92%                | ~93%                      |

---

## Conclusion

- **Random Forests** outperformed Decision Trees in accuracy and generalization.
- Controlling tree depth was crucial to prevent overfitting.
- Feature importance provided explainability into model behavior.
