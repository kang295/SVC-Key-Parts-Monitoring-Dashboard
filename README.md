# SVC-Key-Parts-Monitoring-Dashboard

### 📌 Project Background
-------
LG Electronics manages over 30,000 active service parts for customer service operations. Due to the sheer volume, each product division is assigned to a PIC (Person In Charge) to independently monitor and manage their parts' PSI (Production, Sales, and Inventory). However, upper management had no centralized access to key inventory information or issue updates unless they directly contacted each PIC. 
### 📌 Objective
-------
To solve this, I developed an ETL process using Python and BigQuery on Google Cloud Platform. Then, I designed a Tableau dashboard that provides real-time visibility into key service parts (330ea) inventory and issues. This enabled better decision-making and proactive risk management at the executive level.

##### Insights and recommendations are provided on the following key areas:
* ss

-------

### 🔧 Tools Used
- Python (Pandas, Numpy), SQL (BigQuery), Tableau

-------

### 📁 Data Structure & Initial Checks 

* `Raw Data`: Each PIC updates the shared Excel file monthly for Rep Part, category, division, forecasted demand, RA History, and Supply Delay Status. This Excel file also includes the Rep Part Master sheet.
* `Inventory`: Part Inventory data that includes on-hand (have), in-transit (move), and open quantity (order) for each part
* `Daily BO`: Daily back order quantity lists per part
* `Supplier`: Supplier information for each part
* `Bulky Parts`: This data contains the bulky status per part

-------

### Process
1. Data Extracting and Cleaning (Aggregating, Joining, Dropping)
2. Data Transforming (New Field Calculation, long-format)  - Turnover rate, Demand trend
3. Data storing in a BigQuery table to connect with Tableau

-------

### Final Dataframe Schema for Data Visualization
![Dataframe Schema](Dataframe%20Schema.png)

-------

### Tableau Dashboard

-------

# **Recommendation** 
