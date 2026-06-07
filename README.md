# 🏥 Hospital Emergency Room Dashboard

An end-to-end **Power BI analytics project** analyzing hospital emergency room operations across **9,216 patient records** to help stakeholders make data-driven decisions on patient management and service quality.

---

## 📊 Key KPIs

| KPI | Value |
|---|---|
| Total Patients | **9,216** |
| Avg. Wait Time | **35.3 min** ⚠️ *(target: ≤ 30 min)* |
| Satisfaction Score | **4.99 / 10** |
| Admission Rate | **50%** (4,612 admitted) |
| Patients Referred | **3,816** |

---

## 🖥️ Dashboard Pages

| # | Page | Purpose |
|---|---|---|
| 1 | **Monthly View** | KPIs, age groups, gender, race, referrals, day/hour heatmap |
| 2 | **Consolidated View** | Same metrics aggregated over a custom date range |
| 3 | **Patient Details** | Searchable patient-level grid with all key fields |
| 4 | **Key Takeaways** | Insights, patterns, and recommendations |

---

## 🔍 Key Insights

- ⏱️ Avg. wait time **(35.3 min)** exceeds the 30-minute target — staffing review needed at peak hours
- 😐 Satisfaction score of **4.99/10** correlates with high wait-time periods
- 🏥 **General Practice (1,840)** and **Orthopedics (995)** receive the most ER referrals
- 👥 Near-equal admission split — **50% admitted**, 50% treated & discharged

---

## 🧮 DAX Measures

```DAX
No of Patients = COUNT(Hospital_ER_Data[Patient Id])

Avg Wait Time = AVERAGE(Hospital_ER_Data[Patient Waittime])

% Seen Within 30 Mins =
    DIVIDE(
        COUNTROWS(FILTER(Hospital_ER_Data, Hospital_ER_Data[Patient Waittime] <= 30)),
        [No of Patients]
    )

No of Patients Referred =
    COUNTROWS(FILTER(Hospital_ER_Data, Hospital_ER_Data[Department Referral] <> "None"))
```

---

## 🚀 How to Use

1. Clone the repo and open `Hospital_dashboard.pbix` in **Power BI Desktop**
2. If prompted, update the data source path to `data/Hospital_ER_Data.csv`
3. Click **Refresh** and explore all 4 dashboard pages with the slicers

---

## 🛠️ Tools Used

`Power BI Desktop` · `Power Query ` · `DAX` · `CSV` · `GitHub`

---

