# Water Wells Condition Prediction in Tanzania

## Project Overview
Access to safe water is a critical issue in Tanzania, where millions of people rely on water wells. Some wells are fully functional, some need maintenance, and others are completely non-functional.  

The objective of this project is to **predict the condition of water wells** using historical data. By accurately classifying wells into three categories—**Functional**, **Functional Needs Repair**, and **Non-Functional**—we aim to help stakeholders prioritize maintenance and improve water accessibility efficiently.

---

## Dataset
The dataset contains information about the wells, including:
- Pump type and source
- Installation year
- Geographical coordinates
- Basin and region
- Technical characteristics like well depth and water quality

The target variable is `status_group`, indicating the condition of each well. The dataset also includes a test set for which we provide predictions.

---

## Data Preparation
- Missing values were handled:
  - **Numerical features**: imputed with the median
  - **Categorical features**: imputed with the most frequent value
- Only **numerical features** were used for the final model as requested.
- Feature engineering included:
  - Well age = `recorded_year - construction_year`
  - Extracted year and month from `date_recorded`
- Numerical features were scaled when necessary for models like Logistic Regression.

---

## Modeling
Two models were trained and compared:

1. **Logistic Regression (Baseline)**
   - Multinomial classification
   - Class weighting to address imbalance
   - Validation results:
     - Macro-F1: 0.403
     - Accuracy: 47%
     - Recall for non-functional wells: 54%

2. **Random Forest (Tuned)**
   - Hyperparameters optimized for maximum performance
   - Validation results:
     - Macro-F1: 0.613
     - Accuracy: 70%
     - Recall for non-functional wells: 70%

**Selected Model:** Random Forest, due to its superior ability to identify **non-functional wells**, which is the most critical category for maintenance planning.

---

## Evaluation and Visualizations
Key visualizations were used to understand and validate model performance:

1. **Confusion Matrix**: Shows how well the model classifies each well category and highlights misclassifications.
2. **Feature Importance**: Identifies the most influential features, such as **pump type**, **well age**, and **geographical location**.
3. **ROC Curve**: Evaluates the model’s ability to distinguish between classes, particularly **non-functional wells**, helping to assess the reliability of predictions.

These visualizations provide clear insights into the model’s strengths and limitations.



## Results and Impact
- The Random Forest model reliably detects non-functional wells, enabling better prioritization of maintenance tasks.
- Critical features influencing predictions include pump type, well age, and location.
- This approach allows stakeholders to allocate resources efficiently, reducing downtime for broken wells and improving water access for communities.

---

## Next Steps
- Deploy the model for real-time predictions on new wells.
- Update the model regularly as new data becomes available.
- Explore additional features such as seasonal patterns and proximity to other water sources.
- Integrate the model into existing decision-support systems used by NGOs and local authorities.


## Tools and Libraries
- Python 3.x  
- pandas, numpy  
- scikit-learn  
- matplotlib, seaborn  
- python-pptx  

---

## Author
Richecard Blade DAMEUS  
Data Scientist & AI Student 
Contact: [https://www.linkedin.com/in/richecard-blade-dam%C3%A9us-817429249?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3BNqsT%2BseAQ9enPAC8U%2BaM1Q%3D%3D]

