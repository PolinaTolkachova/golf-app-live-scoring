### Use Case: View Tournaments (User)

**Primary Actor:** User

**Preconditions:** None

**Trigger:** User navigates to the tournaments page.

**Main Success Scenario:**
1. User accesses the tournaments page.
2. User views a list of all tournaments.
3. User selects a particular tournament to view.
4. User views participants in the selected tournament.
5. User views players divided by groups within the tournament.
6. User views scorecards of players.
7. User views total scores and individual hole scores.

### Use Case: View Leaderboard (User)

**Primary Actor:** User

**Preconditions:** None

**Trigger:** User navigates to the leaderboard page.

**Main Success Scenario:**
1. User accesses the leaderboard page for a tournament.
2. User views the list of all players in the tournament.
3. User views scorecards within the tournament.
4. User sees real-time updates of scores, points, and rankings.

### Use Case: Registration (User)

**Primary Actor:** User

**Preconditions:** None

**Trigger:** User navigates to the registration page.

**Main Success Scenario:**
1. User accesses the registration page.
2. User fills out the registration form.
3. User submits registration information.
4. System confirms registration and provides login credentials.

### Use Case: Login (User)

**Primary Actor:** User

**Preconditions:** User is registered.

**Trigger:** User navigates to the login page.

**Main Success Scenario:**
1. User accesses the login page.
2. User inputs valid credentials.
3. System authenticates the user.
4. User gains access to the application.

### Use Case: View Players' Profiles (Administrator)

**Primary Actor:** Administrator

**Preconditions:** Administrator is logged in.

**Trigger:** Administrator navigates to the players' page.

**Main Success Scenario:**
1. Administrator accesses the players' page.
2. Administrator views a list of all registered players.

### Use Case: Manage Players' Profiles (Administrator)

**Primary Actor:** Administrator

**Preconditions:** Administrator is logged in.

**Trigger:** Administrator navigates to the edit player page.

**Main Success Scenario:**
1. Administrator accesses the edit player page.
2. Administrator adds a new player.
3. Administrator edits a player's profile.
4. Administrator removes a player.

### Use Case: Manage Players for Tournaments (Administrator)

**Primary Actor:** Administrator

**Preconditions:** Administrator is logged in.

**Trigger:** Administrator navigates to the edit tournament page.

**Main Success Scenario:**
1. Administrator accesses the edit tournament page.
2. Administrator adds players to a tournament.
3. Administrator edits player details for a tournament.
4. Administrator removes players from a tournament.
5. Administrator manages players' scores and scorecards.

### Use Case: Manage Tournament (Administrator)

**Primary Actor:** Administrator

**Preconditions:** Administrator is logged in.

**Trigger:** Administrator navigates to the tournaments page.

**Main Success Scenario:**
1. Administrator accesses the tournaments page.
2. Administrator views all tournaments.
3. Administrator adds a new tournament.
4. Administrator edits tournament details.
5. Administrator removes a tournament.

### Use Case: Enter Tournament Scores (Player)

**Primary Actor:** Player

**Preconditions:** Player is logged in and part of a tournament.

**Trigger:** Player participates in an active tournament.

1. The player selects the active tournament.
2. The player inputs a score for a hole.
3. The player submits the score.

**Extension:**
- Player edits scores before the round is finalized.