# MMM General Architecture

SQLite DB -> Server Side Code -> Front End Code

## Bracket JSON

The Bracket JSON will look like the example below. It'll just be the selections, since name data is handed by Cookies with our login system.

{
"Round 1": ["Animal 1", "Animal 2", "Animal 3", "Animal 4"],
"Round 2": ["Animal 1", "Animal 2", "Animal 3", "Animal 4"],
"Round 3": ["Animal 1", "Animal 2", "Animal 3", "Animal 4"],
"Round 4": ["Animal 1", "Animal 2", "Animal 3", "Animal 4"],
"Round 5": ["Animal 1", "Animal 2", "Animal 3", "Animal 4"],
"Champion": "Animal 8",
"Wild Card": "Animal 10"
}

## User

POST signup:  
username, password, email, grade

POST signin:  
same data as signup, sets cookie for auth

POST bracket:  
send the bracket predictions
send the Bracket JSON

GET bracket:  
get the bracket predictions, and score. Response in JSON
response will be Bracket JSON

GET leaderboard:  
get all the people, ranked and broken down by grade. Response in JSON
leaderboard is updated each time the bracket is updated
JSON will be an array of objects, with each object having a name, grade, and score. Like `[{"name":"Sam","grade":12,"score":10000},{"name":"Tiffany","grade":11,"score":1}]`

## Admin

POST update_bracket:  
update for the new match result. Request w/ JSON
the players brackets will be scored each time it's updated, and that score will be stored in the DB
JSON will be Bracket JSON

POST new_bracket:  
a new march mammal madness season. Request w/ JSON
JSON will be a 64 length array with each animal name, like `["bear","cat","donkey"]` but longer
