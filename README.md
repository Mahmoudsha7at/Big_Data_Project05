#  Spotify Big Data Analytics Platform

##  Project Overview

This project demonstrates a complete End-to-End Big Data pipeline for analyzing Spotify music tracks using Apache Spark, Apache Hive, Docker, and Power BI.

The system starts with a Spotify CSV dataset, processes the data using Apache Spark, stores and queries the processed results with Apache Hive, and finally visualizes the insights through an interactive Power BI dashboard.

---

##  Technologies Used

-  Docker
-  Docker Compose
-  Apache Spark (PySpark)
-  Apache Hive
-  PostgreSQL (Hive Metastore)
-  Apache Kafka
-  Zookeeper
-  Python
-  Power BI
-  GitHub

---

#  Project Structure

```
Big_Data_Pro/
│
├── dataset/
│   └── spotify-tracks-dataset.csv
│
├── hive/
│   ├── Dockerfile
│   └── entrypoint.sh
│
├── spark/
│   ├── spotify_analysis.py
│   └── output/
│       ├── genre_popularity/
│       └── top_songs/
│
├── powerbi/
│
├── presentation/
│
├── report/
│
├── docker-compose.yml
│
└── README.md
```

---

# System Architecture

```
                Spotify Dataset (CSV)
                        │
                        ▼
               Apache Spark (PySpark)
                        │
          Data Cleaning & Transformation
                        │
                        ▼
         Average Popularity by Genre
                        │
                        ▼
                 CSV Output Files
                        │
                        ▼
            Apache Hive External Table
                        │
                 SQL Queries (Hive)
                        │
                        ▼
                 Power BI Dashboard
                        │
                        ▼
             Business Insights & Reports
```

---

#  Workflow

1. Load Spotify Dataset.
2. Read CSV using Apache Spark.
3. Clean and transform the data.
4. Group songs by genre.
5. Calculate average popularity.
6. Sort genres by popularity.
7. Save processed data as CSV.
8. Create Hive External Tables.
9. Execute SQL queries using Hive.
10. Import processed data into Power BI.
11. Build interactive dashboards.

---

#  Apache Spark

Spark is responsible for:

- Reading the Spotify dataset.
- Processing large-scale data efficiently.
- Cleaning and transforming records.
- Grouping tracks by genre.
- Calculating Average Popularity.
- Exporting processed results.

---

#  Apache Hive

Hive is used for:

- Creating databases.
- Creating external tables.
- Querying Spark output using SQL.
- Organizing processed data.

Example Query:

```sql
SELECT *
FROM genre_popularity
LIMIT 10;
```

---

#  Power BI Dashboard

The dashboard includes:

- Clustered Column Chart
- Pie Chart
- KPI Card
- Data Table

Dashboard Insights:

- Top music genres.
- Average popularity.
- Genre comparison.
- Business analytics.

---

#  How To Run

## 1. Start Docker Containers

```bash
docker compose up -d
```

---

## 2. Check Running Containers

```bash
docker ps
```

---

## 3. Run Spark Application

```bash
spark-submit /opt/spark-apps/spotify_analysis.py
```

---

## 4. Connect To Hive

```bash
docker exec -it hive-server bash
```

```bash
beeline -u jdbc:hive2://localhost:10000
```

---

## 5. Execute SQL Query

```sql
USE spotify_db;

SELECT *
FROM genre_popularity
LIMIT 10;
```

---

##  Project Results

The project successfully:

- Processed Spotify data using Apache Spark.
- Generated genre popularity statistics.
- Stored processed data in Hive.
- Queried data using SQL.
- Built an interactive Power BI dashboard.
- Provided business insights into music popularity.

---

#  Screenshots

Add screenshots here:

- Docker Containers
- Spark Master UI
- Spark Worker UI
- Spark Job Execution
- Hive SQL Queries
- Power BI Dashboard
- GitHub Repository

---



#  Future Improvements

- Integrate Kafka for real-time data streaming.
- Add Apache Flink for stream processing.
- Store data in HBase.
- Deploy the project to a cloud environment.
- Build a real-time Power BI dashboard.

---

#  Conclusion

This project demonstrates a complete Big Data analytics pipeline using modern Big Data technologies.

Apache Spark was used for distributed data processing, Apache Hive provided SQL-based querying, Docker simplified deployment, and Power BI delivered professional data visualization.

The project showcases how raw Spotify data can be transformed into meaningful business insights through a scalable and efficient architecture.

---

#  License

This project was developed for educational purposes as part of the Big Data course.