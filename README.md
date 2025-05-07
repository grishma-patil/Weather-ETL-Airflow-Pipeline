## 🌦️ Weather ETL Pipeline using Airflow, PostgreSQL & Docker

This project is an end-to-end **ETL pipeline** that I built to extract, transform, and load real-time weather data using **Apache Airflow**. It fetches live data from the Open-Meteo API and stores it in a PostgreSQL database. I containerized the pipeline using **Docker** and orchestrated all tasks using **Astro CLI** for local Airflow development.


## Project Overview

The goal of this project was to demonstrate how to build a production-ready ETL workflow with Airflow. I implemented tasks for:
- **Data extraction** via HTTP API
- **Transformation** of raw JSON into structured weather data
- **Loading** the data into a relational database

All components are containerized using Docker, making the pipeline reproducible and easy to deploy locally or in the cloud.


## DAG Structure

The DAG runs on a **daily schedule** and performs the following tasks:

1. **Extract**: Uses Airflow's `HttpHook` to call the Open-Meteo API for current weather data.
2. **Transform**: Parses the JSON response to extract meaningful fields like temperature, windspeed, etc.
3. **Load**: Inserts the cleaned data into a PostgreSQL table called `weather_data`.


## Technologies Used

- **Apache Airflow** (via Astro CLI) – DAG scheduling and orchestration
- **Docker** – Containerization of Airflow and PostgreSQL
- **PostgreSQL** – Target database for storing transformed weather data
- **Python** – Task logic and ETL scripting
- **Open-Meteo API** – Free and open-source weather data provider


## Core Functionality

- Daily scheduling of weather data ingestion
- API integration using Airflow's built-in hooks
- Custom Python transformations
- Schema creation and auto-loading into PostgreSQL
- Local development powered by Docker and Astro CLI

