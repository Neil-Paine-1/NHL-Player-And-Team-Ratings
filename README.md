# Historical GAR Data
This file contains Goals Above Replacement (GAR) data for NHL history. GAR is my spin on Tom Awad’s Goals Versus Threshold (GVT) and Hockey-Reference.com’s Point Shares (PS), calculated by running a series of regressions and properly rescaling leaguewide value to better distribute between forwards, defensemen and goalies. (I assign forwards 60 percent of leaguewide value, while defensemen get 30 percent and goalies get 10 percent; the metric also creates more separation between league goaltending performances and balances total league offensive value against the value of defense plus goaltending.)


| Abbreviation |                         Key                          |
|--------------|------------------------------------------------------|
| player_id    | Hockey-Reference player ID tag                       |
| player_name  | Player's name                                        |
| year_id      | Season                                               |
| age          | Age as of Feb. 1                                     |
| team_id      | H-R team ID                                          |
| pos          | Player's position for season                         |
| team_name    | Full team name                                       |
| franch_id    | H-R franchise ID                                     |
| stint_id     | Stint no. within season (may be incomplete)          |
| lg_id        | League ID                                            |
| maj_pos      | Major position (F, D or G)                           |
| GP           | Games played                                         |
| G            | Goals                                                |
| A            | Assists                                              |
| Pts          | Points                                               |
| GCPG         | Goals Created per game                               |
| +/-          | Plus/minus rating                                    |
| PIM          | Penalty minutes                                      |
| ATOI         | Average time on ice per game                         |
| S%           | Shooting percentage                                  |
| GP_G         | Games (goalies)                                      |
| GA_G         | Goals against (goalies)                              |
| SA_G         | Shots against (goalies)                              |
| SV%          | Save percentage (goalies)                            |
| Offense      | Offensive Goals Above Replacement                    |
| Defense      | Defensive Goals Above Replacement                    |
| Goalie       | Goaltending Goals Above Replacement                  |
| Total_GAR    | Total Goals Above Replacement                        |
| Adj_Off      | Adjusted Offensive GAR                               |
| Adj_Def      | Adjusted Defensive GAR                               |
| Adj_Gltd     | Adjusted Goaltending GAR                             |
| Adj_GAR      | Adjusted GAR (scaled to modern schedule/roster size) |

# Historical Elo Data

This file contains Elo ratings for every game in NHL history (1918-). Elo ratings measure a team's strength over time, accounting for the strength of opponents, locations of games and margin of victory. The win probability between any two teams with given Elo ratings is found via:

Pr(Win) = 1 / (10^(-ELODIFF/400) + 1)

Where ELODIFF is equal to the difference in pregame Elo ratings between teams, plus or minus a home-ice bonus. In hockey, home ice is worth 50 Elo points.

Ratings update after each game in proportion to both how unlikely the result is and the margin of victory. Multipliers for each of these is applied to the "K-factor", which in hockey is found to be 6 in the regular season, with a 50% boost to become 9 in the playoffs. The margin of victory multiplier is found via:

MULT = 0.6686*LN(ABS(Margin)) + 0.8048

for cases where a game is decided in regulation or overtime. For ties (pre-current era) or shootout games, the multiplier is set to a fixed value of 0.8.

The change in a team's rating after the game is equal to (KFACTOR * MULT * DELTA), where DELTA represents the difference between the actual outcome (1 for a regulation or OT win, 0 for a regulation or OT loss and 0.5 for a tie or shootout result) and the pregame win probability according to Elo.

An expansion team's initial Elo is set to be 1380. A team's final Elo from the end of one season is reverted toward a mean of 1505 by 30 percent at the start of the following season.

# Playoff Odds

Playoff odds are derived by using Elo ratings to simulate the remainder of the NHL schedule 1,000 times. For regular-season games, Elo differential is used to generate the odds of each team gaining 2, 1 or 0 points in a matchup (i.e., a win or regulation loss, or an overtime/shootout loss) via logistic regression. Simulations are run using the 2021 NHL season structure, with the assumption that teams with fewer than 56 games will be ranked and seeded according to Points Percentage. In the Stanley Cup Semifinals, the winners of each division bracket are re-seeded by regular-season points percentage with wins (per game) as the tie-breaker.
