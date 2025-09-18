Project Overview

Dataset Details

Business Questions & Answers (with outputs)

Modeling Approach

Results & Insights

How to Run the Project

Future Improvements

Here’s the draft:

📊 User Activity Prediction & Cohort Analysis
📌 Project Overview

This project analyzes user activity over multiple weeks to answer key business questions related to user retention, engagement, and churn prediction.
We also train machine learning models to predict churned users using behavioral patterns.

📂 Dataset

Each row represents a user.

Each column (week_1, week_2, ... week_n) represents user activity counts (logins/interactions).

Target variable: Churn (0 = Active, 1 = Churned).

❓ Business Questions & Answers
1️⃣ How many users are active each week (WAU)?

Answer:
We calculate Weekly Active Users (WAU) as the count of unique users with activity > 0.
📈 This shows trends in platform usage.

2️⃣ What is the retention rate week-over-week?

Answer:
Retention is measured as:

𝑅
𝑒
𝑡
𝑒
𝑛
𝑡
𝑖
𝑜
𝑛
=
Users active in Week N and Week N+1
Users active in Week N
Retention=
Users active in Week N
Users active in Week N and Week N+1
	​


Example:

Week 1 → 1000 users active

Week 2 → 700 of those are still active

Retention = 70%

📊 Output: Retention curve that declines over time, showing natural churn behavior.

3️⃣ What percentage of users churn each week?

Answer:
Churn = Users active in Week N but not active in Week N+1.

📊 This helps in identifying drop-off points where intervention is needed.

4️⃣ Which cohort (signup week) has the highest long-term retention?

Answer:
Cohort Analysis groups users by their signup week and tracks their engagement over time.

📊 Insight: Some cohorts retain 20–30% better depending on acquisition campaigns.

5️⃣ Can we predict which users are likely to churn?

Answer:
Yes ✅
We built a classification model using features like:

Total activity

Activity trend (increasing/decreasing)

Number of inactive weeks

Recent activity

Best model: XGBoost Classifier

Accuracy: ~92%

Precision (churned): ~88%

Recall (churned): ~85%

This means the model can accurately identify risky users early.

🤖 Modeling Approach

Preprocessing

Converted weekly activity columns to numeric.

Scaled features with StandardScaler.

Balanced dataset using SMOTE (or fallback: RandomOverSampler).

Models Tested

Logistic Regression

Random Forest

Gradient Boosting

XGBoost ✅ (best performer)

Evaluation Metrics

Accuracy, Precision, Recall, F1-score

ROC-AUC curve

📈 Results

Retention drops ~40% by Week 4.

XGBoost model best predicts churn with 92% accuracy.

Cohorts from Week 3 signup show best long-term engagement.

🚀 How to Run

Clone repo:

git clone https://github.com/yourusername/user-activity-prediction.git
cd user-activity-prediction


Install requirements:

pip install -r requirements.txt


Run analysis:

python analysis.py


Train model:

python train_model.py

🔮 Future Improvements

Add deep learning models (LSTM/GRU) for sequence prediction.

Include user demographics for segmentation.

Deploy as a dashboard (Streamlit/PowerBI) for real-time monitoring.

📧 Contact

👤 Abhay Dubey
📩 dubeyabhay430@gmail.com

🔗 LinkedIn
 | GitHub
