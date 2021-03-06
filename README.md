# Wie-is-het
This is the repository with the code for the wie-is-het experiment at Night University.

## Requirements
The code runs with the packages in the reqs.txt file. Make sure to have the right versions (in particular the sanic package) We used python 3.8 and run the program in Windows using pycharm.

## Frontend
We have used the chatroom by scalable minds as a frontend for our bots (https://github.com/scalableminds/chatroom). The next things we changed on the front-end side:
- Title (to: Professor Betweter or Betweter in opleiding)
- Welcome message (to: Hallo ik ben Professor Betweter! Begin het gesprek door hallo te zeggen! or Hallo ik ben Betweter in opleiding. Begin het gesprek door hallo te zeggen!)
- QueuedMessageInterval (to 1500 from 800)
- Font-family (to: Arial, Helvetica, sans-serif)

## How to install the bots
We have two different versions of the bots. One can be found in the "expert" directory and the other one in the "leek" directory. Both can be installed in the same way.
We use sqlite3 to save the data to a database. Download sqlite3 command line tools from: https://www.sqlite.org/download.html 
We use Django to make a connection between the bot and the frontend.

Make a database in the correct folder (the betweter folder in both directories). 
```
sqlite3 betweter.db
```
Install and download Dutch spacy packages.

```
pip install spacy
python -m spacy donwload nl_core_news_sm
```

Train a rasa model:
```
rasa train
```
Finally, run the bot and the server:
```
rasa run -m models --enable-api --cors "*"
python manage.py runserver
```

