# Are Philadelphia Crime Rates Related to Philadelphia Sports Wins?

<img width="391" alt="Screenshot 2024-07-29 at 7 43 42 PM" src="https://github.com/user-attachments/assets/19a4656b-e0ea-4202-88d9-67660be452f8">

Have you ever wondered if there's more to the spirit of sports than just cheering from the stands? 🔥

**The City of Brotherly Love**, home to teams like the **Eagles, Phillies, Flyers, and 76ers**, boasts a fan base as passionate as any in the nation. 
However, this enthusiasm sometimes spills over into the streets, raising questions about sports celebrations and public safety. \
We collected data to see if there is a correlation between Philadelphia sports wins and higher crime rates (initial thinking is because of the rowdiness) in areas near and surrounding the stadiums/arena and Philly sports bars. 
However, a study done by UC Davis showed that happier youths, say from your local sports team winning, tend to be deterred from crime. 

***So, does the happiness and exhilaration associated with a hometown sports team win influence Philadelphia residents from committing crimes and getting arrested?*** Let's find out!

Let's take a look at the number of arrests in Philly from 2018-2019 during the individual seasons that these arrests occurred in. We included data before 2019 so that COVID would not be a variable in our results. 
There are some interesting trends to pay attention to!


### METHOD 
---
#### 1) We use the geopandas library to have a base map
<img width="619" alt="Screenshot 2024-07-29 at 7 07 37 PM" src="https://github.com/user-attachments/assets/9b153123-8a06-4ce7-9d62-1be65c2e3fbf">

-----

#### 2) We add the zip codes of the locations we are interested to observe (sport bars and stadiums) 

* Convert to geodataframe
```
sports_bars_loc_gdf = gpd.GeoDataFrame(sports_bars_loc_df,geometry=gpd.points_from_xy(sports_bars_loc_df['Latitude'], sports_bars_loc_df['Longitude']))
```
* Plot on top of the base
```
base = philly_map.plot(edgecolor='gray', color='white', figsize=(10,10))
sports_bars_loc_gdf.plot(ax = base)
```
<img width="833" alt="Screenshot 2024-07-29 at 7 17 41 PM" src="https://github.com/user-attachments/assets/701162e4-d511-4912-9e4a-f968c5a6cc50">

----

#### 3) Arrests by Season Analysis

<img width="283" alt="Screenshot 2024-07-29 at 6 46 39 PM" src="https://github.com/user-attachments/assets/ed132616-bd86-4b6f-b4c1-85ad6a7c964b">

The 2018 season was a rollercoaster for Eagles fans. At the start in September, the total daily arrests were soaring at about 1,175. However, by the end of their season in December, this number dipped to around 1,075 arrests per day. 
But here's the kicker (pun intended): the lowest point was in November, totalling about 1,000 arrests per day, coinciding with the Eagles' most challenging period (1 win to 2 losses ratio). 
As the team bounced back in December with more wins, the arrest rates began to climb again. Does the city's mood sway with the team's fortunes? It seems so!

----
#### 4) Sports Bar and Arrests together 
With this data, **we decided to take a deeper look and analyze where exactly people tend to gather together and watch sports games: sports bars!**
We gathered addresses and coordinates of famous sports bars around the Greater Philadelphia area to see if there was a further connection between the locations of these crimes and the outcomes of sports games. 
In addition to sports bars, **we located the stadiums that Philadelphia sports teams play in to further support that large gatherings of sports fans watching a game can contribute to crime.**
We then took game data for Sixers, Eagles, and Phillies to observe how the crime rates change when there are games for their respective teams: 

--- 
<img width="800" alt="Screenshot 2024-07-29 at 7 31 39 PM" src="https://github.com/user-attachments/assets/2bf3d86b-862b-4f35-af28-881973c25cea">

Here we see that the number of arrests during the game day do in fact move on average in terms on the zone and they focus on the left side
We see they are no directly concentrated in the stadium area, however, they are highly concentrated on the left zone which is something worth investigating for us

----

<img width="800" alt="Screenshot 2024-07-29 at 7 24 56 PM" src="https://github.com/user-attachments/assets/d1bb35e6-422a-49d1-8494-0b9097809b69">

For Eagles, while on all games we do see a significant increase in crime rate, both when it is a home game played at the Philadelphia stadium (29% increase in stadium area) or when displayed at a bar (34% increase in stadium area) we see a dramatic increase of arrests in the zipcode nearest the stadiums which aligns with our hypothesis.

----

<img width="800" alt="Screenshot 2024-07-29 at 7 28 50 PM" src="https://github.com/user-attachments/assets/aaefe9e3-0219-48f3-a8aa-881f2936bc83">

For Phillies we notice again an increase in crime rates near the stadium area, especially during home games (16,4%)

----

### **What can we take away from all of this?** 

When comparing with data about attendance to each of the games of the teams analyzed, we can observe that the Eagles are the most popular ones. This may justify why the increase in crime rates is higher when there is an eagles game. 

<img width="585" alt="Screenshot 2024-07-29 at 7 37 41 PM" src="https://github.com/user-attachments/assets/64135af6-3df2-4c1b-8116-ce7f79e6f235">


* *Sources: https://www.phillyvoice.com/, https://www.phillysportsnetwork.com/, https://www.statista.com/*


Therefore we can conclude that the general trend is that during games the number of crimes increases. 
This study can be expanded with further analysis about different games and observe how the relationship changes. Moreover, it would be interesting to understand if the change in crime rates when there is a game is significant in other states as well and evaluate whether it is having an impact only on certain demographics where the crime rate has a higher variance than average (ie it is more likely to find spikes due to events). 

----
**By Bea, Emmy, and Lillie**
*COMM2550 Data Project*
