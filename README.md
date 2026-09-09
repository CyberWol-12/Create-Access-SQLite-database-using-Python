# 🗄️ Chicago Data Analysis Using Python & SQLite

<p align="center">

### 📊 SQL-Based Data Analysis Project

**Exploring Crime, Public Schools & Socioeconomic Data in Chicago**

</p>

---

## 📊 Project Overview

This project demonstrates how Python, Pandas, SQLite, and SQL can be used together to build a structured data analysis workflow.

The project integrates three Chicago datasets:

- 🏙️ Chicago Census Data
- 🏫 Chicago Public Schools Data
- 🚨 Chicago Crime Data

The datasets are loaded using Pandas and stored inside a SQLite database. SQL queries are then used to investigate crime patterns, socioeconomic conditions, school-related incidents, and community-level characteristics.

The project focuses on transforming raw datasets into structured database tables and extracting meaningful information using SQL.

---

## 🎯 Objectives

The main objectives of this project are:

- Create and manage a SQLite database using Python
- Load CSV datasets into Pandas DataFrames
- Store DataFrames as relational database tables
- Connect Python with SQLite
- Execute SQL queries using Jupyter Notebook
- Analyze Chicago crime records
- Identify communities with lower per-capita income
- Analyze crime involving minors and children
- Identify crime types recorded at schools
- Explore school-related database attributes
- Analyze socioeconomic characteristics of Chicago communities
- Practice real-world SQL data analysis techniques

---

## 🗂️ Dataset

The project uses three datasets:

### 1. 🏙️ Chicago Census Data

Contains socioeconomic information about Chicago community areas.

Important attributes include:

- `COMMUNITY_AREA_NUMBER`
- `COMMUNITY_AREA_NAME`
- `PERCENT_OF_HOUSING_CROWDED`
- `PERCENT_HOUSEHOLDS_BELOW_POVERTY`
- `PERCENT_AGED_16__UNEMPLOYED`
- `PERCENT_AGED_25__WITHOUT_HIGH_SCHOOL_DIPLOMA`
- `PERCENT_AGED_UNDER_18_OR_OVER_64`
- `PER_CAPITA_INCOME`
- `HARDSHIP_INDEX`

### 2. 🏫 Chicago Public Schools Data

Contains information about Chicago public schools.

Important attributes include:

- `School_ID`
- `NAME_OF_SCHOOL`
- `Elementary, Middle, or High School`
- `SAFETY_SCORE`
- `Environment_Score`
- `Instruction_Score`
- `Leaders_Score`
- `AVERAGE_STUDENT_ATTENDANCE`
- `Average_Teacher_Attendance`
- `COMMUNITY_AREA_NUMBER`
- `COMMUNITY_AREA_NAME`

### 3. 🚨 Chicago Crime Data

Contains crime records and related information.

Important attributes include:

- `ID`
- `CASE_NUMBER`
- `DATE`
- `BLOCK`
- `IUCR`
- `PRIMARY_TYPE`
- `DESCRIPTION`
- `LOCATION_DESCRIPTION`
- `ARREST`
- `DOMESTIC`
- `BEAT`
- `DISTRICT`
- `WARD`
- `COMMUNITY_AREA_NUMBER`
- `YEAR`
- `LATITUDE`
- `LONGITUDE`
- `LOCATION`

---

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| 🐍 Python | Data processing and database integration |
| 🐼 Pandas | Data loading and DataFrame manipulation |
| 🗄️ SQLite | Relational database management |
| 🔎 SQL | Data querying and analysis |
| 📓 Jupyter Notebook | Interactive analysis environment |
| 📋 PrettyTable | SQL result formatting |
| 🔗 IPython-SQL | Executing SQL directly inside Jupyter |

---

## 🔄 Workflow

```text
Raw CSV Datasets
       ↓
Load Data using Pandas
       ↓
Create SQLite Database
       ↓
Create Database Tables
       ↓
Connect SQLite with Jupyter
       ↓
Execute SQL Queries
       ↓
Analyze Results
       ↓
Extract Business & Socioeconomic Insights
       ↓
Document Results

---

## 🗄️ Database Architecture

The project uses a SQLite database named:

`FinalDB.db`

The database contains three main tables:

```text
FinalDB.db
│
├── CENSUS_DATA
│
├── CHICAGO_PUBLIC_SCHOOLS
│
└── CHICAGO_CRIME_DATA

👩‍💻 About Me

Hi, I'm Divya Upadhyay, a final-year B.Tech Computer Science student specializing in Artificial Intelligence.

I am passionate about building practical projects in:

Data Science
Machine Learning
Artificial Intelligence
Data Analytics
Python
SQL
Database Management

I enjoy working with real-world datasets and transforming raw data into meaningful insights using programming, statistics, SQL, and machine learning techniques.

I am continuously building projects and strengthening my technical skills to pursue opportunities in Data Science, Machine Learning, and AI.

📬 Connect With Me
💻 GitHub

GitHub Profile

💼 LinkedIn

LinkedIn Profile

📧 Email

divyau0802@gmail.com

⭐ Conclusion

The Chicago Data Analysis Using Python & SQLite project demonstrates a complete workflow for working with structured public datasets.

By combining Python, Pandas, SQLite, and SQL, the project transforms raw Chicago datasets into a relational database and uses SQL queries to investigate crime, socioeconomic conditions, community characteristics, and school-related information.

This project demonstrates practical skills in data analysis, SQL, database management, Python programming, and analytical problem solving.

⭐ If You Found This Project Useful

If you found this project useful or interesting, feel free to:

⭐ Star the repository
👀 Explore the notebook
💬 Connect with me
🤝 Collaborate on data science projects
<p align="center">
🐍 Python • 🐼 Pandas • 🗄️ SQLite • 🔎 SQL • 📊 Data Analysis

Built with curiosity, data, and code. 🚀

</p> ```