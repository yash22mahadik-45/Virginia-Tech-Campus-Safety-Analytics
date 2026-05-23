# Virginia Tech Campus Safety Analytics

> **Academic Disclaimer:** This project is intended for academic and portfolio purposes only. It should not be interpreted as a production-ready campus safety system or as professional legal, law enforcement, transportation, accessibility, or policy advice.

This project applies business intelligence and data visualization methods to examine how Virginia Tech students experience safety on and around the Blacksburg campus. Using 114 student survey responses and Virginia Tech Police Department (VTPD) crime log data spanning January 2022 through March 2026, the analysis compares perceived safety with documented incident patterns across locations, times of day, transportation modes, demographic groups, and case outcomes.

The final Tableau story identifies where student concerns align with official records, where important gaps remain, and which campus safety interventions stakeholders should prioritize.

---

## Objective

The goal of this project is to evaluate how Virginia Tech students perceive safety on and around campus and compare those perceptions with official VTPD crime records.

The analysis focuses on understanding whether students' lived experiences align with documented campus incident patterns. It also examines how safety perceptions vary across gender, academic role, disability status, transportation mode, location, and time of day.

The project is designed to help campus stakeholders move from broad safety concerns to specific, evidence-backed actions — improving nighttime safety, strengthening communication about reporting outcomes, reviewing transportation reliability, and prioritizing high-concern campus locations.

---

## Methods

| Category | Techniques |
|---|---|
| Survey Analysis | Descriptive statistics, frequency distributions, subgroup comparisons |
| Crime Log Analysis | Incident counts, offense grouping, location analysis, disposition analysis |
| Spatial Analysis | Geocoding, latitude/longitude assignment, geographic hotspot mapping |
| Temporal Analysis | Time-of-day categorization, monthly trend analysis, year-over-year comparison |
| Data Preparation | Survey cleaning, offense normalization, disposition standardization |
| Data Transformation | Tableau Prep cleaning flow, offense splitting, unpivoting, Hyper file export |
| Visualization | Tableau dashboards, maps, bar charts, trend charts, word cloud, outcome flows |
| Storytelling | Seven-dashboard Tableau story connecting perceptions, records, and recommendations |

The analysis uses descriptive statistics rather than causal or inferential modeling. Survey findings are interpreted as directional, especially where subgroup sample sizes are limited. Cross-group comparisons are treated as directional rather than statistically definitive given that some subgroups — particularly non-binary respondents — are too small to support strong conclusions.

---

## Tools

- **Tableau Desktop 2024.1 or later** — final dashboard story and visual analytics
- **Tableau Prep Builder 2024.1 or later** — VTPD crime log cleaning and transformation workflow
- **Microsoft Excel** — survey data review and supporting tabular data
- **Python 3.10+** — VTPD crime log preprocessing, geocoding via Google Maps API, offense normalization via Claude API, disposition standardization, and Hyper file export preparation
- **Google Forms / Google Sheets** — survey collection and initial data review

> **Note on Python scripts:** The Python preprocessing pipeline is not included in this repository because it requires private API credentials (Google Maps Geocoding API and Anthropic Claude API). The pipeline stages are documented in detail in the Project Planning Worksheet. The cleaned outputs of that pipeline are the `.hyper` files included here, which can be used directly in Tableau without re-running any Python code.

---

## Repository Contents

### Tableau Files

> Requires Tableau Desktop 2024.1 or later and Tableau Prep Builder 2024.1 or later to open.

| File | Description |
|---|---|
| `VT_Campus_Safety_Dashboard_Story.twbx` | Final packaged Tableau workbook containing the complete seven-dashboard story. Data is embedded in the package — no external connection is required to open and explore it. |
| `VT_Campus_Safety_Tableau_Prep_Flow.tflx` | Tableau Prep flow used to clean, split, unpivot, and export VTPD crime log data. Connect its input step to `BIT_5424_Group_04_VTPD_Crime_Logs__Original_.hyper` before running. |

### Data Files

| File | Description |
|---|---|
| `VT_Campus_Safety_Survey_Data.xlsx` | Survey dataset collected from 114 Virginia Tech students. Includes demographic information, safety perceptions, transportation experiences, resource awareness, and reporting confidence. |
| `VT_Campus_Safety_Original_Crime_Logs.hyper` | Cleaned Tableau Hyper file preserving the one-row-per-incident structure of the VTPD crime log data. Used for dashboards where the unit of analysis is the incident. |
| `VT_Campus_Safety_Expanded_Crime_Logs.hyper` | Expanded Tableau Hyper file with one row per offense, produced by the Tableau Prep flow. Used for offense-level charts, filters, and breakdowns. |

### Project Documentation

| File | Description |
|---|---|
| `VT_Campus_Safety_Project_Planning_Worksheet.pdf` | Project motivation, audience, research questions, methodology, data cleaning approach, analysis goals, and planned outcomes. Includes a detailed description of the Python preprocessing pipeline stages. |
| `VT_Campus_Safety_Data_Collection_Worksheet.pdf` | Data collection plan, inquiry questions, measurement indicators, data sources, collection methods, and timing. |
| `VT_Campus_Safety_Storytelling_Worksheet.pdf` | Data story outline, hand-drawn dashboard storyboards, narrative structure, and final stakeholder call to action. |

---

## Data Sources

| Source | Coverage | Access |
|---|---|---|
| Group Survey Results | 114 VT student responses, Spring 2026 | Included — `BIT_5424_Group_04_Survey_Data.xlsx` |
| VTPD Monthly Crime Logs | January 2022 – March 2026 | Included — `.hyper` files above. Original PDFs at [police.vt.edu](https://police.vt.edu/crime-stats/crime-logs.html) |
| Virginia Tech 2024 Annual Security Report (Clery Report) | 2022–2024 three-year crime trends and institutional safety policies | Not included — accessed externally at [police.vt.edu/clery-reports](https://police.vt.edu/content/dam/police_vt_edu/clery-reports/2024%20ASR.pdf) |

---

## Dashboard Story

The final Tableau workbook is organized as a seven-part dashboard story that moves from student perceptions to institutional evidence to a stakeholder call to action.

| # | Dashboard | Description |
|---|---|---|
| 1 | Student Safety Perceptions | Shows how perceived safety varies across gender, academic role, and time of day. Establishes the core finding that safety is not experienced equally and that nighttime perceptions are markedly lower. |
| 2 | Resource Awareness & Reporting Confidence | Examines student awareness of campus safety resources and confidence that reported issues will be addressed. Introduces the communication gap between available resources and student trust. |
| 3 | Transportation Safety & Student Perceptions | Analyzes how walking, biking, buses, and personal vehicles shape students' safety experiences. Shows how transportation is a concrete, daily dimension of campus safety. |
| 4 | Geographic Distribution of Crimes | Maps VTPD crime incidents and identifies geographic hotspots on and around campus. Tests whether documented incident locations align with where students feel least safe. |
| 5 | Temporal Crime Patterns | Examines when incidents occur by time of day, month, and year. Validates the survey finding that nighttime carries higher documented risk. |
| 6 | Case Outcomes & Resolution Patterns | Shows how cases are resolved and how outcomes vary by offense type. Provides evidence for the gap between student confidence in reporting and actual resolution rates. |
| 7 | Perceptions vs. Reality | Compares student perceptions with documented VTPD records and summarizes stakeholder priorities. Supports the final call to action. |

---

## Key Findings

- Students report feeling less safe at night than during the day (86% feel safe at night vs. 95% during the day).
- Women report lower perceived safety than men, especially after dark.
- Confidence in reporting varies across academic roles; the overall average is approximately 53%.
- Awareness of campus safety and accessibility resources is uneven across the student population.
- Transportation — particularly Blacksburg Transit — is closely connected to students' lived experience of safety.
- VTPD incidents are geographically concentrated in specific residential and parking areas, with Pritchard Hall as the most frequently reported location.
- Evening and nighttime periods account for the largest share of documented incidents, consistent with student perceptions of when campus feels least safe.
- Several top offense types have resolution rates of 92–100% through arrest or referral to Student Conduct, substantially higher than students' self-reported confidence in reporting — indicating a communication gap rather than a performance gap.

---

## Recommendations

Based on the dashboard findings, this project recommends that Virginia Tech stakeholders prioritize five targeted actions:

1. **Pritchard Priority Plan** — Launch a focused safety review for the highest-incident residential area, with VTPD and Housing as joint owners.
2. **Quarterly case outcome updates** — Share resolution data with students each semester to close the gap between actual resolution rates and student confidence in reporting. Owner: VTPD and Student Affairs.
3. **Evening BT reliability review** — Assess Blacksburg Transit route coverage and reliability after 7 p.m. Owner: Blacksburg Transit.
4. **Gender-informed nighttime walking audit** — Conduct a structured audit of lighting, visibility, and route safety with attention to how different groups experience nighttime navigation. Owner: VT Facilities with DABS and SOC.
5. **Orientation safety brief** — Add a short safety-and-reporting module to fall orientation. Owner: Student Affairs.

Each recommendation should have a clear owner, timeline, and success metric so stakeholders can track whether safety conditions and student confidence improve over time. Suggested KPIs include nighttime safety perception scores, reporting confidence rates, case-resolution awareness, transportation disruption frequency, and location-specific incident trends.

---

## Getting Started

Users **with Tableau Desktop** can open the packaged workbook for the complete seven-dashboard story:

```
VT_Campus_Safety_Dashboard_Story.twbx
```

Users **with Tableau Prep Builder** can open the cleaning flow to inspect or re-run the data transformation pipeline:

```
VT_Campus_Safety_Tableau_Prep_Flow.tflx
```

Connect the flow's input step to `VT_Campus_Safety_Original_Crime_Logs.hyper` before running. The flow will regenerate `VT_Campus_Safety_Expanded_Crime_Logs.hyper` as output. The flow is documented visually in Figure 01 of the Project Planning Worksheet.

Users **without Tableau** can review the three project documentation PDFs and explore the survey data in `VT_Campus_Safety_Survey_Data.xlsx`.

---

## Authors

Josh Bae, Nikolas Cullifer, Tessa Hunt, Yash Mahadik, Mouni Surapaneni, & Ritika Venketesh

---

## License

Copyright © 2026 Josh Bae, Nikolas Cullifer, Tessa Hunt, Yash Mahadik, Mouni Surapaneni, and Ritika Venketesh. All rights reserved. This repository is intended for academic and portfolio reference only. The report, analysis files, datasets, visualizations, and supporting materials may not be copied, modified, redistributed, or used for commercial purposes without prior written permission from the authors.
