# Project description:
As an online shop analyst we have been provided with a list of hypotheses to test in order to increase the shops profitability and margins. The task was to prioritise these hypotheses, test the most important ones, conduct an A/B test and analyze the results. Research consists of data acquisition, pre-processing, exploratory analysis, hypothesis prioritisation, main body including structured analysis and A/B testing.

# Conclusions:
1. Two methods were used to prioritise hypotheses - the ICE (Impact, Confidence, Effort) methodology and RICE (Reach, Impact, Confidence, Effort) methodology. The latter has been chosen as a more inclusive one, featuring an important "Reach" aspect, potentially important for profitability asessment.
2. A/B testing has shown a statistically significant increase (~20% better conversion from visits to orders) for group B at a 99% confidence interval. Difference stems from group B users making more orders, while average bill remains largely similar between control and treatment groups.
3. Interestingly enough, pre-processing data (getting rid of anomalies) has decreased group B's advantage - which may indicate that the changes tested may also be causing a higher degree of better paying users. That indicates an interesting prospect for further research.

# Data:
Dataset has been provided by the app and features data about users acquired between May 1 and October 29 of year 2019.
Data points feature:
- File /datasets/hypothesis.csv. Features the hypotheses.
    - `Hypothesis` — краткое описание гипотезы;
    - `Reach` — охват пользователей по 10-балльной шкале;
    - `Impact` — влияние на пользователей по 10-балльной шкале;
    - `Confidence` — уверенность в гипотезе по 10-балльной шкале;
    - `Efforts` — затраты ресурсов на проверку гипотезы по 10-балльной шкале. Чем больше значение Efforts, тем дороже проверка гипотезы.
    
- File /datasets/orders.csv. Features information about user purchases (orders).
    - `transactionId` — идентификатор заказа;
    - `visitorId` — идентификатор пользователя, совершившего заказ;
    - `date` — дата, когда был совершён заказ;
    - `revenue` — выручка заказа;
    - `group` — группа A/B-теста, в которую попал заказ.
    
- File /datasets/visitors.csv. Features information for A\B testing.
    - `date` — дата;
    - `group` — группа A/B-теста;
    - `visitors` — количество пользователей в указанную дату в указанной группе A/B-теста

# Libraries used:
*pandas, numpy, scipy, matplotlib, seaborn, datetime*

