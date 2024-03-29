# bb2parse
---
Parse Bloodbowl2 replay files for statistics

## Install
---
Install using pip:
```$ pip install bb2parse```

## Usage
### Initializing a Season/Match Object
```python
from bb2parse import BloodBowlMatch, BloodBowlSeason

game = BloodBowlMatch('{XML file}')

season = BloodBowlSeason('{XML file}','{XML file}','{XML file}','{XML file}'...)
```

### Attributes of Match Objects
```python
game.match_outcome
game.home
game.away

# Subclass 
game.HomeTeam
game.AwayTeam

game.HomeTeam.coach     

#Object and its methods and attributes
game.HomeTeam.Offense 
        .interceptions
        .touchdowns
        .running_yards
        .passing_yards
        .passes
        .catches
        .possession
        .occupation_own
        .get_pass_completion()
        .get_pass_intercept_ratio()
game.HomeTeam.Defense
        .casualties_inflicted
        .interceptions
        .ko_inflicted
        .injuries_inflicted
        .kills_inflicted
        .expulsions
        .occupation_their
        .get_ratio_injuries()
        .get_ratio_casualties()
        .get_ratio_kills()
game.HomeTeam.Injuries
        .deaths_sustained
        .ko_sustained
        .casualties_sustained
        .injuries_sustained
```

### Attributes of Season objects
```python
season.seasonlength
season.scoreboard

season.Teams.teamlist # returns regular set of teams involved in games

# Use this attribute to look for stats/data
season.getTeams
# Should return list of team objects

season.getTeams[0].name
season.getTeams[0].matches_played
season.getTeams[0].matches # Returns list of BloodBowl Match Objects
season.getTeams[0].get_total_kills()
season.getTeams[0].get_total_touchdowns()
season.getTeams[0].get_total_running_yards()
season.getTeams[0].get_total_passing_yards()
season.getTeams[0].get_td_avg()


```