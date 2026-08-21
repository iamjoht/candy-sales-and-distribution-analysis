# Candy Distribution Analysis
A Power BI dashboard analyzing candy sales, shipping efficiency, and factory-to-customer distribution routes across the US.
## Business Questions
- What are the most / least efficient factory-to-customer shipping routes?
- Which product divisions have the best profit margin?
## Data Model
<img width="1322" height="1054" alt="Image" src="https://github.com/user-attachments/assets/dd3673b4-2139-4c4b-86ef-3a3831226746" />

| Table         | Description                                                                                                   |
| ------------- | ------------------------------------------------------------------------------------------------------------- |
| **Sales**     | Fact table of order-level transactions (dates, customer location, product, sales, cost, gross profit, units). |
| **Products**  | Product catalog with division, assigned factory, unit price, and unit cost.                                   |
| **Factories** | Factory names with latitude/longitude for distance calculations.                                              |
| **US Zips**   | US zip code reference data (lat/lng, city, state, population, density) used to geolocate customers.           |
| **Date**      | Calendar table (Date, Month, Quarter, Year) for time intelligence.                                            |
| **Targets**   | Sales targets by division for 2024.                                                                           |
## Dashboard Pages
1. **Route Efficiency** — Avg shipping distance, avg ship days, and total orders by factory/route, with top 10 most/least efficient routes and a geographic map of shipments.

<img width="1966" height="1084" alt="Image" src="https://github.com/user-attachments/assets/5dec94c0-cacc-4b84-b04f-dda496052b67" />

2. **Product Sales / Margin Analysis** — Profit margin by product and division, price vs. cost comparison, and sales/orders trend over time.

<img width="1962" height="1082" alt="Image" src="https://github.com/user-attachments/assets/a3a2c639-4b9b-4b5e-8d1c-fec757f5c5fa" />

## Key Calculations
- **Distance (km)**: Haversine distance between a factory's coordinates and a customer's zip code coordinates, calculated per Sales row.
- **Shipping Efficiency Score** = Total Gross Profit ÷ Avg Distance: Measure the economic efficiency of a route or factory.
- **Avg Distance / Avg Ship Days**: Average shipping distance and delivery time (Ship Date − Order Date) per factory/route.
- **Profit Margin %**: Total Gross Profit ÷ Total Sales.
## Tools
- Power BI Desktop
- Native Power BI visuals (Card, Matrix, Table, Bar, Combo, Map)
