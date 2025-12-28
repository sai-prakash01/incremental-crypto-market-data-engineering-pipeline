# Incremental Crypto Market Data Engineering Pipeline

## Overview
This project demonstrates an end-to-end **data engineering pipeline** that ingests historical cryptocurrency market data from a public REST API, processes it incrementally, enforces data quality, and stores analytics-ready datasets in a relational warehouse.

The pipeline is fully re-runnable, idempotent, and implemented in a single notebook environment.

## Architecture
API Ingestion → Incremental Load → Deduplication → Data Quality Checks → Fact & Dimension Modeling → SQLite Warehouse → SQL Analytics

## Tech Stack
- Python
- Pandas
- REST APIs (CoinGecko)
- SQLite
- SQL
- Google Colab

## Data Model
**Dimension Table**
- `dim_asset (asset_sk, asset_id, effective_from, effective_to, is_current)`

**Fact Table**
- `fct_price_history (asset_sk, price_date, price_usd, market_cap, volume, ingestion_timestamp)`

## Key Features
- Historical time-series ingestion
- Incremental and idempotent loads
- Surrogate keys and dimensional modeling
- Data quality enforcement
- SQL-based analytics

## How to Run
1. Open the notebook in Google Colab
2. Run all cells from top to bottom
3. Final outputs will be generated as CSV files and a SQLite database

## Outputs
- `data/dim_asset.csv`
- `data/fct_price_history.csv`
- `warehouse/crypto_dw.db`
