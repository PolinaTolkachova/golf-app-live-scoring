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
    - `Start date`: Date on which the tournament is started.
    - `Finish date`: Date on which the tournament is finished.
    - `Players`: List of PlayerIDs who are participating.
    - `Format`: Format of the tournament (Individual, Team).
    - `Group`: Players group (Men HCP0-12, Men HCP 12.1-24, Men HCP 24.1-36, Women HCP 0-24, Women HCP 24.1-36).
    - `Scoring type`: Scoring type for calculation the tournament results. 

- **Relationships:**
    - A Tournament can have many Players.
    - Each Tournament is reflected on one Leaderboard.

### Leaderboard

- **Attributes:**
    - `LeaderboardID`: Unique identifier for each leaderboard.
    - `TournamentID`: Foreign key linking to the Tournament entity.

- **Relationships:**
    - Every Leaderboard belongs to one specific Tournament.

### Scorecard

- **Attributes:**
    - `ScorecardID`: Unique identifier for each scorecard.
    - `PlayerIDs`: List of foreign keys linking to the Player entities. 
    - `TournamentID`: Foreign key linking to the Tournament entity.
    - `Scores`: List of scores per hole.
    - `TotalScore`: Cumulative total score for the player.

- **Relationships:**
    - Each Scorecard is associated with one Player or one Team.
    - Each Scorecard is tied to one specific Tournament.

### PlayerProfile

- **Attributes:**
    - `ProfileID`: Unique identifier for each player profile.
    - `PlayerID`: Foreign key linking to the Player entity.
    - `Name`: Player's name.
    - `Surname`: Player's surname.
    - `Gender`: Player’s gender (Female, Male).
    - `Handicap`: Player's handicap.

- **Relationships:**
    - Each Player is linked to one PlayerProfile.