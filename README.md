# MMM General Architecture

SQLite DB -> Server Side Code -> Front End Code

## User

POST signup:  
username, password, email, grade

POST signin:  
same data as signup, sets cookie for auth

POST bracket:  
send the bracket predictions

GET bracket:  
get the bracket predictions, and score. Response in JSON

GET leaderboard:  
get all the people, ranked and broken down by grade. Response in JSON

## Admin

POST update_bracket:  
update for the new match result. Request w/ JSON

POST new_bracket:  
a new march mammal madness season. Request w/ JSON
