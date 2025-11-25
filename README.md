Music Listener Churn & Subscription Retention – SQL & Python Project
This project analyzes a music streaming platform to understand listener behavior, churn risk, and subscription retention using SQL and Python (Jupyter Notebook).
It simulates a real-world music business database with users, songs, subscriptions, and listening history, then uses 50+ SQL queries plus Python analysis to answer business questions like:
1) Who are the most engaged users?
2) How are users listening over time?
3) Which songs and artists perform best?
4) How can we detect churn risk and inactive users? 

Listener Churn & Subscription R…
Project Structure
Music_Business_SQL_Analytics
│
├── Listener Churn & Subscription Retention.sql   # All SQL queries for analysis
├── LCPRA.ipynb                                   # Python notebook (EDA & visualizations)
└── README.md                                     # Project documentation

Problem Statement;-
Online music platforms want to retain paying subscribers and reduce churn.
Using a relational database for a fictional music business, this project:
1) Tracks who listens to what, when, and how long
2) Differentiates active vs. inactive users
3) Compares free vs. premium subscribers
4) Measures engagement & skipping behavior
5) Supports churn and retention insights using SQL and Python

Database Design:-
The SQL file works on a database named Music_Business and uses the following core tables: 
a) users:-
   user_id, country, subscription_type, is_active, signup_date, …

b) songs:-
   song_id, title, artist, genre, duration, …

c) subscriptions:-
   subscription_id, user_id, payment_method, auto_renew, start_date, …

d) listening_history:-
   history_id, user_id, song_id, timestamp, duration_played, skipped, …

These tables together capture who the user is, what they listen to, and is are they premium or not.

What the SQL File Covers:-
The file Listener Churn & Subscription Retention.sql includes structured queries grouped by concept: 
Listener Churn & Subscription Retention

1️) Basic Selection & Filtering:-
Select all users, songs, subscriptions, listening history
Filter users by country, subscription_type, is_active
Filter songs by duration, genre, and title patterns

2) Aggregations & Grouping
Users per country
Average song duration per genre
Total listening time per user
Subscriptions
Skipped songs per user

3️) Sorting & Ranking:-
Latest signups
Top 5 users by total listening time
Artists with most songs

4️) Date & Time Analysis:-
Users signed up in the last 30 days
Listening sessions in a specific month
Days since last listening session per user (inactivity metric)

5️) Joins for Business Insights:-
Users with their subscription details (INNER JOIN)
Listening history + song titles
Songs with and without listening history (LEFT JOIN)
Total sessions per song

6️) Window Functions (Advanced SQL):-
Total listening time per user using SUM() OVER()
Session order per user with ROW_NUMBER()
Rank users by total listening time using RANK()
Cumulative listening duration over time
Moving average over last 5 sessions per user

7️) Set Operations & Behavior Segmentation:-
Union of USA users and Premium users
Pop + Rock songs using UNION ALL
Users who did not skip songs and are Premium
Users in India who are not Premium
Users who are active OR Premium
These queries together form a strong SQL portfolio piece showing comfort with:
SELECT, WHERE, GROUP BY, HAVING
JOINs
Window functions (OVER, ROW_NUMBER, RANK)
Date functions and business logic
Simulated churn & retention metrics

What the Python Notebook (LCPRA.ipynb) includes:-
The notebook LCPRA.ipynb is used for:
Loading query outputs / CSV exports (e.g., from the above SQL)
Doing additional Exploratory Data Analysis (EDA) in Python
Creating visualizations such as:
Distribution of active vs inactive users
Listening time per subscription type
Skipped vs non-skipped sessions
Country-wise user and revenue potential trends
Optionally preparing simple ML-ready features for churn prediction (if added later)
This combination of SQL + Python + visualizations makes the project excellent for a Data Analyst / Data Science resume.

Tech Stack
Tool / Technology	Usage
MySQL / SQL	Database, queries, window functions
Python	Data analysis and visualization
Jupyter Notebook	Running EDA & charts
Pandas / NumPy	Data handling (if used in notebook)
Matplotlib / Seaborn	Visualizations & plots

How to Run the Project:-
a) Set Up the Database
   Open MySQL Workbench / MySQL CLI

b) Run the SQL file:-
   SOURCE path/to/"Listener Churn & Subscription Retention.sql";
   or copy–paste sections into your SQL editor and run them step by step.
   This will:
      Create the Music_Business database (if included in your script)
      Run all queries for analysis and insights
      You can turn key queries into views or export results to CSV for Python.

c) Run the Python Notebook:-
  Open Jupyter Notebook or VS Code
  Launch the LCPRA.ipynb notebook
  Run the cells in order to:
  Load exported data / connect to the database
  Perform EDA
  Generate charts for churn & retention metrics

Key Learnings:-
By browsing this project, a reviewer can see that you:
Understand relational database design for a business use case
Can write clean SQL from beginner to advanced (window functions, joins, date logic)
Know how to convert raw tables into churn and retention insights
Can combine SQL + Python for end-to-end analysis and visualization

📌 Possible Extensions (Future Work):-
Build a small churn prediction model (logistic regression / tree-based model)
Add Dash/Streamlit dashboard for business stakeholders

Include KPIs like:
Monthly Active Users (MAU)
Retention rate
Churn rate
Average Revenue Per User (ARPU)**
