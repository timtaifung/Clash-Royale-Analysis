# NTU-SC1015-Mini-Project
School of Computer Science and Engineering
Nanyang Technological University
Lab: B140
Group : 6

Members:

1. Timothy Nyan Lin Htoo
2. Koh Jia Xuan
3. .Wei Tuck
---
#### Description:
##### This repository contains all the Jupyter Notebook and datasets we have used and created as part of the Mini Project for SC1015: Introduction to Data Science and Artificial Intelligence.
##### This README briefly goes through the accomplisment as well as the elaboration of dataset.
---
#### Table of Content
1. Problem Formulation
2. Data Preparation & Cleaning
3. Exploratory Data Analysis
4. Dimensionality Reduction
5. CLustering
6. Data Driven Insights & Conclusion
7. References
---
#### Problem Formulation
![Clash Royale](https://static1.thegamerimages.com/wordpress/wp-content/uploads/2023/02/clash-royale-man-and-match.jpg)
Clash Royale has always been a nostalgic game we played as a child, filled with magical characters, thrilling battles, and endless excitement. Whether you're a seasoned player or just starting out, Clash Royale offers a unique and engaging experience that keeps you coming back for more. The pprimary gameplay was simple, challenge player around the word on a 1v1, each player having 8 character cards, the winner wins crowns while the loser loses it. With over 100 over Character Cards with all of them having unique abilities and elixist requirement, it is stragetic game that gives player multiple ways to win the game.

In this projectm, we will be taking a look at player's data to determine what are the key citeria for players to win consistently. We will primirly be taking a look at these quetions.
1. What is the best Deck Combination for winning?
2. Is there a best "broken" Card for winning?
3. Is climbing throphy level difficulty consisted across all arenas?
4. How management of Elixir Leak affect win rate?
5. Does total playtime affect win rates?

![Clash Royale](https://gifdb.com/images/high/video-game-clash-royale-laughing-king-emote-5ms9vhxu14101bam.gif)
#### Data Preparation & Cleaning
Source: https://developer.clashroyale.com/#/documentation

We conducted a data collection process to obtain a sample of players for our project. Using the official Royale API, we randomly selected **960 clans** with a minimum of 20 members, and retrieved the clan tags through Postman in the form of JSON. From this initial set, we narrowed it down to a final sample of **100 clans**, from which we extracted individual player tags. We used another API request call to retrieve the player details for these tags, resulting in a total of **3,695 player records**.

To ensure the quality of our data, we conducted a data cleaning process. First, we removed irrelevant columns. Then, we applied numerical filters to remove certain players based on the following requirements:

The player must have played at least 10 matches.
The player must have played no more than 40,000 matches.
The player must have a trophy count of more than 1,000.
To determine these numerical filters, we plotted a box-whisker graph and removed prominent outliers. After filtering the data, we were left with a final sample of 1,197 players for our project.

In addition to the player details, we also retrieved the top 3 recent battle logs for each player. This data will be used to analyze player performance and behavior in Clash Royale.

![comparison](https://user-images.githubusercontent.com/64196627/228193008-8d43abf1-1ed2-4dd2-9fea-c279a0aea6a4.png)

Currently now, we have 2 primary datasets that we will use for further exploration, battle_logs, and player_info

#### Exploratory Data Analysis


#### Dimensionality Reduction


#### Clustering


#### Data Driven Insights & Conclusion


#### References

