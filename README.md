# NTU-SC1015-Mini-Project
School of Computer Science and Engineering
Nanyang Technological University
Lab: B140
Group : 7

Members:

1. Timothy Nyan Lin Htoo
2. Koh Jia Xuan
3. Yong Wei Tuck
---
#### Description:
##### This repository contains all the Jupyter Notebook and datasets we have used and created as part of the Mini Project for SC1015: Introduction to Data Science and Artificial Intelligence.
##### This README briefly goes through the accomplisment as well as the elaboration of dataset.
---

#### Table of Content
1. [Problem Formulation](####-Problem-Formulation)
2. [Data Preparation & Cleaning](####-Data-Preparation-&-Cleaning)
3. [Exploratory Data Analysis](####-Exploratory-Data-Analysis)
4. [Dimensionality Reduction](####-Dimensionality-Reduction)
5. [Clustering](####-Clustering)
6. [Data Driven Insights & Conclusion](####-Data-Driven-Insights-&-Conclusion)
7. [References](####-References)
---
## Problem Formulation
![Clash Royale](https://static1.thegamerimages.com/wordpress/wp-content/uploads/2023/02/clash-royale-man-and-match.jpg)
Clash Royale has always been a nostalgic game we played as a child, filled with magical characters, thrilling battles, and endless excitement. Whether you're a seasoned player or just starting out, Clash Royale offers a unique and engaging experience that keeps you coming back for more. The pprimary gameplay was simple, challenge player around the word on a 1v1, each player having 8 character cards, the winner wins crowns while the loser loses it. With over 100 over Character Cards with all of them having unique abilities and elixist requirement, it is stragetic game that gives player multiple ways to win the game.

In this project, we will be taking a look at player's data to determine what are the key citeria for players to win consistently. We will primirly be taking a look at these quetions.
1. What is the probability of winning a battle given a certain combination of cards?
2. How does card level affect the win rates?
3. Which specific card is the most effective in winning battles?
4. Which cards are most commonly used by top players?
5. Does the management of elixir usage affect win rate? (Elixir Leakage)

![Clash Royale](https://gifdb.com/images/high/video-game-clash-royale-laughing-king-emote-5ms9vhxu14101bam.gif)
## Data Preparation & Cleaning
Source: https://developer.clashroyale.com/#/documentation

### Player Data Cleaning
We conducted a data collection process to obtain a sample of players for our project. Using the official Royale API, we randomly selected **960 clans** with a minimum of 20 members, and retrieved the clan tags through Postman in the form of JSON. From this initial set, we narrowed it down to a final sample of **100 clans**, from which we extracted individual player tags. We used another API request call to retrieve the player details for these tags, resulting in a total of **3,695 player records**.

To ensure the quality of our data, we conducted a data cleaning process. First, we removed irrelevant columns. Then, we applied numerical filters to remove certain players based on the following requirements:

The player must have played at least 10 matches.
The player must have played no more than 40,000 matches.
The player must have a trophy count of more than 1,000.
To determine these numerical filters, we plotted a box-whisker graph and removed prominent outliers. After filtering the data, we were left with a final sample of 1,197 players for our project.

![comparison](https://user-images.githubusercontent.com/64196627/228193008-8d43abf1-1ed2-4dd2-9fea-c279a0aea6a4.png)


### Battle Log Cleaning
From the ``97 Players, we then obtained their top 20 recently battle logs through API Calling. The data is then initally filtered for "PvP" Gamemode only, leaving us with a total dataset of 10,401 matches for review.


Once that is done, as the API data is very messy, we filtered the column names and added in some of our own leaving us with only the useful variables for comparision for further analysis and machine learning.


## Exploratory Data Analysis
### Card Analysis
In the game, we have a total of 109 cards, with each card having their own unique abilities and exlixir cost. Out of those 109 cards, a player will then select 8 cards to form a deck. 

- Highest Cost: Three Musketeers (9 Exlixir)
- Lowest Cost: Ice Spirit (1 Exlixir)

### Player Analysis
We first conducted some Single Variable Data representation on basis varibles such as thophies, 3CrownWins and experience level, giving us the following breakdown.

![single](https://github.com/timtaifung/timtaifung-NTU-SC1015-Mini-Project/blob/main/Common/Initial%20Cleaning/single%20Variable.png)

![single](https://raw.githubusercontent.com/timtaifung/timtaifung-NTU-SC1015-Mini-Project/main/Common/Initial%20Cleaning/Arena%20Breakdown.png)

From the data, we can infer that our player's trophies lies within mainly in the 4000 to 5500 ranges. hence, most players will exists in at Arena 15 to Arena 17.

## Battle Analysis
From the 10,401 battles, we gathered Most Common Card, Best Deck By Win rate & Frequency and current Meta.

### Top 3 Most Common Deck
![single](https://raw.githubusercontent.com/timtaifung/timtaifung-NTU-SC1015-Mini-Project/main/Common/Initial%20Cleaning/Common.png)

### Top 3 Most Won Deck
![single](https://raw.githubusercontent.com/timtaifung/timtaifung-NTU-SC1015-Mini-Project/main/Common/Initial%20Cleaning/MostWin.png)

### Current Meta
![single](https://raw.githubusercontent.com/timtaifung/timtaifung-NTU-SC1015-Mini-Project/main/Common/Initial%20Cleaning/meta.png)


## Machine Learning

| machine Learning Question | Machine Learning Approaches  |
| ---------------| --------------- |
| 1. What is the probability of winning a battle given a certain combination of cards? | 1. Naive Bayes<br>2. Neural Networks<br>3. K-Nearest Neighbors |
| 2. How does card level affect the win rates? | Linear Regression Model |
| 3. Which specific card is the most effective in winning battles? | 1. Decision Trees<br>2. Random Forests<br>3. Gradient Boosting |
| 4. Which cards are most commonly used by top players? | 1. Association Rule Mining<br>2. Logistic Regression<br>3. Support Vector Machines |
| 5. Does the management of elixir usage affect win rate? (Elixir Leakage) | TBC |

## Data Driven Insights & Conclusion
1. Certain cards prominents shows the usage of it will have a slightly higher chance at winning such as the valkries.
2. Card Combination of the deck plays a important factors in win condition, with the best one being the Mega Knight + Bats combo
3. Higher Card levels found to significant increase win rate. Showing that Grinding to increase level of cards definitely have a higher chance of winning

However, Our sample data that was used was not sufficient as there are other factos that we are unable to take into full consideration such as player's specific strategy such as card placement during matches and how specific cards were used to counter the enemies. Data were also limited to specific period and player base, resulting in some biasnes of current meta.

## References
https://developer.clashroyale.com/#/documentation (Class Royale API)
https://www.kaggle.com/datasets/rodsaldanha/clash-royale-matches?resource=download (Statistic of Specific Cards)
