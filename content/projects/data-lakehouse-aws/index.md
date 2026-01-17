---
title: "Data Lakehouse on AWS"
date: 2024-01-15
draft: false
description: "Building a modern data lakehouse architecture using AWS Glue, dbt, and Apache Spark"
tags: ["aws", "dbt", "spark", "data-engineering"]
categories: ["Data Engineering"]
---

## Overview

A modern data lakehouse implementation leveraging AWS services for scalable data processing and analytics.

## Tech Stack

- **Storage**: S3 with Apache Iceberg tables
- **Processing**: AWS Glue / Apache Spark
- **Transformation**: dbt
- **Orchestration**: Apache Airflow
- **Catalog**: AWS Glue Data Catalog

## Architecture

The lakehouse follows a medallion architecture pattern:

1. **Bronze** - Raw data ingestion from various sources
2. **Silver** - Cleaned and conformed data
3. **Gold** - Business-level aggregates and metrics

## Key Features

- Incremental processing for cost efficiency
- Schema evolution support with Iceberg
- Data quality checks using dbt tests
- Automated pipeline monitoring

---

*This is a template project entry. Replace with your actual project details.*
