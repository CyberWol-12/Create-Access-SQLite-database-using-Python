````markdown
# 🗄️ Chicago Data Analysis Using Python & SQLite

<p align="center">
  <strong>Python • Pandas • SQLite • SQL • Data Analysis</strong>
</p>

<p align="center">
  A practical data analysis project exploring Chicago crime, public school,
  and socioeconomic datasets using Python and SQL.
</p>

---

## 📌 Project Overview

This project demonstrates a practical **data analysis and database management workflow** using Python, Pandas, SQLite, and SQL.

Three Chicago public datasets are processed and analyzed:

- **Chicago Census Data** — socioeconomic and community-level information
- **Chicago Public Schools Data** — school characteristics and performance-related information
- **Chicago Crime Data** — crime records and incident details

The datasets are loaded using **Pandas**, structured into a **SQLite database**, and analyzed using SQL queries to answer real-world analytical questions.

### Project Workflow

**Data Loading → Database Creation → SQL Analysis → Results → Insights**

---

## 🎯 Objectives

The main objectives of this project are to:

- Create and manage a SQLite database using Python
- Load CSV datasets into Pandas DataFrames
- Convert DataFrames into relational database tables
- Connect Python with SQLite
- Execute SQL queries from a Jupyter Notebook
- Analyze Chicago crime records
- Identify communities with lower per-capita income
- Analyze crimes involving minors and children
- Identify crime types recorded at schools
- Explore socioeconomic characteristics of Chicago communities
- Practice real-world SQL data analysis techniques

---

## 🗂️ Datasets

### 1. Chicago Census Data

The Census dataset contains socioeconomic and demographic information about Chicago communities.

**Key attributes include:**

- `COMMUNITY_AREA_NUMBER`
- `COMMUNITY_AREA_NAME`
- `PERCENT_OF_HOUSING_CROWDED`
- `PERCENT_HOUSEHOLDS_BELOW_POVERTY`
- `PERCENT_AGED_16__UNEMPLOYED`
- `PERCENT_AGED_25__WITHOUT_HIGH_SCHOOL_DIPLOMA`
- `PERCENT_AGED_UNDER_18_OR_OVER_64`
- `PER_CAPITA_INCOME`
- `HARDSHIP_INDEX`

### 2. Chicago Public Schools Data

This dataset contains information about Chicago public schools.

**Key attributes include:**

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

### 3. Chicago Crime Data

This dataset contains information about reported crime incidents in Chicago.

**Key attributes include:**

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
| Python | Data processing and database integration |
| Pandas | Data loading and DataFrame manipulation |
| SQLite | Relational database management |
| SQL | Data querying and analysis |
| Jupyter Notebook | Interactive development and analysis |
| PrettyTable | Formatting SQL query results |
| IPython-SQL | Executing SQL queries inside Jupyter |

---

## 🔄 Data Analysis Workflow

```text
Raw CSV Datasets
       │
       ▼
Load Data using Pandas
       │
       ▼
Create SQLite Database
       │
       ▼
Create Database Tables
       │
       ▼
Connect SQLite with Jupyter
       │
       ▼
Execute SQL Queries
       │
       ▼
Analyze Query Results
       │
       ▼
Extract Meaningful Insights
```

---

## 🗄️ Database Architecture

The project uses a SQLite database named:

`FinalDB.db`

The database contains three primary tables:

```text
FinalDB.db
│
├── CENSUS_DATA
├── CHICAGO_PUBLIC_SCHOOLS
└── CHICAGO_CRIME_DATA
```

The tables are created by loading Pandas DataFrames into SQLite using `DataFrame.to_sql()`.

### Python–SQLite Connection

```python
import pandas as pd
import sqlite3
import csv

conn = sqlite3.connect("FinalDB.db")
cur = conn.cursor()
```

---

## 🔎 SQL Analysis

The project uses SQL to answer a series of analytical questions based on the Chicago datasets.

### 1. Total Number of Crimes

**Result:** 533 crime records

```sql
SELECT COUNT(*)
FROM CHICAGO_CRIME_DATA;
```

---

### 2. Communities with Per-Capita Income Below $11,000

The analysis identifies four community areas with a per-capita income below `$11,000`.

| Community Area | Community Number |
|---|---:|
| West Garfield Park | 26 |
| South Lawndale | 30 |
| Fuller Park | 37 |
| Riverdale | 54 |

```sql
SELECT COMMUNITY_AREA_NAME,
       COMMUNITY_AREA_NUMBER
FROM CENSUS_DATA
WHERE PER_CAPITA_INCOME < 11000;
```

---

### 3. Crimes Involving Minors

The query searches crime descriptions containing the term `MINOR`.

**Resulting case numbers:**

- `HL266884`
- `HK238408`

```sql
SELECT CASE_NUMBER
FROM CHICAGO_CRIME_DATA
WHERE DESCRIPTION LIKE '%MINOR%';
```

---

### 4. Kidnapping Crimes Involving a Child

The analysis filters kidnapping records whose descriptions contain the term `CHILD`.

| Case Number | Crime Type | Description |
|---|---|---|
| HN144152 | KIDNAPPING | CHILD ABDUCTION/STRANGER |

```sql
SELECT *
FROM CHICAGO_CRIME_DATA
WHERE PRIMARY_TYPE = 'KIDNAPPING'
AND DESCRIPTION LIKE '%CHILD%';
```

---

### 5. Crime Types Recorded at Schools

The analysis identifies distinct crime categories associated with school locations.

**Crime types identified:**

- BATTERY
- CRIMINAL DAMAGE
- NARCOTICS
- ASSAULT
- CRIMINAL TRESPASS
- PUBLIC PEACE VIOLATION

```sql
SELECT DISTINCT PRIMARY_TYPE
FROM CHICAGO_CRIME_DATA
WHERE LOCATION_DESCRIPTION LIKE '%SCHOOL%';
```

---

### 6. Exploring the School Database Structure

The structure of the `CHICAGO_PUBLIC_SCHOOLS` table is examined using SQLite metadata.

```sql
PRAGMA table_info(CHICAGO_PUBLIC_SCHOOLS);
```

This provides information about the columns and structure of the school database table.

---

## 📈 Key Results

The analysis produced the following results:

- **533** crime records are present in the analyzed crime dataset.
- **4** community areas have a per-capita income below `$11,000`.
- The identified minor-related case numbers are `HL266884` and `HK238408`.
- One child-related kidnapping record was identified: `HN144152`.
- Six distinct crime categories were identified at school locations.
- The SQLite database successfully organizes the three datasets into separate relational tables.

---

## 💡 Key Insights

### Socioeconomic Analysis

The Census dataset provides useful community-level indicators such as:

- Per-capita income
- Poverty
- Unemployment
- Education levels
- Housing conditions
- Hardship index

These variables can be used to understand socioeconomic differences between Chicago communities.

### Crime Analysis

SQL filtering and pattern matching make it possible to isolate specific crime categories and descriptions.

For example:

```sql
WHERE DESCRIPTION LIKE '%MINOR%'
```

can be used to identify records related to minors.

### School-Related Crime Analysis

Using:

```sql
WHERE LOCATION_DESCRIPTION LIKE '%SCHOOL%'
```

allows the analysis to identify different crime categories associated with school locations.

### Database Organization

Storing the datasets in SQLite provides a structured environment for querying and analyzing multiple datasets rather than repeatedly working with raw CSV files.

---

## 🧠 SQL Concepts Demonstrated

This project provides hands-on practice with:

- `SELECT`
- `WHERE`
- `LIKE`
- `DISTINCT`
- `COUNT()`
- `AVG()`
- `MAX()`
- `GROUP BY`
- `ORDER BY`
- `LIMIT`
- Subqueries
- `PRAGMA`
- SQLite metadata
- Filtering
- Aggregation
- Relational data analysis

---

## 🐍 Python Concepts Demonstrated

The project also demonstrates:

- Python programming
- Pandas DataFrames
- CSV data loading
- SQLite database connections
- SQLite cursors
- DataFrame-to-SQL conversion
- SQL execution from Python
- Jupyter Notebook integration

Example:

```python
import pandas as pd
import sqlite3
import csv

conn = sqlite3.connect("FinalDB.db")
cur = conn.cursor()
```

---

## 📸 Screenshots

Screenshots can be added here to demonstrate the project workflow and SQL results.

Recommended screenshots:

```text
screenshots/
├── database-tables.png
├── sql-results.png
├── jupyter-notebook.png
└── database-structure.png
```

Example:

```markdown
![Database Tables](screenshots/database-tables.png)

![SQL Results](screenshots/sql-results.png)

![Jupyter Notebook](screenshots/jupyter-notebook.png)
```

> Replace the placeholder image paths with the actual screenshot files available in the repository.

---

## 📊 Project Presentation

A presentation can be included to provide a visual overview of the project.

Recommended structure:

```text
presentation/
└── Chicago_Data_Analysis_SQL.pptx
```

If the presentation is added to the repository, it can be linked here:

```markdown
[📊 View Project Presentation](presentation/Chicago_Data_Analysis_SQL.pptx)
```

---

## 💻 How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/CyberWol-12/Create-Access-SQLite-database-using-Python.git
```

### 2. Navigate to the Project Directory

```bash
cd Create-Access-SQLite-database-using-Python
```

### 3. Install Required Libraries

```bash
pip install pandas
pip install ipython-sql
pip install prettytable
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 5. Run the Notebook

Open:

```text
final_project.ipynb
```

Run the notebook cells sequentially to reproduce the database creation and analysis.

---

## 📁 Project Structure

```text
Create-Access-SQLite-database-using-Python/
│
├── final_project.ipynb
├── FinalDB.db
├── data/
│   ├── ChicagoCensusData.csv
│   ├── ChicagoPublicSchools.csv
│   └── ChicagoCrimeData.csv
│
├── screenshots/
│   ├── database-tables.png
│   ├── sql-results.png
│   ├── jupyter-notebook.png
│   └── database-structure.png
│
├── presentation/
│   └── Chicago_Data_Analysis_SQL.pptx
│
└── README.md
```

> Update the structure above if the repository contains different folders or filenames.

---

## 🧠 Skills Demonstrated

### Programming

- Python
- Pandas
- Jupyter Notebook

### Database

- SQLite
- Database creation
- Table creation
- Python–SQLite integration
- Relational data management

### SQL

- Data filtering
- Aggregation
- Pattern matching
- Sorting
- Grouping
- Subqueries
- Database metadata
- Analytical querying

### Data Analysis

- Crime data analysis
- Socioeconomic analysis
- Community-level analysis
- School-related data analysis
- Real-world dataset exploration

### Problem Solving

- Translating analytical questions into SQL queries
- Working with multiple datasets
- Structuring data for analysis
- Interpreting query results
- Extracting meaningful information from public datasets

---

## 🚀 Future Improvements

The project can be further extended with:

- Interactive dashboards using Power BI or Tableau
- Data visualizations using Matplotlib or Plotly
- Geographic crime visualization
- Advanced SQL joins across datasets
- Time-series crime analysis
- Deeper school safety analysis
- Socioeconomic comparison dashboards
- Machine Learning-based crime prediction
- Web-based analytical dashboard
- Automated SQL reporting

---

## 🎓 Learning Outcomes

Through this project, I gained practical experience in:

- Creating SQLite databases programmatically
- Working with Pandas DataFrames
- Converting DataFrames into SQL tables
- Writing analytical SQL queries
- Filtering and aggregating real-world data
- Executing SQL inside Jupyter Notebook
- Working with multiple public datasets
- Translating business-style questions into SQL solutions
- Extracting insights from structured data

---

## 👩‍💻 About Me

I'm **Divya Upadhyay**, a final-year **B.Tech Computer Science student specializing in Artificial Intelligence**, with a strong interest in **Data Science, Machine Learning, Artificial Intelligence, and Data Analytics**.

I enjoy working with real-world datasets and building projects that combine programming, data analysis, SQL, and machine learning to solve practical problems.

### Areas of Interest

- Data Science
- Machine Learning
- Artificial Intelligence
- Data Analytics
- Python
- SQL
- Database Management

I am continuously building practical projects and strengthening my technical skills to pursue opportunities in **Data Science, Machine Learning, and AI**.

---

## 📬 Connect With Me

### 💻 GitHub

[GitHub Profile](https://github.com/CyberWol-12)

### 💼 LinkedIn

[LinkedIn Profile](https://www.linkedin.com/in/divya-upadhyay-a77060348)

### 📧 Email

**divyau0802@gmail.com**

---

## ⭐ Conclusion

The **Chicago Data Analysis Using Python & SQLite** project demonstrates an end-to-end approach to working with structured public datasets.

By combining **Python, Pandas, SQLite, and SQL**, the project transforms raw Chicago datasets into structured database tables and uses analytical queries to investigate crime, socioeconomic conditions, community characteristics, and school-related information.

The project demonstrates practical skills in:

- Python Programming
- Pandas
- SQLite
- SQL
- Data Analysis
- Database Management
- Analytical Problem Solving
- Real-World Dataset Analysis

Most importantly, the project demonstrates the ability to translate real-world analytical questions into **structured SQL queries** and extract meaningful information from data.

---

## ⭐ If You Found This Project Useful

If you found this project interesting or useful:

- ⭐ Star the repository
- 👀 Explore the notebook
- 💬 Connect with me
- 🤝 Collaborate on future data science projects

<p align="center">

**Python • Pandas • SQLite • SQL • Data Analysis**

<br>

<strong>Built with curiosity, data, and code. 🚀</strong>

</p>
````
