# Enterprise Autonomous Intelligence System

### Multi-Agent AI Framework for Predictive Analytics, Automated Decision-Making & Business Intelligence

This project explores how machine learning and multi-agent AI can be used to solve a practical business problem: customer churn.

The idea is simple. Predict which customers are likely to leave, understand why they might leave, and use that information to make better retention decisions.

Instead of stopping at a churn prediction, the system takes the output further by estimating revenue at risk, suggesting retention strategies, and evaluating the expected return on those strategies.

## Project Overview

The project uses the IBM Telco Customer Churn dataset to build a complete predictive analytics and decision-making workflow.

It combines a Deep Neural Network, SHAP explainability and a LangGraph-based multi-agent system.

## Key Features

- **Customer Churn Prediction:** Predicts the probability of a customer leaving using a Deep Neural Network.
- **Exploratory Data Analysis:** Studies customer behaviour, service usage, contracts and payment patterns.
- **Feature Engineering:** Creates additional features to capture customer spending habits and service engagement.
- **Model Explainability:** Uses SHAP to identify the main factors influencing individual predictions.
- **Customer Risk Segmentation:** Groups customers into High, Medium and Low risk categories.
- **Multi-Agent Decision System:** Uses specialised agents for risk assessment, explanations, retention planning, financial impact and reporting.
- **ROI Analysis:** Estimates campaign costs, expected savings and potential return on investment.
- **Autonomous Re-planning:** If the first retention strategy produces negative estimated ROI, the workflow attempts a lower-cost alternative.

## Technology Stack

| Area | Technologies |
|---|---|
| Programming | Python |
| Data Analysis | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn |
| Deep Learning | TensorFlow, Keras |
| Explainable AI | SHAP |
| AI Agents | LangGraph |
| LLM Integration | LangChain, OpenAI |
| Model Persistence | Joblib |

## Dataset

**IBM Telco Customer Churn Dataset**

Source: https://www.kaggle.com/datasets/blastchar/telco-customer-churn

The dataset contains customer information such as tenure, monthly charges, total charges, contract type, internet services and churn status.

The target variable is `Churn`.

The notebook includes data quality checks and handles missing `TotalCharges` values before model training.

## How the System Works

The workflow is divided into several stages:

**1. Data Preparation**

- Load the Telco customer dataset.
- Inspect missing values and duplicate records.
- Clean and transform `TotalCharges`.
- Perform exploratory data analysis.

**2. Feature Engineering**

Additional features are created, including:

- Average monthly spending
- New customer indicator
- Number of additional services
- Month-to-month contract indicator
- Electronic check payment indicator

**3. Churn Prediction**

A Deep Neural Network is trained using TensorFlow/Keras.

The architecture uses:
- Dense layers
- Batch Normalization
- Dropout
- Adam optimizer
- Early Stopping
- Class weighting

**4. Model Evaluation**

The notebook evaluates the model using:

- ROC-AUC
- PR-AUC
- Precision
- Recall
- F1-score
- Confusion Matrix

It also calculates an optimal classification threshold using F1-score.

**5. Explainable AI**

SHAP is used to understand which customer features contribute most to churn predictions.

**6. Multi-Agent Decision Framework**

The LangGraph workflow contains the following agents:

| Agent | Responsibility |
|---|---|
| Risk Agent | Assigns customer risk levels |
| Explanation Agent | Identifies important churn drivers |
| Retention Agent | Recommends customer retention actions |
| Impact Agent | Estimates campaign cost, savings and ROI |
| Report Agent | Generates a structured business report |

The orchestrator checks the estimated ROI. If it is negative on the first attempt, it sends the workflow back to the Retention Agent to try a cheaper strategy.

**7. Business Intelligence**

The final stage calculates revenue at risk, customer lifetime value proxy, campaign cost, expected savings and ROI sensitivity.

## Running the Notebook

The easiest way to run this project is through Kaggle.

1. Download or clone this repository.
2. Open Kaggle Notebooks.
3. Upload `Enterprise_Autonomous_Intelligence_System.ipynb`.
4. Attach the IBM Telco Customer Churn dataset.
5. Configure your OpenAI API key using Kaggle Secrets if you want LLM-powered recommendations.
6. Run the notebook cells in order.

Without an available LLM provider, the retention workflow can use its deterministic mock fallback.

## Important Notes

- The dataset is not included in this repository. Download it separately from Kaggle.
- OpenAI API access is optional.
- LLM-powered recommendations require valid API configuration.
- Without an available LLM, the notebook falls back to predefined rules.
- Revenue savings and ROI are estimates based on assumptions in the notebook, not guaranteed financial outcomes.
- Model performance should be evaluated on the validation data before using predictions in real business decisions.

## Future Improvements

- Experiment with additional ML and deep learning architectures.
- Improve churn prediction through hyperparameter tuning.
- Explore more advanced agent collaboration.
- Add a business dashboard for customer risk monitoring.
- Test retention strategies against different cost and success-rate assumptions.
- Improve model deployment and scalability.

## Author

**Harsh Verma**

GitHub: https://github.com/harsh-12-dev

---

Built as a hands-on project exploring predictive analytics, explainable AI and autonomous business decision-making.
