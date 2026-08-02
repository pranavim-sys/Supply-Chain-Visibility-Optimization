# Milestone 3 - Supply Chain Visibility and Optimization

This milestone focuses on building a robust supply chain visibility framework using Power BI. It includes supplier scorecards, ranking and benchmarking, transportation cost analysis, and carrier performance evaluation. The goal is to provide actionable insights for improving supplier reliability, reducing transportation costs, and enhancing overall supply chain efficiency.

---

## 📊 Supplier Scorecard Calculation Methodology
- **KPIs Considered**:
  - Quality Score (defect-free shipments)
  - Reliability % (on-time delivery consistency)
  - Lead Time (average days to fulfill orders)
  - Product Coverage (number of distinct products supplied)
  - Orders Fulfilled (proxy for operational capacity)
- **Weighting Approach**:
  - Quality and Reliability are prioritized as they directly impact customer satisfaction.
  - Lead Time and Fulfillment capacity provide operational efficiency measures.
- **Normalization**:
  - Each KPI is scaled to a comparable range before aggregation.
- **Composite Score**:
  - A weighted average is used to calculate the final supplier score.

**DAX Queries:**
```DAX
Total Suppliers = DISTINCTCOUNT(Dim_supplier[supplier_name])

Avg Quality Score = AVERAGE(Dim_supplier[quality_score])

Avg Reliability % = AVERAGE(Dim_supplier[reliability_%])

Avg Lead Time (Days) = 
    AVERAGEX(
        VALUES(Dim_supplier[supplier_name]),
        CALCULATE(AVERAGE(Dim_supplier[lead_time_(days)]))
    )

Products Supplied = DISTINCTCOUNT(Dim_supplier[product_card_id])

Orders Fulfilled (Proxy) = 
    CALCULATE(
        DISTINCTCOUNT(Fact_table[order_id]),
        Fact_table[order_status] IN { "COMPLETE", "CLOSED" }
    )


🏆 Supplier Ranking and Benchmarking Approach
Ranking Logic:

Suppliers are ranked using a composite score derived from KPIs.

RANKX function ensures consistent ordering across suppliers.

Benchmarking:

Suppliers compared against industry averages and top quartile performers.

Tier classification:

Tier 1: Strategic suppliers (score > 85)

Tier 2: Reliable suppliers (70–85)

Tier 3: Improvement needed (< 70)

DAX Queries:
SupplierRank = 
    RANKX(
        ALL(Dim_supplier[supplier_name]),
        [Avg Quality Score] + [Avg Reliability %],
        ,
        DESC,
        Dense
    )

🚚 Transportation Cost Analysis Methodology
KPIs Considered:

Cost per ton

Cost per kilometer

Average profit per order

Discounts given and discount rate

Methodology:

Costs are aggregated at route and carrier level.

Discounts are analyzed to understand margin erosion.

Profitability is assessed per order to identify high-margin vs low-margin routes.

DAX Queries:
TransportationCostPerTon = SUM(Transportation[Cost]) / SUM(Transportation[Tons])

TransportationCostPerKM = SUM(Transportation[Cost]) / SUM(Transportation[DistanceKM])

Avg Profit Per Order = AVERAGE(Fact_table[order_profit_per_order])

Total Discount Given = SUM(Fact_table[order_item_discount])

Avg Discount Rate = AVERAGE(Fact_table[order_item_discount_rate])

🛤️ Route and Carrier Performance Evaluation
Metrics Evaluated:

On-Time Deliveries %

Late Delivery Rate by Shipping Mode

Same Day Delivery Share %

Carrier Performance Index

Approach:

Carriers are benchmarked by delivery reliability and cost efficiency.

Shipping modes are analyzed separately to identify bottlenecks.

DAX Queries:

CarrierPerformanceIndex = 
    (SUM(Carrier[OnTimeDeliveries]) / SUM(Carrier[TotalDeliveries])) * 100

Same Day Share % = 
    DIVIDE(
        CALCULATE(
            DISTINCTCOUNT(Fact_table[order_id]),
            Fact_table[shipping_mode] = "Same Day"
        ),
        [Total Orders],
        0
    )

Late Rate by Shipping Mode = 
    CALCULATE(
        [Late Delivery %],
        ALLEXCEPT(Fact_table, Fact_table[shipping_mode])
    )

💡 Key Insights and Business Recommendations
Supplier Insights:

High reliability suppliers should be prioritized for critical orders.

Suppliers with long lead times need process optimization.

Transportation Insights:

Certain routes show high cost per ton due to inefficient carrier allocation.

Discounts are eroding margins on specific product categories.

Recommendations:

Negotiate better terms with carriers showing high costs but low reliability.

Shift critical shipments to Tier 1 suppliers.

Optimize shipping mode allocation to reduce late deliveries.

Implement dashboards for continuous monitoring of supplier and carrier KPIs.

 










    





