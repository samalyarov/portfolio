# Project description:
Premise of the research is that potential investors from a fund have decided to open a food place (cafe, restaurant, fast food or something else entirely) in Moscow and have ordered a comprehensive market analysis in order to determine how to best approach the situation. Analytics require acquiring insights on Moscow food market, and prepare recommendations based on that data. 

Apart from the .ipynb document attached, a presentation with key findings has been prepared for the investors. The presentation can be found here: https://disk.yandex.com.tr/i/1ElYUobu4Yv13w 

# Conclusions:
1. The more appealing locations for a new place are the "rich" districts of Moscow - Central, Western and South-Western. The first two feature higher average bills, but also higher competition - mostly big chains and established locations. An alternative option is opening a place in some of the other districts - while less profitable they feature even less competition and thus may need less marketing expen
2. The South-Western district features similarly high bills, the highest average cup of coffee price and much less competition (only 96 total cafes, compared to 428 in the Central district). Based on these factors in seems to be the most opportune location for a new place and is recommended for further investigation.
3. The fact that most places in these districts are chains can also prove to be a strong point - since investors do not seek to start a new chain (at least, not yet), then a unique design ("Central Perk Moscow" - the idea promoted by the investors themselves) can efficiently target certain TA (Target Audiences) - upper middle class citizens interested in "new, unique places".
4. The most common type of catering place in Moscow is "cafe", while "cafeteria" are in third place - thus, the competition for opening this particular type of place is going to be one of the most severe.
5. Only 4.4% of all cafes in Moscow work round the clock (59 out of 1397). Technically, opening a place that does will give the location another distinct advantage, but needs to be accounted for (night shifts, menu positions etc.), especially considering the nature of cafeterias (generally, coffee sells better in the morning).

# Data:
Dataset consists of data from "Yandex.Maps" and "Yandex.Business" applications, dated summer 2022. Data entries are various food catering organizations. The information was uploaded by various users of these applications.
Dataset is located at: `/datasets/moscow_places.csv`. Data points feature:
- `name` — name of the catering organization
- `address` — address of the catering organization
- `category` — organization's type (cafe, pizza place, restaurant etc.)
- `hours` — working days|hours
- `lat` — latitude (geographical data)
- `lng` — longitude (geographical data)
- `rating` — places rating in Yandex.Maps (based on user reviews, top score is 5.0);
- `price` — price category (cheap, average, more than average etc.)
- `avg_bill` — average bill. Apart from number in RR contains info dependent on the place's type, such as:
    - «Average bill: 1000–1500 ₽»;
    - «Average cup of cappuccino price: 130–220 ₽»;
    - «Average glass of beer price: 400–600 ₽».
- `middle_avg_bill` — average bill - contains a number from previous data point, but only for places where the previous data point starts with "average bill":
    - If "avg_bill" has a range (xxxx-xxxx) then a median of those is displayed.
    - If "avg_bill" has a single number - then that number is displayed.
    - If "avg_bill" has no number or does not begin with "average bill" - then nothing is displayed.
- `middle_coffee_cup` — similar to previous data point, but only for places for which "avg bill" starts with "average cup of capuccino price":
- `chain` — binary, whether a place is a part of a bigger chain or a stand-alone.
- `district` — Moscow district in which the place is located
- `seats` — number of seats (or people that the place can accomodate)

# Libraries used:
*pandas, numpy, matplotlib, seaborn, math, re, plotly, folium, geojson*

