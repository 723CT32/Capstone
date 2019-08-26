## Executive summary:


### Problem Statement:
I am a Data Scientist working with an NBA team my goal is to build a model that will assist our front office in identfying players 
based on their skillsets rather than positions. 5 positions is a bit archaic being that players within those position can have 
vastly different skillsets. This model can be used when trying to decide what type of player will be available during free-agency
and if our team should target them. Data for G-League players was included to find any hidden gems among the lower levels.


### Webscraping 
Data was scraped from Basketball reference and NBA.com using both BeautifulSoup and Selenium. Over 88 csv's were Acquired from 
both scoures.




### EDA process
Data was then imported after Webscraping. I chose not to use Per Game Stats and Per 36 minute stats. My decision was solely
because Per 100 and Advanced Stats in my opinion regularize data better also we are trying to help our front office look for 
"hidden gems" aka undervalued players. Data needed to be cleaned also some data needed to be converted to the correct dtype
and not strings. After all data was cleaned, I needed to merge DataFrames from AdvancedStats, Per100 Possesions as well as Shot Types. At this point I had 71 columns of Stats.




### Modeling
After Reading in the file, I dropped players who did not play at least 20 games this was because I did not want someone's stats to be too heavily weighted for playing a sample size of games. After this I began Pre-Processing, I dropped columns that I felt were redundant or not useful for the modeling. I applied PCA to the model which is a dimensionality reduction technique. Then fit regularized data into a K-Means model. I choose 9 clusters at many attempts of different clusters this to me was the correct amount based on different playertypes across the league. An interesting finding was seeing Lou Willams clustered with Superstars. He is very well respected for his scoring ability off the bench but, the model clusters him with players like James Harden and Steph Curry .In conclusion, I feel that the model did well however we can improve this with more detailed stats. For example, more features realative to passing can be determine if someone is a playmaker and instead of using STL% possibly some tracking metric to see how well Player A stays in front of the Offensive Player would further make the model do better.# Capstone
