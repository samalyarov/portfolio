# Project description:
Project involves analysis of "Procrastinate Pro+" entertainment app. Despite the large investment into advertisement the company keeps losing money for several months in a row already. Our job was to find out what could have caused it and made recommendation on optimising advertisement strategies.

# Conclusions:
1. Most of our users come from the United States (~100k users). In addition to that, US users have a higher degree of actual payers (6,9% compared to ~4% on average). Most popular platform for using our app is Iphone (phones are more popular than PCs), but the share of paying users is the same among different platforms.
2. Most users found our app organicaly (not through any advertisement method), but "organic" users are less likely to turn out to be payers (only ~2% of them). FaceBoom is the best user sourcing platform in our "arsenal" - it attracted 29.144 new users throughout the analysed period, of which 12% (almost 3 times more than average!) became paying users over time. Second place - TipTop (19.561 users, 10% payers).
3. Overall marketing expenses are $105.497. Most of these funds have been spent on two "heavy hitters" - FaceBoom and TipTop, who, while attracting the most users (and paying users) are also the most expensive (cost per user in TipTop is twice it's closest competition). These costs have been higher than average from the very start, but over the analysed period have continued to grow rapidly. Over that period average RPU (Revenue Per User) and RPPU (Revenue Per Paying User) remained the same, while UAC (User Acquisition Costs) continued to grow.
4. User LTV (LifeTime Value) over the same period stayed largely the same - by the end of analysed period due to increased UAC it took users 2 weeks to pay off their acquisition cost - not even become profitable, which indicates a huge financial risk for the company.
5. One of the "risk points" are Apple platforms - ROI (Return On Investment) on Iphone and Mac users exceed required limits, and stipulate significant challenges for the company. It is recommended that the problems with these platforms are analysed more thoroughly - in order to uncover potential insights on issues related to using our app on these platforms.
6. The biggest "risk points" are the aforementioned marketing agencies. AdNonSense has shown the worst ROI value (0.83 by the end of second week), incurring mostly losses for the majority of analysed period (mostly due to very low user retention), FaceBoom fared even worse on average (AdNonSense had select profitable cohorts of users, while FaceBoom did not) even though it had the highest conversion rate (from user to paying user) of all analysed agencies (users were more willing to pay but less likely to stay), while TipTop was profitable at the start, but the huge increase in marketing expenses did not pay off. Other user acquisition channels fared better - showing ROI from 1.53 (WahooNetBanner) all the way up to 2.24 and higher.
7. In regards to regions - EU is mostly profitable and is showing stable results, while US has certain issues - which mostly come from the previously discussed problematic channels. It is important to note that the problem lies in interaction with these channels, as the region also hosts some of the more profitable user acquisition channels (MediaTornado, RocketSuperAds and YRabiit, having shown 244%, 224% and 258% ROI accordingly). There is, however, a general problem with retention in regards to american users, which constitutes a perspective avenue for further research and analysis.

# Data:
Dataset has been provided by the app and features data about users acquired between May 1 and October 29 of year 2019.
Data points feature:
- File *visits_info_short.csv* keeps server logs on website and app entries:
    - `User Id` — users ID
    - `Region` — users country
    - `Device` — users device type (platform used)
    - `Channel` — marketing agency ID
    - `Session Start` — date and time of session start
    - `Session End` — date and time of session end
- File *orders_info_short.csv* keeps orders info:
    - `User Id` — unique user ID
    - `Event Dt` — date and time of purchase
    - `Revenue` — order total
- File *costs_info_short.csv* keeps info on marketing campaigns expenses:
    - `dt` — marketing campaign date
    - `Channel` — marketing agency ID
    - `costs` — marketing campaign expenses

# Libraries used:
*pandas, numpy, matplotlib, seaborn, datetime, tqdm*
