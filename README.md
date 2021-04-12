# clustering-players-for-auction

## Source of the dataset
The dataset is obtained fom [Kaggle Website](https://www.kaggle.com/#). The specific download link is [here](https://www.kaggle.com/nowke9/ipldata#).

Indian Premier League (IPL) is a Twenty20 cricket format league in India. It is usually played in April and May every year. The league was founded by Board of Control for Cricket India (BCCI) in 2008.

Content - Data till Season 11 (2008-2019)

There are two inputs---

    matches.csv - Match by match data
    deliveries.csv - Ball by ball data


# Inspiration

Cricket is a craze in a country like India and a great form of entertainment. However, there is a financial aspect also in this tournament. Usually at the start of every season, an auction is held wherein the players are distributed among the different teams. The Team Management board tried to optimize the cash they are willing to spend on each player basis their performance. We felt that this detailed data on previous IPL may be used for creating clusters among the players so that the similar players are grouped in the same cluster (ie in the same price bracket) and actionable insights can be drawn for Team Managers for an informed decision.For now, we have considered only the batsman and have considered batting performance for clustering.Thesame can however be done for bowlers , taking respective metrics.

## Structure of the data

The dataset contains the following 21 variables with the corresponding descriptions:

1. match_id: Unique Identifier for a match
2. inning : Match innings - 1st innings/2nd innings
3. batting_team : Name of the batting team
4. bowling_team : Name of the bowling team
5. over : Current over
6. ball : Current ball of the over
7. batsman : Name of the batsman on strike
8. non_striker : Name of the batsman on non-striker's end
9. bowler : Name of the bowler
10. is_super_over : Is this a super-over (0 or 1)
11. wide_runs : Runs given as wide
12. bye_runs : Runs given as bye
13. legbye_runs : Runs given as leg-bye
14. noball_runs : Runs given as no-ball
15. penalty_runs : Runs given as penalty
16. batsman_runs : Runs scored by the batsman
17. extra_runs : Total extra runs (Wide, Bye, No-ball, Penalty)
18. total_runs : Total runs from the ball (extra_runs, batsman_runs)
19. player_dismissed : Name of the player dismissed (If out)
20. dismissal_kind : How the player was dismissed (If out)
21. fielder : Fielder involved in the dismissal (If any)





## Aim of the study

Our aim is to  clusters  the  players with respect to similarity in batting performance so that the batsman in the same cluster may fall in the same price bracket and this might help the Team Managers to take an informed decision
on whether to consider including a particular player in auction.


## Installing / Getting started

The analysis was conducted using Python 3.7.4 in the Jupyter Notebook.

Minimal setup required:

1. Python -- 3.7.4
2. Jupyter Notebook

Also apart from the Python core packages, Numpy  and Pandas are used for numerical computations and Data analysis respectively. For graphical analysis, we have used Seaborn . Note that all the packages are included in the Anaconda Distribution itself and can be used directly.

Once the libraries are set up, you can clone the repository with the following command

```shell
git clone https://github.com/satarupa5/clustering-players-for-auction.git
```
Then you can run the [Notebook](/code_for_clustering.ipynb)  containing all the  analysis

## Flow of the project
In this project an attempt has been made to categorise the players according to their batting performance, so that the team owners can determine the actual value of a batsman before an auction.

We have a detailed data on IPL matches from 2008 to 2019.The data is highly elaborate and in order to find the feature that might help in clustering, we first create some summary statistics ( like the Total Balls faced, the total runs scored, the total dismissals etc) on the basis of ball-by-ball data that is available for each batsman in the IPL.

Once we create this derived columns from the raw data, we venture out to create some performance statistics (Strike Rate, Batting Average etc) from the summarized data.

Once these summarized informations are prepared, we consider this data as the input for our further clustering procedure.

We start with a Dendogram and try to find out the number of clusters present in the data. Next using Ward's method, we create the clusters containing the players with similar batting capabilities.

## Limitations
An assumption is that all the batsman who have played previously are likely to take part in the coming IPL.
New players valuation have to be done basis their current performance ony, as no data is availble for them on previous IPL.

## Status
The Project is still in progress.

## Road Ahead
The same analysis can be done for the Bowlers, basis their performance matrix to have a cluster for the Bowlers also.

## Development

 Want to contribute? Great!

 To enhance the existing analysis, follow these steps:

 - Fork the repo
 - Create a new branch (`git checkout -b improve-feature`)
 - Make the appropriate changes in the files
 - Add changes to reflect the changes made
 - Commit your changes (`git commit -am 'Improve feature'`)
 - Push to the branch (`git push origin improve-feature`)
 - Create a Pull Request
