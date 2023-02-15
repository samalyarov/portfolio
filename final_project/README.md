**Final project consisted of three separate tasks:**
1. Analysing user behaviour of mobile marketplace app.
2. Analyzing results of A/B test conducted by another group of analysts. Apart from analysing the results themselves, recommendations were given on how to improve future A|B tests on the same platform.
3. Analyzing the database of an app featuring book subscriptions. This project featured SQL-related skills.

All aforementioned projects have been done separately and thus, are located in separate Jupyter Notebooks:
1. [Analyzing mobile app user behaviour](#Analytics)
2. [A/B testing](#A/B)
3. [SQL](#SQL)

<a id='Analytics'></a>

[**Analyzing mobile app user behaviour**](https://github.com/samalyarov/practicum_projects/blob/main/final_project/Final%20project.%20Mobile%20App%20User%20Behaviour%20Analysis.ipynb)

# Project description:
Project features analysis of user behaviour within a marketplace app called 'Unnecessary things'. During the analysis **data was loaded, pre-processed and subsequently analysed. That analysis included statistical analysis** of conversion into the target action, as well as analysing several core behavioural patterns (creating user roadmaps based on logged data).

A **presentation** was done as a result of that research with core points to demonstrate to the managers: https://disk.yandex.ru/i/clHuzxWsucVVLA
A **dashboard** was also created, listing key important features at the request of app managers and owners: https://public.tableau.com/views/2_16730628439990/2?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link

User behaviour was analyzed by 'sessions'. **User activity was segmented into sessions based on time between their actions** - once the user has been inactive for 30 minutes his current session was treated as 'finished' and his next action was treated as a start of next session. 3**0 minutes were chosen based on average metric from Google Analytics and discussion with team lead** (as an appropriate time for mobile marketplace app).

# Conclusions:

1. Most common user source for our app is 'Yandex" which sourced ~45% of all users within the analysed period. The other 55% are spread between 'Google' and 'Other' sources. Yandex was leading throughout the whole analysed period, however, beginning at 28-31 October their lead was diminishing as the amount of users from 'Other' sources was growing significantly. As a result, one of the core recommendations is to conduct a thorough financial analysis on profitability of users from various sources. As of right now, Yandex appears to be the best partner, although it is recommended to continue the diversification of sources, as a substantial share of app's users come from 'Google' and 'Other' sources.
2. General trend appears to be largely negative - good growth was demonstrated in the beginning (before 13th-15th), but then that growth slowed and eventually came to a halt. Considering the fact that our product is new and is just establishing itself in the market - at this stage exponential growth is a requirement, which means that this problems needs to be adressed. Primary recommendation is further analysis of user sourcing, increasing marketing spending, introducing new user recruitment programms and looking into changes which may have halted the apps growth. User acquisition also spiked around 22-23 and 13-15th - there may have been certain successful user acquisition programms introduced at these dates.
3. User retention during the first days was about 9.7% - 11.7%, while by the end of second week it decreased to around 3-4%. Users from 'Other' sources demonstrate substantially higher retention rates. There are also interesting 'spikes', potentially prompting older users to return around aforementioned dates.
4. The most common event in logs is `tips_show`, second place is taken by `photos_show`, third one - by `advert_open`. There are certain differences between users from different sources, which indicate different app using practices.
5. The dataset features 4293 unique users and 10368 sessions - about 2.42 sessions per user which is higher than average, which appears to be around 2 sessions per user (according to open sources research). This metric is mostly similar between users from different sources. 
6. A list of 1% most active users has been formed and is ready to be given to other departments (marketing, customer service and|or devs) and may be used in further analysis to determine their motivations. As for current research - data corresponding to those users was discarded as it may heavily influence the outcome of research and our "behavioural patterns" would only show information on those users.
7. Analysing the target action (`contacts_show`) has shown that alongside being common, actions with the highest conversion rates (into the target action) are `favories_add` (38,6%) and `photos_show` (30,5%). Thus, it is recommended to focus on developing tools to interact with your favorites list and encourage sellers to post pictures as both those actions influence conversion heavily.
8. There are significant differences in action lengths - for example, `contacts_call` is an action with median length of 138,5 seconds, `tips_show` is second with 76 seconds, while some actions usually only take seconds. Average session length is 771 seconds (bit less than 13 minutes) and features slight differences between users from different sources (users from 'Other' sources on average have shorter sessions)
9. Most active day is Monday, after which user activity gradually decreases over the week, while active hours generally correspond with working hours of an average adult - app usage is realtively high at 09.00 - 16.00 and after work hours with a slight decrease during a most common end of working day hours. A main recommendation here would be to focus marketing and ad campaigns around those hours.
10. Average session features ~4.64 actions taken during it, with 75% sessions ending in 5 actions or less. Analysis has uncovered several core user journey maps and succesfully determined our 'core' users (from the target action conversion perspective) - that would be users following one of two following scenarios:
  - `map` => `tips_show` => `contacts_show` shows and 18% conversion of all people in the funnel.
  - `search` => `photos_show` => `contacts_show` also features high conversion rate (11%), and especially high conversion from step 2 to step 3 (29%, compared to 20% of the previous pattern).
11. Statistical analysis was employed to test 3 main hypotheses:
  - There is no difference between conversion into target action between two groups of users: those that encounter `tips_show` and `tips_click` and those that only encounter `tips_show` (were shown tips but did not click on them). That null hypothesis was rejected - there is indeed statistically significant difference between those three groups with the first one showing ~12% better conversion rate.
  - There is no difference between conversion into target action between those that added an advert to favories and those that did not. That null hypothesis has also been rejected - first group has shown ~17.6% better conversion rate.
  - There is no difference between conversion into target action between users from different sources. That null hypothesis has also been rejected - there is statistically significant difference between users from 'Other' sources and 'Google'/'Yandex'-sourced users, although there is no significant difference between users from latter two sources.
Statistical analysis was done using z-test. Bonferroni correction was employed as at one point several comparisons were being done at the same point, and as such alpha had to be adjusted to provide statistically sound data.

# Data:
Our datasets feature logs of action taken by the apps users. Only actions by users whose first action is logged later than 7th October 2019 is logged so as to only analyze recent events. 

Data points feature:
Dataset 'mobile_sources.csv':
- `userId` — user ID,
- source — user source ('Yandex', 'Google', 'Other').

Dataset `mobile_dataset.csv`:
- event.time — event time,
- user.id — user ID,
- event.name — user action. Types of actions:
  - advert_open — opened an advert for an object,
  - photos_show — was shown photos within an advert,
  - tips_show — was shown recommended adverts,
  - tips_click — clicked a recommended advert,
  - contacts_show and show_contacts — was shown seller's phone number,
  - contacts_call — called the listed phone number,
  - map — opened advert map,
  - search_1—search_7 — various search actions,
  - favorites_add — added an advert to favorites.
  
# Python libraries used:
*pandas, numpy, math, requests, datetime, scipy.stats, matplotlib, seaborn, plotly, warnings*

# Tools used:
*Microsoft PowerPoint, Tableau*

<a id='A/B'></a>

[**A/B testing**](https://github.com/samalyarov/practicum_projects/blob/main/final_project/Final%20project.%20AB%20testing.ipynb)

# Project description:
The task involved assessing the results of a conducted A/B test - both in terms of analysing the results using statistical criteria and in terms of analysing the organisation itself - whether the test can be considered 'properly organized' or should be discarded and if any changes are required for further tests. The task featured strict technical specifications that were to be followed and that thus serve as a benchmark for comparison.

# Conclusions:
1. The data was successfully loaded, however, the logs seem to not contain any data on actions later then 30th of December (actions of users that are of interest to us), even though the test was scheduled to end on 4th of January. This may be a logging error, or an organizational one. Either way - a further inquiry into the subject is recommended.
2. Some users involved into our A/B test were also involved in another one. Seeing how those test may potentially influence each other's results (due to the nature of elements tested) that constitutes a problem which needs to be solved to ensure integrity of further tests. Additionaly, the users that are present in both tests are unequally divided between groups - which further removes the possibility of ignoring that fact.
3. The system did try to get 15% of new users from the EU region (as stated in technical specifications), but failed to account for their activity - only 48% of users selected to participate in the test had any activity at all (which equals to 7.8% of new users in the region).
4. Experimental and control groups had different number of users allocated to them. That does not constitute a major problem - but is overall less than ideal.
5. End of A/B test coincides with one of major marketing campaigns that target that specific region. In addition to that, the test is conducted during the end of the year, which is a unique season in terms of consumption and is generally to be avoided when conducting market research and tests like that (the results are hard to extrapolate).
6. Users in group A (control group) were more active than those in group B. However, group B had a higher number of positive anomalies (users with very high activity).
7. Throughout the whole analyzed period group A was leading in user activity. The only day with different results was the first day of testing - December 7th.
8. Three main hypotheses were tested using statistical methodology: whether the conversion rate (into opening item page, adding item to cart and item purchase) is different between two groups. Only the first hypotheses featured a statistically significant result - users from group A were more likely to open item page as compared to group B. Other two hypotheses had similar results (group A fared better), but failed to achieve statistical significance.

# Data: Data featured several datasets associated with the conducted A/B test.
Dataset `ab_project_marketing_events.csv` — list of marketing events and campaigns in the year 2020:
- `name` — event or campaign name;
- `regions` — regions affected by the campaign;
- `start_dt` — campaign starting date;
- `finish_dt` — campaign finishing date.

Dataset `final_ab_new_users.csv` — information about users registered between 7 and 21 December 2020:
- `user_id` — user ID;
- `first_date` — registration date;
- `region` — user region;
- `device` — user registration device.

Dataset `final_ab_events.csv` — log of user action. Includes users registered from 7 December 2020 and 4 January 2021:
- `user_id` — user ID;
- `event_dt` — date and time of event;
- `event_name` — event name (type);
- `details` — additional details about the event. For instance, if the event is `purchase,` then this field includes the total sum of money spent in USD.

Dataset `final_ab_participants.csv` — list of users included in A/B testing:
- `user_id` — user ID;
- `ab_test` — test name;
- `group` — user groupd (experimental or control).

# Libraries:
*pandas, numpy, math, datetime, scipy.stats, matplotlib, seaborn, plotly, warnings*

<a id='SQL'></a>

[**SQL**](https://github.com/samalyarov/practicum_projects/blob/main/final_project/Final%20project.%20SQL.ipynb)

# Project description:
Our company has recently purchased a big business which rotates around book subscriptions. Our job as an analyst is to analyze the database acquired with the sale to get some information about books, authors and publishers, as well as user ratings and reviews.

# Conclusions:
Analysis was structured around specific questions (and thus, specific queries) which needed answering. 
1. A total of 821 books were published in year 2000 and after that. Out of those 2 were published on 1st of January 2000 - thus, technically, 819 were published AFTER 2nd of January.
2. The first 'Twilight' book has the biggest number of reviews (7). However, it's average rating is rather low - only 3.66.
3. Publisher with the most books over 50 pages published is the 'Penguin Books', which published 42 books that satisfy that criterium.

# Data:
*Database structure:*
![image](https://user-images.githubusercontent.com/107198574/219220347-34bee82e-2736-4d99-a3a9-9dae5bac9c34.png)
Tables listed above feature:

Table `books`. Contains information about books:
  - `book_id` — book ID;
  - `author_id` — author ID;
  - `title` — book title;
  - `num_pages` — number of pages in the book;
  - `publication_date` — book publucation date;
  - `publisher_id` — publisher ID.
  
Table `authors`. Contains information about authors:
  - `author_id` — author ID;
  - `author` — author name.
  
Table `publishers`. Contains information about publishers:
  - `publisher_id` — publisher ID;
  - `publisher` — publisher name;
  
Table`ratings`. Contains information about user ratings:
  - `rating_id` — rating ID;
  - `book_id` — book ID;
  - `username` — username of person who posted the rating;
  - `rating` — book rating.
  
Table `reviews`.** Contains information about user reviews:
    - `review_id` — review ID;
    - `book_id` — book ID;
    - `username` — username of person who posted the review;
    - `text` — review text.

# Libraries:
*pandas, matplotlib, seaborn, sqlalchemy*
