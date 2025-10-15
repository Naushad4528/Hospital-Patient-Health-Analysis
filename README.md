# Hospital Patient Health Analysis

**Power BI Dashboard** — *Hospital Patient Health Analysis*

---

## Project Overview

This Power BI project visualizes health metrics and medical-condition trends for a hospital dataset of **~30,000 patients**. The dashboard helps identify high-risk groups, monitor clinical KPIs, and support data-driven decisions for clinical teams and administrators.

## Key Metrics & KPIs

* **Total Patients:** 30,000
* **Average BMI:** 28.48
* **Average Glucose:** 105.08
* **Average Length of Stay:** 4.41 days

## Visualizations

The dashboard contains the following pages / visuals:

1. **Title & KPI Row** — Project title and high-level KPI cards (Total Patients, Avg BMI, Avg Glucose, Avg Length of Stay).
2. **Blood Pressure by Medical Condition** — Horizontal bar chart comparing average blood pressure across medical conditions (Hypertension, Diabetes, Cancer, Asthma, Obesity, Arthritis, Healthy, N/A).
3. **Gender Distribution** — Pie chart showing distribution between Male, Female and N/A.
4. **HbA1c by Age Group** — Column chart comparing average HbA1c values across age groups (`<20`, `20-39`, `40-59`, `60+`).
5. **Stress Level by Medical Condition** — Column chart showing average stress levels by condition.
6. **Total Patients by Medical Condition** — Donut chart showing patient share per condition.
7. **Avg BMI by Age** — Line chart showing BMI trend across ages.

Screenshot: `assets/Dashboard.png` (included in repository)

## Data

* Source: (Replace with your data source description — e.g., de-identified hospital records / synthetic dataset / CSV export).
* File(s): `data/hospital_patients.csv` (expected)
* Important columns used:

  * `PatientID`
  * `Age`
  * `Gender`
  * `MedicalCondition`
  * `BloodPressure`
  * `BMI`
  * `Glucose`
  * `HbA1c`
  * `StressLevel`
  * `LengthOfStay`

> ⚠️ Ensure all patient data is de-identified and handled according to applicable privacy regulations (HIPAA, GDPR, local laws).

## Data Preparation & Modeling

* Cleaned missing values and standardized medical condition categories.
* Created age groups (`<20`, `20-39`, `40-59`, `60+`) for grouped analysis.
* Star schema approach: a central `Patients` fact table with related dimension tables (e.g., `Dim_AgeGroup`, `Dim_Condition`) where useful.

## DAX Measures (Examples)

```dax
Total Patients = DISTINCTCOUNT(Patients[PatientID])
Avg BMI = AVERAGE(Patients[BMI])
Avg Glucose = AVERAGE(Patients[Glucose])
Avg Length of Stay = AVERAGE(Patients[LengthOfStay])
Patients by Condition = COUNTROWS(FILTER(Patients, Patients[MedicalCondition] = "Hypertension"))
```

(Adapt measures as needed for your dataset.)

## How to Run / Recreate

1. Clone the repository.
2. Place your dataset in `data/hospital_patients.csv` or update the Power BI queries to point to your source.
3. Open `Hospital_Patient_Health_Analysis.pbix` in Power BI Desktop.
4. Refresh the data model and verify relationships.
5. Publish to Power BI Service (optional).

## Design Choices & UX Notes

* Contrasting KPI cards at the top for quick executive view.
* Condition-focused visuals to quickly spot which conditions have higher average blood pressure, stress, or share of patients.
* Time/age trend visualization to track BMI and HbA1c changes across age groups for early intervention planning.

## Recommendations & Next Steps

* Add interactive filters for hospital unit, admission type, or time period.
* Include outcome metrics (readmission rate, mortality rate) if available.
* Implement role-based views (Clinician, Admin, Executive) to tailor insights.
* Use row-level security when deploying with identifiable or sensitive datasets.

## Folder Structure (suggested)

```
/ (root)
├─ README.md
├─ Hospital_Patient_Health_Analysis.pbix
├─ data/
│  └─ hospital_patients.csv
├─ assets/
│  └─ Dashboard.png
└─ docs/
   └─ data_dictionary.md
```

## License

This project is released under the MIT License. See `LICENSE` for details.

## Contact

Created by: **Naushad Saifi**

Connect: [[LinkedIn](https://www.linkedin.com](https://www.linkedin.com/public-profile/settings?trk=d_flagship3_profile_self_view_public_profile))
