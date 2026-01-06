# LendingClubCaseStudy

---

# Lending Club Loan Data Analysis

A data-driven project analyzing Lending Club's loan dataset to uncover insights about borrower behaviors, credit risks, and loan performance.

## Table of Contents

* [General Information](#general-information)  
* [Technologies Used](#technologies-used)  
* [Conclusions](#conclusions)  
* [Acknowledgements](#acknowledgements)  
* [Contact](#contact)

## General Information

- **Project Background:**  
  Lending Club is a peer-to-peer lending company that facilitates loans to borrowers while allowing investors to fund these loans. This dataset provides an opportunity to analyze borrower behaviors, credit risk factors, and loan repayment trends.  
- **Business Problem:**  
  The analysis aims to address key business problems such as identifying factors contributing to loan defaults, evaluating borrower risk, and improving loan approval decisions.  
- **Dataset Used:**  
  The Lending Club loan dataset includes 111 columns with information such as loan amount, interest rate, annual income, credit utilization, and repayment status. Key columns analyzed include `int_rate`, `annual_inc`, `loan_amnt`, `fico_range`, `loan_status`, and `revol_util`.

# Loan Default Risk Prediction 

> This project aims to apply Exploratory Data Analysis (EDA) techniques to analyze loan applicants' data and identify patterns that predict the likelihood of loan default. The goal is to provide valuable insights to minimize the risk of financial loss for the company while lending.

## Table of Contents follows
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)
* [Business Understanding](#business-understanding)
* [Business Objectives](#business-objectives)
* [Contact](#contact)

## General Information
- **Background**: This project focuses on understanding the risks associated with lending by analyzing past loan applications, identifying patterns and trends to predict future loan defaults. The project applies EDA to identify key factors that influence the likelihood of default and helps businesses make informed decisions about loan approvals.
- **Business Problem**: The company faces two risks when approving loans:
  1. If a loan is not approved for a creditworthy applicant, the company loses a potential business opportunity.
  2. If the loan is approved for an applicant who defaults, the company faces financial losses.
- **Dataset**: The dataset includes information about past loan applicants, including features like income, credit history, loan amount, interest rates, and payment status (e.g., 'fully paid', 'current', 'charged-off'). The goal is to identify applicants who are likely to default (charged-off) on their loans.

## Business Understanding
In this case study, you work for a consumer finance company that lends loans to urban customers. The company makes loan decisions based on applicants' profiles, and the decision can lead to one of two outcomes:
1. **Loan Accepted**: 
   - **Fully Paid**: The applicant has fully repaid the loan.
   - **Current**: The applicant is in the process of repaying the loan.
   - **Charged-off**: The applicant has defaulted on the loan, causing a loss to the company.
2. **Loan Rejected**: The loan is denied due to various reasons like not meeting the requirements.

The company aims to predict whether an applicant is likely to default, which can help mitigate financial losses and improve decision-making processes. By understanding consumer and loan attributes, we can identify patterns that signify the risk of default and take necessary actions such as denying loans, adjusting loan amounts, or offering higher interest rates to risky applicants.

## Business Objectives
The main objective of this project is to understand the driving factors behind loan defaults. By identifying risky loan applicants, the company can:
- **Reduce Credit Loss**: Credit loss occurs when borrowers default. Identifying these risky applicants and minimizing their loans helps the company cut down on losses.
- **Risk Analytics**: The company aims to assess the risk of lending to individual customers and understand the variables that are most likely to influence default.

The insights generated from this analysis will help the company in better portfolio management and risk mitigation, which is crucial for improving business profitability.

## Data Understanding
- **Identifying Data Quality Issues**: 
  - **Missing Values**: The dataset has some missing values, which were handled by using strategies like replacing with the median or mean, depending on the nature of the column (numerical or categorical).
  - **Data Types**: Ensuring all columns are of the correct data type is essential for proper analysis. For instance, some columns that are strings (like `int_rate` and `revol_util`) were converted into numerical formats after removing non-numeric characters such as '%'.
  - **Outliers**: Some columns showed a few extreme values which may influence model predictions. These were either capped or transformed to minimize their impact.





## Analysis:

---

### **Univariate Analysis Results in Business Terms**

Univariate analysis focuses on analyzing one variable at a time, aiming to summarize its key patterns and characteristics. Here’s how the results can be interpreted for business impact:

1. **Interest Rate (`int_rate`) Distribution:**  
     
   - **Insight:** Interest rates are mostly distributed between 10% and 20%, with very few loans exceeding 30%.  
   - **Business Interpretation:** Lending Club has set interest rates competitively, but higher interest rates may increase the risk of default. This emphasizes the importance of balancing risk-based pricing strategies.

   

2. **Loan Amount (`loan_amnt`):**  
     
   - **Insight:** Most loans fall within the range of $5,000 to $15,000, with a few outliers for higher amounts.  
   - **Business Interpretation:** Borrowers often request moderate loan amounts, which align with average consumer credit needs like debt consolidation or home improvement. However, larger loans might warrant stricter underwriting criteria to mitigate risk.

   

3. **Debt-to-Income Ratio (`dti`):**  
     
   - **Insight:** The majority of borrowers have a DTI below 20%, but some exceed 35%.  
   - **Business Interpretation:** Borrowers with high DTI ratios may face financial stress, increasing default risk. Lending Club can use this insight to refine loan approval criteria by setting DTI thresholds.

   

4. **Employment Length (`emp_length`):**  
     
   - **Insight:** A significant number of borrowers have 5+ years of employment history.  
   - **Business Interpretation:** Borrowers with stable employment are more reliable. This supports focusing on employment length as a key feature for creditworthiness evaluation.

---

### **Bivariate Analysis Results in Business Terms**

Bivariate analysis examines relationships between two variables, uncovering patterns that impact business outcomes.

1. **Interest Rate (`int_rate`) vs. Loan Status (`loan_status`):**  
     
   - **Insight:** Default rates are higher for loans with higher interest rates.  
   - **Business Interpretation:** Loans with higher interest rates might disproportionately attract riskier borrowers, leading to increased defaults. Adjusting risk-based pricing or enhancing credit assessments for such borrowers could reduce defaults.

   

2. **Annual Income (`annual_inc`) vs. Loan Amount (`loan_amnt`):**  
     
   - **Insight:** Higher loan amounts are typically associated with borrowers with higher annual incomes.  
   - **Business Interpretation:** Borrowers’ repayment capacity aligns with income levels. Encouraging higher-income borrowers to apply for larger loans might improve repayment rates and profitability.

   

3. **Debt-to-Income Ratio (`dti`) vs. Loan Status (`loan_status`):**  
     
   - **Insight:** Loans with higher DTIs have higher default rates.  
   - **Business Interpretation:** Borrowers with high debt burdens are less likely to repay loans on time. Implementing stricter DTI thresholds for loan approvals could mitigate this risk.

   

4. **Credit Utilization (`revol_util`) vs. Loan Status (`loan_status`):**  
     
   - **Insight:** High credit utilization correlates with a higher probability of default.  
   - **Business Interpretation:** Borrowers heavily utilizing their credit lines may indicate financial instability. Lending Club could prioritize reducing exposure to such borrowers or offer smaller loans with stricter terms.

   

5. **Loan Term (`term`) vs. Loan Status (`loan_status`):**  
     
   - **Insight:** Loans with 60-month terms have a higher default rate compared to 36-month loans.  
   - **Business Interpretation:** Longer-term loans increase borrower exposure to financial uncertainty. Offering incentives for shorter-term loans or stricter terms for 60-month loans could mitigate default risks.

---

### **Business Recommendations Based on Analysis**

1. **Risk-Based Pricing:**  
     
   - Interest rates should reflect not just the borrower’s creditworthiness but also other factors such as loan purpose and DTI ratio. For high-risk borrowers, consider smaller loans or higher collateral requirements.

   

2. **Loan Approval Policies:**  
     
   - Use thresholds for critical metrics like DTI, annual income, and credit utilization to filter high-risk applicants.

   

3. **Customer Segmentation:**  
     
   - Identify low-risk segments, such as borrowers with stable employment and low DTI, and target them with promotional loan products to improve profitability and reduce defaults.

   

4. **Monitoring High-Risk Factors:**  
     
   - Continuous monitoring of borrowers with high credit utilization and longer loan terms can help in early identification of potential delinquencies.

   

5. **Dynamic Loan Terms:**  
     
   - Offer tailored terms (e.g., interest rates, loan amounts, repayment periods) based on borrower characteristics to optimize repayment rates.

## Conclusions

- **Conclusion 1:** Borrowers with higher credit utilization (`revol_util`) tend to have a higher probability of loan defaults.  
- **Conclusion 2:** Income levels (`annual_inc`) significantly impact loan repayment performance. Borrowers with lower annual income are more likely to default.  
- **Conclusion 3:** Loans with longer terms (60 months) and higher interest rates (`int_rate`) show a higher default rate compared to shorter-term loans.  
- **Conclusion 4:** Employment length (`emp_length`) and credit score range (`fico_range`) are strong indicators of borrower reliability.  
- **Conclusion 5:** Debt-to-Income ratio (`dti`) is a critical factor in determining borrower risk.
- **Key Factor 1**: Variables such as `income`, `debt-to-income ratio (DTI)`, and `credit utilization` significantly impact loan default rates.
- **Key Factor 2**: Applicants with higher `interest rates` and `loan amounts` tend to have a higher likelihood of default.
- **Key Factor 3**: Employment length and the applicant's home ownership status have a moderate effect on default behavior.
- **Key Factor 4**: Applicants with a higher number of delinquencies (`delinq_2yrs`) and recent credit inquiries (`inq_last_6mths`) are more likely to default.

## Presentation and actionable items
https://github.com/sendtoshailesh/LendingClubCaseStudy/blob/main/Lending%20Club%20case%20study%20Presentation%20and%20Recommendations.pdf

## Technologies Used

- **Python 3.9**  
  Libraries:  
  - **pandas** \- 1.3.3  
  - **numpy** \- 1.21.2  
  - **matplotlib** \- 3.4.3  
  - **seaborn** \- 0.11.2  
  - **scikit-learn** \- 0.24.2

## Acknowledgements

- This project was inspired by the Lending Club loan data analysis challenge.  
- References:  
  - [Lending Club Data Dictionary](https://www.lendingclub.com/info/download-data.action)  
  - Open-source tutorials and documentation from Pandas and Matplotlib libraries.

## Contact

Created by \[@sendtoshailesh\] \- feel free to contact me for further details or collaboration\!


