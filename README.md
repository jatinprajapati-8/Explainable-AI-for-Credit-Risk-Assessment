Credit Risk Prediction with Explainable AI

A beginner-friendly machine learning project that predicts whether a loan will be paid back or defaulted. Uses XGBoost for predictions and SHAP for explanations.

📋 Project Overview

This project helps predict credit risk (whether a borrower will default on a loan) using real data from LendingClub. It includes:

Machine Learning Model: XGBoost classifier
Explainability: SHAP values to understand why predictions are made
Web Interface: Streamlit app for easy interaction
Public Dataset: LendingClub loan data (2007-2018)
🎯 Objective

Develop a model with high predictive accuracy for credit risk and implement explainability methods to justify model decisions using the LendingClub dataset.

📁 Files in This Project

mINOR/
├── train_model.py          # Script to train the model
├── app.py                  # Streamlit web application
├── best_model.pkl          # Trained model (generated)
├── feature_names.pkl       # Feature list (generated)
├── best_threshold.pkl      # Optimal threshold (generated)
└── credit-risk-xai/
    └── data/
        └── accepted_2007_to_2018Q4.csv.gz  # Dataset
🚀 Getting Started

Step 1: Install Required Packages

Open your terminal and run:

pip install streamlit pandas numpy scikit-learn xgboost shap
Or if you have a requirements.txt:

pip install -r requirements.txt
Step 2: Train the Model

Run the training script to create the model:

python train_model.py
This will:

Load the data (10,000 samples)
Create features from the raw data
Train an XGBoost model
Evaluate the model performance
Save the model files
Expected Output:

Training accuracy ~80-90%
Test accuracy ~75-85%
AUC score ~0.70-0.85
Step 3: Run the Web App

Start the Streamlit app:

streamlit run app.py
This will open a web browser with the interactive interface where you can:

Input loan details
Get instant predictions
See SHAP explanations
📊 How to Use the Web App

Enter Loan Details:

Loan Amount: How much the borrower wants
Interest Rate: Annual interest rate
Annual Income: Borrower's yearly income
Monthly Payment: The monthly installment
Loan Term: 36 or 60 months
Home Ownership: OWN, MORTGAGE, or RENT
Get Prediction:

Click "Predict Credit Risk"
See if it's a good or bad loan
View the default probability
Understand the Prediction:

See which features influenced the decision
SHAP values show feature importance
Positive values → bad loan
Negative values → good loan
🔍 Features Used

The model uses 9 features:

loan_amnt - Original loan amount
int_rate - Annual interest rate
annual_inc - Borrower's annual income
installment - Monthly payment amount
loan_to_income - Loan amount / Income (risk ratio)
log_annual_inc - Log of income (normalized)
installment_to_income - Monthly burden ratio
term_numeric - Loan term in months
home_ownership_numeric - Encoded home ownership
🎓 Understanding Key Concepts

What is Credit Risk?

The risk that a borrower won't repay the loan. We predict this using historical data.

What is XGBoost?

A powerful machine learning algorithm that combines many decision trees to make accurate predictions.

What are SHAP Values?

SHAP (SHapley Additive exPlanations) tells you:

Which features matter most
How each feature pushes toward good or bad loan
Why the model made a specific decision
What is a Threshold?

The probability cutoff for making decisions:

Low threshold (0.3) = lenient (more loans approved)
High threshold (0.7) = strict (fewer loans approved)
Optimal threshold = best balance (from training)
📈 Model Performance Metrics

The model reports several metrics:

Accuracy: Percentage of correct predictions
AUC Score: How well the model separates good and bad loans (0-1, higher is better)
F1 Score: Balance between precision and recall
Confusion Matrix: Shows correct and incorrect predictions
Example performance:

Training Accuracy: 85%
Test Accuracy:     80%
AUC Score:         0.75
F1 Score:          0.60
🐛 Troubleshooting

Error: "Model files not found"

Solution: Run python train_model.py first to create the model files.

Error: "Module not found"

Solution: Install missing packages:

pip install pandas numpy scikit-learn xgboost shap streamlit
Low Accuracy

Solution: The model uses 10,000 samples. For better accuracy:

Increase to 50,000+ samples in train_model.py
Tune hyperparameters
Add more features
SHAP Not Working

Solution: Ensure SHAP is installed:

pip install shap
💡 Tips for Beginners

Start Simple: The model uses 9 features and 10k rows - easy to understand
Read the Comments: Each script has detailed comments explaining the code
Experiment: Try different loan scenarios in the web app
Understand SHAP: SHAP values show "why" - the most important part!
Adjust Threshold: Use the slider in the app to see how threshold affects predictions
📚 What You Can Learn From This Project

Data preprocessing and feature engineering
Training machine learning models
Model evaluation and validation
Explainable AI techniques (SHAP)
Building interactive web apps
Working with real-world financial data
🔄 Improving the Model

To make the model better, you can:

Use More Data: Change nrows=10000 to 50000+ in train_model.py
Add More Features: Use more columns from the dataset
Tune Hyperparameters: Adjust XGBoost parameters
Try Other Models: Random Forest, Neural Networks, etc.
Feature Selection: Remove irrelevant features
📞 Need Help?

If you're stuck:

Check the error message carefully
Make sure all packages are installed
Verify the data file exists
Read the comments in the code
📄 License

This is an educational project using public LendingClub data.

 Acknowledgments

Dataset: LendingClub public loan data
Libraries: scikit-learn, XGBoost, SHAP, Streamlit
Made for beginners in Machine Learning and Explainable AI 
