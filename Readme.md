# Fradulent Firm Detection

## Contents
* [Problem Statement](#problem-statement)
* [Data Source](#data-source)
* [Data Description](#data-description)
* [Technologies Used](#technologies-used)


## Problem Statement
> Building a predictive model that predicts the audit risk of a firm in the form of a score and this score can in turn be used to classify a firm as fraudulent or otherwise.

## Data Source
This project is assigned to us as a part of our curriculum for "Applied Machine Learning" at The University of Texas at Dallas. The dataset for this project and the
problem statement are inspired by a [case study](https://www.tandfonline.com/doi/full/10.1080/08839514.2018.1451032) published in the Applied Artificial Intelligence Journal.
They collected this data from CAG of India. Comptroller and Auditor General (CAG) of India is an independent constitutional
body of India. It is an authority that audits receipts and expenditure
of all the firms that are financed by the government of India. While maintaining
the secrecy of the data, exhaustive one year(2015 - 2016) nonconfidential data of firms is collected from the Auditor General Office (AGO) of CAG. There are total 777 firms from 46 different cities of a state that are
listed by the auditors for targeting the next field-audit work. The targetoffices
are listed from 14 different sectors.

## Data Description
The dataset was made available through 2 csv files – audit_risk and trial. The audit_risk has 27 columns and trial has 18 columns. The 27 columns in audit_risk file are the following: 
Sector_Score – Historical risk score value for each target sector
LOCATION_ID – Unique ID of the city or province
PARA_A - Discrepancy found in the planned expenditure of inspection and summary report A in Rs (in crore)
SCORE_A, RISK_A – These columns can be derived from the PARA_A
PARA_B - Discrepancy found in the unplanned expenditure of inspection and summary report B in Rs (in crore)
SCORE_B, RISK_B - These columns can be derived from the PARA_B. TOTAL - Total amount of discrepancy found in other reports Rs (in crore)
numbers - Historical discrepancy score
Score_B.1, Risk_C - These columns can be derived from the numbers
Money_Value - Amount of money involved in misstatements in the past audits
SCORE_MV, Risk_D - These columns can be derived from the Money_Value
District_Loss - Historical risk score of a district in the last 10 years
PROB – probability of District_Loss
Risk_E – It is the product of District_Loss and PROB
History - Average historical loss suffered by firm in the last 10 years
Prob – Probability of Historical Loss score
Risk_F – It is the product of History and prob
Score – It is a deciding factor in classifying a firm as ‘Fraud’ or ‘Not Fraud’, In the trial file, if the score is less than or equal to 2, the firm is labelled ‘Not Fraud’, if it is greater than 2, it is labelled ‘Fraud’
Inherent_Risk - the risk present due to the discrepancies present in the transactions
CONTROL_RISK - the risk due to the discrepancies which are left undetected by an internal control system
Detection_Risk - risk of discrepancies present in the firm which are not even detected by the audit procedures
Audit_Risk – It is the product of Inherent, control and detection risks
Risk – It is dependent on Audit_Risk, If the Audit_Risk is less than or equal to 1, the firm is labelled ‘Not Fraud’ and if it is greater than 1, it is labelled ‘Fraud’.

The Score_A in Audit_Risk multiplied by 10 is the Score_A in trial. The same applies to Score_B. Audit_Risk dataset contains Risk_A(a derivative of PARA_A and Score_A) and Risk_B(a derivative of PARA_B and Score_B) which are not present in trial. TOTAL and numbers columns are identical in Audit_Risk and trial. Score_B.1 multiplied by 10 is the Marks column in trial. Audit_Risk has an extra column Risk_C( a derivative of numbers and Score_B.1) compared to trial. Score_MV in Audit_Risk multiplied by 10 is the Money_Marks column in trial dataset. Risk_D( a derivative of Money_Value and Score_MV) is absent in trial. PROB(probability of district loss score) in Audit_Risk multiplied by 10 is the Loss_Score in trial. prob(probability of historical loss score) in Audit_Risk multiplied by 10 is the History_Score in trial. Score is exactly identical in both Audit_risk and trial datasets. Risk column in trial is calculated based on Score value. The discrepancy in the Risk columns of Audit_Risk and trial datasets arises from the fact that Audit_Risk dataset uses Audit_Risk column(Product of Inherent_Risk, Controlled_Risk and Detection_Risk columns) to classify a firm as Fraud or otherwise.

## Technologies used
Python
> Pandas, Numpy, mglearn, sklearn, matplotlib, Seaborn, TensorFlow, Keras
