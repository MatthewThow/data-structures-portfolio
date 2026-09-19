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

## Visualizations and Insights

### Team Talent vs. ATS Win Percentage

The scatterplot below examines whether more talented teams cover the spread more frequently.
![Scatterplot of Team Talent vs. ATS Win Percentage](images/teamtalent_vs_ATSwin%.png)

The fitted line slopes slightly downward, but the observations are widely dispersed. This suggests that teams with greater talent were not consistently better at covering the spread. The visual pattern appears weak rather than strongly predictive.

### Team Talent vs. Average Cover Margin

Average cover margin measures how far above or below the betting spread a team finished on average.
![Scatterplot of Team Talent vs. Average Cover Margin](images/teamtalent_vs_avgcover.png)

This relationship is also nearly flat. Teams at similar talent levels show both positive and negative average cover margins, indicating that roster talent by itself does not explain much of the variation in market adjusted performance.

### Correlation Analysis
The correlation between talent and ATS win percentage is -0.12, while the correlation between talent and average cover margin is approximately -0.05. Both are very close to zero, indicating little linear relationship between talent and ATS performance in this sample. ATS win percentage and average cover margin are much more strongly related (approximately 0.78), which is expected because teams that cover more frequently should generally have stronger average cover margins.

### Top 10 Teams by Talent

This bar chart displays the ten college football teams with the highest talent ratings.

![Top 10 Teams by Talent](images/top10teamsbytalent.png)


### Top 10 Teams by Average Cover Margin

This chart identifies the ten teams that outperformed betting spreads by the largest average margin.

![Top 10 Teams by Average Cover Margin](images/top10teamsbyavgcovermargin.png)


## Main Findings

The 2025 data provide little evidence that a more talented roster automatically leads to better performance against the betting spread. The two measures of ATS performance tell a consistent story: talent had only a very weak negative relationship with ATS win percentage and almost no relationship with average cover margin. This result is plausible because point spreads are designed to incorporate expectations about team strength. A talented team may be expected to win by a large margin, making it difficult to cover even when the team wins the game. Conversely, a less talented team can perform well ATS by exceeding relatively lower market expectations. Therefore, the analysis should not be interpreted as evidence that talent makes teams worse. Instead, it suggests that team talent alone was not a useful predictor of whether a team would outperform the betting market during the 2025 season.

## Limitations, Ethics, and Reflection

### Limitations
- The analysis covers only the 2025 season, so the relationship may differ in other seasons.
- Team talent is represented by a single composite score and does not capture injuries, coaching, transfers during the season, player development, or matchup specific factors.
- ATS results depend on betting market spreads, which incorporate information beyond roster talent.
### Ethics
This project uses publicly accessible sports data for analysis. The results should not be treated as gambling advice or as evidence of a reliable betting strategy.
### Reflection and Next Steps
A useful extension would be to repeat the analysis across several seasons, compare conferences, or add variables such as team record, offensive efficiency, defensive efficiency, or preseason expectations. Analysis using multiple seasons would help determine whether the weak relationship observed in 2025 is persistent or season specific.

## Code and Transparency

The complete Python analysis is contained in this notebook. Data were accessed from the CollegeFootballData API through the cfbd Python wrapper.

### Data / Documentation Source
- CollegeFootballData. cfbd-python: Python wrapper for the CFBD API. GitHub: https://github.com/CFBD/cfbd-python




## Notebook
[View Jupyter Notebook](../notebooks/MatthewThow_CFBproject.ipynb)
