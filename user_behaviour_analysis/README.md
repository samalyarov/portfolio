# Project description:
This project features the analysis of customers in an online food store. Primary task is to understand the behavioural patterns of our customers and conduct an A|B test (in conjunction wih A|A testing) in order to determine the profitability of proposed changes.

# Conclusions:
1. WIthin given logs each user participates in, on average, 32.28 actions, but only in ~2.67 unique actins (which means that out of 5 possible actions analysed each user only experiences about half of them).
2. Most of data in the logs is timed August 1st or later - which may imply an important update being pushed at this date or a marketing campaign bearing fruit. In order ot reflect that, the analysis focuses on data between 1st and 7th of August. Getting rid of prior data removed 17 unique users and 2826 entries.
3. Overall share of anomalous users is ~3%. A table with their IDs has been created and is ready for use by other departments (supposedly, sales, UX and development) as these 3% of users have taken 20% of overall actions in the logs. Understanding their motivations and behaviour is very important, but is somewhat outside the scope of current research - especially for A|B testing, as they alone would determine the results.
4. 98% of users encountered the `MainScreenAppear` event, while only 46% made it to `PaymentScreenSuccessful`. The `Tutorial` event has been discarded while analyzing the event funnels, as it is not a required step (lies otside the strict funnel) and only 11% of users have finished it).
5. 39% of users visiting the main page `MainScreenAppear` do not make it to the 'offers' screen `OffersScreenAppear` 19% of users seeing the offers page don't make it to the cart screen `CartScreenAppear`. 5% of users opening the cart do not make it to the payment screen `PaymentScreenSuccessful`. Thus, the biggest user leak is seen during the transition from `MainScreenAppear` to `OfferScreenAppear` - and that is exactly where the analytical and development efforts are to be focused. A deeper look into that particular stage is recommended, potentially coupled with UX-research in order to increase conversion on that stage.
6. Three datasets were used for A|B testing: the original dataset, a cleaned dataset including the anomalous user's data and a fully "cleaned" dataset without data corresponding to anoumalous users. All datasets feature different number of people in all three groups - which is not ideal, but acceptable.
7. Statistical analysis has conclusively shown that there are no significant (within 95% confidence interval) differences between both control groups. Thus, the mechanism for assigning groups works correctly.
8. The A|B test itself has shown that there is no significant difference (within the same 95% confidence interval) between user behaviour in control and treatment groups and as such, changing the font bore no effect on user funnels. The analysis compaired the results of treatment group to both control groups individually and to the combined results of both of them.
9. Increasing 'alpha' to 0.1 (and, consequently, lowering the confidence interval to 90%) has lead to null hypothesis being rejected in only one of 6 tested cases, while significantly increasing the chance of error. 


# Data:
Research is based on recorded logs stored in the following file: `/datasets/logs_exp.csv`
Data points feature:
- `EventName` — event name 
- `DeviceIDHash` — unique device ID
- `EventTimestamp` — event time
- `ExpId` — A|B test group number. Groups #246 and #247 — are control groups, group #248 is a treatment group.

# Libraries used:
*pandas, numpy, math, scipy, matplotlib, seaborn, datetime, plotly*


