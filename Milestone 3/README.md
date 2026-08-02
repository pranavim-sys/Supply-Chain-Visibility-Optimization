# Milestone 3 - Supply Chain Visibility and Optimization

This milestone focuses on building a robust supply chain visibility framework using Power BI. It includes supplier scorecards, ranking and benchmarking, transportation cost analysis, and carrier performance evaluation. The goal is to provide actionable insights for improving supplier reliability, reducing transportation costs, and enhancing overall supply chain efficiency.

---

##  Supplier Scorecard Calculation Methodology
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
-  - A weighted average is used to calculate the final supplier score.

**Supplier Ranking and Benchmarking Approach**
Ranking Logic: Suppliers are ranked based on a composite score that combines quality, reliability, lead time, and fulfillment capacity. This ensures that performance is measured holistically rather than on a single metric.

Benchmarking: Each supplier’s score is compared against industry averages and top quartile performers. This helps identify which suppliers are leading, which are average, and which need improvement.

Tier Classification:

Tier 1 (Strategic Partners): High-performing suppliers who consistently deliver quality and reliability.

Tier 2 (Reliable Suppliers): Adequate performers who meet expectations but have room for improvement.

Tier 3 (Underperformers): Suppliers who fall below benchmarks and require corrective action.

Purpose: This ranking system helps prioritize supplier relationships, negotiate better contracts, and identify where supplier development programs are needed.

**Transportation Cost Analysis Methodology**
Cost Dimensions: Transportation costs are broken down by route, carrier, and shipping mode. This allows for granular visibility into where money is being spent.

KPIs Considered: Cost per ton, cost per kilometer, total spend, and discount impact.

Comparative Analysis: Routes and carriers are compared to highlight inefficiencies. For example, two carriers on the same route may have very different cost structures.

Profitability Check: Costs are linked to order profitability to ensure that transportation expenses don’t erode margins.

Outcome: Identifies high-cost routes, carriers with poor cost efficiency, and opportunities to renegotiate contracts or optimize logistics.

**Route and Carrier Performance Evaluation**
Metrics Evaluated: On-time delivery percentage, average delay, cost efficiency, and shipping mode reliability.

Carrier Benchmarking: Carriers are compared against each other to identify the most reliable and cost-effective options.

Shipping Mode Analysis: Different modes (Same Day, Standard, Express) are evaluated separately to understand their impact on late deliveries and costs.

Insights Gained:

Which carriers consistently meet delivery commitments.

Which routes are prone to delays or excessive costs.

How shipping mode choices affect customer satisfaction and profitability.

Purpose: Provides a clear view of logistics performance, enabling better carrier selection and route planning.

**Key Insights and Business Recommendations**
Supplier Insights:

High-performing suppliers should be prioritized for critical orders.

Suppliers with long lead times or poor reliability need targeted improvement plans.

Transportation Insights:

Certain routes are disproportionately expensive and need optimization.

Discounts are eroding margins in specific product categories.

Same Day shipping has higher costs but boosts customer satisfaction.

Recommendations:

Negotiate better terms with carriers that have high costs but low reliability.

Shift critical shipments to Tier 1 suppliers to reduce risk.

Optimize shipping mode allocation to balance cost and service quality.

Implement continuous monitoring dashboards to track supplier and carrier KPIs in real time.

Use benchmarking results to guide supplier development programs and strengthen partnerships.
