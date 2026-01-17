---
title: "Rebuilding a Data Platform in One Year"
date: 2025-12-11
draft: false
description: "Ground-up rebuild of an internal data platform using Data Mesh principles, Iceberg, and dbt on AWS"
tags: ["aws", "dbt", "iceberg", "data-mesh", "glue", "athena"]
categories: ["Data Engineering"]
---

## Overview

Led the rebuild of Funnel's internal data platform from the ground up, adopting Data Mesh principles to distribute ownership while centralizing definitions of core business metrics.

## Tech Stack

- **Storage**: S3 with Apache Iceberg tables
- **Catalog**: AWS Glue Data Catalog (federated across accounts)
- **Query Engine**: Athena
- **Transformation**: dbt
- **Ingestion**: Custom Python pipelines with Polars

## Key Outcomes

- Halved the number of dbt models while improving coverage
- 33% reduction in daily incremental run times
- Federated data catalog enabling self-serve analysis across the org
- Clear ownership model: product teams as data producers, Analytics Engineers as platform owners

## Architecture Highlights

- **Data Mesh**: Product teams own first-order data products with consistent schemas
- **Iceberg**: Enables upserts, schema evolution, and concurrent reads/writes
- **Core Datasets**: Centralized definitions of customers, users, revenue, and usage metrics

---

Read the full story on the [Funnel Dev Blog](https://funnel.io/devblog/rebuilding-our-data-platform-in-one-year).
