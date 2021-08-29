# DNSC-6301-Group-Project

# Credit Line Increase Model Card

### Basic Information

* **Person or organization developing model**: Melis Diken 'midiken@gwu.edu', Andrea Ho 'andreaho@gwu.edu', Hyemin Park 'hyemin0918@gwu.edu', Chanmi Shin 'chanmishin@gwu.edu'
* **Model date**: August, 2021
* **Model version**: 1.0
* **License**: MIT
* **Model implementation code**: [DNSC_6301_Example_Project.ipynb](DNSC_6301_Example_Project.ipynb)

### Intended Use
* **Primary intended uses**: This model is an *example* probability of default classifier, with an *example* use case for determining eligibility for a credit line increase.
* **Primary intended users**: Students in GWU DNSC 6301 bootcamp.
* **Out-of-scope use cases**: Any use beyond an educational example is out-of-scope.

### Training Data

* Data dictionary: 

| Name | Modeling Role | Measurement Level| Description|
| ---- | ------------- | ---------------- | ---------- |
|**ID**| ID | int | unique row indentifier |
| **LIMIT_BAL** | input | float | amount of previously awarded credit |
| **SEX** | demographic information | int | 1 = male; 2 = female
| **RACE** | demographic information | int | 1 = hispanic; 2 = black; 3 = white; 4 = asian |
| **EDUCATION** | demographic information | int | 1 = graduate school; 2 = university; 3 = high school; 4 = others |
| **MARRIAGE** | demographic information | int | 1 = married; 2 = single; 3 = others |
| **AGE** | demographic information | int | age in years |
| **PAY_0, PAY_2 - PAY_6** | inputs | int | history of past payment; PAY_0 = the repayment status in September, 2005; PAY_2 = the repayment status in August, 2005; ...; PAY_6 = the repayment status in April, 2005. The measurement scale for the repayment status is: -1 = pay duly; 1 = payment delay for one month; 2 = payment delay for two months; ...; 8 = payment delay for eight months; 9 = payment delay for nine months and above |
| **BILL_AMT1 - BILL_AMT6** | inputs | float | amount of bill statement; BILL_AMNT1 = amount of bill statement in September, 2005; BILL_AMT2 = amount of bill statement in August, 2005; ...; BILL_AMT6 = amount of bill statement in April, 2005 |
| **PAY_AMT1 - PAY_AMT6** | inputs | float | amount of previous payment; PAY_AMT1 = amount paid in September, 2005; PAY_AMT2 = amount paid in August, 2005; ...; PAY_AMT6 = amount paid in April, 2005 |
| **DELINQ_NEXT**| target | int | whether a customer's next payment is delinquent (late), 1 = late; 0 = on-time |

* **Source of training data**: GWU Blackboard, email `jphall@gwu.edu` for more information
* **How training data was divided into training and validation data**: 50% training, 25% validation, 25% test
* **Number of rows in training and validation data**:
  * Training rows: 15,000
  * Validation rows: 7,500

### Test Data
* **Source of test data**: GWU Blackboard, email `jphall@gwu.edu` for more information
* **Number of rows in test data**: 7,500
* **State any differences in columns between training and test data**: None

### Model Details
* **Columns used as inputs in the final model**:
   * 'LIMIT_BAL'
   * 'PAY_0'
   * 'PAY_2'
   * 'PAY_3'
   * 'PAY_4'
   * 'PAY_5'
   * 'PAY_6'
   * 'BILL_AMT1'
   * 'BILL_AMT2'
   * 'BILL_AMT3'
   * 'BILL_AMT4'
   * 
* **columns used as targets in the final model**:
* **Type of model**:
* **Software used to implement the model**:
* **Version of the modeling software**:
* **Hyperparameters or other settings of your model**:

### Quantitative Analysis
* **Metrics used to evaluate your final model**:
  * Area Under Curve (AUC)
* **State the final values of the metrics for all data: training, validation, and test data**:
* **Provide any plots related to your data or final model**:











### Ethical Considerations
* **Describe potential negative impacts/uncertainties relation to the impacts of using your model**:
  * Math or software problems:
  * Real-world risks: who, what, when or how?

**Biases**

Although biases are considered in the training process and tested so that it is minimized, it is extremely difficult to completely eliminate biases in the model. A decision tree, by its nature, only allows nodes with binary choices that must be expressed in numbers. This also applies to variables that are not numerical or cannot be quantitatively measured (e.g., race, gender, etc.), which means that the model could be trained to give preferable outputs for a specific type of group. In other words, the model still contains the risk of producing biased and inaccurate outputs that has the potential of impacting the evaluation of individuals, eventually leading to incorrect decisions.

**Data Security**

Another potential ethical issue of the decision model can be on data security. While it is important for the user of the model to put significant effort on protecting personal data, it is challenging to control external attacks on the data or model. Such attacks could be data poisoning, backdoors and watermarks, model inversion, adversarial, impersonation, etc. The reason these attacks are threatening and uncontrollable is because of the uncertainty of their occurrences: you can never know who, what, how, or when the data will be attacked. Therefore, decision-makers should always consider the possibility of such risks and be prepared with a safety net to protect the data and model.


