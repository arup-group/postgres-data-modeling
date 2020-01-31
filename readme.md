# Sparkify song database

The purpose of this database is to store song, artist and user log records for a startup called Sparkify that provides music streaming services. Data is first extracted from raw JSON files and subsequently transformed and loaded into a PostgreSQL database. The database is designed with the intent of enabling and facilitating data analytics for exploring user activity and behavior.

## Schema
The design of the database follows a star schema in order to optimize queries for data analysis. This includes the following tables and their respective attributes:

Fact Table

    songplays: songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

Dimension Tables

    users: user_id, first_name, last_name, gender, level
    songs: song_id, title, artist_id, year, duration
    artists: artist_id, name, location, latitude, longitude
    time: start_time, hour, day, week, month, year, weekday


## Files
create_tables.py - Drops and creates tables in the schema from scratch. Run this file to reset the tables before each time the ETL script is run.

etl.ipynb - Reads and processes a single file from song_data and log_data and loads the data into the tables. This notebook contains detailed instructions on the ETL process for each of the tables.

etl.py - Reads and processes all files from song_data and log_data and loads them into the tables.

sql_queries.py - Contains all the sql queries for ETL, and is imported into the last three files above.

test.ipynb - Displays the first few rows of each table for testing purposes.

## Usage

1. Run create_tables.py to create the schema
2. Run etl.py to extract, tranform and load data into the database
