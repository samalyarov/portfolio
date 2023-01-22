# Project description:
The beneficiary of this research is a bank. More specifically - the crediting department. Main questions that they have are whether potential client's marital status and number of children correlate with likelyhood of him fulfilling his obligations to the bank. The results of said research are to be used in creating a credit score model, which in turn will be used to evaluate how likely is a given client to return the money borrowed.

# Conclusions:
1. Loans taken in order to purchase an automobile are, in general, 15% more likely to cause payment delays. Education loans are 14% more likely. The safest loan to give is the one that is taken with the purpose of purchasing housing - the share of loans with payment delays in their history in this category is 11% less than average.
2. People earning 200.000 - 1.000.000 rubles per month are 13% less likely to delay their payments. In general, there is a correlation between client's salary and his likelyhood to delay payments, although that requires further analysis due to small sample size. Another "reliable" income group is people with income ranging between 30 and 50 thousand rubles, but likewise, the sample size is too small to make any statistically viable conclusions.
3. Share of people with payment delays is 13% higher among those with kids (compared to those without), but there is no significant difference among people with different number of children.
4. People, that are "living together, not married" feature a 14% higher than average share of people with payment delays. Another "risky group" are unmarried people (20% higher). The safest group are widows (19% lower than average share of payment delays).
5. More detailed analysis can be found in the .ipynb file attached.

# Data:
Data from analysis has been provided by the bank. Data points for each client:
- 'children' — number of children
- 'days_employed' — total number of days employed
- 'dob_years' — cliends age in years
- 'education' — education level
- 'education_id' — education level ID
- 'family_status' — marital status
- 'family_status_id' — marital status ID
- 'gender' — client's gender
- 'income_type' — income source
- 'debt' — whether the client has ever delayed his loan peyments
- 'total_income' — overall monthly income
- 'purpose' — stated purpose for taking a loan

# Libraries used:
*pandas, matplotlib, seaborn*
