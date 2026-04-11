# evaluating-credit-fairness
A case study on the trade-off between model accuracy and disparate impact using the German Credit Dataset.

*Project by Hilary L.*  

**1. Project Overview**  
This experiment works with UCI's German Credit Data dataset and understanding potential trade-offs between creating a fair model and an accurate model. Using the German Credit Dataset, a Random Forest classifier was developed to predict approval of credit loan while evaluating the model for gender-based bias using the disparate impact (DI) framework. 

As a whole, this framework could be applied to real-world lending with fair credit acts. Women were not allowed to open banking accounts in their own name until 1974, following the Equal Credit Opportunity Act of 1974. With less establised history, it is important to see if data sets, used to train future models, are making predictions based on gender.

**2. Key Results**   
A model accuracy of 73% was achieved while maintaining a disparate impact ratio of 0.94. This exceeds the legal "Four-Fifths Rule" threshold (0.80) for fair decision making. All three models exceeds the legal "Four-Fifths Rule", meaning there is no evidence of discrimination against the protected group.

| Metric | Baseline Model | Added Features Model | Tuned Model |
| :--- | :---: | ---: | ---: |
| Accuracy | 72.5% | 73.0% | 72.0% |
| Disparate Impact (DI) | 0.985 | 0.942 | 0.933 |

**3. Fairness vs. Accuracy Analysis**  
The first two models may serve as an indicator that, for accuracy to increase, the disparate impact ratio may decrease. In this scenario, the accuracy does not change by much, and the both DI ratios are still well above the 0.8 threshold for the disparate impact framework. However, it will be interested to see that, if accuracy could further improve, whether DI could continue to drop to a level below the acceptable threshold.  

**4. Methodology & Features**  
+ **Model**: Random Forest Classifier with Hyperparameter Tuning
+ **Feature Engineering**: Created stability_score, monthly_payment, and relative_burden to better capture borrower behaviour
+ **Fairness evaluation**: Used function to track selection rates across protected classes in experiment (gender). DI ratio = (female selection rate)/(male selection rate).
  
**5. How to Run** 
+ Clone the repository
+ Install dependencies: pip install -r requirements.txt
+  Open notebooks/FairnessEvaluationExperiment.ipynb to view the full analysis  

**6. Future Steps**  
Analyze alternative fairness metrics to evaluate fairness of prediction. Attempt to improve accuracy of the model.
