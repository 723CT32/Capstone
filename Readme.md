## Executive summary:


### Problem Statement:
I am a Data Scientist working with an NBA team. My goal is to build an Unsupervised Learning model that will assist our front office in identfying players based on their skillsets and/or production rates rather than positions. Basketball has now become a positionless game. The 5 positions that were more common in the 80s and 90s is a bit archaic now. Players no longer primarily have their back to the basket if they are a big and many Centers shoot the 3 ball in today's game. This model can be used when trying to decide what type of player will be available during free-agency and how they will fit our system. Data for G-League players was included to find any hidden gems among the lower ranks.


### Webscraping 
Data was scraped from Basketball reference and NBA.com using both BeautifulSoup and Selenium. Over 88 csv's were Acquired from 
both scoures. 




### EDA process
Data was then imported after Webscraping. I chose not to use Per Game Stats and Per 36 minute stats. My decision was solely
because Per 100 and Advanced Stats in my opinion regularize data better also we are trying to help our front office look for 
"hidden gems" or undervalued players. Per 100 Possesion stats regularize better for pace. For example, if Player A plays in a system that is alot slower than Player B we can evaluate better who scores more based on their Per 100 Possesion Stats. Data needed to be cleaned and, some data needed to be converted to the correct data type not strings but we needed numerical data. After all data was cleaned, I needed to merge DataFrames from AdvancedStats, Per100 Possesions as well as Shot Types. At this point I had 71 columns of Stats. Then I concatenated the NBA data on to the G-League dataset.




### Modeling
After Reading in the file, I dropped players who did not play at least 20 games this was because I did not want someone's stats to be too heavily weighted for playing a sample size of games. After this I began Pre-Processing, I dropped columns that I felt were redundant or not useful for the modeling. I applied PCA to the model which is a dimensionality reduction technique. Then fit regularized data into a K-Means model. I choose 9 clusters at many attempts of different clusters this to me was the correct amount based on different playertypes across the league. An interesting finding was seeing the lack of traditional big men. Their was a cluster of big men but, they are primarily pick and roll guys not the traditional back to the basket guys. Another interesting finding was seeing Brook Lopez clustered with guards. If you followed the Bucks last year he primarily spaced the floor and shot 3s to create space for Giannis to attack. With the recent rise in analytics teams are starting to take a better look at what shots are valuable and which aren't. This project was interesting because you can see the impact analytics has on the game today. Teams are either looking for high percentage shots at the basket with big guys that catch easy lobs at the rim or players that can efficiently shoot the 3. In conclusion, I feel that the model did well however we can improve this with more detailed stats. For example, more features realative to passing can be determine if someone is a playmaker and instead of using STL% possibly some tracking metric to see how well Player A stays in front of the Offensive Player would further make the model do better.