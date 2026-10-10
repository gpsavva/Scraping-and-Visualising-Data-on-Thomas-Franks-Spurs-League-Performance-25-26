# Scraping and Visualising Football Data Based on Thomas Frank’s Spurs Premier League Performance (25/26)
#
# 
## 1. Project Context & Background

Thomas Frank was relieved of his duties as Tottenham Hotspur Head Coach on 11 February 2026 with the club in 16th Place and hovering JUST 5 points above the relegation zone.  Many fans and neutrals have been curious as to what exactly went so wrong in his short tenure and how a club like Tottenham were so close to relegation.

The goal of this project was to identify how and where specifically Tottenham were underperforming, with a deeper look into how Spurs compared with their opposition both home and away. 

Using Python, Excel and Power BI, code was firstly designed to scrape raw football data from websites ‘Understat’ and ‘Football Web Pages’ and then a simple interactive dashboard was created to track/visualise Tottenham Hotspur’s performance in the 25/26 season under Head Coach Thomas Frank. This will ultimately help answer everyone's curiosity and capture the true core reasons on how everything unfolded.
##
## 2. Executive Summary

After a respectable start to the season for Thomas Frank’s Tottenham where they sat 3rd in the table, results dramatically declined with ONLY 2 wins achieved in the manager’s next 17 games before he was relieved of his duties. He left the club in a relegation battle, with a win percentage of only 26.92%. While Thomas Frank’s decline as manager at the club can be somewhat characterised by the team’s poor home form in the league and his pragmatic and defensive style of play, the upcoming segments will delve into other key contributing influences with recommendations into how this project can be taken further.

Here is a snippet of the Power BI dashboard that was constructed. It’s visualisations are included within the report below.

<img width="2431" height="1387" alt="DashboardOverview" src="https://github.com/user-attachments/assets/14eb04b0-87b4-47fe-999b-88cc53801753" />


There are a number of key valuable insights summarised below:

* This is officially the lowest of any PERMANENT Tottenham Hotspur manager in the premier league AT THE TIME OF HIS SACKING.

* A total of only 29 points was achieved in 26 premier league games. This consisted of 11 losses, 8 draws and 7 wins.

* 0 wins gained when in losing positions in the premier league both home and away.

* WINLESS in final 8 games consisting of 4 draws and 4 defeats

* Spurs had a considerably poor home league form of only 2 wins in 13. This is a 15.38% win percentage. Also, only 10 points were gained at home.

* Away form was better in comparison with 5 wins recorded in 13. This is a 38.46% win percentage. A clear vast improvement from home form but still could have been much higher. A total of 19 points was recorded away from home. 
##
## 3. Tools Utilised

There were three main tools that went into completing this project, with all helping to deliver the analysis required. These are:

* **Python** – This programming language was needed as it contains the library Beautiful Soup which was imperative to swiftly scrape the football stat data from 52 different web pages (2 for each of the 26 premier league games). Additionally, with the Pandas library the raw data collected can be processed, stored in tables and then exported as CSV files for use with Excel and Power BI.

* **Excel** – A spreadsheet and statistical tool that was needed to inspect the CSV files generated from Python. Calculations were practiced and planned for the eventual creation of simple and complex visualisations with Power BI.

* **Power BI** – A visualisation tool that was crucial in building the dashboard and showcasing the main performance metrics of Tottenham with Thomas Frank as manager. It is semi-interactive so most visuals change if the user selects specific matches played both home or away, allowing for more in-depth analysis.
##
## 4. The Project Process

Firstly, what was most important for this project was finding football websites that actually allowed you to scrape their data. There are many websites that block the Beautiful Soup library from working due to bot detection so after extensive research it was found that the websites ‘Understat’ and ‘Football Web Pages’ were scrapable. It was also vital to consider what specific data metrics to collect to allow for proper comparison and analysis. These metrics have been summarised below:
* **xG** – Expected Goals. Helps determine the quality of shots in a match.

* **PPDA** - Passes Per Defensive Action. Quantifies the intensity of a team’s press. This is done through calculating the amount of passes the opposition can complete before Spurs make an attempt to win the ball back. The score of PPDA can represent different things:

    * **<6** = Very high intense pressing done by a team.
    * **6 – 8** = High press that is still constant and very intense.
    * **8.1 – 10** = An average normal press.
    * **>10** = Passive pressing. Team prefers to wait back in a structured manner, forcing the opposition into wide areas with the eventual aim to counter attack.

* **Yellows, Reds and Penalties** – Checking the discipline of both teams in each match.

* **Corners, Fouls and Offsides** – Establishes how active a team were in a match.

* **Possession** - How much a team is keeping the ball and dictating the game.

* **Passes Attempted, Completed & Accuracy** – How well a team is able to move the ball between each other.

* **Shots Attempted, On-Target, Off-Target, Inside Box, Outside Box & Accuracy** – How active and level of threat a team were in front of goal.

After that a total of four dataframes (tables) were created to store the data that was being scraped. The main dataframe which stores the core football data has a total of 49 columns so that the data can be differentiated correctly. The URL codes of the 52 sites for ‘Understat’ and ‘Football Web Pages’ were stored in two lists so that the program can sequentially access the data on the premier league games.

There are two methods responsible for the running of the program. These are:

* **‘goal_segment’** – Method to categorise goals into the correct time minute segments (1-15, 16-30, 31-45, 46-60, 61-75, 76-90) when Tottenham/Opposition scored.


* **‘collect_results’** – MAIN method to collect results and add to relevant dataframes. 

Finally, once both methods have ran, the main dataframe of ALL results is used to filter and then separate home and away results into two separate dataframes with columns being correctly formatted/renamed. 

These two separate dataframes are then used to recreate and replace the main dataframe now that the columns have the correct names/format. All dataframes are then exported as CSV files for use with Power BI to create the final dashboard.

##
## 5. Insights Deep Dive

There were plenty more insights that were uncovered to showcase how Tottenham were struggling for form. These findings are explained below:

### 5.1 - Style of Play

<img width="1224" height="710" alt="PossessionPPDA" src="https://github.com/user-attachments/assets/16966a3a-a827-4b30-ba01-a57a0600f204" />

When Tottenham were playing at Home, they enjoyed more possession than their opponents on average at 53.2% and a PPDA (Passes Per Defensive Action) of 9.04 which suggests average to intense style of pressing. However, when playing away from home, Tottenham had on average less possession than their opponents at 49% and a PPDA score of 14.17. This is indicative of more passive pressing in comparison with the team opting to wait back in a structured manner and counter attack. Despite this passive style of play and less average possession, Tottenham recorded an extra 3 wins away when compared to home.

These findings are quite interesting and could point towards Thomas Frank not adequately preparing the squad on attacking patterns and so when they did press, they were extremely vulnerable to the counter attack and left too much space behind the back line which explains the 2 wins and 7 losses at Home. Additionally, when they did have more possession at Home the build-up play was sideways and predictable. Thomas Frank like at Brentford preferred and adapted better when his team has less of the ball and utilising a low block. This does not match the high expectations of Tottenham fans which would have put the squad under an enormous amount of pressure at Home.

<img width="1354" height="790" alt="Shots" src="https://github.com/user-attachments/assets/b52d83c9-63e4-4976-a99d-223a0cc265c3" />

If we assess Shots on Target and off Target for Tottenham Home and Away it further solidifies the previous findings. When Tottenham played at Home under Frank, they recorded 63 shots OFF TARGET in total which equates to 55.26% of ALL SHOTS. When playing Away this number is much lower at 45 which equates to 48.39%. Tottenham were making themselves more vulnerable to counter attacks and transitions at Home as well as wasting possession. Furthermore, it indicates an inefficiency in front of goal as well as poor decision making from the players that the manager was unable to correct.

### 5.2 - Late Goals Conceded

<img width="957" height="552" alt="ForAgainst" src="https://github.com/user-attachments/assets/5417da66-ca86-44dc-b276-25521b8fe7ad" />

Interestingly, Tottenham were most vulnerable to conceding a goal at the end of both the first and second half. This adds up to 22 goals conceded during Frank’s tenure which is 59.46% of ALL Tottenham goals conceded in the premier league. Again, Tottenham were unable to nullify counter attacks and opponents pressing them, especially when losing possession. When comparing shots OUTSIDE the box of both Tottenham and their opposition, the opposition outranked them a staggering 17 out of 26 times. Thomas Frank’s men were enabling the opposition to have easy shooting chances.

### 5.3 - Expected Goal (xG) Difference vs Opposition

<img width="2032" height="1204" alt="xg" src="https://github.com/user-attachments/assets/c0617035-f1f3-4afd-a43b-cc9a50d61a4f" />

#### 5.3.1 - HOME xG Difference

<img width="2291" height="591" alt="table1" src="https://github.com/user-attachments/assets/3c0e8edd-f06a-4545-aef1-5cd90bdcffd1" />

When Tottenham played at Home, they had a HIGHER xG (Expected Goal) to their opponents 7 out of 13 times, so just OVER half. However, of these 7 times they only recorded 2 wins against mid to low opposition Burnley and Brentford, drew twice and lost 3 times against tough opposition like Aston Villa and Liverpool. This highlights the team’s lack of ruthlessness against top teams.

<img width="2290" height="668" alt="table2" src="https://github.com/user-attachments/assets/191cede3-b636-4465-8d52-5d6ddacfebde" />

Of the 6 times Tottenham had a LOWER xG to their opponents at home, they recorded NO wins against their opposition, drawing just twice and losing the other 4 matches. This signifies their struggles at Home to create lucrative scoring opportunities and not being ruthless enough to capitalise on the few chances they get. Not being an imposing threat when you have Home advantage is a worry that many fans were echoing.

#### 5.3.2 - AWAY xG Difference

<img width="2293" height="589" alt="table3" src="https://github.com/user-attachments/assets/ae4b280f-2b1c-43c3-b23e-cfca35a87f2c" />

When Tottenham played away, they had a higher xG (Expected Goal) to their opponents 6 out of 13 times, so just UNDER half. They recorded a respectable 3 wins one of which was against top opposition Manchester City, 2 draws and just 1 loss.

<img width="2288" height="683" alt="table4" src="https://github.com/user-attachments/assets/a3d4ba2c-a064-48b8-8c09-b4e3f1f56498" />

Of the 7 times Tottenham had a lower xG to their opponents away they were only able to record 2 wins, 2 draws and 3 losses against tough opposition like Arsenal and Manchester United and also a damaging 3-0 loss against relegation rivals Nottingham Forest. Again, better when compared to Home when in the same circumstances but it still could be indicative of Thomas Frank being unable to implement a successful tactical plan of sitting back against TOP OPPOISITION and elevating the potential of low value shots being converted to goals.  

### 5.4 - Goal Margins

<img width="1474" height="812" alt="margin" src="https://github.com/user-attachments/assets/5d29c152-15ab-421f-83ae-03eef0bacca8" />

Most of Tottenham’s 7 wins (5) have had a goal margin of 2-3 goals. Only 2 wins have had a margin of 1 goal.

On the contrary, from the 11 defeats Spurs suffered in the prem, 8 have had a goal margin of -1. Nearly most (7) were astonishingly at Home which serves as further proof of form struggles at the Tottenham Hotspur Stadium.

### 5.5 - Half Time Results

<img width="1206" height="961" alt="ht" src="https://github.com/user-attachments/assets/0cb40361-d360-4fb6-810e-3bf4b0a293af" />

The half-time results of Tottenham games were analysed: 

* Winning only 6 times out of 26 at the end of the first half. A resulting very low win percentage of 23.08%.
  
* Drawing 8 times which is equal to 30.77%.
  
* Staggering 12 losses which is nearly half at 46.15%. Indication that Tottenham were not able to start games quickly and with the right intensity compared to their opponents.

##
## 6. Conclusion and Reflections

It is evident that the players did not buy into Thomas Frank’s pragmatic style of play. Whilst his low block approach to football games saw most of his premier league wins coming AWAY from Home, this was only suitable against low to mid-level clubs. Against top oppositions, Tottenham capitulated and could not deal with their pressure, leaving the midfield out of position and the defence without any support.

Whilst this project has yielded a number of interest results and findings this is only the surface. There are a number of ways this project can be taken further to delve deeper and produce even more rich insights. 

* Excessive Set-Piece Dependence. How many of our goals came from set pieces?

* Data on how quickly Spurs win the ball back in the final third with Thomas Frank compared with Ange Postecoglou and other managers.

* Goals conceded and scored last 15 mins COMPARED to other teams.

* Injuries? Were there a higher or lower than average set of injuries to other teams in the league?
  
* Goals conceded per game compared to league average.

* Goals conceded and scored last 15 mins COMPARED to other teams.
