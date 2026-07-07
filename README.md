# 🩺 Patient Health Records EDA: Diagnoses, BMI & Cholesterol Trends

This project explores a synthetic healthcare dataset using Python and pandas. The data is loaded, inspected, cleaned, and analyzed through a full exploratory data analysis pipeline, then visualized to uncover patterns across diagnosis, age, gender, and treatment plans.

## Dataset

500 patient records with Age, Gender, Blood_Pressure, Heart_Rate, Cholesterol_Level, BMI, Diagnosis, Treatment_Plan, and Follow_Up_Date. The dataset shows uniformly bounded ranges and zero statistical outliers across all numeric fields, which indicates it is synthetically generated rather than drawn from real clinical records. It is best treated as a clean dataset for demonstrating an EDA and visualization pipeline, not for drawing real clinical conclusions.

## Steps Followed

1. **Data Loading** – Imported the CSV file with patient records.
2. **Initial Inspection** – Checked shape, data types, and summary statistics for numeric and categorical fields.
3. **Data Quality Checks** – Checked missing values, duplicate records, and implausible values (9 rows with Age = 0).
4. **Data Cleaning** – Filled missing Treatment_Plan values as "Unknown," flagged invalid ages rather than dropping them, converted data types, and created age group bins.
5. **Univariate Analysis** – Reviewed the distribution of each numeric variable and the counts of each categorical variable.
6. **Bivariate & Multivariate Analysis** – Compared BMI, cholesterol, and age against diagnosis, gender, and treatment plan, and reviewed a correlation matrix across all numeric fields.
7. **Outlier Detection** – Applied the IQR method to Blood_Pressure, Heart_Rate, Cholesterol_Level, and BMI.
8. **Visualization** – Built histograms, count plots, boxplots, a correlation heatmap, and a treatment plan doughnut chart.
9. **Summary Insights** – Consolidated diagnosis-level statistics and key findings.
10. **Export** – Saved the cleaned dataset and diagnosis summary table to CSV.

## Key Insights

**Correlation and outliers**
No strong linear relationships exist between Age, Blood_Pressure, Heart_Rate, Cholesterol_Level, and BMI. The IQR method flagged zero outliers across all four numeric fields, reinforcing that this dataset was generated within tight, uniform ranges rather than reflecting natural clinical variance.

**Diagnosis by gender**
Diagnosis counts are fairly evenly spread across Female, Male, and Other. Male patients have the highest counts for both Coronary Artery Disease and Hyperlipidemia, while Female patients have the highest count for Hypertension. Healthy cases are close to evenly split across all three gender categories.

**BMI, cholesterol, and age by diagnosis**
Averages are broadly similar across diagnosis groups, with only modest differences. Diabetes patients skew youngest at 43.0 average age, compared to 53.6 for Healthy patients. The Healthy group actually has the highest average BMI and second-highest average cholesterol of all groups, which is counterintuitive and consistent with the dataset being randomly generated rather than clinically realistic.

**Treatment plans**
Treatment varies by diagnosis: Coronary Artery Disease is most often tied to Surgery, Diabetes and Healthy to Medication, and Hypertension to Observation. Hyperlipidemia's most common recorded value is "Unknown." About 19% of all records (95 of 500) have no recorded treatment plan.

**Data quality**
Nine records have an Age of 0, which is not a plausible clinical age. These rows were flagged rather than dropped, so any age-based analysis should account for them.

## Conclusions

- This dataset behaves as a clean, synthetic dataset rather than real-world patient data, based on the absence of correlations and outliers.
- Diagnosis groups differ more by treatment pattern than by demographic or clinical averages.
- Treatment plan completeness (19% missing) is the most meaningful data quality gap in the dataset.
- The pipeline here, from cleaning through outlier detection to visualization, is built to generalize to real clinical datasets where these same checks would carry more diagnostic weight.

## Tools

Python, pandas, matplotlib, seaborn
