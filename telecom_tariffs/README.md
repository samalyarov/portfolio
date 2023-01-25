# Project description:
Project includes preliminary research of various tariffs on a sample of telecom company clients. Analysis of client's behaviour has been conducted in regards to common practices of company's services usage. The final result of such analysis are optimal tariff options for various clients, which were recommended for use by the company.
Project consists of data pre-processing and their subsequent analysis. 
Main questions answered: is there a difference between overall profitability of different tariffs (and if so - then what is that difference), and is there a difference between clients from Moscow and other regions (in regards to how much money they bring the company).

# Conclusions:
1. There is a statistically significant difference in profitability between two tested tariffs, but there is no significant difference between clients from Moscow and other regions.

# Data:
"Users" dataset - containing information about users:
- 'user_id' — unique user ID
- 'first_name' — user's first name
- 'last_name' — user's last name
- 'age' — user's age (in years)
- 'reg_date' — date of tariffs activation by the user (day, month, year)
- 'churn_date' — date of tariffs deactivation by the user (if empty - tariff still in use)
- 'city' — user's city
- 'tarif' — user's tariff name
"Calls" dataset — information about calls:
- 'id' — unique call ID
- 'call_date' — date of the call
- 'duration' — call duration (minutes)
- 'user_id' — ID of user making the call
"Messages" dataset — information about messages:
- 'id' — unique message ID
- 'message_date' — message date
- 'user_id' — ID of user sending the message
"Internet" dataset - information about internet-sessions:
- 'id' — unique session ID
- 'mb_used' — total traffic used throughout the session (in MB)
- 'session_date' — session date
- 'user_id' — ID of session user
"Tariffs" dataset — information about tariffs:
- 'tariff_name' — tariff name
- 'rub_monthly_fee' — tariff monthly fee (in RUR)
- 'minutes_included' — tariff monthly minute allowance
- 'messages_included' — tariff monthly message allowance
- 'mb_per_month_included' — tariff monthly internet allowance (in MB)
- 'rub_per_minute' — cost per minute over the tariff allowance (if the tariff provides 100 minutes - that is how much you would pay for 101-st and so on, in RUR)
- 'rub_per_message' — cost per message over the tariff allowance
- 'rub_per_gb' — cost per GB over the tariff allowance

# Libraries used:
*pandas, numpy, matplotlib, seaborn, scipy.stats*
