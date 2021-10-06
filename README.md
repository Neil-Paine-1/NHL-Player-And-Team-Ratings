# Historical GAR Data
This file contains Goals Above Replacement (GAR) data for NHL history. GAR is my spin on Tom Awad’s Goals Versus Threshold (GVT) and Hockey-Reference.com’s Point Shares (PS), calculated using Goals Created on offense, Goals Saved Above Average for goalies and Relative On-Ice Goals Allowed on defense to properly rescale leaguewide value and better distribute between forwards, defensemen and goalies. (I assign forwards 60 percent of leaguewide value, while defensemen get 30 percent and goalies get 10 percent; the metric also creates more separation between league goaltending performances and balances total league offensive value against the value of defense plus goaltending.)

**Update (10/6/21):** The file ```NHL-GAR-data-v2.5-1956-2021.csv``` contains a new update to the GAR formula that does a better job of reconciling the sum of a team's GAR to its actual regular-season goal differential. In the past, GAR was somewhat decoupled from the player's team context and only concerned with balancing positions at a league-wide level. Now GAR has an element that ensures each team's offensive GAR is based on its goals per game (relative to league average) and its defensive GAR is based on the implied team defensive performance after extracting goaltending GAR (which itself is based on Save%). As a result, we should no longer see cases like the 2020-21 Philadelphia Flyers, who (while a bad team) had an artificially poor total GAR because the team was independently being penalized for horrible goaltending and low defensive GAR. Now the sum of those categories will correspond to a team's goals allowed relative to league average.



|  Abbreviation  |                                           Key                                            |
|----------------|------------------------------------------------------------------------------------------|
| player_ID      | Hockey-Reference player ID tag.                                                          |
| name_common    | Player's name.                                                                           |
| year_ID        | Season.                                                                                  |
| age            | Age on Jan 31 of the season.                                                             |
| team_ID        | Team ID tag.                                                                             |
| pos            | Position.                                                                                |
| maj_pos        | Major position (i.e., F/D/G).                                                            |
| gp             | Games played as skater.                                                                  |
| g              | Goals.                                                                                   |
| a              | Assists.                                                                                 |
| pts            | Points.                                                                                  |
| gc             | Goals Created.                                                                           |
| plusminus      | Plus/Minus.                                                                              |
| minus_vs_exp   | Minuses vs. expected (based on team/position average).                                   |
| pim            | Penalty minutes.                                                                         |
| s              | Shots on goal.                                                                           |
| s_pct          | Shooting percentage.                                                                     |
| toi            | Time on ice.                                                                             |
| g_gp           | Goalie games played.                                                                     |
| g_ga           | Goalie goals allowed.                                                                    |
| g_sa           | Goalie shots against.                                                                    |
| g_sv           | Goalie saves.                                                                            |
| g_sv_pct       | Goalie save percentage.                                                                  |
| g_min          | Goalie minutes played.                                                                   |
| g_adj_ga_rt    | Goalie GA%- (adjusted rate of allowing goals, where 100 is average and lower is better). |
| g_gsaa         | Goalie goals saved above average.                                                        |
| g_lg_sv_pct    | Goalie league-average SV% in season.                                                     |
| off_gar        | Offensive Goals Above Replacement.                                                       |
| def_gar        | Defensive Goals Above Replacement.                                                       |
| gltd_gar       | Goaltending Goals Above Replacement.                                                     |
| tot_gar        | Total Goals Above Replacement.                                                           |
| tm_sched       | Team schedule length.                                                                    |
| roster_sz      | Active roster size (skaters) in season.                                                  |
| adj_off        | Adjusted offensive GAR (accounts for sched/roster sz).                                   |
| adj_def        | Adjusted defensive GAR (accounts for sched/roster sz).                                   |
| adj_gltd       | Adjusted defensive GAR (accounts for sched).                                             |
| adj_gar        | Adjusted Total GAR (accounts for sched/roster sz).                                       |
| mpg            | Minutes per game.                                                                        |
| tot_gmsc       | Total Game Score (as per Hockey-Graphs.com formula).                                     |
| gmsc_pg        | Game Score per game.                                                                     |
| gmsc_pg_vs_avg | Game Score per game vs. average at position.                                             |
| gmsc_60        | Game Score per 60 minutes.                                                               |
| gmsc_60_vs_avg | Game Score per 60 vs. average at position.                                               |



# Historical Elo Data and Playoff Odds

The Elo model and forecast has been revamped and will now be hosted at FiveThirtyEight.
