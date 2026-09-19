# College Football Team Talent and Against-the-Spread Performance

## Research Question
Is greater team talent associated with better against the spread (ATS) performance in college football during the 2025 season?

This data analysis compares team talent ratings with two measures of betting market performance: ATS win percentage and average cover margin. The goal is to determine whether more talented teams consistently outperform the expectations implied by betting spreads.

## Problem Definition

College football teams differ substantially in roster talent, but betting markets attempt to account for differences in team quality when setting point spreads. Because of this, a highly talented team may win many games without necessarily performing well against the spread. This project examines whether teams with higher talent ratings also perform better relative to betting market expectations. This question may be useful to sports analysts, bettors, and fans interested in the relationship between roster quality and market adjusted performance.

## Data Source and Variables

Data was collected through the CollegeFootballData (CFBD) API using the cfbd Python package. Two team level endpoints were used for the 2025 season:

- Team talent data: one row per team with a team talent score.
- Against the spread data: one row per team with ATS wins, ATS losses, ATS pushes, games, conference, and average cover margin.

### Key Variables
- talent: CFBD team talent score; higher values indicate greater roster talent.
- atsWins: number of games in which the team covered the betting spread.
- atsLosses: number of games in which the team failed to cover the betting spread.
- atsPushes: number of games in which the final margin exactly matched the spread.
- atsWinPct: ATS wins divided by ATS wins plus ATS losses. Pushes are excluded because they are neither wins nor losses.
- avgCoverMargin: average number of points by which the team exceeded or fell short of the betting spread. Positive values indicate outperforming the spread on average.
- conference: the team's conference affiliation.

Source documentation: https://github.com/CFBD/cfbd-python

## 6. Visualizations and Insights

### Team Talent vs. ATS Win Percentage

The scatterplot below examines whether more talented teams cover the spread more frequently.



## Notebook
[View Jupyter Notebook](../notebooks/MatthewThow_CFBproject.ipynb)
