# Project description:
Project involves analysis of data from online game marketplace. Key factors influencing popularity of different genres|games have been identified among different segments of users. Goal of the research is to prepare the marketplace for next year ad and promotional campaigns. Conducted analysis has allowed to create profiles of users among various regions (in order to better target the aforementioned campaigns) and test several hypotheses regarding game consumption practices of different users. 

Projects consists of data acquisition, pre-processing, exploratory data analysis, main research and statistical analysis.

# Conclusions:
1. Data has been segmented between various platforms. The most important for next year projections have been identified - the "cows" (3ds|PC), the "growers" (Xbox One|PS4), the "fading away" segment (PSV, WiiU).
2. A decision to focus the research on most recent results has been made (years 2010-2016), as it features several key changes in the industry (advent of mobile gaming + several others, as indicated by further research) in addition to being relatively recent.
3. Better selling games typically have better ratings (the correlation is noticably). Interestingly enough, with the exception of WiiU, the correlation between user ratings and game sales are minimal, if present at all, while correlation between critic ratings and sales is quite significant, which constitutes the neccesity to focus on critics and influencers during promotional campaigns.
4. North America seems to bring in the most profit for the company, while Japanese regions is only bringing in small amounts.
5. Best-selling genres overall (within the period of interest) are: shooters, sport games and platformers. Action-games and fighting simulators also perform rather well. There is also a question of "star" games - ones performing way better than competition. Number of said games is way higher in sport games, while shooters and platformers are better "on average". 
6. Preferences in genres also differ by region - japanese users express bigger interest in RPGs (much like NA users) and platformers, while in Europe racing games are one of top-3 genres. The differences are not limited to game genres - they are also present when analysing platform preferences - while PS3, PS4 and Wii are present in all 3 regions, EU and NA users also frequently use PCs and Xbox360, while Japanese ones favor PSV and 3DS.
7. Two statistical hypotheses have been tested: that average user ratings of Xbox360 and PC games are equal and that average user ratings of Action and Sports games are the same. Both hypotheses have been proven wrong - indicating that user ratings differ in both cases. T-test (independent samples) has been chosen as a method of testing these hypotheses.

# Data:
Dataset has been provided by the marketplace itself and features data about games up to year 2016. The campaigns
Data points feature:
- `Name` — name of the game
- `Platform` — platform the game has been released for
- `Year_of_Release` — year of release
- `Genre` — game genre
- `NA_sales` — sales in North America (millions of copies sold)
- `EU_sales` — sales in Europe (millions of copies sold)
- `JP_sales` — sales in Japan (millions of copies sold)
- `Other_sales` — sales in other regions (millions of copies sold)
- `Critic_Score` — critic score (1-100)
- `User_Score` — user score (1-100)
- `Rating— ESRB` (Entertainment Software Rating Board) rating.

# Libraries used:
*pandas, numpy, scipy, matplotlib, seaborn, tqdm*


