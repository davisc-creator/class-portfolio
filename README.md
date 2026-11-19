I am doing this project with Solomon Selkin. 

General topic: Using 2023–2026 MLB Baseball Savant (Statcast) data (full-season bat tracking starts in 2024) to find out which measurable skills are associated with team success and with "deceptive" pitching. We are looking at two sides of the game: how hitters swing (bat tracking and attack direction) and how pitchers disguise what they throw (velocity gaps between pitches and pitch movement relative to arm angle). The goal is to see which of these newer tracking metrics are associated with team success, and whether they add anything beyond traditional stats such as wOBA and OPS.

Data sources:

Baseball Savant pitch-level exports (2023–2026 regular seasons). We are using this to gather data on: Pitch type, release speed, horizontal and vertical movement, arm angle, zone location, and outcomes, plus official final scores. 
Pros: public, official MLB data; hundreds of thousands of pitches with consistent player, team, and season IDs; we can compute our own derived measures such as velocity gap and movement-arm disparity. 
Cons: pitch data has to be aggregated to pitchers or teams, and at the team level that leaves only 30 teams per season (about 120 team-seasons across four years), so statistical power is low. Trades split a player across several teams.
Baseball Savant bat tracking leaderboard (bat-tracking-swing-path.csv). We are using this to gather data on: Player-level average bat speed, swing tilt, attack angle, attack direction and number of competitive swings. 
Pros: directly measures swing path, which is the core of our first question; includes the swing count, so we can weight or filter by sample size. 
Cons: bat tracking only began in the second half of 2023, so only 2024–2026 are full seasons; it is player-level and must be aggregated to teams.
Savant statistic catalog and team-level outcome measures (xwOBA, win percentage, Pythagorean expected wins). 
Pros: gives clear outcome variables and documents what each stat means. 
Cons: xwOBA is partly built from the same contact-quality data as the swing metrics, so some correlation is mechanical, and some Savant fields have no fully documented formula.
Questions:

Is a team's average batting attack direction (how much its hitters pull the ball versus hitting it the other way) associated with its xwOBA, win percentage, and expected wins?
Does the gap in velocity between a pitcher's primary and secondary pitch, compared with an arsenal of mostly fastballs and sliders with little change in speed ("no change, no curve"), predict deceptive outcomes such as whiff rate and called-strike rate in the heart of the zone? (The aim is to determine whether pitchers without elite velocity can still generate deception through speed differences. We will control for average velocity and use zone rate and walk rate as rough measures of command.)
Does the angle of a pitch's movement relative to the pitcher's arm angle (the disparity between them) predict whiff rate and heart-zone called-strike rate?
Plan and early results: We plan to use correlation and regression (with multiple-comparison adjustment) as our main tools. A first pass on 2026 team-level data (30 teams) showed weak associations, and none of the 14 correlations survived multiple-comparison adjustment. Because 30 teams is such a small sample, we expect to move to pitcher-level and multi-season data for the final project. All of this is observational, so we will describe associations rather than causes.
