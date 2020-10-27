# Player stats

## Forbidden stlats
Every player has a significant number of hidden properties (or *"stlats"*) not visible through any public interface directly. Visible star ratings are calculated based on a weighted combination of these, but differences in the composition of each player's stlats will affect their performance in different game scenarios, leading to a much more complex and interesting simulation.

### Range
Most stlats range between zero and one, however there's no known upper limit to most of them. Most stlats do seem to have a lower limit of `0.01`, and the "negative stlats" an upper limit of `0.99`, presumably to prevent the star calculations from breaking.

This was demonstrated by Raúl Leal's minimization, leaving them with a `buoyancy`, `coldness`, `divinity`, `chasiness`, `martyrdom`, `baseThirst`, `omniscience`, `suppression`, `ruthlessness`, `laserlikeness`, `overpowerment`, `tenaciousness`, `anticapitalism` and `shakespearianism` value of exactly `0.01`, and a `patheticism` value of exactly `0.99`.

### Batting stlats
Name | Star weight | Description
--- | --- | ---
`divinity` | 0.35 | Home run frequency, boosted by "Power" blessings (eg. Ooze, Mushroom)
`thwackability` | 0.35 | "Quality" of contact with the ball, reducing the chance of balls being fielded. High thwackability is correlated to higher batting average, OBP, etc.
`moxie` | 0.075 | Ability to draw walks, likely represents some kind of plate discipline
`musclitude` | 0.075 | Extra base hits (specifically seems to be Doubles), and appears to impact fouls.<br>Positively correlates to doubles, got a 10% boost on players affected by the +10% boost to Speed in the Season 6 election, as well as 10% from the Power buff, and is boosted by the Mushroom.
`patheticism` | -0.05 | Likelihood of the batter (not) making contact with the ball. Correlates with high strikeout rate, lower BA, OBP, and other derived stats.
`martyrdom` | 0.02 | Potentially related to Fielder's Choices in a way, potentially a gatekeeper check for when a batter rolls an out to see if it becomes a FC (and then perhaps a Double Play)
`tragicness` | -0.01 | Low tragicness seems to increase overall performance, specifics are unknown.<br>Players are generated with a randomized tragicness value (like all stats), but tragicness gets set to 0.1 at the start of seasons and upon siestas/delays etc throughout the season (since S3 and around the server instability of that era). Allegedly linked to `shakespearianism`.
`buoyancy` | 0 | Appears to make fielding outs specifically into fly outs. Included in the batting stars calculation, but does not affect the output. Also represents vibe period in the vibe calculation formula.

### Pitching stlats
Name | Star weight | Description
--- | --- | ---
`unthwackability` | 0.5 | Lowers hits allowed, reduces "quality" of contact, increases likelihood of the ball being fielded. Likely the "counter" to the `thwackability` batting stlat.
`ruthlessness` | 0.4 | Reduces walks and increases strikeouts - seems to essentially determine whether a given pitch is in or out of the strike zone, so to speak.
`overpowerment` | 0.15 | Lowers home runs - seems to be involved in all hit types, potentially used to counter triples and doubles as well (likely by reducing the power of batted balls)
`shakespearianism` | 0.1 | Unknown effect...? Allegedly linked to `tragicness`, according to [Joel](https://www.youtube.com/watch?v=zO05p-e57AQ&t=1188s), but further analysis indicates it's more likely to be linked to `martyrdom` as a FC/DP gatekeeper.
`coldness` | 0.025 | Unknown effect.
`suppression` | 0 | Unknown effect. Included in pitching star calculations, but does not affect the output.

### Baserunning stlats
Name | Star weight | Description
--- | --- | ---
`laserlikeness` | 0.5 | Steal success, steal attempts (correlation stronger than baseThirst). Along with indulgence, appears to impact runner advancement on outs, and may just be a general running speed/ability. Boosted by Speed blessings.
`continuation` | 0.1 | Appears to quite strongly control advancement on hits - whether a runner advances 1 or 2 bases on a Single/Double (also somewhat linked to indulgence)
`baseThirst` | 0.1 | Stealing attempts in general, successful or not (eg. high `baseThirst` and low `laserlikeness` means lots of failed attempts). Boosted by Speed blessings.
`indulgence` | 0.1 | Seems to be related to runner advancement on an out (and likely related to sac plays/runs in general) together with laserlikeness.
`groundFriction` | 0.1 | Appears to govern the rate of triples, slight negative correlation with doubles, possibly by converting them to triples instead? Boosted by Speed *and* Power blessings.

### Defense stlats
Name | Star weight | Description
--- | --- | ---
`omniscience` | 0.2 | Likely the chance of turning a hit into an out.
`tenaciousness` | 0.2 | Unknown effect.
`watchfulness` | 0.1 | Reduces base stealing *attempts*, unknown effect on success rate.
`anticapitalism` | 0.1 | Potentially represents defense against base theft (or at least second base).
`chasiness` | 0.1 | Unknown effect.

### Other
Name | Description
--- | ---
`totalFingers` | Finger count appears to represent instances of change to pitching stats. All players start with 10 fingers. Players impacted by general stat buffs all received 1 more finger, regardless of the size of the buff. Party buffs don't appear to grant fingers.<br>Raúl Leal received an over-debuff of 0.51 with the Iffey Jr. to Minimize them, and gained 51 fingers - they appear to have been given -0.01 to all stlats 51 times to get them to 0 in everything.<br>This process in reverse is likely how PolkaDot Patterson and Axel Trololo got their pitching maximized (we can check on Axel since we have their stat history) by adding a small amount repeatedly until they hit 5 stars.<br>Goodwin Morin seems to have gotten the reverse of Raúl's process when being maximized, instead of the same process PolkaDot Patterson and Axel Trololo got - resulting in gaining 81 fingers and +0.81 to *every* attribute. This brought their pitching to 5 stars, but boosted other ratings much further - they ended up with 7 baserunning stars, for example.
`pressurization` | Represents "minimum vibes" in the vibe calculation formula (higher pressurization = lower vibe floor).
`cinnamon` | Represents "maximum vibes" in the vibe calculation formula (higher cinnamon = higher vibe ceiling).
`soul` | Represents the amount of 11-letter "chunks" in the player's soulscream. All players have a value between 2 and 9, with the exception of [Chorby Soul](https://www.blaseball.com/player/a1628d97-16ca-4a75-b8df-569bae02bef9), with a value of 1777 (hence the broken soulscream).
`peanutAllergy` | Whether the player is allergic to peanuts. An allergic player will get an allergic reaction (a debuff) from swallowing a peanut during Peanut weather, whereas a non-allergic player will get a "yummy" reaction (a buff) instead.
`fate` | Unknown. Ranges between 1 and 99. Directly visible on the player page, unlike other stlats.

## Star ratings
Each of the four star ratings (batting, pitching, baserunning and defense) is calculated based on relevant player stlats using a weighted formula. The formulas are present in the frontend code, and don't appear to ever have changed.

A "paraphrased" version of the formulas can be found below:

<!-- title: Player rating calculation -->
```javascript
function calculateBattingRating(player) {
  return (
    Math.pow(1 - e.tragicness, 0.01) *
    Math.pow(e.buoyancy, 0) *
    Math.pow(e.thwackability, 0.35) *
    Math.pow(e.moxie, 0.075) *
    Math.pow(e.divinity, 0.35) *
    Math.pow(e.musclitude, 0.075) *
    Math.pow(1 - e.patheticism, 0.05) *
    Math.pow(e.martyrdom, 0.02)
  );
}

function calculatePitchingRating(player) {
  return (
    Math.pow(e.shakespearianism, 0.1) *
    Math.pow(e.suppression, 0) *
    Math.pow(e.unthwackability, 0.5) *
    Math.pow(e.coldness, 0.025) *
    Math.pow(e.overpowerment, 0.15) *
    Math.pow(e.ruthlessness, 0.4)
  );
}

function calculateBaserunningRating(player) {
  return (
    Math.pow(e.laserlikeness, 0.5) *
    Math.pow(e.continuation, 0.1) *
    Math.pow(e.baseThirst, 0.1) *
    Math.pow(e.indulgence, 0.1) *
    Math.pow(e.groundFriction, 0.1)
  );
}

function calculateDefenseRating(player) {
  return (
    Math.pow(e.omniscience, 0.2) *
    Math.pow(e.tenaciousness, 0.2) *
    Math.pow(e.watchfulness, 0.1) *
    Math.pow(e.anticapitalism, 0.1) *
    Math.pow(e.chasiness, 0.1)
  );
}

function ratingToStarsUnrounded(rating) {
  return rating * 5;
}

function ratingToStarsRounded(rating) {
  return Math.round(rating * 10) / 2;
}
```

Note that these functions will usually return a value between `0.0` and `1.0` - a value of `1.0` means five stars. There's no known upper limit here; Richardson Games currently has a defense rating of ~1.63, meaning *eight* visible defense stars.

To get the unrounded star count, multiply the value by five. This value can be rounded to the *nearest* half-star to get the displayed amount of stars. This can be done by doubling the star count, rounding that to the nearest integer, then halving it again - or in code, `Math.round(stars * 2) / 2`.

Starting in mid-October, the rating values (from 0-1) are also present in a pre-calculated form in the players object, as the properties `hittingRating`, `pitchingRating`, `baserunningRating`, and `defenseRating`, but are currently unused in the frontend code (the calculation is done directly instead). This may imply the star calculation is going to change at some point, and that we're not going to be able to see the new formulas going forward.

## Vibes
Vibes oscillate over the course of the season as a sine wave with parameters based on a few player stlats. `buoyancy` controls the period of the oscillation, `pressurization` the minimum value, and `cinnamon` the maximum value.

A visual representation of both individual player vibes and combined team vibes can be seen with [our "Vibe Check" tool](https://vibecheck.sibr.dev/).

### Formula
The formula can be found in the site frontend code, and a cleaned version is reproduced below:

<!-- title: Vibe calculation -->
```javascript
function calculatePlayerVibes(player, day) {
  const frequency = 6 + Math.round(10 * player.buoyancy);
  const phase = Math.PI * ((2 / frequency) * day + 0.5);

  const range = 0.5 * (player.pressurization + player.cinnamon);
  return (range * Math.sin(phase)) - (0.5 * player.pressurization) + (0.5 * player.cinnamon);
}
```

### Display
Vibes are displayed in the frontend as one of seven categories based on an underlying floating point value:

From | To | Display
--: | :-- | ---
0.8 | - | ⬆️⬆️⬆️ Most Excellent
0.4 | 0.8 | ⬆️⬆️ Excellent
0.1 | 0.4 | ⬆️ Quality
-0.1 | 0.1 | ↔️ Neutral
-0.4 | -0.1 | ⬇️ Less Than Ideal
-0.8 | -0.4 | ⬇️⬇️ Far Less Than Ideal
- | -0.8 | ⬇️⬇️⬇️ Honestly Terrible

## Soulscreams
Soulscreams (or, for Released players, *soulsongs*) are purely visual, but are derived from five stlats: `pressurization`, `divinity`, `tragicness`, `shakespearianism`, and `ruthlessness`.

It's grouped into chunks of 11 letters, each chunk representing a single digit of each of the stlats. Since there are only five stlats, the chunks repeat internally modulo five (in a 5-5-1 pattern).

The code for generating soulscreams can be found in the front-end code, and a cleaned version is reproduced below:

<!-- title: Soulscream calculation -->
```javascript
function generateSoulscream(player) {
  const stlats = [
    player.pressurization,
    player.divinity,
    player.tragicness,
    player.shakespearianism,
    player.ruthlessness
  ];
  const letters = ["A", "E", "I", "O", "U", "X", "H", "A", "E", "I"];

  let soulscream = "";
  for (let chunk = 0; chunk < player.soul; chunk++) {
    // first 1, then 0.1, then 0.01, then 0.001, etc...
    const magnitude = 1 / Math.pow(10, chunk);

    for (let stlatIndex = 0; stlatIndex < 11; stlatIndex++) {
      const stlat = stlats[stlatIndex % stlats.length];

      // Picks out the single digit corresponding to the `chunk`th decimal place
      const stlatDigit = Math.floor(((stlat % magnitude) / magnitude) * 10);
      
      soulscream += letters[stlatDigit];
    }
  }

  return soulscream;
}
```

Because JavaScript works with double-precision floating point numbers, it's unable to represent numbers over 10^309. With a `soul` value of larger than 309, the `magnitude` variable above will become exactly zero (`1 / Infinity`), a division by zero will occur in the `stlatDigit` calculation, and the resulting letter will instead be the word `undefined`. This explains why [Chorby Soul](https://www.blaseball.com/player/a1628d97-16ca-4a75-b8df-569bae02bef9) has 3400 valid soulscream letters (309 * 11 = 3399) until it just becomes the word `undefined` repeated over and over :)

## Blood type
Player blood type is usually cosmetic, but in the case of team-wide blood type blessings, may have an effect.

It has been observed that blood type effects only occur when the player has the required blood type, *and* is on a team with the blood type modifier attribute. When the blessing was awarded, all team members had their blood type changed, but later additions keep their existing type.

For example, Jaylen Hotdogfingers, who transferred to the Lovers after Season 10, has blood type "AA", and has never been observed to Charm a batter. The opposite example is Francisca Sasquatch, who transferred (back) to the Dale while already having Electric blood - Sasquatch *does* successfully trigger the effects of Electric blood, despite not being on the team when the blessing was won.

ID | Name | Team | Modifier
--- | --- | ---
0 | A | - | None, used as a placeholder for newly generated players.
1 | AAA | - | None.
2 | AA | - | None.
3 | Acidic | - | None.
4 | Basic | Sunbeams | "Base Instincts": Batters have a chance to move directly to second, third, or fourth base (but never home) when drawing a walk.
5 | O | - | None.
6 | O No | Magic | "0 No": Converts would-be strikeouts to foul balls when there are 0 Balls on the count. This often leads to [very large amounts of consecutive fouls](https://reblase.sibr.dev/game/ab10b339-4de9-4bc3-b057-5bf702607583#4d593d33-ec11-e90c-204b-f3a4b4fb9e6d) for batters with high patheticism and low moxie.
7 | H₂O | - | None.
8 | Electric | Dale | "Electric": Batters have a chance to "zap" away strikes on the board.
9 | Love | Lovers | "Charm": Batters have a chance to draw a walk during their at-bat, and pitchers have a chance to make the batter strike out immediately.
10 | Fire | - | -
11 | Psychic | - | -
12 | Grass | Flowers | "Growth": Teams will play better as the season goes on, up to a 5% boost by the season's end. The actual effect of this isn't known.
- | Blood? | - | Fallback value.

## Coffee style
Purely cosmetic, as far as we know.

ID | Name | Notes
--- | ---
0 | Black | -
1 | Light & Sweet | -
2 | Macchiato | -
3 | Cream & Sugar | -
4 | Cold Brew | -
5 | Flat White | -
6 | Americano | -
7 | Espresso | [Missing from the display name lookup table, so will display as "Coffee?" on player pages.](https://twitter.com/SIBROfficial/status/1305545970285862912)
8 | Heavy Foam | -
9 | Latte | -
10 | Decaf | -
11 | Milk Substitute | -
12 | Plenty of Sugar | -
13 | Anything | -
- | Coffee? | Fallback value.