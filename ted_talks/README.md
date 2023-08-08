# Description
This projects features a dashboard creating after analysing a complex dataset with data regarding TED-talks throughout the last ~35 years. Dashboard was created in accordance with the Technical Assignment provided. 
1. After loading the data it had to properly merged - 'UNION' was used to combine 3 separate tables with data on talks and other relationship types were used to properly add data from the two other tables. Based on the results of conducted EDA a date filter was added to all dashboards within the story, default setting was set to the year the initial jump in talks count happened - 2002.
2. Various tools were used in creating the story: sets, calculated fields, LOD, actions, parameters etc. Four dashboards were created correlated to main themes within the dataset, with interactable graphs and conclusions written down on all of them. Those have been combined into a story and published on [Tableau.public](https://public.tableau.com/views/TED-Talks_16902911535330/TED-Talks?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link). Dashboards within the story are designed to be viewed in fullscreen mode (even though they're set to automatic on smaller resolutions graphs may not be fully displayed or may not be readable).

# Conclusions
Key conclusions as presented on the dashboard itself:
1. 2002 is when the massive increase in talks count was first seen. English-speaking countries historically account for most of TED-talks with more then half being held in USA alone and Canada + UK hosting a substantial share of events.
2. There are many topics on which the talks are being held (81 total in current dataset), but the most popular ones are science, technology, culture, society and global issues. Most popular topics are mostly similar among top-3 countries, but there still are some differences - US seem to like technology talks slightly less, while UK does not favor the topic of society, while having more talks on cultural topics. Science and Technology are the topics that generate the highest number of applauses per minute, while Culture and Society seem to the most humorous ones, producing the most laughs. There seems to be a correlation between the duration of the talk and views - but only to a certain extent. The most viewed talks are generally around 20 minutes long, while only rare ones manage to exceed the 40 minute mark and get a large viewership.
4. The most common occupations are displayed on the graph above: mostly creative professions like writers, journalists, authors, designers etc. Vast majority of speakers have only ever done a single talk (88%), with a dozen or so outliers having 5, 6 or even more talks. The most invited speaker is Hans Rosling - he has given 10 talks on various topics throughout the years.
5. The majority of events were held in the United States - 63% of them, to be precise. The number of events has been fluctuating - it has increased substantially around year 2009, peaked in 2011 with 39 events being held and began to somewhat decrease after the second peak during the year 2016. There has been a huge structural change in the number of talks per event: on average, that number has been steadily decreasing through the years.

# Data
Note - the dataset was collected via a separate parser and is not a copy of a [kaggle TED talks dataset](https://www.kaggle.com/datasets/rounakbanik/ted-talks) This dataset consists of several tables:
1. `tableau_project_data_1.csv`, `tableau_project_data_2.csv`, `tableau_project_data_3.csv` store the data about talks themselves. Data points include:
  - talk_id — unique talk ID
  - url — talk URL
  - title — talk title
  - description — a short talk description
  - film_date — recording date
  - duration — talk lenght (in seconds)
  - views — views count
  - main_tag — main talk category
  - speaker_id — unique speaker ID
  - laughter_count — number of times the audience laughed during the talk
  - applause_count — number of times the audience applauded during the talk
  - language — talk language
  - event_id — unique conference ID
    
2. `tableau_project_event_dict.csv` has data on various conferences, during which the talks were held. Data points include:
  - conf_id — unique conference ID
  - event — conference name
  - country — conference country

3. `tableau_project_speakers_dict.csv` has data on individual speakers. Data points include:
  - author_id — unique speaker ID
  - speaker_name — speaker name
  - speaker_occupation — main speaker occupation
  - speaker_description — short description of the speaker and his competences

# Tools used:
*Tableau*
