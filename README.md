# SearchBarDemo
There's a copy of this demo under the NotesOnTextTasks repo I have, but this is a more complete and modular demo. 

The search bar feature comes up in basically every application. Think about the Google Search home page, Ask Jeeves, Bing; these are all search bar and go button. Shazam, Spotify, YouTube, Social media pages, all have search bars -- shazam and spotify in particular though Hash a set of features that they pull from audio file spectrograms. So your SQL database is more useful the more creative you get with the tags.

This is just a simple demo to wrap my head around this thing for other applications. 

1. Wordcheck.py: asynchronously read text files of books downloaded from wikisouce (HTTP requests are a different thing and they have a bot checker for this one. wikipedia has a REST API though). The book directory path is stored in an environement variable. The DataEntry class works as a data structure to hold the file line id, the text sample, matching word set from the sample, and a timestamp. The time stamp increments artificially to simulate different times of text message generation / logging. It outputs an SQLite3 database file, and a JSON file for a human readable format. Wordlist is hardcoded, and it would be better to hash the wordset matches instead of saving the list wordset. 

2. main.html : website layout for the search bar. references script.js, and style.css

3. style.css : stores styles to make the website look nice.

4. script.js :  defines search bar + button functionality, and sends http requests to the server 

5. TextServer.py : FastAPI server to serve the UI at the same time as call SQLite commands to search through the database and respond to http requests. Doesn't have a CORS policy to allow all IP adresses, so right now it's just a local app. This set up is inspired by the NanoChat demo  https://github.com/karpathy/nanochat

# Wordlist 
this is an arbitrary word list that can be entered into the search bar. 

'love', 'passion', 'faith', 'war'
'time','seconds', 'minutes', 'days', 'weeks',
'months', 'years', 'hours', 
'mind', 'mental', 'memory', 'memories',
'think', 'thinking', 'thought', 'thoughts',
'prayers', 'pray', 'prayed', 'meditate',
'soul', 'spirit', 'dream', 
'body', 'bodies', 'blood', 'guts', 'spit', 
'vomit', 'excrement', 'soiled',
'eyes', 'mouth', 'nose', 'ears', 'hands',
'hand', 'fingers', 'finger', 'feet', 'toes',
'heart', 'stomach', 'nerve', 'nervous',
'neck', 'chest', 'breast', 'shoulders',
'kill', 'killed','murder',
'death', 'died', 'dead',
'drunk', 'drink', 
'drinking', 'smoking', 
'gambling', 'gamble','gambler', 'alcoholic',
'habit', 'drug', 'drugs','opium', 'cocaine',
'family','father', 'mother', 'brother', 'sister',
'aunt', 'uncle', 'cousin', 'son', 'daughter', 