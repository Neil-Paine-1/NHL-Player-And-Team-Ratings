# NHL_GAR_data
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

