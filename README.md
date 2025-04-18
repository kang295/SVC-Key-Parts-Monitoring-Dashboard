# SVC-Key-Parts-Monitoring-Dashboard

### 📌 Project Background
-------
LG Electronics manages over 30,000 active service parts used in global customer service operations. Each product division assigns a PIC (Person In Charge) to manage their own PSI (Production, Sales, Inventory). However, upper management lacked a centralized system to monitor key inventory issues, often relying on manual communication with each PIC.

-------
### 🎯 Objective

To improve visibility and streamline decision-making, I built an **end-to-end monitoring system** with the following architecture:

- **ETL Pipeline**: Automated using Python and BigQuery on GCP  
- **Data Visualization**: Executive-friendly dashboard built in Tableau  
- **Monitoring Scope**: Focused on ~330 critical service parts  

Although not real-time, the dashboard is **refreshed weekly** and **shared via email** with key stakeholders, providing **timely insights** into inventory status and supply chain risks.

This solution enabled executives to:

- Make faster, **data-driven decisions**
- **Proactively** respond to potential inventory issues
- Reduce dependency on **manual, ad-hoc reports** from each division

-------
### 📈 Key Features & Insights

- **Return Authorization (RA) & Supply Delay Monitoring**  
  Identify parts with a history of frequent return authorizations or delivery delays.

- **6-Month Demand Trend (Per Part)**  
  Analyze individual part demand patterns to detect abnormal behavior or anticipate restocking needs.

- **Division-Level Demand Trend (Per GBU)**  
  Aggregate demand trends by Division such as refregirator, Washing Machine, or Cooking for broader strategic insights.

- **Turnover Rate Analysis**  
  Evaluate inventory efficiency using on-hand quantity, in-transit volume, and turnover rate metrics.

- **Demand Pattern Classification**  
  Automatically classify demand trends as **Normal**, **Surge**, or **Drop** to detect potential risks.

-------
### 🔧 Tools Used
- Python (Pandas, Numpy), BigQuery, Tableau

-------
### 📁 Data Structure & Initial Checks 

* `Raw Data`: Each PIC updates the shared Excel file monthly for Rep Part, category, division, forecasted demand, RA History, and Supply Delay Status. This Excel file also includes the Rep Part Master sheet.
* `Inventory`: Part Inventory data that includes on-hand (have), in-transit (move), and open quantity (order) for each part
* `Daily BO`: Daily back order quantity lists per part
* `Supplier`: Supplier information for each part
* `Bulky Parts`: This data contains the bulky status per part

-------
### ⚙️ Process

1. **Data Extraction & Cleaning**  
   - Aggregating, joining, filtering, and dropping unnecessary fields

2. **Data Transformation**  
   - Creating new fields (e.g., turnover rate adjusted for bulky parts)  
   - Restructuring data into long-format for Tableau compatibility  
   - Detecting demand trends (Normal / Surge / Drop)

3. **Data Loading**  
   - Store processed data in a **BigQuery** table  
   - Connect BigQuery to **Tableau** for visualization

-------
### ✅ Business Impact

- Reduced **manual reporting time by over 80%** by automating the data pipeline and dashboard generation
- Enabled **weekly monitoring** of 330+ key service parts, improving visibility and early issue sensing across divisions
- Helped executives **proactively address supply chain risks** by providing timely insights

-------
### Final Dataframe Schema for Data Visualization
| Field name     | Type    | Mode     |
|----------------|---------|----------|
| rep\_part      | STRING  | NULLABLE |
| category       | STRING  | NULLABLE |
| division       | STRING  | NULLABLE |
| ra\_history\_yn | BOOLEAN | NULLABLE |
| sd\_yn         | BOOLEAN | NULLABLE |
| inventory      | INTEGER | NULLABLE |
| transit        | INTEGER | NULLABLE |
| open           | INTEGER | NULLABLE |
| BO qty         | INTEGER | NULLABLE |
| description    | STRING  | NULLABLE |
| supplier\_code | STRING  | NULLABLE |
| current\_TO    | FLOAT   | NULLABLE |
| demand\_trend  | STRING  | NULLABLE |
| bulky          | BOOLEAN | NULLABLE |
| Review         | BOOLEAN | NULLABLE |
| month          | STRING  | NULLABLE |
| demand         | INTEGER | NULLABLE |

-------
### Dashboard Preview
![Monitoring Dashboard](Key%20Parts%20Monitoring%20Dashboard.JPG)  

![Monitoring Dashboard](Key%20Parts%20Monitoring%20Filtered.JPG)
-------
### **Recommendation** 

- **Target Turnover Benchmarks per Part/Category**  
  Establish target turnover rates for each part or category to help identify gaps between current turnover and the target.
  This would allow for more precise monitoring of underperforming items and provide executives with actionable insights to improve stock movement.

- **Minimum Stock Level Status (Safety Stock)**  
  Implement minimum stock level Status for key parts. This will help assess if PICs are utilizing safety stock effectively and ensure that critical parts are not understocked during high-demand periods.

- **Part Registration Date**  
  This provides insight into whether a low current turnover rate is due to its new part status or a recent surge in demand unlike the normal period.

These additions could help executives better contextualize performance, improve inventory management, and make more informed decisions regarding procurement and replenishment strategies.
