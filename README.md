# NBA-LeBron-James-stats-R-Shiny
This project focuses on LBJ's career stats, including overall stats, shooting stats and the data when he against others, also the comparsion about how he played on different teams and ages.

Data Source:
A.	LeBron James’s total stats in regular session and playoff games from 2003 to 2021 
https://www.basketball-reference.com/players/j/jamesle01/gamelog/2021

B.	LeBron James’s shooting distance in regular session and playoff games from 2003 to 2021 
https://www.nba.com/stats/events/?flag=3&CFID=33&CFPARAMS=2020-21&PlayerID=2544&ContextMeasure=FGA&Season=2020-21&section=player&sct=plot



## Introduction and Motivation

I have been an NBA fan when I was a kid. 
There are over 400 players in NBA, and in every single year, some of them could be eliminated. In a such competitive league, LeBron James not only still survive, but also one of the legends in NBA. 
Although he is 37 years old, he is still among the top performers in the league. 
As a result, I am interested with his career data and would like to verify that if LeBron James’s stats are not affected by his physical age and other factors. 

There is a lot of analytical data can be found on the Internet; however, most of them are season by season and lack an overall integrated analysis. 
Hence, I would like to know more about his career integrated data changes. From NBA fans side, we could expect how his games may look like and how his style of playing ball could change in the future.

## Data Wrangling

Step 1: Obtain data and save into .csv files

Dataset:
<img width="619" alt="截圖 2022-05-13 下午3 58 25" src="https://user-images.githubusercontent.com/105199493/168220465-7a6b6f20-b7cd-441c-a340-5fafd2f26186.png">

Step 2: Combine files

each season’s data have to combine together by using R libraries, `readr` and `data.table`, and `for loop` 

Step 3: Transform into a data frame

Transform the data from a `csv` file into a `dataframe` to have better view and easier to clean the data by using R library `tidyverse`.

Step 4: Clean data

There are some “Inactive”, “Did Not Dress” or “Did Not Play” records in data which need to be deleted.

<img width="632" alt="截圖 2022-05-13 下午3 59 04" src="https://user-images.githubusercontent.com/105199493/168220539-5eaf9a03-4cde-4d4e-9e6b-6869ff65c8d4.png">

## Data Checking

Check the dataset by using `Tableau`

<img width="508" alt="截圖 2022-05-13 下午4 04 01" src="https://user-images.githubusercontent.com/105199493/168221158-da3cadd2-cef1-4083-893d-0e7f8389a962.png">

<img width="540" alt="截圖 2022-05-13 下午4 05 09" src="https://user-images.githubusercontent.com/105199493/168221292-6ebf57a3-66ba-4f34-8c37-7be17bf9b5f7.png">

## Data Exploration

By `R`:

The graph tells the stats in first five year and recent five year. 

<img width="555" alt="截圖 2022-05-13 下午4 06 22" src="https://user-images.githubusercontent.com/105199493/168221391-1d46d3d1-abbe-469e-b21b-07890a1808d0.png">

Displays the situation in different teams.

<img width="577" alt="截圖 2022-05-13 下午4 07 16" src="https://user-images.githubusercontent.com/105199493/168221481-0ec4416b-c5d0-49a2-a7a7-3c7121615155.png">

By `Tableau`:

3 point shooting attempts VS Field goal (2 points) shooting attempts trend

<img width="628" alt="截圖 2022-05-13 下午4 08 26" src="https://user-images.githubusercontent.com/105199493/168221603-78e838b1-3433-456f-9d03-2d1c04fe28bc.png">

The data of shooting, separating by first five years and recent five year in two colors which can tell that how the shooting area change.
<img width="703" alt="截圖 2022-05-13 下午4 09 45" src="https://user-images.githubusercontent.com/105199493/168221729-6d68e167-528a-4d35-869c-7d2f5b5dc011.png">

More Exploartions check out in Project file!


## Data Visualization

The visualization part is done by `R Shiny`. The data I used is from 2003 to 2022, which is from his first career year till now.
The completed R script can be found in `DVP.R` file. The needed data are `dvpallgame.csv`, `shot_accuracy.csv`, `dvpshooting.csv` and `winrate.csv`.


#### On the first page- Overall Stats
This page shows the overall trend from the first career year to 2022. There are four interactive plots. 2/3 point shooting stats and rebound/block stats.

<img width="1426" alt="截圖 2022-06-17 下午6 44 26" src="https://user-images.githubusercontent.com/105199493/174262248-827f295a-aba2-43a5-9693-4bde92853e0c.png">


plot-

<img width="1407" alt="截圖 2022-06-17 下午6 51 59" src="https://user-images.githubusercontent.com/105199493/174263672-3d42e5cc-03ff-443f-bdcb-e0f7332cdcb6.png">


On the top left is shooting attempt trend, we focus on 2 point and 3 point shot. As we all know, when people impacted by aging, they usually change their playing style from the shot closed to basket to 3 point shot in order to avoid body collision and protect themselves. 

On the top right is rebound/block trend. Again, when player influenced by aging, their physical status may not be as good as when they were young, and the relative rebounds and blocks will decline, because the body can no longer withstand too many bounces and collisions.

<img width="697" alt="截圖 2022-06-17 下午6 54 56" src="https://user-images.githubusercontent.com/105199493/174264253-c6049dab-e0bc-41ac-b6d3-e8cb8a159226.png">

When mouse hovering, the stats of corresponding age will be highlight.

#### Second page- Shooting.

The second page focus on the shooting stats. 

From the top to bottom, the plots would like to display- shooting accuracy at different zones, shooting frequency, total number of shooting attempt and the shooting type proportion.


<img width="1420" alt="截圖 2022-06-17 下午7 04 40" src="https://user-images.githubusercontent.com/105199493/174266074-b02ab138-fa1f-4f8c-8df8-d77b388c1f45.png">
<img width="1393" alt="截圖 2022-06-17 下午7 04 56" src="https://user-images.githubusercontent.com/105199493/174266136-84c5620e-5017-48d6-9bb3-fff674d0e685.png">

The users first can choose whether they want to compare the stats by different teams or age.

While team- there are four selections

<img width="242" alt="截圖 2022-06-17 下午7 07 31" src="https://user-images.githubusercontent.com/105199493/174266537-c38d088b-1647-4fb6-9918-d788f3bdacf4.png">

While age- the drop down menu change the team options to age from 18 to 37 years old.

<img width="238" alt="截圖 2022-06-17 下午7 08 10" src="https://user-images.githubusercontent.com/105199493/174266644-f18f1788-cd62-4524-84c4-b78eff8f37bc.png">

For example, users can choose 18 vs 28 to compare and check out the data at the sepecfic age.

<img width="1401" alt="截圖 2022-06-17 下午7 09 29" src="https://user-images.githubusercontent.com/105199493/174266880-688367c5-2469-4c74-9cf1-de365862bd96.png">

#### Third page- Win Rate

The final page is abot the win rate when against other teams.
There are two plot on this page, one is map and the other is a bar chart.

<img width="1411" alt="截圖 2022-06-17 下午7 10 54" src="https://user-images.githubusercontent.com/105199493/174267166-b979fdd1-0332-4502-aa76-b1d4ea849809.png">

Again, users can choose whether they would like to know more about in different teams or ages-
<img width="244" alt="截圖 2022-06-17 下午7 12 17" src="https://user-images.githubusercontent.com/105199493/174267410-4f3597aa-27b4-41dc-a16d-696072523900.png">

When click on the logo on the map, it shows the detail data including win rate, points, field goals, 3 points, rebounds and blocks on average of all period (team or age).
<img width="1177" alt="截圖 2022-06-17 下午7 13 42" src="https://user-images.githubusercontent.com/105199493/174267677-ef89e4ba-c681-472f-af9c-41739c20d5cc.png">

Below is a bar chart, when mouse hover, the selected bar would be highlight.
<img width="1371" alt="截圖 2022-06-17 下午7 15 54" src="https://user-images.githubusercontent.com/105199493/174268132-3931c616-b647-4054-b252-399fa3d2504d.png">


## Next Step


This project done by R Shiny. Shiny is one of the tools that allow users to build a webpage visualzation with interactive functions; however, customized design is not easy to implement by Shiny. As a result, the next step I am tring to do is to implement the visualization part by `D3` which is one of the packages that in javascript. 


### Now, try on `DVP.R` and have fun!
