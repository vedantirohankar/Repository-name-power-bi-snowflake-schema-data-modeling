# Power BI Snowflake Schema Data Modeling Project

## Project Overview

This project demonstrates dimensional data modeling in Power BI using a Snowflake Schema.

The model was designed to organize sales and budget data into fact and dimension tables. Dimension tables were further normalized into related sub-dimensions to reduce redundancy and improve data organization.

## Data Model

![Power BI Snowflake Schema](screenshots/snowflake-schema-model.png)

## Schema Type

**Snowflake Schema**

Unlike a basic Star Schema, some dimensions in this model are normalized into additional related dimension tables.

Examples include:

* Product information connected with the Category dimension
* Customer information connected with the Geography dimension
* Sales and budget information connected with shared business dimensions

## Tables Used

### Fact Tables

#### Sales

The Sales table contains transactional sales information and acts as the main fact table of the model.

It is used for analysing:

* Sales performance
* Product sales
* Customer transactions
* Date-wise trends
* Regional performance

#### FactBudget

The FactBudget table stores budget-related values.

It can be used to compare:

* Actual sales versus budget
* Category-wise budget performance
* Date-wise budget trends

### Dimension Tables

#### Dim customer

Contains customer-related descriptive information.

#### Dim geography

Contains geographical information associated with customers, such as city, state, region or country.

#### Dim product

Contains product-level information.

#### Dim category

Contains product-category information and supports the normalized product hierarchy.

#### Dim Date

Contains date attributes used for time-based analysis.

Possible attributes include:

* Date
* Month
* Quarter
* Year
* Month name
* Financial period

## Model Structure

```text
Dim Geography
      ↓
Dim Customer
      ↓
    Sales
      ↑
 Dim Product
      ↓
 Dim Category

Dim Date → Sales
Dim Date → FactBudget
Dim Category → FactBudget
```

## Snowflake Schema Explanation

This model follows a Snowflake Schema because some dimension tables are divided into additional normalized dimensions.

For example:

```text
Sales → Dim Product → Dim Category
```

and:

```text
Sales → Dim Customer → Dim Geography
```

Instead of storing category details repeatedly inside the Product table, they are maintained in a separate Category dimension.

Similarly, geography details can be stored separately from customer details.

This design helps:

* Reduce duplicate data
* Improve data organization
* Maintain clear business hierarchies
* Support reusable dimensions
* Improve model maintainability

## Data Modeling Concepts Applied

* Fact and dimension table design
* Snowflake Schema
* Table relationships
* One-to-many relationships
* Primary and foreign keys
* Shared dimensions
* Data normalization
* Dimensional modeling
* Date dimension
* Business hierarchy design

## Tools Used

* Microsoft Power BI Desktop
* Power Query
* Data Modeling
* DAX
* GitHub

## Project Files

```text
├── Power-BI-Snowflake-Data-Model.pbix
├── README.md
├── screenshots
│   └── snowflake-schema-model.png
└── documentation
    └── relationships.md
```

## Key Learning

Through this project, I gained practical experience in designing a structured Power BI data model using fact tables, dimension tables and normalized dimension hierarchies.

I also learned how to establish relationships between tables and design a model suitable for sales and budget analysis.

## Author

**Vedanti Rohankar**

Data Analyst | Power BI | SQL | Azure Data Factory | Data Modeling
