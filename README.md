# Predictive Maintenance Project for IBM SkillsBuild Internship

This project was developed as part of the IBM SkillsBuild Internship program in collaboration with Edunet Foundation.

## 1. Project Objective

The goal of this project is to develop a predictive maintenance model for a fleet of industrial machines. The model analyzes sensor data from machinery to identify patterns that precede a failure. The objective is to create a classification model that can predict the specific type of failure (e.g., Tool Wear Failure, Heat Dissipation Failure, Overstrain Failure) based on real-time operational data, enabling proactive maintenance and reducing operational costs.

## 2. Technologies Used

* **Cloud Platform:** IBM Cloud
* **AI/ML Environment:** IBM watsonx.ai (Watson Studio)
* **Automated ML Tool:** IBM AutoAI
* **Model Deployment:** IBM Watson Machine Learning
* **Data Storage:** IBM Cloud Object Storage

## 3. Methodology

The project was executed following a structured machine learning workflow:

1.  **Project Setup:** An IBM watsonx.ai project was created and configured with IBM Cloud Object Storage and Watson Machine learning services.
2.  **Data Loading:** The provided predictive maintenance dataset from Kaggle was uploaded to the project as a data asset.
3.  **Model Training with AutoAI:** The AutoAI tool was used to automatically preprocess the data and train several machine learning models. The target for the prediction was set to the `Failure Type` column.
4.  **Model Evaluation:** AutoAI generated and ranked multiple model "pipelines." The top-ranked pipeline, **Pipeline 5 (Batched Tree Ensemble Classifier)**, was selected based on its high accuracy of **99.5%**.
5.  **Model Deployment:** The selected model was saved and promoted to a deployment space. It was then deployed as a real-time "Online" web service using the Watson Machine Learning service.
6.  **Testing:** The live, deployed model was tested with various input scenarios to validate its performance.

## 4. Results and Performance

The final deployed model demonstrated exceptional performance and robustness.

### Test Scenario 1: Healthy Machine

* **Inputs:** Normal operating values for temperature, torque, etc.
* **Result:** The model correctly predicted **"No Failure"** with 100% confidence.

<img width="1785" height="738" alt="output" src="https://github.com/user-attachments/assets/ef2e4fbf-3d78-4eb9-8895-95b6c16cb1a4" />


<img width="1787" height="735" alt="input data" src="https://github.com/user-attachments/assets/48fca405-6579-4705-b1a4-2bd3845ec53a" />



### Test Scenario 2: High-Stress Machine

* **Inputs:** Extreme values for multiple sensors to simulate a machine under high stress.
* **Result:** The model still predicted **"No Failure"** but its confidence level dropped significantly to **80%**. This demonstrates the model's reliability and resistance to false alarms while still indicating that the machine is entering a non-standard state.



