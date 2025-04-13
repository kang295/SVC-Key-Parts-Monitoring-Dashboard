# SVC-Key-Parts-Monitoring-Dashboard

### 📌 Project Background
-------
Our company manages over 30,000 active service parts for customer service operations. Due to the sheer volume, each product division is assigned to a PIC (Person In Charge) to independently monitor and manage their parts' PSI (Production, Sales, and Inventory). However, upper management had no centralized access to key inventory information or issue updates unless they directly contacted each PIC. 
### 📌 Objective
-------
To solve this, I developed an ETL process using Python on Google Cloud Platform. I designed a Tableau dashboard that provides real-time visibility into key service parts inventory and issues. This enabled better decision-making and proactive risk management at the executive level.

##### Insights and recommendations are provided on the following key areas:
* ss

### 🔧 Tools Used
- Python (Pandas, Numpy), SQL, Tableau

### 📁 Data Description

* **Raw Data**: Each PIC updates the shared Excel file monthly for Rep Part, category, division, forecasted demand, RA History, and Supply Delay Status. This Excel file also includes the Rep Part Master sheet.
* **Inventory**: Part Inventory data that includes on-hand (have), in-transit (move), and open quantity (order) for each part
*  **Back order**: Daily back order quantity lists per part
*  **Supplier**: Supplier for each parts



# **Recommendation** 
