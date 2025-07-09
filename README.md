Project Overview
This project involves building a relational database to store information about World Cup games from 2014 onwards. It covers creating the database schema, populating it with data from a CSV file, and then querying that data to answer specific questions about the tournament.

The core components are:

A PostgreSQL database (worldcup).

Two tables: teams (to store unique team names) and games (to store game details).

A bash script (insert_data.sh) to parse game data and insert it into the database, handling team relationships.

A bash script (queries.sh) to run various analytical queries against the populated database.

Features
Database Design: Normalized schema with teams and games tables, linked by foreign keys.

Data Import: Efficiently imports data from games.csv into the database.

Dynamic ID Assignment: Automatically assigns team_id from the teams table to winner_id and opponent_id in the games table, avoiding hardcoding.

Data Integrity: Utilizes PRIMARY KEY, FOREIGN KEY, UNIQUE, and NOT NULL constraints to maintain data quality.

Comprehensive Queries: Demonstrates various SQL query types, including:

Aggregate functions (SUM, AVG, MAX, COUNT).

JOIN operations (INNER JOIN, LEFT JOIN).

WHERE clauses for filtering.

DISTINCT for unique results.

UNION for combining query results.

ORDER BY for sorting.

Database Schema
The database consists of two tables:

teams

team_id: SERIAL (Primary Key, auto-incrementing), NOT NULL

name: VARCHAR(255), UNIQUE, NOT NULL

games

game_id: SERIAL (Primary Key, auto-incrementing), NOT NULL

year: INT, NOT NULL

round: VARCHAR(50), NOT NULL

winner_id: INT, NOT NULL (Foreign Key referencing teams.team_id)

opponent_id: INT, NOT NULL (Foreign Key referencing teams.team_id)

winner_goals: INT, NOT NULL

opponent_goals: INT, NOT NULL

Files Included
games.csv: The raw data file containing World Cup game information.

insert_data.sh: Bash script to create and populate the database.

queries.sh: Bash script containing SQL queries to extract data.

expected_output.txt: The expected output for the queries.sh script.

worldcup.sql: A database dump file containing the SQL commands to recreate the database structure and data. (Generated after project completion).

README.md: This file.

How to Set Up and Run
This project is typically run within a Linux environment with PostgreSQL installed, such as a freeCodeCamp virtual machine or Gitpod.

Prerequisites
PostgreSQL installed and running.

Bash shell.

psql client installed and accessible.
