# 🗳️ Ogun State Election Data Project

*Prepared by:* Osolake Mariam Omotolani  
*Tools Used:* Python (Pandas), Google Sheets, Geopy  
*Date:* October 2024  

---

## 📌 Project Overview

This project focuses on improving the *accuracy, **consistency, and **transparency* of election data for *Ogun State, Nigeria*.

The work was completed in two major stages:

1. *Data Cleaning & Preparation*  
2. *Outlier Detection & Geospatial Analysis*

The final output is a *clean, **geocoded, and **analysis-ready* dataset aimed at supporting the detection of possible electoral anomalies.

---

## 🎯 Project Objectives

- Clean and organize the Ogun State election dataset.  
- Assign accurate geographic coordinates to each polling unit.  
- Identify polling units with suspicious voting patterns using statistics & geospatial analysis.  
- Provide insights to improve election data quality and integrity.

---

## 📂 Dataset Overview

The dataset contains:

- *4,069 polling units*
- *19 columns* of electoral & verification-related information
- 

### Key Fields

- *PU-Code, PU-Name*
- *LGA, Ward*
- *Registered_Voters, Accredited_Voters*
- *APC, LP, PDP, NNPP* vote counts
- *Result Sheet indicators*
- *Latitude & Longitude* (added during cleaning)

---

## 🔧 Data Cleaning & Preparation

### ✔ Standardized Location Names  
Example: "OGUN" → "Ogun State, Nigeria"

### ✔ Corrected Abbreviations  
Example: "PRY." → "PRIMARY"

### ✔ Handled Missing/Ambiguous Entries  
Replaced "UNKNOWN" and similar placeholders.

### ✔ Removed Duplicates & Extra Spaces  

### ✔ Validated Numeric Fields  
Ensured only valid numbers in key vote count columns.

---

## 📘 Supporting Files
This Google Sheet contains the calculations, geospatial formulas, neighbor detection, and additional cleaning steps used during this project.

🔗 *Analysis Workbook (Google Sheets):* [Click here to view]
https://docs.google.com/spreadsheets/d/1ldLBBhuCVobA6bvO6O3sjS73HfPalM3h/edit?usp=sharing&rtpof=true&sd=true

## 🛠 Tools & Methods

- *Python (Pandas):* cleaning, validation, filtering  
- *Geopy:* calculating distances for geospatial comparison  
- *Google Sheets:* supporting verification & Haversine calculations  

---

## 🌍 Geospatial Analysis & Outlier Detection

Outliers were detected by comparing each polling unit to nearby units within a *1 km radius*.

### 1️⃣ Neighbor Identification

- Based on latitude & longitude  
- Units within *1 km* → Neighbour  
- Implemented using:
  - Haversine formula (Sheets)
  - geopy.distance.geodesic (Python)

### 2️⃣ Outlier Score Formula
Outlier Score = |PU Votes – Mean Neighbor Votes| / Standard Deviation


###  3️⃣ Ranking

Top outliers (highest deviations) were reviewed per party.

📊 Findings

| Party | Polling Unit (PU-Code) | LGA | Outlier Score | Remark |
|-------|--------------------------|------------------|---------------|-------------------------------------------------------------|
| APC   | PU-001 (Abeokuta North) | Abeokuta North    | 4.21          | Recorded 520 votes while neighbors averaged 150 unusually high. |
| LP    | PU-157 (Ward 3)         | Ijebu Ode         | 3.76          | LP performance here was significantly higher than nearby units. |
| PDP   | PU-089 (Ward 1)         | Sagamu            | 3.54          | PDP scored nearly triple the surrounding units’ average. |
| NNPP  | PU-026                  | Ijebu North       | 3.12          | NNPP recorded unusually low votes compared to close neighbors. |

🔍 Insights
	•	Some units show strong deviations → possible inflation/suppression/reporting errors
	•	Majority of units show normal patterns
	•	Outliers should be flagged for deeper investigation
  

⚠️ Limitations
	•	1 km radius may not reflect real catchment areas
	•	Some coordinates needed manual correction
	•	Analysis does not consider demographic or political context


📌 Summary Insights
	•	Dataset is now fully cleaned, validated, and geocoded
	•	Outlier detection offers strong leads for election audits
	•	Demonstrates how modern analytics enhances election transparency


✅ Recommendations
	1.	Standardize data entry during elections
	2.	Automate validation at point of data capture
	3.	Conduct routine geospatial audits
	4.	Encourage open data for analyst review


🏁 Conclusion

This project successfully prepared and analyzed the Ogun State election dataset using data cleaning, geospatial techniques, and statistical outlier detection.
It contributes to improving election integrity, trust, and transparency in Nigeria.
