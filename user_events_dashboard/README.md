# Description
The task was to create a dashboard displaying several key metrics of user interaction with topics on Yandex.Dzen platform. Work on that project was done on a remote server hosted by me on the Yandex.Cloud service. The work proceeded as follows:
1. After installing PostgreSQL I have succesfully deployed a database on remote machine. Accessing the data was done via a SQLalchemy python library.
2. Data pipeline has been developed - I have written a script that collects data over the required time period and used crontab to make that script run on designated time.
3. Visualizing the data was done via a Tableau dashboard. Several filters were utilised when creating a dashboard, after which that dashboard was hosted on that remote machine. Dashboard link: https://public.tableau.com/app/profile/sam4588/viz/shared/7CP29P4DX 
4. Apart from ongoing analysis, the project required a presentation - a link to which is as follows: https://disk.yandex.com/i/EgOVmI1O85uVag

# Conclusions
1. Data features significant fluctuations over time - most active time is around 18:52, while before that the activity rates are very low.
2. Most people are interested in the following topics: "Science" (7% of all publications), "Relationships" (6,6%), "Interesting Facts" (6,4%) and "Society" (6,3%).
3. Most common source topics are: "Family Relations" (10,7%), "Russia" (9,6%), "Useful Tips" (8,8%), "Travelling" (7,7%), "Celebrities" (7,7%).
4. Popular topics most commonly presented together are: "Stories and Travelling" (4587 mentions), "Society and Russia" (3471), "Science and Cinema" (3279).
5. There are no significant differences in behaviour displayed by people from variying age groups. At the same time, it is recommended to not take that conclusion at face value and conduct a further research on a more extensive dataset if that topic in of interest.

# Data
Using the SQLalchemy library, the data acquired from the database was further transformed into an .csv file which was used to create a Tableau dashboard.

# Python libraries used:
*pandas, matplotlib, seaborn, sqlalchemy*
# Tools used:
*Microsoft PowerPoint, PostgreSQL, Tableau*


