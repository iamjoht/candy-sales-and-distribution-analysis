# Candy Distribution Analysis
A Power BI dashboard analyzing candy sales, shipping efficiency the US.
## Business Questions
- What are the most / least efficient factory-to-customer shipping routes?
- Which product divisions have the best profit margin?
## Dashboard Pages
1. **Route Efficiency** — Avg shipping distance, avg ship days, and total orders by factory/route, with top 10 most/least efficient routes and a geographic map of shipments.

2. **Product Sales / Margin Analysis** — Profit margin by product and division, price vs. cost comparison, and sales/orders trend over time.
## Data Model
![](Pasted%20image%2020260821130932.png)

| Table         | Description                                                                                                   |
| ------------- | ------------------------------------------------------------------------------------------------------------- |
| **Sales**     | Fact table of order-level transactions (dates, customer location, product, sales, cost, gross profit, units). |
| **Products**  | Product catalog with division, assigned factory, unit price, and unit cost.                                   |
| **Factories** | Factory names with latitude/longitude for distance calculations.                                              |
| **US Zips**   | US zip code reference data (lat/lng, city, state, population, density) used to geolocate customers.           |
| **Date**      | Calendar table (Date, Month, Quarter, Year) for time intelligence.                                            |
| **Targets**   | Sales targets by division for 2024.                                                                           |
## Key Calculations
- **Distance (km)**: Haversine distance between a factory's coordinates and a customer's zip code coordinates, calculated per Sales row.
- **Shipping Efficiency Score** = Total Gross Profit ÷ Avg Distance: Measure the economic efficiency of a route or factory.
- **Avg Distance / Avg Ship Days**: Average shipping distance and delivery time (Ship Date − Order Date) per factory/route.
- **Profit Margin %**: Total Gross Profit ÷ Total Sales.
## Tools
- Power BI Desktop
- Native Power BI visuals (Card, Matrix, Table, Bar, Combo, Map)