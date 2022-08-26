# Disaster-Message-Classification

## Packages
  - Pandas
  - Numpy
  - ScikitLearn
  - Nltk
  - Sqlite3
  - Sqlalchemy
  - Pickle
  - Plotly
  - Json
  - Flask
  Please use python 3.9 and above.
  
## Motivation

The project is an example of real world data science problem and how to solve it with using different data skills, such as data engineering,
data cleaning, natural language processing, machine learning as well as model deployment with Flask.
The problem I solved is classify the messages sent during a disaster event by this means it can be prioritized and be actioned based on the urgency.
I've created an ETL pipeline to process the data and export it into a relational database. Later I used the data retrieved from database and created
a machine learning pipeline to train the data and create a classification model. Finally deployed the model as a web app using the Flask.

## File Description

app
  - templates
    - go.html       # html for message classification
    - master.html   # main html page with the visuals
  - run.py          # python file for running the flask app

data
  - disaster_categories.csv     # csv file including categories
  - disaster_messages.csv       # csv file including messages
  - DisasterResponse.db         # db created after running process_data.py
  - process_data.py             # python file to process the data and load into db
  
models
  - train_classifier.py     # python file to train the data and create the model
  - classifier.pkl          # pickle file including saved model
  
  
  
  
  
  
## How to run the app:


1. After cloning the repository go to root directory and type;
"python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db"
This will run the ETL pipeline to process the data and load it into DisasterResponse.db

2. Later type; "python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl"
This will run the machine learning pipeline to create the model and saved it as classifier.pkl
It will approximately take 20 min to create the model.

3. Finally run this command "python app/run.py" to run the Flask app
The app will be running on http://127.0.0.1:3001.
Don't hesitate to type couple of messages to test the app if it classifies the messages good enough!


## Thank you

Thanks to udacity guiding along the way completing the project.
