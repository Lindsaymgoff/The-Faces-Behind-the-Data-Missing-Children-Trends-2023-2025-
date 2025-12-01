# The-Faces-Behind-the-Data-Missing-Children-Trends-2023-2025-
Data-driven analysis of missing children from 2023–2025, uncovering demographic disparities and high missing-child rates among Native American and Black youth.
📘 Missing Children Data Analysis (2023–2025)
By: Lindsay Goff

Presentation: https://www.canva.com/design/DAG6NxwzquI/7NR4ylNocuGVM7NFAuLhMQ/view

 Project Overview

This project analyzes demographic patterns among missing children in the United States between 2023–2025. The project was inspired by growing concerns that Native American and African American children are disproportionately represented among missing-child cases, while receiving less media coverage and public awareness compared to White/Caucasian children.

To understand these disparities, this project examines missing-child trends by
age, gender, ethnicity, and state, and incorporates national child population data to calculate missing-child rates per 100,000.

This rate-based approach reveals deeper insights into which demographic groups are most affected and how reporting limitations (especially missing Hispanic ethnicity data in federal systems) impact visibility.

 Project Objectives

Identify demographic patterns among missing children from 2023–2025.

Examine disparities affecting Native American and African American children.

Analyze geographic variation across states to identify high-risk regions.

Compare missing-child raw counts vs population-adjusted rates.

Highlight gaps in media visibility, federal reporting, and demographic inclusion.

 Data Sources
Primary Data

FBI NCIC – 2024 Missing and Unidentified Person Statistics

NAMUS – Current Missing Juveniles (2020–2025)

NCMEC Missing Kids Database – 2023–2024 cases

Kids Count Data Center – Child population by race/ethnicity

User-compiled datasets (state, age, gender, ethnicity)

Citations

Annie E. Casey Foundation Data Center – Child Population by Race and Ethnicity

FBI – 2024 NCIC Missing & Unidentified Person Statistics

NAMUS Dashboard

NCMEC – 2023 and 2024 Our Impact Reports

 Key Research Questions

Which age groups have the highest missing-child counts?

Which ethnicities show the largest disparities or increases over time?

How do missing-child rates compare for Native American, Black, White, and Hispanic children?

Which states report the highest numbers and most consistent patterns?

Did any demographic group show a significant rise or decline from 2023–2025?

📊 Major Findings
1️⃣ Age Trends

Adolescents (12–17) account for the majority of missing cases across all groups.

Older teens show especially elevated numbers among females.

2️⃣ Ethnicity Trends (Counts & Rates)

Raw totals showed disparities, but population-adjusted rates revealed deeper inequities.

Missing Juvenile Rate (per 100,000 children)

Using the formula:
(Missing Children ÷ Total Children in Group) × 100,000

2023 → 2024 Rates

Native American/Pacific Islander: 70.1 → 124.0

Black: 66.3 → 101.63

Hispanic/Latino: 29.1 → 26.42

White: 22.62 → 23.60

Asian: 3.0 → 3.78

➡️ Native American children are the most disproportionately affected.
➡️ Black children show a significant and growing burden.
➡️ Hispanic children become visible only when incorporated from external datasets.

3️⃣ Gender Trends

Females, especially ages 13–17, are consistently at higher risk in multiple ethnic groups.

4️⃣ Geographic Trends

Certain states show clustering of high numbers, influenced by:

population size

urban vs rural distribution

Tribal land jurisdiction

reporting consistency

SQL Queries Used
A. Total Missing Children by Ethnicity
SELECT ethnicity, COUNT(*) AS total_missing
FROM missing_children
GROUP BY ethnicity
ORDER BY total_missing DESC;

B. Missing Children by State
SELECT state, COUNT(*) AS total_missing
FROM missing_children
GROUP BY state
ORDER BY total_missing DESC;

C. Missing Children by Gender
SELECT gender, COUNT(*) AS total_missing
FROM missing_children
GROUP BY gender
ORDER BY total_missing DESC;

D. Missing Children by Year
SELECT year_missing, COUNT(*) AS total_missing
FROM missing_children
GROUP BY year_missing
ORDER BY year_missing;

E. Gender + Ethnicity Breakdown
SELECT "Biological Sex" AS gender,
       "Ethnicity" AS ethnicity,
       COUNT(*) AS missing_count
FROM missing_children
GROUP BY "Biological Sex", "Ethnicity"
ORDER BY "Biological Sex", "Ethnicity";

F. Missing Juvenile Rate Calculation
SELECT mc.ethnicity,
       mc.total_missing,
       pop.child_population,
       (mc.total_missing::FLOAT / pop.child_population) * 100000 AS missing_rate
FROM missing_counts mc
JOIN child_population pop USING (ethnicity)
ORDER BY missing_rate DESC;

Conclusion

The analysis of missing children from 2023–2025 reveals:

Adolescents (12–17) are the most affected age group.

Native American children have the highest missing-child rate in the U.S.

Black children also face significantly elevated and rising rates.

Hispanic children appear underrepresented due to missing federal reporting categories.

Major disparities are hidden unless population-based rates are examined, rather than raw totals.

These findings demonstrate the need for improved reporting, equitable media coverage, and targeted assistance programs.

Proposed Solutions
1. Improve National Data Reporting

Include Hispanic/Latino as a required demographic category.

Add more specific Indigenous classifications.

Standardize demographic fields across all federal systems.

2. Increase Targeted Prevention Resources

Focus support in:

Tribal communities

Predominantly Black urban neighborhoods

High-risk states

Through:

culturally informed outreach

youth support services

community safety programming

3. Strengthen Media Coverage Equity

Encourage equal visibility for missing children from all backgrounds.

Promote national awareness campaigns focusing on the most at-risk groups.

4. Expand State + Tribal Collaboration

Improve coordination between state law enforcement and Tribal agencies.

Support cross-jurisdictional reporting and Tribal AMBER Alerts.

Ensure cases are uploaded and updated consistently.

📎 Presentation Link

View the full presentation on Canva:
https://www.canva.com/design/DAG6NxwzquI/7NR4ylNocuGVM7NFAuLhMQ/view

👤 Author
Lindsay Goff
Healthcare & Social Impact Data Analyst
Specializing in public health, equity, and human rights analytics.

Lindsay Goff
Healthcare & Social Impact Data Analyst
Specializing in public health, equity, and human rights analytics.
