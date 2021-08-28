# DNSC-6301-Group-Project

# Credit Line Increase Model Card

### Basic Information

* **Person or organization developing model**: Melis Diken, Andrea Ho, Hyemin Park, Chanmi Shin
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
* **columns used as targets in the final model**:
* **Type of model**:
* **Software used to implement the model**:
* **Version of the modeling software**:
* **Hyperparameters or other settings of your model**:

### Quantitative Analysis
* **Metrics used to evaluate your final model**:
* **State the final values of the metrics for all data: training, validation, and test data**:
* **Provide any plots related to your data or final model**:











### Ethical Considerations
* **Describe potential negative impacts of using your model**:
  * Math or software problems:
  * Real-world risks: who, what, when or how?
* **Describe potential uncertainties relating to the impacts of using your model**:
     * Math or software problems: 
        * Uncertain in how the maths will translate across especially given how race is coded in the data and using those cutoff to calculate, even historically how credit scores are calculated
        * software has limitations, at risk individuals can be broken down by race, black vs asian for example just by simple coding of race in the model and what numbers are assigned to each race. So even if we change the coding of race, we could potentially inject more biases like if we changed the numbers we coded each race, and put black as 1 and cycled every race up a number
        * Even if we modify our biases to try to rectify them, the uncertainty is that we could be injecting more bias into the model, which then becomes an ethics issue, how much bias are we willing to accept before we skew the model too much
  *** Real-world risks: who, what, when or how?**
       * Age demographics have huge uncertainty, younger people are less secure in their finances and that reflects on credit scores and subsequently their ability to qualify for credit increases. So credit increases while younger would be more volatile and uncertain which makes it hard to model in a concrete fashion
       * Data gets more polarised based on income and age, and if the model is based on these inputs, the results for approving credit increases also becomes more polarising which can become inherent
       * data poisoning and hacking also have the potential to create uncertainty in the model, data breaches beyond a company’s control could lead to data poisoning which is hard to rectify from within the model
       * there are many factors that contributes to on time credit payments  that we cannot control or even try to code for in the data, so any manipulation of data coding creates more uncertainty in validity of our model for example accidents and natural disasters that affect on time credit payments so by just using a rigid model, it doesn’t account for real life incidents
