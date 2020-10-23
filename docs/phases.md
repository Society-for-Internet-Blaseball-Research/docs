# Simulation phases
Each season is split up into various phases depending on what's currently going on in the world of Blaseball. The current season state is transmitted in the `sim` object (see [Simulation data](../reference/Blaseball-API.v1.yaml/components/schemas/SimulationData)) as a single integer.

Each season (as defined by the `season` property in `sim`) starts in phase 1, and ends in phase 0.

## List of phases
Below is a list of sim phases experienced throughout a standard season of Blaseball, in chronological order.

Phase # | Name | Description
---|---|---
1 | Pre-Season | The "pre-season" - this is when the next season's decrees and blessings become publicly visible, and when the upcoming season's game schedule gets generated. This starts on Monday at 1am PST, where the season number also ticks over.
2 | Season | Normal season games are in progress here. Starts at 12pm PST on Monday.
7 | - | Starts as soon as the last game of Day 99 finishes, and lasts until the next top of the hour. This is eg. when the "ominous line" on the idol board would start to vibrate.
3 | Offseason | Between the regular season and the Wild Card games. Starts on the top of the hour after Day 99, and lasts for the duration of that hour.
10 | Postseason | Wild Card games are in progress. 
11 | Wild Card Evening | The postseason, break between the Wild Card games and the quarterfinals.
4 | Postseason | Postseason games (after Wild Card) are in progress.
9 | Day X | Boss fight time! Seems to happen immediately after the Internet League finals.
5 | - | After post-season, before election. Transitions to phase 6 on Sunday at 5am PST. Unknown why this happens or what the differences are.
6 | - | Same as phase 5.
0 | Blaseball Gods' Day | Post-election, results are visible here. Starts at 12pm PST on Sunday, and lasts until the season ticks over at 1am PST on Monday.