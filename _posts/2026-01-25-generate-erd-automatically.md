---
layout: post
title: "Auto-Generating ER Diagrams from dbt Constraints"
subtitle: "Turning dbt tests into database constraints and always-up-to-date ER diagrams"
categories: projects
tags: [python, dbt, snowflake, automation]
---

![Auto-generated ER diagram example](/assets/images/projects/generate-erd-automatically.png)

A code-first tool that keeps data model documentation from ever going stale. dbt tests define primary/foreign key relationships once; a Python generator reads the resulting database constraints via SQLAlchemy, recursively traverses the relationship graph — identifying fact tables and detecting star/snowflake schemas along the way — and renders the result as a Mermaid ER diagram. Change the schema, and the diagram updates with it. No hand-drawn diagrams, no drift.

**Tech Stack:** Python · dbt Core · Snowflake / PostgreSQL · SQLAlchemy · Mermaid.js · dbt_constraints (Snowflake Labs)

**Highlights**

* Converts standard dbt tests (`primary_key`, `relationships`) into real, physical database constraints
* Automatic schema intelligence: detects fact tables and star/snowflake schema shapes
* Outputs native `.mmd` files usable directly in GitHub, VS Code, and Confluence
* A concrete example of treating documentation as a build artifact, not a manual chore

[View the code and full write-up on GitHub →](https://github.com/ThorstenWeberGER/generate-erd-automatically)
