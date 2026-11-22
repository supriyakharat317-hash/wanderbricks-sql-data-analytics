# Wanderbricks | SQL Data Analytics

A business-focused SQL analytics project exploring bookings, revenue, properties, hosts, cities, cancellations, and amenities for Wanderbricks. The analysis is written for Databricks SQL and combines portfolio-level KPIs with city, property, and time-based views.

## Project Overview

This project uses SQL to turn Wanderbricks marketplace data into operational and commercial insights. It covers the booking lifecycle, confirmed booking revenue, property supply, demand by property type and month, geographic performance, cancellation patterns, and amenity prevalence.

## Business Objectives

- Establish a clear baseline for marketplace scale and booking status.
- Quantify confirmed booking revenue, average confirmed booking value, and cancellation rate.
- Identify cities and hosts with the largest property portfolios.
- Compare booking volume across property types and over time.
- Highlight cities with high cancellation counts and amenities commonly associated with listings.
- Provide a reproducible starting point for further marketplace analysis.

## Dataset Description

The supplied SQL references the following tables in the `wanderbricks` schema:

| Table | Use in this analysis |
|---|---|
| `bookings` | Booking status, amount, property, and creation date |
| `properties` | Property price, type, host, and city relationships |
| `users` | Marketplace user row count |
| `hosts` | Host row count |
| `cities` | City row count and city names |
| `amenities` | Amenity names and IDs |
| `property_amenities` | Property-to-amenity associations |
| `employees` | Employee row count |

The project brief describes a nine-table dataset, while the supplied SQL names eight distinct tables. The ninth table is not identifiable from the provided query file; add its name and description here when confirmed. The SQL also uses the Databricks catalog `databricks_wanderbricks_dataset_dais_2025`.

## Tools and Technologies

- **Databricks SQL** — querying the catalog and schema
- **SQL** — aggregations, joins, common table expressions, date functions, and ranking
- **Charts** — supplied visualizations for monthly bookings, property type, cancellations by city, and amenities

## Key Business KPIs

| KPI | Definition used |
|---|---|
| Total users, properties, bookings, hosts, cities, amenities, employees | Row counts from the corresponding tables |
| Confirmed booking revenue | Sum of `bookings.total_amount` where `status = 'confirmed'` |
| Average confirmed booking value | Average of `total_amount` for confirmed bookings |
| Cancellation rate | Cancelled booking count divided by all booking rows, multiplied by 100 |
| Average property base price | Average of `properties.base_price` |

The supplied SQL calculates KPI values when run; numeric KPI results were not included in the materials provided. Cancellation rate is based on all booking rows, so its denominator includes every status present in the table.

## SQL Analysis Performed

The query file includes:

1. Row counts for core marketplace entities.
2. Booking counts by status.
3. Confirmed booking revenue and average confirmed booking value.
4. Overall cancellation percentage.
5. Average property base price.
6. Top five cities by property count.
7. Top five cities by booking revenue.
8. Top five hosts by number of properties.
9. Booking counts by property type.
10. Monthly booking volume grouped by booking creation year and month.
11. Top five cities by cancellation count.
12. Top five amenities by number of linked property-amenity records.



## Key Findings and Business Insights

- **Booking mix is evenly distributed across the four displayed property types.** Ski resorts lead at 25.21%, followed by urban year-round at 25.11%, summer getaways at 24.90%, and historical places at 24.78%. This chart reflects booking counts, not revenue or profitability.
- **Singapore has the highest cancellation count in the displayed city chart.** It shows 2,491 cancellations, compared with approximately 1,290–1,302 for each of the next four cities. Counts alone do not reveal cancellation risk; compare cancellations against total bookings per city to calculate rates.
- **The monthly booking chart shows a steep decline during 2023.** The displayed series falls from 23,159 in January to 3,566 in December. The chart also shows 2022 only for September–December and 2024 only for January–March, so the years are incomplete and should not be compared as full-year totals. Confirm whether the dataset contains partial-year coverage or filtering before drawing trend conclusions.
- **The five displayed amenities have similar linked-record counts.** 24-Hour Security is highest at 8,739 and Home Theater lowest at 8,694. These appear to be counts of property-amenity associations, not an independent measure of guest preference.
- **Revenue, average booking value, city revenue leaders, property supply leaders, and host leaders are query outputs but no result values were supplied.** Run the SQL to populate those findings before publishing claims about those measures.

## Conclusion

This project demonstrates how Databricks SQL can be used to analyze Wanderbricks marketplace performance across bookings, revenue, properties, cities, cancellations, hosts, and amenities. The findings highlight booking patterns and areas for further investigation, providing a practical foundation for data-informed business decisions.


