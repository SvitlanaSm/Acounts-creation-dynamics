#  Email & Account Activity Analytics Project
 ## **Description**  
This project focuses on gathering and analyzing data to understand:

* The dynamics of account creation

* User engagement with emails (sends, opens, clicks)

* Behavior in categories such as send intervals, account verification, and subscription status

The dataset enables:

* Cross-country activity comparison

* Identification of key markets

* User segmentation based on behavioral and demographic criteria

 ## **SQL Query Requirements**  
The SQL query return data grouped by the following dimension fields (non-aggregated):

* `date`: account creation date (for account metrics) or email send date (for email metrics)

* `country`: the user's country

* `send_interval`: the interval setting for email sending

* `is_verified`: whether the account is verified

* `is_unsubscribed`: whether the user has unsubscribed

 ## **Metrics**
**Primary Metrics**
* `account_cnt`: number of created accounts

* `sent_msg`: number of sent emails

* `open_msg`: number of opened emails

* `visit_msg`: number of email link clicks

**Derived Metrics**
* `total_country_account_cnt`: total number of created accounts by country

* `total_country_sent_cnt`: total number of sent emails by country

* `rank_total_country_account_cnt`: ranking of countries by total account count

* `rank_total_country_sent_cnt`: ranking of countries by total sent emails

*Account and email metrics calculated separately (due to differing date logic), and merged using UNION. Final results include only countries ranked in the Top 10 for either accounts or emails.*

In query i use **CTE** to separate logical query blocks and **window functions** for ranking.

 ## **Visualization (Looker Studio)**
Create a Looker Studio dashboard with the following:

**1. Charts by country:**

* `account_cnt`

* `total_country_sent_cnt`

* `rank_total_country_account_cnt`

* `rank_total_country_sent_cnt`

**2. Time series:** `sent_msg over time`


