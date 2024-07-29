# Are Philadelphia Crime Rates Related to Philadelphia Sports Wins?
**By Bea, Emmy, and Lillie**

Have you ever wondered if there's more to the spirit of sports than just cheering from the stands? 🔥

**The City of Brotherly Love**, home to teams like the **Eagles, Phillies, Flyers, and 76ers**, boasts a fan base as passionate as any in the nation. 
However, this enthusiasm sometimes spills over into the streets, raising questions about sports celebrations and public safety. \
We collected data to see if there is a correlation between Philadelphia sports wins and higher crime rates (initial thinking is because of the rowdiness) in areas near and surrounding the stadiums/arena and Philly sports bars. 
However, a study done by UC Davis showed that happier youths, say from your local sports team winning, tend to be deterred from crime. 

***So, does the happiness and exhilaration associated with a hometown sports team win influence Philadelphia residents from committing crimes and getting arrested?*** Let's find out!

Let's take a look at the number of arrests in Philly from 2018-2019 during the individual seasons that these arrests occurred in. We included data before 2019 so that COVID would not be a variable in our results. 
There are some interesting trends to pay attention to!

### METHOD 

#### 1) We use the geopandas library to have a base map
<img width="619" alt="Screenshot 2024-07-29 at 7 07 37 PM" src="https://github.com/user-attachments/assets/9b153123-8a06-4ce7-9d62-1be65c2e3fbf">

#### 2) We add the zip codes of the locations we are interested to observe (sport bars and stadiums) 

```sports_bars_loc_gdf = gpd.GeoDataFrame(sports_bars_loc_df,geometry=gpd.points_from_xy(sports_bars_loc_df['Latitude'], sports_bars_loc_df['Longitude']))
```


**Number of Arrests by Season**

<img width="283" alt="Screenshot 2024-07-29 at 6 46 39 PM" src="https://github.com/user-attachments/assets/ed132616-bd86-4b6f-b4c1-85ad6a7c964b">

The 2018 season was a rollercoaster for Eagles fans. At the start in September, the total daily arrests were soaring at about 1,175. However, by the end of their season in December, this number dipped to around 1,075 arrests per day. 
But here's the kicker (pun intended): the lowest point was in November, totalling about 1,000 arrests per day, coinciding with the Eagles' most challenging period (1 win to 2 losses ratio). 
As the team bounced back in December with more wins, the arrest rates began to climb again. Does the city's mood sway with the team's fortunes? It seems so!

The Phillies' season from March to September 2018 showed a dramatic fluctuation in arrest numbers. 
But here, we need to tread carefully, as warmer summer days might play a part in bringing more people (and potentially more arrests) outdoors. It's a classic case of correlation not always implying causation, but it's a fascinating observation nonetheless to see a tight Phillies' season (almost split between wins and losses at home) and non-consistent arrest data.

During the short April-May season of 2019 for the 76ers, there's a noticeable increase trend. April saw an average of about 1,175 arrests per day, which increased to 1,275 in May. Interestingly, this increase in arrests contradicts our hypothesis because of the team's performance dip from 6 wins and 1 loss in April to a less favorable outcome in May. 
Basically, for the 76ers, when the team was doing well in April, there were fewer arrests than the arrests during the worse set of games in May (2 wins to 3 losses).

With this data, **we decided to take a deeper look and analyze where exactly people tend to gather together and watch sports games: sports bars!**
We gathered addresses and coordinates of famous sports bars around the Greater Philadelphia area to see if there was a further connection between the locations of these crimes and the outcomes of sports games. 
In addition to sports bars, **we located the stadiums that Philadelphia sports teams play in to further support that large gatherings of sports fans watching a game can contribute to crime.**

<img width="264" alt="Screenshot 2024-07-29 at 6 50 16 PM" src="https://github.com/user-attachments/assets/d39b8770-0d84-45a6-971f-81be46c5d033">

In this image, the blue dots represent locations of sports bars. The deeper red means a higher concentration of arrests. 

We then took game data for Sixers, Eagles, and Phillies to observe how the crime rates change when there are games for their respective teams: 





**What can we take away from all of this?** We found a correlation between sports seasons and crime rates! However, it's essential to note that our findings don't extend to all aspects of the sports scene. When it comes to sports bars and the areas surrounding stadiums and arenas, the data doesn't reveal a significant change in arrest rates, regardless of whether our teams clinch victory or face defeat. This suggests that while the overall mood of the city might fluctuate with the cycle of sports triumphs and setbacks, these specific locales don't necessarily mirror the same pattern.

Philadelphia sports fans are unpredictable. With our triumph in the Superbowl in 2018, fans wreaked havoc throughout the city: igniting fires, flipping over cars, climbing poles, and clashing with the police. While our data shows that increased crime rates can be correlated with Eagles and Phillies sports wins, for now it is safe to conclude, **Philly sports fans are just extremely passionate about their teams regardless of the outcome of any game during any season.**

🔥!
