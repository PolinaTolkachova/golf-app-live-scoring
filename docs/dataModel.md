# Data model

## Key Entities and Attributes

### 1. User
- **Attributes:**
    - UserID (Primary Key)
    - Username
    - PasswordHash
    - Email
    - Role (Player, Administrator)
    - RegisteredDate

### 2. Player
- **Attributes:**
    - PlayerID (Primary Key, Foreign Key from User)
    - Name
    - Handicap
    - Sex
    - Email
    - Phone
    - Picture

### 3. Tournament
- **Attributes:**
    - TournamentID (Primary Key)
    - Name
    - StartDate
    - EndDate
    - Description

### 4. Course
- **Attributes:**
    - CourseID (Primary Key)
    - Name
    - Location

### 5. Hole
- **Attributes:**
    - HoleID (Primary Key)
    - HoleNumber
    - Par
    - Stroke Index
    - Tees

### 6. Tee
- **Attributes:**
    - Color
    - Length

### 7. Score
- **Attributes:**
    - ScoreID (Primary Key)
    - PlayerID (Foreign Key)
    - TournamentID (Foreign Key)
    - HoleID (Foreign Key)
    - ScoreValue
    - Timestamp

### 8. Leaderboard
- **Attributes:**
    - LeaderboardID (Primary Key)
    - TournamentID (Foreign Key)
    - PlayerID (Foreign Key)
    - Rank

## Relationships

- **User to Player:** One-to-One
    - A user may have a single player profile.

- **Tournament to Course:** One-to-One
    - Each tournament is conducted on one course.

- **Course to Hole:** One-to-Many
    - Each course consists of multiple holes.

- **Tournament to Score:** One-to-Many
    - Each tournament has multiple scores, one per hole for each player.

- **Player to Score:** One-to-Many
    - Players can have multiple scores, one per hole during tournaments.

- **Hole to Score:** One-to-Many
    - Each hole can have multiple scores, one per player.

- **Tournament to Leaderboard:** One-to-One
    - Each tournament has one leaderboard.

- **Player to Leaderboard:** Many-to-One
    - Each player appears once in each tournament's leaderboard.