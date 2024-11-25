# Use Case Scenarios

## Use Case 1: Player Enters Score for a Hole

### Actors
- **Player**

### Preconditions
- Player is registered and logged into the application.
- The tournament is active, and the player is on the course.

### Main Success Scenario
1. Player logs into the application using their credentials.
2. Navigates to the "Enter Score" section for the ongoing tournament.
3. Selects their name or unique player ID from the list of participants.
4. Chooses the current hole they have completed.
5. Inputs the score for the selected hole.
6. Submits the score.
7. System validates and stores the score in the database.
8. Updated score is broadcast in real time to the tournament leaderboard and other users.

### Postconditions
- Player's score for the specific hole is recorded and visible in the live leaderboard.
- All authorized users have access to the updated scoring information.

## Use Case 2: View Personal Scorecard

### Actors
- **Player**

### Preconditions
- Player is participating in the tournament and has scores recorded for some holes.

### Main Success Scenario
1. Player logs into the application.
2. Navigates to their personal scorecard within the tournament dashboard.
3. Views scores entered for completed holes and the total score summary.

### Postconditions
- Player has full visibility of their performance in the tournament.

## Use Case 3: Edit Score

### Actors
- **Player**

### Preconditions
- Player has already entered scores.
- The tournament rules allow score editing before a round is officially closed.

### Main Success Scenario
1. Player accesses their personal scorecard.
2. Identifies a score that needs correction and selects it.
3. Edits the score for the specified hole.
4. Re-submits the amended score.
5. System updates the score and reflects changes in real time on the leaderboard and other related statistics.

### Postconditions
- The player's score is updated within the permissible time frame, and accuracy is maintained in tournament records.