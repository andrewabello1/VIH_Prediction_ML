# HIV Classification using Tree-Based Machine Learning Models

## Project Overview

This project builds and evaluates multiple tree-based machine learning models to classify individuals as **VIH (HIV positive)** or **Sano (Healthy)** using clinical and behavioral features.

The objective is to evaluate model performance, analyze feature importance, and determine whether the dataset is highly separable based on medical indicators.

---

## Dataset

The dataset contains **120 observations** with the following features:

- `Edad` (Age)
- `Carga_Viral_Ajustada` (Adjusted Viral Load – log scale)
- `CD4` (CD4 cell count)
- `Sexo`
- `Adherencia_Tratamiento`
- `Tipo_Tratamiento`
- `Nivel_Riesgo_Conductual`
- `Ocupacion`
- `Clase` (Target: VIH or Sano)

Target distribution:

- **VIH:** 66  
- **Sano:** 54  

The dataset is relatively balanced.

---

## Methodology

### Data Preparation
- Target encoding: `VIH → 1`, `Sano → 0`
- One-hot encoding for categorical variables
- Removal of redundant correlated features
- Stratified train-test split (80/20)

### Models Implemented
- Decision Tree
- Random Forest
- XGBoost

### Evaluation Strategy
- Test accuracy
- Classification report (precision, recall, F1-score)
- 5-fold **Stratified Cross-Validation**
- Permutation feature importance (model-agnostic)

---

## Results

All models achieved strong and consistent performance:

- **Test Accuracy:** ~95% – 100%  
- **Cross-Validation Mean Accuracy:** ~93% – 97%  
- Low to moderate variance across folds  

The consistency between test performance and cross-validation suggests the models generalize well and are not simply overfitting.

---

## Feature Importance Analysis

Permutation importance showed that:

- `Carga_Viral_Ajustada`
- `CD4`

are the dominant predictive features across all models.

All other variables contribute minimally.

This indicates that the dataset is **highly separable**, with viral load and CD4 count carrying most of the discriminative signal between VIH and Sano classes.

---

## Key Insights

- Tree-based models perform exceptionally well on this dataset.
- Viral load and CD4 levels are strong biological indicators of HIV status.
- Stratified cross-validation ensured stable and reliable evaluation.
- The dataset appears inherently separable due to strong medical signals.

---

## Technologies Used

- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- XGBoost  

---

## Conclusion

This project demonstrates how tree-based machine learning models can effectively classify HIV status using clinical features.

The analysis confirms that the dataset is strongly driven by viral load and CD4 count, resulting in high predictive performance across multiple models.
