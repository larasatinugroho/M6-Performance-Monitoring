# M6-Performance-Monitoring

<a href="https://github.com/larasatinugroho/M6-Performance-Monitoring/blob/main/M6%20-%20Performance%20Monitoring.PNG?raw=true">
  <img src="https://github.com/larasatinugroho/M6-Performance-Monitoring/blob/main/M6%20-%20Performance%20Monitoring.PNG?raw=true" width="600"/>
</a>

### Background overview
The existing dashboard in Apache Superset did not track the progress of the core KPI for M6 agents: paid-up.
This is used as the benchmark for whether agents receive incentives or not.

As a result, the Operations Manager requested an interactive dashboard to monitor M6 bucket performance. The goal is to allow managers to track each agent and team leader progress over time without needing to manually process or reorganize raw data.

Core Insights:
- KPI Target & Number of Agents: Represents the total assigned target and the number of active agents.
- KPI Paid-up: Shows the total paid-up collected across the entire bucket.
- KPI Achievement: Measures performance against the target.
 

### Data structure overview
The database consists of several tables, including case_job, case_bill, case, repayment, manual_dial, case_job_assist, and offline tables. The case_job table works as the primary link between cases handled by desk collection and field collection.

![image_alt](https://github.com/larasatinugroho/M6-Performance-Monitoring/blob/main/ERD%20-%20M6.png)

Given that the dataset reaches approximately >1 million rows for a single month (March 2026), an aggregated table was created to optimize performance for visualization purposes. This table is named hive_store.risk_analysis.ln_dashboard_m6_dailypaidup.

The SQL queries used to generate this table can be found at the following link:
[View SQL Queries](https://github.com/larasatinugroho/M6-Performance-Monitoring/blob/main/QUERY%20DAILY%20PAIDUP%20-%20M6.txt)


### Further improvement
- Allowing more interactive feature due to limitation of superset itself.
