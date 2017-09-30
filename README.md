# fluffy-guide
captured fluffy simulation data

can be used in match prediction and stuff


This data is captured semi-automatically, some matches might be missing, while i will always try to capture the entire stream i can't guarantee you that.

# Capture process

The scripts used to dump the data are closed but i will document the technology when i get the time.

# Data format

The data dump is organised in league seasons each is identified by a unique number, normally the directory name. Inside each season directory there are sub directories each number 01-38 to represent the week of the matches in the season.

Each week has around 10 matches. Each match has a corresponding file in the format```home_team-vs_away_team.json``` eg. ```arsenal-vs-southampton.json```

Each file looks like this

```json
{
  "eventId": "1025905",
  "teams": {
    "teamA": {
      "teamId": "48",
      "teamName": "ARS",
      "teamFlag": "arsenal"
    },
    "teamB": {
      "teamId": "52",
      "teamName": "SOU",
      "teamFlag": "southampton"
    }
  },
  "goals": {
    "teamAGoals": 0,
    "teamBGoals": 2
  },
  "odds": {
    "home": {
      "oddId": "Home",
      "marketId": "mr",
      "odd": "2.07",
      "prob": 0,
      "oddIdNumber": 0
    },
    "draw": {
      "oddId": "Draw",
      "marketId": "mr",
      "odd": "3.23",
      "prob": 0,
      "oddIdNumber": 2
    },
    "away": {
      "oddId": "Away",
      "marketId": "mr",
      "odd": "3.97",
      "prob": 0,
      "oddIdNumber": 1
    }
  }
}
```

Remember teamA is the home team while teamB is the away team.

# Payload details

eventID should be unique for each match, last two characters represent the week while the preceding ones represent the season id. 

teams participating

odds that were set by simulation server

and the match results that is, the score for home team and score for away team.

More on the docs later