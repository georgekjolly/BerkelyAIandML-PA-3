**Required Assignment 17.1: Comparing Classifiers**

Jupyter Note Book link :

**Introduction**

The objective of this project was to predict whether a client would subscribe to a term deposit based on historical data collected from a Portuguese bank’s telemarketing campaigns. Understanding these patterns can help the bank target future marketing efforts more effectively and reduce campaign costs.

**Modeling**
**Use of Multiple Models**: Four machine learning models were applied and compared — K-Nearest Neighbors (KNN), Logistic Regression, Support Vector Classifier (SVC), and Decision Tree Classifier.

**Cross-Validation**: Each model was evaluated using k-fold cross-validation to ensure performance consistency and minimize overfitting risks.

**Grid Search for Hyperparameters**: A GridSearchCV approach was used to optimize hyperparameters for each model, selecting the best combination based on cross-validation scores.

**Interpretation of Coefficients**: Logistic Regression coefficients were analyzed to interpret feature impacts. For example:

**num__emp.var.rate** had a strong negative effect (coefficient: -2.60), with an odds ratio of 0.07, indicating that a higher employment variation rate significantly lowers subscription likelihood.

**cat__month_mar** had a positive coefficient (1.92), with an odds ratio of 6.79, suggesting calls in March were over six times more likely to result in a subscription.

**Evaluation Metric:**

**Accuracy** was selected as the primary evaluation metric for comparing model performance.

Additional metrics included **precision**, **recall**, and **F1-score**, which are particularly useful in assessing model behavior on the minority (positive) class.

**Metric Rationale:**

Accuracy was prioritized due to the relatively balanced nature of the training data after preprocessing.

F1-score was used to evaluate performance on positive class predictions, balancing both precision and recall — crucial for marketing conversion scenarios.

**Model Performance Summary:**

Model	                  Accuracy (Test)	   Precision	Recall	 F1-score
K-Nearest Neighbors	    90.45%	           0.608	    0.444	   0.513
Logistic Regression	    91.11%	           0.669	    0.429	   0.523
Support Vector Machine	91.11%	           0.675	    0.419	   0.517
Decision Tree	          91.50%	           0.651	    0.542	   0.592

The Decision Tree model had the best F1-score and recall, making it the most effective at identifying true positives (subscribers).

Logistic Regression remains valuable due to its interpretability and solid performance.

SVC achieved the same accuracy as logistic regression but is less interpretable.

KNN, while performing well, had the lowest F1-score and recall.

**Findings**
**Business Understanding**: The goal was to predict whether a customer would subscribe to a term deposit based on past marketing interactions. Better predictions enable more efficient targeting and cost-effective campaigns.

**Data Cleaning & Preparation:**

  Missing values were imputed.

  Categorical features were one-hot encoded.

  Numerical features were scaled using standardization techniques.

  Irrelevant or highly correlated features were removed to enhance model generalizability.

**Descriptive & Inferential Statistics:**

  Features like call duration, month, job, and previous outcomes were found to strongly influence the likelihood of subscription.

  Customers contacted in March, or those with a successful previous campaign, were significantly more likely to subscribe.

**Clear, Actionable Insights for a Nontechnical Audience:**

  Clients contacted in **March** were ~6.8× more likely to subscribe.

  **Call duration** remains a strong positive predictor; longer calls generally result in higher success.
  
  Positive outcomes in previous campaigns significantly increase the chances of subscription.

  **Blue-collar** and **unknown job types**, and contact via **telephone**, reduce subscription likelihood.

**Next Steps & Recommendations:**

  Prioritize calling during high-performing months (e.g., March, August).

  Optimize call scripts to engage clients early, as call duration is strongly predictive.
  
  Explore ensemble models (e.g., Random Forest or XGBoost) to further improve predictive power.
  
  Focus future marketing on groups with higher predicted odds of subscription, like retirees and students.
  
  Consider a dashboard for the marketing team that integrates model predictions to guide real-time decision-making.


