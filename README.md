# SVC-Key-Parts-Monitoring-Dashboard

### 📌 Project Overview
-------
Our company manages over 30,000 active service parts for customer service operations. Due to the sheer volume, each product division is assigned to a PIC (Person In Charge) to independently monitor and manage PSI (Production, Sales, and Inventory) for their parts. However, upper management had no centralized access to key inventory information or issue updates unless they directly contacted each PIC. 
### 📌 Objective
-------
To solve this, I developed a ETL process using Python on Google Cloud Platform and designed a Tableau dashboard that provides real-time visibility into key service parts inventory and issues. This enabled better decision-making and proactive risk management at the executive level.

### 🔧 Tools Used
- Python (Pandas, Numpy), SQL, Tableau

### 📁 Data Description

* **Raw Data**: Each PIC updates shared excel file monthly for Rep Part, category, division, monthly forecasted demand, RA History, and Supply Delay Status. This excel file also includes Rep Part Master sheet.
* **Inventory**: Part Inventory data that includes on-hand (have), in-transit (move), and open quantity (order) for each part
*  **Back order**: Daily back order quantity lists per parts
*  **Supplier**: Supplier for each parts
