---
layout: post
title: "Dockerized Data Analytics & Engineering Stack"
subtitle: "A reproducible, cloud-independent playground for data pipeline work"
categories: projects
tags: [docker, dbt, airflow, postgresql, spark]
---

A fully containerized data engineering environment — Spark, dbt, PostgreSQL, and Apache Airflow, orchestrated via Docker Compose and wired into VS Code Dev Containers. Spin up an entire data stack, from warehouse to transformation layer to orchestration, on a laptop with one command, independent of any cloud provider, and hand it to a teammate for identical results. Secrets stay out of the codebase entirely via a gitignored `.env` file shared between dbt and Python.

**Tech Stack:** Docker & Docker Compose · Apache Spark (PySpark) · dbt · PostgreSQL · Apache Airflow · BigQuery · VS Code Dev Containers

**Highlights**

* Five orchestrated services: dev environment, Postgres, Airflow webserver/scheduler, and Airflow's metadata DB
* dbt pre-wired against both PostgreSQL and BigQuery targets
* Airflow DAG orchestration for dbt runs via the `airflow-dbt-python` provider
* Secure-by-default secrets handling, separate from application code

[View the full setup on GitHub →](https://github.com/ThorstenWeberGER/docker-data-analytics)
