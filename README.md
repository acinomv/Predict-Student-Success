# Predict-Student-Success

Repository for Student Success Project

---

## Predicting Student Dropout & Academic Success

---

## Project Overview
This project applies supervised machine learning techniques to predict student outcomes using the "Predict Students’ Dropout and Academic Success" dataset from the UCI Machine Learning Repository. The primary goal is to classify students as **dropout**, **graduate**, or **enrolled**, and uncover the most influential academic, financial, and structural predictors behind those outcomes.

The project demonstrates full-cycle data science capability: data cleaning, preprocessing, modeling, evaluation, interpretation, and business-domain translation—making it suitable for real-world decision-making contexts.

---

## Dataset Description
The dataset contains student-level academic performance, admission scores, financial information, and program details.  
Key variable categories include:

- **Academic Performance**: semester grades, evaluations completed  
- **Financial Indicators**: tuition payment status  
- **Demographics**: age, region  
- **Course / Program Data**: specific program enrolled in  
- **Target Variable**:  
  - `0` = Dropout  
  - `1` = Graduate  
  - `2` = Enrolled  

Total observations: **1,328** students.

---

## Exploratory Data Analysis (EDA)
EDA was performed to understand distributions, class imbalances, and influential patterns across academic and financial variables. Key findings included:

- Students with *lower second-semester grades* are far more likely to drop out.  
- *Current tuition payment status* strongly separates dropouts from students who continue.  
- Certain courses/programs show significantly different retention patterns.  
- The "enrolled" class was underrepresented, affecting overall class balance.

Visuals included:
- Count plots of performance metrics against outcome categories  
- Distribution plots of grades and evaluations  
- Correlation heatmaps  
- Class imbalance analysis  

---

## Model Development & Iteration
Two models were implemented:

### **1. Decision Tree (Baseline Model)**
- Built for interpretability and rule extraction  
- Accuracy: **68.45%**  
- Strengths: High recall for graduates  
- Limitation: Weak performance on "enrolled" class due to class imbalance  

### **2. Random Forest (Final Model)**
- Used for improved accuracy and robustness  
- Accuracy: **71.31%**  
- Strongest performance for dropout and graduate prediction  
- Persisting challenge: low recall for enrolled students  

Hyperparameter tuning and cross-validation were implemented to improve generalization.

---

## Results
**Random Forest predictions:**

- **Accuracy:** 0.7131  
- **Precision:** 0.6434  
- **Recall:** 0.5974  
- **F1 Score:** 0.5968  

**By class:**
- **Dropout (0):** Precision 0.78, Recall 0.71  
- **Graduate (1):** Precision 0.71, Recall 0.91  
- **Enrolled (2):** Precision 0.44, Recall 0.17 (class imbalance remains a challenge)  

Random Forest outperformed Decision Tree across all metrics except interpretability.

---

## Interpretation

### **Key Feature Insights**
Top predictors identified by the model:

- **Curricular Units 2nd Sem (Grade):**  
  The single strongest academic predictor. Lower grades strongly correlate with dropout likelihood.

- **Curricular Units 2nd Sem (Evaluations):**  
  Represents number of evaluations (tests/assignments). More evaluations indicate ongoing academic engagement and frequent feedback—important for identifying struggling students early.

- **Tuition Fees Up to Date:**  
  A clear indicator of financial stability. Students behind on tuition payments show significantly higher dropout risk.

- **Admission Grade:**  
  Higher initial academic readiness strongly correlates with long-term success and graduation.

- **Course:**  
  Program-level differences (difficulty, support structure, curriculum design) affect retention and graduation.

### **What This Means for Institutions**
- Academic performance and evaluation frequency highlight *where instructional support should concentrate*.  
- Tuition payment status reinforces the importance of *financial aid and proactive outreach*.  
- Admission grade and course insights help shape *admissions criteria, advising, and curriculum redesign*.

---

## Future Improvements
To strengthen the model and enhance institutional applicability:

- **Address Class Imbalance**: Use SMOTE or class-weighting to improve prediction of “enrolled” students.  
- **Add More Features**: Include behavioral data (attendance, LMS usage), socio-economic indicators, and student support interactions.  
- **Experiment with Advanced Models**: Gradient boosting, XGBoost, LightGBM.  
- **Conduct Longitudinal Studies**: Track students over multiple semesters to model retention trajectories.  
- **Develop Real-Time Dashboards**: Integrate model outputs into advisor dashboards for early-alert systems.

---
