# 🏥 Emergency Room Intelligence Dashboard

![Final Dashboard](screenshots/final_dashboard.png)

[![Watch the video](screenshots/video_thumbnail.png)](https://your-video-link-here)

An interactive **Excel dashboard** to analyze Emergency Room (ER) operations and support hospital decision-making using **Power Query**, **Power Pivot**, and **DAX**.

---

## 🎯 Project Purpose

To create a data-driven **Emergency Room Intelligence Dashboard** that improves patient management efficiency and delivers actionable insights for hospital stakeholders. The dashboard helps analyze ER performance metrics, detect bottlenecks, and track service quality over time.

---

## 🛠 Tools & Technologies

- ✅ Microsoft Excel (with Power Query & Power Pivot)
- ✅ Pivot Tables & Pivot Charts
- ✅ DAX (Data Analysis Expressions)
- ✅ Calendar Table for time intelligence
- ✅ Custom Healthcare-themed Color Palette

---

## 📊 Key KPIs

| KPI | Description |
|-----|-------------|
| **Number of Patients** | Total patients per day with area sparkline to spot peak activity |
| **Average Wait Time** | Average daily patient wait time; highlights operational delays |
| **Patient Satisfaction Score** | Tracks daily average satisfaction to monitor service quality |

---

## 📈 Additional Visuals

- Patient Admission Status (Admitted vs Not Admitted)
- Patient Age Distribution (10-year age bands)
- Timeliness (% seen within 30 mins)
- Gender Analysis (Male vs Female)
- Department Referrals (Top referred departments)

---

## 🔗 Data Model

**Tables:**
- `Calendar`: Dynamic date table (generated with Power Query)
- `Emergency Room Data`: Main patient data (Patient ID, Date, Department, etc.)

**Relationship:**
- `Calendar[Date]` → `Emergency Room Data[Patient Admission Date]`

---

## 🧮 DAX Calculated Columns

### 🧓 Age Group

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
