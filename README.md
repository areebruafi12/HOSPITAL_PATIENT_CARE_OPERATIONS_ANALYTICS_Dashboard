# Hospital Patient Care Operations Analytics

## Project Overview

This project focuses on analyzing hospital appointments, patient behavior, treatment performance, doctor workload, room activity, and operational data quality using **Microsoft Power BI**. The goal is to transform hospital operational datasets into meaningful business insights through interactive dashboards and visualizations.

## Project Objectives

- Analyze hospital appointment demand and service trends.
- Understand patient demographics, segmentation, and visit patterns.
- Monitor treatment performance, treatment status, waiting time, and cost.
- Evaluate doctor workload and specialty-level performance.
- Identify appointment issues, missing data, and operational exceptions.
- Analyze room activity and availability indicators.
- Support data-driven operational decisions using interactive dashboards.

## Tools & Technologies

- **Microsoft Power BI** – Dashboard development and data visualization
- **Power Query** – Data cleaning and transformation
- **DAX** – Measures, KPIs, and calculations
- **CSV Files** – Dataset storage
- **Microsoft Word** – Project documentation

## Project Structure

```text
HOSPITAL_PATIENT_CARE_OPERATIONS_ANALYTICS_Dashboard/
│
├── Dataset/
│   ├── patients.csv
│   ├── appointments.csv
│   ├── treatments.csv
│   ├── doctors.csv
│   ├── rooms.csv
│   └── date_table.csv
│
├── Screenshots PowerBI/
│   └── Dashboard screenshots
│
├── Hospital_Patient_Care_Operations_Project_Report.docx
├── Hospital_Patient_Care_Operations_Project_Report.pdf
├── Hospital_Patient_Care_Operations.pbix
└── README.md
```

*Note: Update filenames and folder names according to the actual files uploaded to the repository.*

## Dataset Description

The project uses six datasets:

| **Dataset** | **Description** |
|---|---|
| Patients | Patient details, demographics, city, age, and patient type |
| Appointments | Appointment dates, patient IDs, doctor IDs, service types, priority, booking channels, and estimated costs |
| Treatments | Treatment records, appointment references, doctor and room IDs, status, treatment cost, waiting time, and duration |
| Doctors | Doctor information, specialties, employment details, ratings, and active status |
| Rooms | Room IDs, room types, floor, equipment, capacity, and availability-related information |
| Date Table | Calendar attributes for time-based analysis |

## Data Cleaning & Preparation

The following data preparation activities were performed using Power Query:

- Reviewed column names, data types, and column quality.
- Applied Trim and Clean transformations to relevant text fields.
- Standardized categorical text values where appropriate.
- Investigated missing values in non-key columns.
- Inspected duplicate records and dimension key uniqueness.
- Removed confirmed duplicate records where appropriate.
- Checked relationships and key consistency between datasets.
- Prepared data for reporting and analysis.

*Note: Data cleaning should preserve legitimate repeated patient and entity references in transactional tables. Missing values should not automatically be replaced with zero.*

## Data Modeling

The data model connects the datasets using their relevant identifiers.

- Patients → Appointments
- Doctors → Appointments
- Appointments → Treatments
- Doctors → Treatments
- Rooms → Treatments
- Date Table → Appointments
- Date Table → Treatments (inactive relationship for treatment-date analysis)

The model uses relationships between dimension and fact tables to support cross-filtering and analytical reporting.

The Date Table supports year, quarter, month, and other calendar-based analysis. Treatment-date measures can use `USERELATIONSHIP` where required.

## Power BI Dashboards

### 1. Executive Summary Dashboard

Provides an overview of hospital operations through total appointments, treatment counts, unique patients, appointment trends, service type distribution, priority, booking channel, patient type, and weekend appointment patterns.

### 2. Patient Behaviour Analysis Dashboard

Analyzes patient demographics, average patient age, returning patients, appointments per patient, patient type distribution, service mix by patient type, top patients by appointment volume, and monthly appointment trends.

### 3. Treatment Performance Analysis Dashboard

Evaluates treatment trends, doctor treatment workload, treatment status distribution, average waiting time by doctor, treatment duration, and treatment cost by service type.

### 4. Doctor & Room Performance Dashboard

Analyzes doctor workload ranking, completed treatments by specialty, room-linked treatment counts, completed treatments by room type, average waiting time, and doctor performance details.

### 5. Appointment & Treatment Problems Analysis Dashboard

Highlights urgent appointments, non-completed treatments, missing estimated costs, appointment priority distribution, treatment status distribution, treatment cost by status, and appointment data quality exceptions.

### 6. Room Activity & Resource Insights Dashboard

Examines room inventory, active room indicators, rooms with treatment records, treatment status by room, and treatment duration across rooms.

*Note: Room availability and room activity do not independently establish actual room utilization.*

## Key Performance Indicators (KPIs)

- Total Appointments
- Total Treatments
- Unique Patients
- Average Patient Age
- Returning Patients
- Average Appointments per Patient
- Total Doctors
- Average Waiting Time
- Completed Treatments
- Non-Completed Treatments
- Urgent Appointments
- Missing Estimated Cost
- Active Rooms
- Rooms with Treatments
- Average Treatments per Used Room

## Key Business Insights

- **Appointment Demand:** Consultation is the largest displayed service category, with 1,183 appointments in the Executive Summary dashboard.
- **Patient Segmentation:** General patients represent 210 (52.5%), Insurance patients 107 (26.75%), and Corporate patients 83 (20.75%) of the displayed 400 unique patients.
- **Booking Channels:** App is the leading displayed booking channel, with 885 appointments.
- **Treatment Outcomes:** The current Treatment Performance dashboard displays 37 completed treatments out of 50 displayed treatment records.
- **Doctor Workload:** Doctor D071 leads the displayed completed-treatment ranking with 3 treatments.
- **Operational Exceptions:** The Problems Analysis dashboard highlights urgent appointments, non-completed treatments, and missing estimated costs.

*These observations reflect the current dashboard screenshots and displayed filter context. Validate the underlying measures and dataset counts before using the figures for final business reporting.*

## How to Use This Project

1. Download or clone this repository.
2. Open the `.pbix` file using Microsoft Power BI Desktop.
3. If required, update the dataset file paths in Power Query.
4. Refresh the data.
5. Explore the dashboards using slicers, filters, and interactive visuals.

## Dashboard Screenshots

Dashboard screenshots are available in the `Screenshots PowerBI` folder.

The report includes six dashboard pages covering executive reporting, patient behavior, treatment performance, doctor and room performance, operational problems, and room activity.

## Project Limitations & Data Quality Notes

- The current dashboard displays 50 treatments, while the original dataset description reports 3,505 treatment records. This discrepancy requires validation.
- Missing estimated cost counts should be reconciled before final reporting.
- Duplicate dimension keys must be investigated to maintain valid relationships.
- Room availability is not equivalent to room utilization. Actual utilization analysis requires occupied-time and available-capacity data.
- Returning patient metrics depend on the documented definition of a repeat visit.
- Patient information should be anonymized before publishing datasets or screenshots.

## Author

**Mohammad Areeb Ruafi**

GitHub: [areebruafi12](https://github.com/areebruafi12)

## Conclusion

This project demonstrates the practical application of Power BI, Power Query, DAX, data modeling, and interactive visualization to analyze hospital patient care operations.

By converting operational datasets into structured dashboards, the project helps explore appointment demand, patient behavior, treatment performance, doctor workload, room activity, and data quality issues while supporting informed operational decision-making.
