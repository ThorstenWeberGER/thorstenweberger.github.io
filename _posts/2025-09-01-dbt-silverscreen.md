---
layout: post
title: "Analytics Engineering ETL Pipeline: dbt, Snowflake & Tableau"
subtitle: "Why is our movie theatre company losing money?"
categories: projects
tags: [dbt, snowflake, tableau, sql, etl]
---

![dbt Silverscreen logo](/assets/images/projects/dbt_silverscreen.png)

A production-style Analytics Engineering pipeline that turns a messy, multi-source dataset into a single source of truth answering a real business question. Using dbt and Snowflake, I built a full Medallion-architecture pipeline (Raw → Staging → Integration → Consumer) with 10+ tested models, then visualized the resulting KPIs in a Tableau dashboard that exposed exactly which locations and movie genres were driving losses.

**Tech Stack:** Snowflake · dbt · SQL · Jinja & Macros · dbt-utils / dbt-expectations · Tableau · Git/GitHub

**Highlights**

* Cloud-native ingestion via Snowflake `COPY INTO` from managed cloud storage
* Comprehensive testing (uniqueness, not-null, custom business-rule tests) at every layer
* Auto-generated documentation and data lineage straight from dbt
* Business insights that directly informed a recommendation (rotate unprofitable titles faster)

[View the full write-up and code on GitHub →](https://github.com/ThorstenWeberGER/dbt_silverscreen)
&nbsp;·&nbsp;
[Tableau Dashboard →](https://public.tableau.com/app/profile/thorsten.weber/viz/movie_performance_FY24-25)
