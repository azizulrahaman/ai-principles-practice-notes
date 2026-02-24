# Assignment 03 — Machine Learning Use Cases

**Course:** Artificial Intelligence: Principles and Practice  
**Student:** Md Azizul Rahaman | Touro University

---

## Use Case 1: Antarctic Penguin Species Identification

### Overview
Supervised multi-class classification system for automated taxonomic classification of penguins based on physical measurements — accelerating ecological studies and democratizing species identification.

### Data Collection
Field observations record morphometric features:
- Flipper length (mm), bill length and depth (mm), body mass (grams)
- Island, sex, observation date, observer identity
- Dataset split: **75% training / 25% testing** with stratified sampling

### Addressing Data Biases

| Bias Type | Remedy |
|-----------|--------|
| **Geographic** | Deploy population-specific models; validate across regions |
| **Temporal** | Multi-year, multi-season data; normalize body mass seasonally |
| **Observer** | Standardized measurement protocols; cross-validation across observers |

### Feature Engineering
- **Flipper length** most diagnostic: Gentoo (220mm) > Chinstrap (195mm) > Adélie (190mm)
- **Bill dimensions:** Gentoo deeper bills; Chinstrap longer, narrower bills
- **Derived variables:** Bill ratio (length/depth), body condition index
- **Class imbalance:** 60% Adélie, 25% Gentoo, 15% Chinstrap → solved with SMOTE and weighted sampling

### Model Results
- **Selected:** Random Forest
- **Accuracy:** 99.2% training, 96.1% validation, **95.8% test**
- **Hyperparameters:** 200 trees, max_depth=15, class_weight adjusted for minority classes

### Deployment
- Researchers collect measurements (2–3 min/bird) → mobile app → real-time predictions
- GPS-tagged logging, population tracking, alerts for unusual morphologies
- **Retraining triggered** if accuracy drops below 93%

---

## Use Case 2: Diabetes Risk Prediction for Healthcare

### Overview
Binary classification system predicting diabetes risk to enable early intervention and preventive care.

### Key Features Used
- Blood glucose levels, BMI, age, blood pressure
- Family history, insulin levels, physical activity

### Model Approach
- Logistic Regression and Random Forest ensemble
- SMOTE for handling class imbalance in medical data
- Human-in-the-loop validation — physician review required before action

### Ethical Considerations
- Transparency of predictions required for healthcare compliance
- Bias testing across demographic groups
- HIPAA compliance for patient data protection

---

## Key ML Concepts Demonstrated

| Concept | Application |
|---------|-------------|
| Supervised Learning | Both use cases use labeled training data |
| Class Imbalance | SMOTE, weighted sampling, threshold tuning |
| Feature Engineering | Derived variables improve model accuracy |
| Continuous Monitoring | Quarterly performance tracking, drift detection |
| Responsible AI | Bias detection, explainability, human oversight |
