# Milestone 2: Supply Chain Visibility Optimization

This milestone focuses on analyzing inventory performance and delivery efficiency using Power BI dashboards. The goal is to provide actionable insights that improve supply chain visibility and support better decision-making.


##  Inventory Turnover Calculation Approach
- **Definition**: Inventory turnover measures how many times inventory is sold and replaced during a given period.
- **Formula**:  
\[
  \text{Inventory Turnover} = \frac{\text{Cost of Goods Sold (COGS)}}{\text{Average Inventory}}
  \]


- **Implementation in Power BI**:
  - COGS values are sourced from transactional sales data.
  - Average inventory is calculated as:  
    

\[
    \frac{\text{Opening Inventory} + \text{Closing Inventory}}{2}
    \]


  - KPI cards and trend charts visualize turnover rates across product categories.



##  Slow-Moving vs Fast-Moving Inventory Identification
- **Logic**:
  - **Fast-Moving Inventory**: Items with high turnover ratio (above threshold, e.g., > 6 times per year).
  - **Slow-Moving Inventory**: Items with low turnover ratio (below threshold, e.g., < 2 times per year).
- **Additional Criteria**:
  - Days-in-inventory metric used to classify items:
    

\[
    \text{Days in Inventory} = \frac{365}{\text{Inventory Turnover}}
    \]


  - Products with > 180 days in inventory are flagged as slow-moving.
- **Visualization**:
  - Conditional formatting highlights slow-moving items in red and fast-moving items in green.
  - Category-level breakdowns show which segments contribute most to inefficiencies.



##  Delivery Performance Analysis Methodology
- **Metrics Evaluated**:
  - **On-Time Delivery %**:  
    

\[
    \frac{\text{On-Time Deliveries}}{\text{Total Deliveries}} \times 100
    \]


  - **Average Delivery Delay**: Difference between promised vs actual delivery dates.
  - **Delivery Reliability Index**: Composite score combining punctuality and consistency.
- **Data Sources**:
  - Shipment logs, customer order records, and carrier performance data.
- **Visualization**:
  - Line charts for delivery trends.
  - Bar charts comparing carriers and regions.
  - Heatmaps for identifying bottlenecks.



##  Key Insights
- High turnover categories (e.g., FMCG products) show strong sales velocity but require tighter replenishment cycles.
- Slow-moving items tie up working capital and increase holding costs.
- Delivery delays are concentrated in specific regions, often linked to logistics partners.
- On-time delivery performance is above 90% for top-tier carriers but below 70% for smaller vendors.



##  Business Recommendations
1. **Inventory Optimization**:
   - Reduce procurement of slow-moving items.
   - Implement demand forecasting to balance stock levels.
2. **Supplier & Carrier Management**:
   - Negotiate service-level agreements with underperforming carriers.
   - Prioritize reliable vendors for critical deliveries.
3. **Process Improvements**:
   - Automate reorder points for fast-moving items.
   - Introduce real-time tracking dashboards for delivery monitoring.
4. **Strategic Actions**:
   - Reallocate warehouse space to high-turnover products.
   - Conduct quarterly reviews of inventory and delivery KPIs.



