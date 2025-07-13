#  Emergency Room Intelligence Dashboard
![Dashboard Demo](screenshots/dashboard_demo.gif)

An interactive **Excel dashboard** to analyze Emergency Room (ER) operations and support hospital decision-making using **Power Query**, **Power Pivot**, and **DAX**.

---

## Download ER Intelligence Dashboard

You can download the **ER Intelligence Dashboard** Excel file below:

**[Download ER_Intelligence_Dashboard.xlsx](./ER_Intelligence_Dashboard.xlsx)**

---

##  Project Purpose
To create a data-driven **Emergency Room Intelligence Dashboard** using **10,000 patient records** that improves patient management efficiency and delivers actionable insights for hospital stakeholders. The dashboard helps analyze ER performance metrics, detect bottlenecks, and track service quality over time.

---

##  Tools & Technologies
-  Microsoft Excel (with Power Query & Power Pivot)
-  Pivot Tables & Pivot Charts
-  DAX (Data Analysis Expressions)
-  Calendar Table for time intelligence
-  Custom Healthcare-themed Color Palette

---

##  KPIs
| KPI | Description |
|-----|-------------|
| **Number of Patients** | Total patients per month to spot peak activity |
| **Average Wait Time** | Average monthly patient wait time; highlights operational delays |
| **Patient Satisfaction Score** | Tracks monthly average satisfaction to monitor service quality |

---

##  Additional Visuals
- Patient Admission Status (Admitted vs Not Admitted)
- Patient Age Distribution (10-year age bands)
- Timeliness (seen within 30 mins)
- Gender Analysis (Male vs Female)
- Department Referrals (Top referred departments)

---

##  Data Model
**Dataset Size:** The dashboard is built using a dataset of **10,000 records.**

**Tables:**
- `Calendar`: Dynamic date table (generated with Power Query)
- `Emergency Room Data`: Main patient data (Patient ID, Date, Department, etc.)

**Relationship:**
- `Calendar[Date]` → `Emergency Room Data[Patient Admission Date]`

---

##  DAX Calculated Columns

###  Age Group
```dax
= FORMAT(
    INT('Emergency Room Data'[Patient Age] / 10) * 10,
    "00"
    )
& "-" &
FORMAT(
    INT('Emergency Room Data'[Patient Age] / 10) * 10 + 9,
    "00"
)
```
Groups patient age into 10-year intervals (e.g., 20–29, 30–39).

###  Patient Attend Status
```dax
= IF('Emergency Room Data'[Patient Waittime] > 30, "Delay", "On Time")
```
Categorizes whether patients were attended to within 30 minutes.

---

##  Calendar Table (Power Query)
```powerquery
= List.Dates(#date(2023, 01, 01), 700, #duration(1, 0, 0, 0))
```

**Additional columns added:**
- Year, Month, Quarter, Week Number, Day Name, IsWeekend

---

##  Color Palette Used
| Purpose | Hex Code | Description |
|---------|----------|-------------|
| Background | `#f1f9ff` | Very light blue |
| Chart Base | `#ccecee` | Soft aqua |
| Primary Bars | `#14967f` | Teal green |
| Comparison Bars | `#14967f` | Teal green |
| KPI Background  | `#e2fcd6` | Light green |

---

## 📸 Screenshots

###  Final Dashboard
![Final Dashboard](screenshots/final_dashboard.png)

###  Daily Emergency Room Visits
![Final Dashboard](screenshots/daily_er_visits.png)

###  Daily Average Patient Wait Time
![Final Dashboard](screenshots/avg_wait_time.png)

###  Daily Average Patient Satisfaction Score
![Final Dashboard](screenshots/score.png)

###  Data Model View (Relationships)
![Data Model](screenshots/data_model.png)

###  Calendar Table (Power Query)
![Calendar Table](screenshots/calendar_table.png)

###  Applied Steps (Power Query)
![Power Query Steps](screenshots/power_query_steps.png)

###  DAX Calculated Columns
![DAX Measures](screenshots/dax_measures.png)

---


## 📂 Folder Structure
```
📁 emergency-room-intelligence-dashboard/
├──  README.md
├──  ER_Intelligence_Dashboard.xlsx
└── 📁 screenshots/
    ├── avg_wait_time.png
    ├── calendar_table.png
    ├── daily_er_visits.png
    ├── dashboard_demo.gif
    ├── data_model.png
    ├── dax_measures.png
    ├── final_dashboard.png
    ├── power_query_steps.png
    └── score.png

```

---

##  Acknowledgments
Created by **Durgesh Nautiyal** as a portfolio project to demonstrate Excel-based reporting and healthcare analytics.

---

## 📞 Contact Me
📩 durgeshnautiyal11@gmail.com     
🔗 [LinkedIn](https://www.linkedin.com/in/durgesh-nautiyal-95a866223/)
