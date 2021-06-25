# Loan Lending Model #

Model developed by the George Washington University Summer Class 2021 
Responsible Machine Learning w/ Professor Patrick Hall

Last updated: June 2021

***
## Intended use
* **Business value of model:**  The purpose of our model is to decide whether to lend money or not to a person who has a higher priced mortgage rate. Our model takes into consideration adverse impacts due to racial differences. As a result, our model provides a more fair lending experience to applicants.

* **Model design:** Our group best model EBM designed to fit with random grid search, and then we need to avoid the discrimination probelm when we find the best cutoff point for Balck vs White AIR. Therefore, it is designed to lessen the discrimination probelm. 

* ** Intended use:**   The intended user for our group best remediated model would be student, professor, and researchers who need a specific sample to make certain conclusions.  

* **Additional use of model:** This model needs more data  in order to make more accuracy. So, it is used only for educational purposes not intended to evaluate the real-world problem.  

***
## Training data
* [Source of training data] (https://github.com/jphall663/GWU_rml/blob/master/assignments/data/hmda_train_preprocessed.zip)

* **Dividing training dataset:** 70% is training part and 30% is validation part

* **Number of rows in training and validation part:** Training part has 111972 rows of data and validation part has 48366 rows of data

* **Meaning of all training data columns:**

  * conforming: Binary numeric input, whether the mortgage conforms to normal standards (1), or whether the loan is different (0), e.g., jumbo, HELOC, reverse mortgage, etc. 	

  * debt_to_income_ratio_std: Numeric input, standardized debt-to-income ratio for mortgage applicants.
 
  * debt_to_income_ratio_missing: Binary numeric input, missing marker (1) for debt to income ratio std.
  
  * income_std: Numeric input, standardized income for mortgage applicants.
  * loan_amount_std: Numeric input, standardized amount of the mortgage for applicants.


  * intro_rate_period_std: Numeric input, standardized introductory rate period for mortgage applicants.
 						
  * loan_to_value_ratio_std: Numeric input, ratio of the mortgage size to the value of the property for mortgage applicants.
 		
 * no_intro_rate_period_std: Binary numeric input, whether or not a mortgage does not include an introductory rate period.
 			
 * property value std: Numeric input, value of the mortgaged property.
 					
 * term 360: Binary numeric input, whether the mortgage is a standard 360 month mortgage (1) or a different type of mortgage (0). 
 						

***
## Evaluation data
* [Source of test data] (https://github.com/jphall663/GWU_rml/blob/master/assignments/data/hmda_test_preprocessed.zip)

* **Number of rows in test dataset:** Test data contains 19831 rows and 22 columns

* **Differences in columns between training and test dataset:** Test dataset contains 1 more column ‘high_priced’ than the training dataset. ‘high_priced’ is the binary target variable in the training dataset

***
## Model details
*  **Input columns include:** ['property_value_std',
               'no_intro_rate_period_std',
               'loan_amount_std',
               'income_std',
               'conforming',
               'intro_rate_period_std',
               'debt_to_income_ratio_std',
               'term_360']
*  **Target columns:** ['high_priced']
*  **Model Type:** Explainable Boosting Machine
*  **Software Implemented:** Python Virtual Environment
*  **Modeling software versions:**  we need to insert our link. currently using professor’s text file link [View software and package versions](https://github.com/jphall663/GWU_rml/blob/master/assignments/requirements.txt)
*  **Parameter settings:** {'max_bins': 512,
              'max_interaction_bins': 16,
              'interactions': 10,
              'outer_bags': 4,
              'inner_bags': 0,
              'learning_rate': 0.001,
              'validation_size': 0.25,
              'min_samples_leaf': 5,
              'max_leaves': 5,
              'early_stopping_rounds': 100.0,
              'n_jobs': 4, 
              'random_state': 12345}


***
## Quantitative analysis
* State the metrics used to evaluate your group's best remediated model<p>
Our group decided to use AUC to evaluate our model. After we run through the stress testing, residual analysis, and remove the outlier. we find the best AUC would be 0.7953. 

* State the values of the metrics for training, validation, and evaluation (or test) data { eval-
uation (or test) metrics come from the most recent class full evaluation results, link under
Assignment 1.


* Provide at least one plot or table from each weekly assignment for a total of at least six plots, that must include the global variable importance and partial dependence of your group's best remediated model.<p>
**Assingment 1**<p>

**Assingment 2**<p>
Global Feature Importance<p>
<p>
Local Feature Importance<p>
<p>

Partial Dependence <p>




**Assingment 3**<p>

**Assingment 4**<p>
A white-hat model extraction attack: Stolen Model<p>
<p>

Adversarial examples seeds rows of Stolen Model<p>
<p>

**Assignment 5**<p>
Stress Testing<p>
<p>



* Address other alternative models considered<p>
Elastic Net
**Evaluation Metrics of Elastic Net Model**


**Variable Importances of Elastic Net Model**



Monotonic XGBoost
**AUC: 0.7928**



***
## Ethical considerations
* ** Potential negative impacts:**
* Models are based on trained data with an adequate accuracy rate but will still incorrectly mark a high-priced loan for a proportion of the population.   
* Although model was remediated to reduce bias, there is still the potential racial discrimination in the model where Black applicants may have more of a chance in receiving a high-priced loan compared to White applicants. 
* **Potential uncertainties:** 
* Software and package versions could cause a problem in reproducing the same results.  Although the team has been using the same application versions and environments, we still came to subtle differences in results that were unexplainable. 
* Due to the above uncertainty, models deployed on different machines may come to rare difference in determining applicants’ loan approval.  
* **Challenges during training:** The model performs poorly when there are noticeable outliers.  The model was unable to provide an accurate prediction of the high-priced loans.  Unexpected global recessions will also cause the accuracy of models to drop. 
	

