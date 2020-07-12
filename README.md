# Project Overview

The idea of the project is to analysis the activity on a music app by artists, songs, users over time. We do so using a star schema data warehouse architecture with dimensions: artists, songs, users, time with facts being the activity by the user of playing songs from the app.

#Setting up your environment for the project

##Prerequisites
- postgres: if not pre-installed, download [here](https://www.postgresql.org/download/){:target="_blank"}

##Getting started
```
$ git clone https://github.com/pranavdixit8/data-modeling-with-postgres.git
$ virtualenv dend-project1
$ source dend-project1/bin/activate
$ pip install -r requirements.txt 
$ ipython kernel install --user --name dend-project1 
```
Note: Use the kernel ***dend-project1*** while using jupyter notebook

##Commands

>Create the database and tables.
```
$ python create_table.py
```
 
>perform etl and insert data into tables
```
$ python etl.py
```

# Files

 - ***create_tables.py***: this file creates the database and the tables (fact and dimension table of the star schema), it uses the file: *sql_queries*.
 - ***etl.py***: this file execute the etl process for our project: loading the files in dataframes, modifying the data and inserting the data in the tables.
 - ***sql_queries.py***: this file contain all the sql queries for creating, inserting, and droping the tables in the database and required selection query for our design
 - ***test.ipynb***: thid is the jupyter notebook to test if the table were created as expected and values inserted into the table.
 - ***etl.ipynb***: this jupyter notebook involves loading a single file into the database before moving to load all the files in the database.





# Design


![](Sparkify%20Data%20warehouse%20ER%20Diagram.png)

### Fact Table

 - ***songplays***: 
 > Columns: songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
 > >
 > Primary key: songplay_id

### Dimension Tables

 - ***artists***:
 > Columns : artist_id, name, location, latitude, longitude
 > >
 >Primary key : artist_id
 
 - ***songs***:
 > Columns: song_id, title, artist_id, year, duration
 > >
 > >Primary key: song_id
 
 - ***users***:
 > Columns: user_id, first_name, last_name, gender, level
 > >
 > Primary key: user_id
 
 - ***time***:
 > Columns: start_time, hour, day, week, month, year, weekday
 > >
 Primary key: start_time
 

 
 