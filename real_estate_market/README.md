# Project description:
We were given an archive of real estate offers from the "Yandex.Real Estate" app. Geography of research consists of Saint Petersburg and several satellite cities nearby. Main objective was to learn how to properly evaluate the market price for various types of real estate. Our job is find out what factors influence the price and to what extent - that information would be used in developing an ML model that would assist with detecting anomalies and fraud when dealing with real estate offers posted on the app.

# Conclusions:
1. There is direct correlation between size of the property (total area, kitchen area, living area and number of rooms) and its price. The bigger the area - the bigger the price. 
2. Another important factor is time - there has been a significant price decrease after they peaked in 2014. That decrase continued up until 2016, after which point hte growth resumed. Time of year also has an impact on price - properties posted in april are more expensive than others, while those posted in may-june are somewhat less so. Interestingly enough, objects posted on friday or holidays are usually somewhat cheaper.
3. When analysing the cities, the price for each square meter is, expectingly, the highest in Saint P (107.5 thousand rubles for m²). The cheapest properties in the analysed dataset are located in the city of Vyborg (~58 thousand rubles per m²).
4. Distance from city center also correlates with price - generally speaking, the further the property is from the city center, the cheaper it gets. There are, however, some notable exceptions at the range of ~25 and ~32 kilomteters, which potentially may indicate the locations of elite country cottages, dachas etc.
5. More detailed analysis can be found in the .ipynb file attached.

# Data:
Each real estate object listed has two types of data points. First are the points that are generated automatically (based on geographical data - such as distance to city center, to the closes airport, closest park of pond). The rest of the data is entered by the user posting the offer.
Data points feature:
- `airports_nearest` — distance to closest airport (meters)
- `balcony` — number of balconies
- `ceiling_height` — ceiling height (meters)
- `cityCenters_nearest` — distance to city center (meters)
- `days_exposition` — how long was the offer public (from posting date to removal)
- `first_day_exposition` — offer publishing date
- `floor` — floor
- `floors_total` — number of floors in the building
- `is_apartment` — whether the object is an apartment or not (boolean)
- `kitchen_area` — kitchen area (m²)
- `last_price` — object price in the moment of advert removal
- `living_area` — living area (m²)
- `locality_name` — city name
- `open_plan` — if the object has an open floor plan (boolean)
- `parks_around3000` — number of parks within 3 kilometers
- `parks_nearest` — distance to the nearest park (meters)
- `ponds_around3000` — number of ponds within 3 kilometers
- `ponds_nearest` — distance to the nearest pond (meters)
- `rooms` — number of rooms
- `studio` — whether the object is a studio or not (boolean)
- `total_area` — total property area (m²)
- `total_images` — number of property pictures in an advert

# Libraries used:
*pandas, matplotlib, seaborn*

