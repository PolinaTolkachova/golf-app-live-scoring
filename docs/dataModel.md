# Data model


[Entities and Attributes](#entities-and-attributes)
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
    - `UserID`: Unique identifier for the user.
    - `Username`: Login name of the user.
    - `Password`: User's password (hashed).
    - `Email`: User's email address.
    - `Role`: Specifies if the user is a regular user, admin, or player.
- **Relationships:**
    - One User can be associated with one PlayerProfile.

### Administrator

- **Attributes:**
    - `AdminID`: Unique identifier for the administrator.
    - `UserID`: Foreign key linking to User entity.
- **Relationships:**
    - One Administrator can manage multiple players and tournaments.

### Player

- **Attributes:**
    - `PlayerID`: Unique identifier for the player.
    - `UserID`: Foreign key linking to User entity.
    - `TournamentIDs`: List of tournaments the player is part of.
- **Relationships:**
    - Many Players can participate in many Tournaments.
    - One Player has one Scorecard per Tournament.

### Tournament

- **Attributes:**
    - `TournamentID`: Unique identifier for the tournament.
    - `Name`: Name of the tournament.
    - `Date`: Scheduled date for the tournament.
    - `Location`: Physical or virtual location of the tournament.
    - `Players`: List of PlayerIDs participating.
- **Relationships:**
    - One Tournament has many Players.
    - One Tournament is featured on one Leaderboard.
    - One Tournament can have multiple Scorecards.

### Leaderboard

- **Attributes:**
    - `LeaderboardID`: Unique identifier for the leaderboard.
    - `TournamentID`: Foreign key linking to Tournament entity.
    - `Scores`: Mapping of PlayerID to their scores and points.
- **Relationships:**
    - One Leaderboard belongs to one Tournament.

### Scorecard

- **Attributes:**
    - `ScorecardID`: Unique identifier for the scorecard.
    - `PlayerID`: Foreign key linking to Player entity.
    - `TournamentID`: Foreign key linking to Tournament entity.
    - `Scores`: List of scores per hole.
    - `TotalScore`: Calculated total score.
- **Relationships:**
    - One Scorecard belongs to one Player.
    - One Scorecard is associated with one Tournament.

### PlayerProfile

- **Attributes:**
    - `ProfileID`: Unique identifier for the player profile.
    - `PlayerID`: Foreign key linking to Player entity.
    - `Name`: Full name of the player.
    - `Age`: Age of the player.
    - `Handicap`: Player's handicap score.
- **Relationships:**
    - One Player has one PlayerProfile.