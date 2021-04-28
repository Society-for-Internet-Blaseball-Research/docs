# Simulation phases
Each season is split up into various phases depending on what's currently going on in the world of Blaseball. The current season state is transmitted in the `sim` object (see [Simulation data](../reference/Blaseball-API.v1.yaml/components/schemas/SimulationData)) as a single integer.

Each season (as defined by the `season` property in `sim`) starts in phase 1, and ends in phase 0.

## List of phases
Below is a list of sim phases experienced throughout a standard season of Blaseball, in chronological order (if applicable).

### Expansion Era (Seasons 12 to Current)
Phase # | Name | Description
---|---|---
1 | Pre-season | The "pre-season" - this is when the next season's decrees and blessings become publicly visible, and when the upcoming season's game schedule gets generated. This starts on Monday at 1am PST, where the season number also ticks over.
2 | EarlSeason | Regular season play, starting at day 1 and ending immediately after day 27. Starts at 9am PST on Monday.
3 | EarlSiesta | The tarot draw and 1 hour break between day 27 and 28.
4 | MidSeason | Regular season play, starting at day 28 and ending immediately after day 72.
5 | LateSiesta | Ballpark renovations and 1 hour break between day 72 and 73.
6 | LateSeason | Regular season play, starting at day 73 and ending immediately after day 99.
7 | Season End | Results based on final regular season standings (such as Free Wills) and the MVP results. Transitions to phase 8 at the top of the next hour.
8 | Pre-Postseason | Selection of Wild Cards, generation of postseason births, and 1 hour break between the end of the regular season and the start of the playoffs. 
9 | Early Postseason | First day of playoffs, including the Wild Card games (Round 1) and quarterfinals (Round 2).
10 | Early Postseason End | The postseason break between the Wild Card games and the semifinals.
11 | Postseason | Second day of playoffs, including semifinals (Round 3) and finals (Round 4). Starts at 9am PST on Saturday.
12 | Postseason End | After post-season, before election.
13 | Election | Drawing of election results. Starts at 11am PST on Sunday.
0 | Blaseball Gods' Day | Post-election. Starts at 12am PST on Sunday and lasts until the season ticks over, either at 1am PST the next Monday or 2 weeks later if the offseason.

### Discipline Era (Seasons 1 to 11)
Phase # | Name | Description
---|---|---
1 | Pre-Season | The "pre-season" - this is when the next season's decrees and blessings become publicly visible, and when the upcoming season's game schedule gets generated. This starts on Monday at 1am PST, where the season number also ticks over.
2 | Season | Normal season games are in progress here. Starts at 12pm PST on Monday.
7 | Idol Results | Starts as soon as the last game of Day 99 finishes, and lasts until the next top of the hour. This is eg. when the "ominous line" on the idol board would start to vibrate. Was skipped in Season 11.
3 | Season End | Between the regular season and the Wild Card games. Starts on the top of the hour after Day 99, and lasts for the duration of that hour.
10 | Wild Card | Wild Card games are in progress. 
11 | Wild Card Evening | The postseason, break between the Wild Card games and the quarterfinals, and (Season 11+) the break between quarterfinals and semifinals.
4 | Postseason | Postseason games (after Wild Card) are in progress.
9 | Day X | Boss fight time! Seems to happen immediately after the Internet League finals.
5 | Postseason End | After post-season, before election. Transitions to phase 6 on Sunday at 5am PST. Unknown why this happens or what the differences are.
6 | Offseason | Same as phase 5.
0 | Blaseball Gods' Day | Post-election, results are visible here. Starts at 12pm PST on Sunday, and lasts until the season ticks over at 1am PST on Monday.
12 | Pre-Tournament | A custom tournament (such as the Coffee Cup) is starting shortly.
13 | Tournament Play | Tournament games are being played.
14 | Tournament Round Complete | A round of the tournament has finished.
15 | Tournament Complete | The tournament is complete.
8 | Bloodbath | Never implemented.
