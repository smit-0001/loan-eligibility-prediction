# Loan Eligibility Prediction

In this project we try  to predict loan eligibilty for a candidate given different parameters about his information such as salary , property owned etc.

## Apendix

- Part 1 - EDA & Visuals
    - Countplot of how many patients have diabetes.
    - Displot of Diabetic patient wrt age
    - Seeing the change of diabetes with no of pregnancy 
    - Histogram plot of Diabetic patient wrt age
    - Heatmap of correlation
    - Histplot of all features
    - Box Plot of Age vs BMI
    - KDE plot of Outcome (Diabetic) wrt numerical feature

- Part 2 - Model Building
    - Train TestSplit
    1) Decision tree
    - Confusion Matrix and Accruacy
    - Predicting
    - Seeing Feature Importance
    2) Naive Bayes
    -  LGBMClassifier
    - gridsearch
    - Model Performance
    - Score table

## A beirf Info On dataset

The details of a candidate include Gender, Marital Status, Education, Number of Dependents, Income, Loan Amount, Credit History, and others.

### Columns of dataset

- Loan_ID             : Unique Loan ID.
- Gender              : Male/ Female
- Married             : Applicant married (Y/N)
- Dependents          : Number of dependents
- Education           : Applicant Education (Graduate/ Under Graduate)
- Self_Employed       : Self-employed (Y/N)
- ApplicantIncome     : Applicant income
- CoapplicantIncome   : Coapplicant income
- LoanAmount -        : Loan amount in thousands
- Loan_Amount_Term    : Term of a loan in months
- Credit_History      : Credit history meets guidelines
- Property_Area       : Urban/ Semi-Urban/ Rural
- Loan_Status         : Loan approved (Y/N)
- CoapplicantIncome   : Coapplicant income
- LoanAmount -        : Loan amount in thousands
- Loan_Amount_Term    : Term of a loan in months
- Credit_History      : Credit history meets guidelines
- Property_Area       : Urban/ Semi-Urban/ Rural
- Loan_Status         : Loan approved (Y/N)

Using these features we pridict the outcome ie if eligible for loan or not.

## Part 1 - Data Preprocessing

1.Handling Missing Values

- Filling missing n umerical values in columns LoanAmount, Loan_Amount_Term, Credit_History with mean value.
- Filling Categorical cloumns Gender, Married, Dependents, Self_Employed with mode.

2.Handling Outliers

- Normalized Applicants Income
- Normalizing Loam Amount

## Part 2 - Visualization

We then Perform EDA on this.
Some key visualizations include
1)Bar Plot to compare How many loans were Approved and not Approved

- 69% of loans were approved

2)Univariate Analysis of Categorical Variable

- Gender : 80% applicatants were male
- Married : 65% applicants were married.
- Self_Employed : 15% applicnats are self employed
- Credit_History : 85% of applicants have repaid their debts

3)Univariate Analysis of Ordinal Variables

- Dependants : Most of the applicants don't have any dependents.
- Education : Around 80% of the applicants are Graduate.
- Property_Area : Most of the applicants are from the Semiurban area.

4)Univariate Analysis of Numerical Variiables

- Applicnats Income : Most of the data in the distribution of applicant income are towards the left between 0 to 20000 (not normally distributed) We should make it normal as algorithms work better if the data is normally distributed.

5)Box plot of Applicn ats income grouped by Education

- there were a higher number of graduates with very high incomes, which are appearing to be outliers.

> Biva=riate Analysis

4)Loan Apporoval status wrt male and female applicants

- The proportion of male and female applicants is more or less the same for both approved and unapproved loans

5)Loan Apporoval status wrt married or unmarried applicant
The proportion of married applicants is higher for approved loans.

6)Loan Apporoval status wrt Education of aaplicant
The proportion of graduate applicants is higher for approved loans.

7)Loan Apporoval status wrt Property Area
The proportion of loans getting approved in the semi-urban area is higher as compared to that in rural or urban areas

8)Loan approval status based on Income
We make 4 bins of group ['Low','Average','High','Very high'] for the applicant income variable based on the values in it and analyze the corresponding loan status for each bin.
It was inferred that Applicant's income does not affect the chances of loan approval

9)Coorelation Plot
The most correlated variables were
- ApplicantIncome & LoanAmount
- Credit_History & Loan_Status
- LoanAmount & CoapplicantIncome

## Part 3 - ML Model Building

### Decision Tree Classification
Accuracy - 69.91%

### Naive Bayes
Accuracy - 82.92%
