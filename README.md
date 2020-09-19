# etl_project

# Group Members

Troy Ramsey, Justan Plumlee, Hermela Mekonnen, Daren Hamilton, Elaine Hamilton

# Data sets

We are working with the two soccer data sets below to create a broad picture between Fifa and English Premier League stats for 2020.

- https://www.kaggle.com/sagunsh/fifa-20-complete-player-dataset
- https://www.kaggle.com/idoyo92/epl-stats-20192020?select=players_1920_fin.csv

The connecting piece, or join, between the two data sets.

- fifa.name and epl.full

# Modules Needed

- pandas
- create_engine (sqlalchemy)
- re (regex)
- psycopg2

# Steps

- Edit configEDIT.py to include your postgres master pass and rename file to config.py
- Start pgadmin
- Run jupyter notebook file ETL_project
    - Database will be created automatically in postgres when ETL_project.ipynb is run.
    - Dataframes will also be automatically be exported to the created database.
- Run sample query which will join both epl and fifa tables then select all data from both; verifying integrity of data.

# Data Exploration

- Reformed CSVs into dataframes containing only the columns we wanted.
- 'full' and 'name' are the primary key columns in both tables which contain the full names of the players in both leagues.
- EPL data was grouped and summed by player name.
- Characters in the 'full' and 'name' columns did not encode properly which created random characters in the CSV files being used. To resolve this issue we utilized regex to find and alter the names to match in both tables.
- We also had to rename the columns to be lower case due to postgres not accepting capitlization.

# Database (Postgres)

We have decided to utilize a Postgres database because the tables are in columns/rows and express unqiue relationships between player data.

- ERD included