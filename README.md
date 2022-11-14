# Determinants of irrecoverable Prosper Loans
## by Nyiko Ndlebe


## Dataset
This study explores a dataset containing a list of loans from credit provider, Prosper. The original dataset consists of a total of 113,937 rows containing the details of loans issued from 2005 to 2014, with 81 different variables.
> The original data can be obtained from the link below: <br>
https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv

>While a dictionary describing all the variables can be found below: <br>
> https://docs.google.com/spreadsheets/d/1gDyi_L4UvIrLTEC6Wri5nbaMmkGmLQBk-Yx3z0XDEtI/edit?usp=sharing

After some preliminary cleaning and removing data that I considered to be irrelevant to the study, the dataset was reduced to 26,210 loans with the following 12 variables:
- Term
- LoanStatus
- BorrowerAPR
- ProsperScore
- ListingCategory
- EmploymentStatus
- IsBorrowerHomeowner
- IncomeRange
- StatedMonthlyIncome
- LoanOriginalAmount
- MonthlyLoanPayment
- Investors

I also limited the LoanStatus variable to only two categories, namely 'Completed' and 'Irrecoverable'

## Summary of Findings
> The aim of this study was to determine which factors, if any, contribute to a Prosper loan being deemed irrecoverable versus being completed. I detail the my findings in the sections below under the headings; Univariate Exploration, Bivariate Exploration and Multivariate Exploration.

#### Univariate Exploration
> This section explored the distribution of the individual variables in the study and made the following findings
- **Term**: The majority of loans are issued for 36 months followed by 60 months 
<br> <br>
- **LoanStatus**: More than three times as many loans are completed than those that are irrecoverable 
<br> <br>
- **BorrowerAPR**: The majority of loans fall between 0.05 and 0.40, with the largest frequency of interest rates just after 0.35. The next highest peaks are around 0.30 and 0.12
<br> <br>
- **ProsperScore**: Scores are slightly skewed to the left, with 8 and 6 being the highest scores respectively. The lowest frequencies are at 11 and 1 respectively
<br> <br>
- **ListingCategory**: Most of the loans taken out are for debt consolidation
<br> <br>
- **EmploymentStatus**: Most borrowers are employed, while an almost insignificant amount of borrowers are either part-time workers or retired
<br> <br>
- **IncomeRange**: Most borrowers have an income between $25,000 and $74,999. The data is slightly skewed to the left
<br> <br>
- **StatedMonthlyIncome**: Incomes are skewed to the right, with the vast majority if observations below $26,500. Most incomes are concentrated around the $5,000 level before dropping off drastically after $10,000
<br> <br>
- **LoanOriginalAmount**: Most loans taken out are valued around $3,000. There are also peaks at $10,000 and $15,000 and some smaller ones at. There are smaller peaks at $20,000 and $25,000
<br> <br>
- **MonthlyLoanPayment**: The data is skewed to the right, with a massive peak around a 200 monthly payment
<br> <br>
- **Investors**: The data is skewed to the right, with a massive peak at 0. Investors did not participate in a lot of loans that presumably did not meet their criteria

#### Bivariate Exploration
> This next section focused on the relationship between a combination of two of the variables above

 - The most significant relationship the study is between the original loan amount and monthly loan payments. The relationship has a correlation coefficient of 0.85. You would expect a higher loan amount to coincide with higher monthly loan payments. The next most significant relationship is between BorrowerAPR and ProsperScore. The relationship is negative with a correlation coefficient of 0.74, indicating that borrowers with higher Prosper Scores receive more favourable interest rates. 

- Other relationships of interest include
    - Slightly negative relationship between the loan amount and BorrowerAPR - indicating that interest rates may be lower for larger loan amounts
    - Slightly negative relationship between the number of investors and BorrowerAPR - interest rates may be lower for loans that have more investors invested
    - The number of investors has a similarly positive relationship with ProsperScore, LoanOriginalAmount and MonthlyLoanPayment
    - An increase in the number of investors may lend credibility to a borrower and thus result in a higher Prosper Score
    - An increase in the number of investors means that there would be more funds available to lend out, hence a higher loan amount and therefore a higher monthly loan payment

- Prosper Scores between 1 and 6 make up 67.7% of irrecoverable loans, with scores of 6,5 and 4 being the most prevalent. There is only one irrecoverable loan amongst borrowers with a ProsperScore of 11, while the most completed loans have borrowers with a ProsperScore of 8, followed by 6 and then 9.

- I could not identify a strong relationship between borrowers employment status on the likelihood of loan being irrecoverable. Employed borrowers dominate the total number of loans issued, however the distribution of the different employment statuses is similar across irrecoverable and completed.

- The most common type of loan is for debt consolidation and by extension it is also the most common loan that becomes irrecoverable. Other loans,business and home improvement loans are the next most common/ The next most common completed loans are for home improvements and business respectively, while there is very little difference between the frequency of completed and irrecoverable loans for household expenses and medical/dental.

- Most borrowers are in the $25,000 to $74,999 income range, making up 44.5% of borrowers. Borrowers in the $25,000 to $49,999 income range appear to be the most likely not to complete their loans. Loans for borrowers with $0 appear almost as likely to be irrecoverable as completed. Initial savings may play a part in them being able to service the debt without an income.

- It appears that borrowers who do not own homes are slightly more likely to default than homeowners, while the majority of loans taken out are for a 36 month term. Most of the defaults are for loans with a 36 month term and there are very few defaults for 12 month loans.In addition irrecoverable loans are more associated with a higher interest rate, on average, than completed loans. The median rate for irrecoverable loans is 0.30 and 0.25 for completed loans.

#### Multivariate Exploration
> In this final section, we explore the finding from the exploration of relationship between three or more variables and how they may impact on a loan being irrecoverable.

- The negative relationship between the number of investors and BorrowerAPR shows that a lower number of investors coupled with higher interest rates leads to more irrecoverable loans. We also find that irrecoverable loans are concentrated where lower incomes meet a lower number of investors and we can also see that for stated monthly incomes above $10,000 the number of irrecoverable loans drops drastically.

- The median loan amount is below $10,000 across all income levels and find that there is generally no difference between the median loan amounts for completed and irrecoverable loans for each income level. The only exception is the $1 - 24,999 range where the loan amount for an irrecoverable loan is slightly higher than a completed loan.

- The median Prosper Score for irrecoverable loans is lower than that of completed loans. This is true across all income ranges, indicating that a loan with a lower Prosper Score, regardless of income level, is more likely to result in a default. For any given Prosper Score, irrecoverable loans will generally have a higher interest rate than completed loans. We also see that BorrowerAPR declines as Prosper Scores increase, while there is only one irrecoverable loan with a ProsperScore of 11.

- Irrecoverable loans with a 36 month term have the highest median BorrowerAPR, followed by 12 months and then 60 months. For Completed loans, the lowest median BorrowerAPR is for a 12 month term. The 36 month term also has the highest BorrowerAPR. The median ProsperScore for completed loans is the same for 12 and 36 month terms. The 60 month term has the lowest median ProsperScore and the median ProsperScore for irrecoverable loans is the same for 12 and 60 month terms. The 36 month term has the lowest median ProsperScore.

- We see that 36 month terms have the higher rates, which coincides with the lowest ProsperScores. This supports the earlier finding of lower Prosper Scores and higher interest rates leading to more irrecoverable loans but also gives us more additional information on which term may be the most problematic.

- The lowest Prosper Scores have the fewest amount of investors and the highest interest rates. Irrecoverable loans for Prosper Scores between 5 and 8 have an almost even distribution across all the interest rates. There are very few irrecoverable loans for Prosper Scores above 8.

- Irrecoverable loans for each Prosper Score are associated with lower incomes than their completed counterparts. Incomes decrease from Prosper Score 1 and reach their lowest levels at Prosper Score 4 and then steadily increase for each level. We find very little difference between loan amounts for irrecoverable and completed loans for each Prosper Score from 1 to 8. For scores of 9 and 10, irrecoverable loans had higher loan amounts than completed loans.

## Key Insights for Presentation

- The biggest predictor of an irrecoverable loan appears to be a higher interest rate (BorrowerAPR). The interest rate is influenced by the borrower's ProsperScore, which is influenced by their income level, loan amount and employment among other factors not explored here. We also see that 36 month terms have higher rates, which coincides with the lowest ProsperScores. This supports the earlier finding of lower ProsperScores and higher interest rates leading to more irrecoverable loans but also gives us more additional information on which term may be the most problematic.