# Banking Data Warehouse Project

## Overview

This project implements a comprehensive data warehouse for a banking environment using a modern medallion architecture approach. The data warehouse breaks down information silos, centralizes business data, and creates a single source of truth for analytics and reporting purposes.

## Architecture

The project uses a three-layer medallion architecture:

### Bronze Layer
- Raw data ingestion from source systems
- Data preserved in its original format
- Sources include CRM data (partitioned by country) and Core Banking transaction data
- Implemented using Delta tables for versioning and ACID compliance

### Silver Layer
- Data cleaning and standardization
- Transformation into structured, consistent formats
- Consolidation of disparate data sources
- Quality checks to ensure data integrity

### Gold Layer
- Business-ready, optimized data models
- Star schema design (fact and dimension tables) 
- Implemented as views for flexibility and performance
- Designed for consumption by BI tools and analysts

## Data Sources

The project simulates two primary data sources:

1. **Customer Relationship Management (CRM) System**
   - Client information (name, account, contact details)
   - Registration and KYC data
   - Segmented by country/subsidiary

2. **Core Banking System**
   - Transaction records (transfers, deposits, withdrawals)
   - Payment channels (mobile, ATM, branch, web)
   - Transaction statuses and amounts

## Components

### Data Generation
- Uses PySpark and Faker to generate synthetic banking data
- Creates realistic customer profiles and transaction records
- Partitions data by country and transaction type

### Data Transformation
- Silver layer transformations consolidate and standardize raw data
- Implements data quality checks to ensure integrity
- Creates a unified view of banking operations

### Data Modeling
- Gold layer implements a star schema design
- Dimension tables: Client, Date, Agency, Terminal, Currency, Country, Transaction Type
- Fact table: Transactions with foreign keys to dimensions

## Implementation Details

### Technologies Used
- Microsoft Fabric 
- PySpark for data processing and generation
- Delta Lake for storage format
- T-SQL for view creation


### Quality Assurance
- Dedicated data quality checks via Python classes
- Schema validation to ensure consistent structure

