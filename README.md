# National Saudi Hospital — Power BI Analytics Portfolio

## Project overview

An interactive six-page **Power BI hospital analytics report** designed to support management decision-making across patient access, revenue cycle, bed capacity, workforce operations, and quality of care.

The project uses a **synthetic demonstration dataset**, not live patient or hospital records. Hospital and organizational names are used for portfolio presentation; the metrics should not be treated as verified real-world operating results.

**Analysis period:** January–September 2026  
**Locations:** Riyadh Central, Jeddah West, Dammam Care  
**Currency:** Saudi Riyal (SAR)  
**Tools:** Power BI Desktop, Power Query, DAX, data modelling, Microsoft Excel

## Business objective

Build one integrated view of hospital performance to help a leadership team:

- Monitor patient demand and clinic access.
- Understand revenue, collections, unpaid balances, and insurance exposure.
- Identify bed capacity and occupancy pressure.
- Track staffing, overtime, absences, and scheduled-versus-actual hours.
- Assess patient experience, quality metrics, and safety signals.

## Report pages

| # | Dashboard | Key questions addressed |
|---|-----------|--------------------------|
| 1 | **Executive Overview** | What is the overall performance across hospitals? |
| 2 | **Patient Flow & Access** | Where are patient volumes, readmissions, and waiting-time pressures? |
| 3 | **Revenue Cycle & Insurance** | How do revenue, collections, outstanding payments, and insurance risks compare? |
| 4 | **Bed Capacity & Utilisation** | How efficiently are beds being used across hospitals and months? |
| 5 | **Workforce Operations** | Are workforce hours, absence rates, and overtime under control? |
| 6 | **Quality & Patient Experience** | What do satisfaction, infections, incidents, and compliance show? |

All report pages use a consistent navy/teal theme, hospital and month slicers, and a custom hamburger-menu navigation panel with open/close bookmarks.

## Selected measures and example results

The following are example values from the exported all-hospitals report; they reflect the synthetic dataset and may change when slicers are applied.

| Area | Example indicator | Value |
|------|-------------------|------:|
| Executive | Total patient visits | 2,400 |
| Executive | Total revenue | SAR 22.04M |
| Patient experience | Patient satisfaction | 64.44% |
| Patient access | Average clinic wait | 68 minutes |
| Finance | Total collections | SAR 14.78M |
| Finance | Outstanding payments | SAR 7.26M |
| Capacity | Bed capacity | 516 beds |
| Capacity | Latest occupied beds | 420 beds |
| Capacity | Latest occupancy | 81.40% |
| Workforce | Staff shifts | 1,600 |
| Workforce | Absence rate | 6.69% |
| Quality | Hospital-acquired infections | 315 |
| Quality | Safety incidents | 438 |

> **Metric definitions matter:** The executive occupancy percentage over the reporting period and the latest occupancy snapshot represent different measures. Clearly distinguish them when explaining the report.

## Data model and analysis approach

A dimensional model combines hospital, department, and date dimensions with operational fact tables for encounters, claims, invoices, bed census, staff shifts, quality measures, and patient feedback.

Key techniques include:

- Data cleaning and transformation in Power Query.
- Relationships between dimensions and fact tables.
- DAX measures for ratios, trend analysis, and KPIs.
- Cross-filtering with hospital and YearMonth slicers.
- Conditional-formatting logic for bed occupancy thresholds:
  - **Green:** below 80%
  - **Yellow:** 80%–85%
  - **Red:** above 85%
- Bookmarks and the Selection pane for compact navigation.

### Illustrative KPI logic

- **Bed occupancy %** = Occupied beds ÷ Total bed capacity.
- **Absence rate %** = Absent shifts ÷ Total staff shifts.
- **Infection rate per 1,000 patient-days** = Hospital-acquired infections ÷ Patient-days × 1,000.
- **Outstanding payments** = Net revenue − Collected amount (using consistent underlying invoice definitions).

## Illustrative business observations

- Patient satisfaction is 64.44% in the selected all-hospitals view, indicating an opportunity to investigate feedback themes and departments.
- Collections (SAR 14.78M) and outstanding payments (SAR 7.26M) should be monitored alongside the revenue definitions used in the report.
- Latest bed occupancy is 81.40%; the heatmap draws attention to hospital-months exceeding the 85% threshold.
- Staff absence and overtime should be interpreted together to assess possible workload pressures.

These are descriptive observations from demonstration data, not causal conclusions or claims about an actual hospital.

## How to view the project

### Power BI Desktop

1. Install **Power BI Desktop**.
2. Open the `.pbix` file (when supplied in the project repository).
3. Use the HospitalName and YearMonth filters.
4. Click the **☰** button to open the pop-up page navigation menu; click **X** to close it.
5. Use **Ctrl + click** when testing navigation button actions in edit mode.

### Without Power BI Desktop

Open the exported `Saudi_Hospital.pdf` or view the page screenshots in the `Screenshots/` folder. **PDFs and screenshots are not interactive.**

## Suggested repository layout

```text
National-Saudi-Hospital-PowerBI/
├── README.md
├── Saudi_Hospital.pbix           
├── Saudi_Hospital.pdf
├── Screenshots/
│   ├── 01_Executive_Overview.png
│   ├── 02_Patient_Flow.png
│   ├── 03_Revenue_Cycle.png
│   ├── 04_Bed_Capacity.png
│   ├── 05_Workforce_Operations.png
│   └── 06_Quality_Patient_Experience.png
└── Data/                       
```


*Portfolio demonstration project. Prepared using Power BI Desktop.*

