# Data Model

## Table of Contents

- [Entities and Attributes](#entities-and-attributes)
    - [User](#user)
    - [Administrator](#administrator)
    - [Player](#player)
    - [Tournament](#tournament)
    - [Leaderboard](#leaderboard)
    - [Scorecard](#scorecard)
    - [PlayerProfile](#playerprofile)

## Entities and Attributes

### User

- **Attributes:**
    - `UserID`: Unique identifier for each user.
    - `Username`: The login name used by the user.
    - `Password`: Hashed password for security.
    - `Email`: Contact email address of the user.
    - `Role`: Designates the user's role (regular user, admin, or player).

- **Relationships:**
    - Each User can have one associated PlayerProfile.

### Administrator

- **Attributes:**
    - `AdminID`: Unique identifier for administrators.
    - `UserID`: Foreign key which links to the User entity.

- **Relationships:**
    - An Administrator can manage several players and tournaments.

### Player

- **Attributes:**
    - `PlayerID`: Unique identifier for each player.
    - `UserID`: Foreign key linking to the User entity.
    - `TournamentIDs`: List indicating the tournaments the player is involved in.

- **Relationships:**
    - Many Players can participate in multiple Tournaments.
    - Each Player has one Scorecard per Tournament.

### Tournament

- **Attributes:**
    - `TournamentID`: Unique identifier for each tournament.
    - `Name`: Tournament name.
    - `Date`: Date on which the tournament is scheduled.
    - `Location`: The physical or virtual location where the tournament takes place.
    - `Players`: List of PlayerIDs who are participating.

- **Relationships:**
    - A Tournament can have many Players.
    - Each Tournament is reflected on one Leaderboard.
    - A Tournament can produce several Scorecards.

### Leaderboard

- **Attributes:**
    - `LeaderboardID`: Unique identifier for each leaderboard.
    - `TournamentID`: Foreign key linking to the Tournament entity.
    - `Scores`: Stores the mapping of PlayerIDs to their scores and points.

- **Relationships:**
    - Every Leaderboard belongs to one specific Tournament.

### Scorecard

- **Attributes:**
    - `ScorecardID`: Unique identifier for each scorecard.
    - `PlayerID`: Foreign key linking to the Player entity.
    - `TournamentID`: Foreign key linking to the Tournament entity.
    - `Scores`: List of scores per hole.
    - `TotalScore`: Cumulative total score for the player.

- **Relationships:**
    - Each Scorecard is associated with one Player.
    - Each Scorecard is tied to one specific Tournament.

### PlayerProfile

- **Attributes:**
    - `ProfileID`: Unique identifier for each player profile.
    - `PlayerID`: Foreign key linking to the Player entity.
    - `Name`: Full player name.
    - `Age`: Player’s age.
    - `Handicap`: Handicap score of the player.

- **Relationships:**
    - Each Player is linked to one PlayerProfile.