# What Drives Patient Experience?
## An Analysis of U.S. Hospital HCAHPS Data


📌 **Project Overview**


Patient experience is an important indicator of hospital performance and can influence whether patients would recommend a hospital to others.
This project analyzes CMS HCAHPS (Hospital Consumer Assessment of Healthcare Providers and Systems) data to identify which aspects of the inpatient experience are most strongly associated with patients' willingness to recommend a hospital.
Business Question:  
What aspects of the inpatient patient experience are most associated with patients' willingness to recommend a hospital?

Tools: SQLite • SQL • Tableau


📊 **Data**


The analysis uses the 2026 CMS HCAHPS Hospital dataset, covering survey results from October 1, 2024 through September 30, 2025.
The raw dataset contains:
- 4,790 hospitals
- 68 HCAHPS measures
- 56 states/areas
- Hospital-level HCAHPS survey results

  Data source: CMS HCAHPS Hospital Data


**🔎 Analysis**


The analysis focused on six patient experience measures and their relationship with hospital recommendation scores:
Patient Experience Measure	Analysis Focus
Nurse Communication	Communication with nurses
Doctor Communication	Communication with doctors
Medication Communication	Communication about medications
Discharge Information	Information provided at discharge
Cleanliness	Hospital cleanliness
Quietness	Quietness of the hospital environment


The primary outcome was the hospital's **linear recommendation score.**


The overall hospital rating measure was intentionally excluded as a primary driver because it represents another broad measure of overall patient experience.


💡 **Key Findings**


**1. Nurse communication showed the strongest association**


Nurse communication had the strongest observed relationship with recommendation scores:
Correlation: 0.81
Doctor communication followed at 0.75, while medication communication and discharge information also showed relatively strong associations.


**2. Communication measures showed the strongest relationships**


Measure	Correlation with Recommendation
Nurse Communication	0.807
Doctor Communication	0.749
Medication Communication	0.727
Discharge Information	0.711
Quietness	0.574
Cleanliness	0.564


**3. Higher-recommended hospitals scored higher across every experience measure**

   
Hospitals in the highest recommendation quartile had higher average scores across all six patient experience measures.
The largest differences between the highest and lowest recommendation groups were:
- Medication communication: +8.75 points
- Quietness: +7.95 points
- Discharge information: +7.00 points
- Cleanliness: +6.28 points
- Nurse communication: +5.06 points
- Doctor communication: +4.86 points

  
**4. Recommendation scores were concentrated in the mid-to-high 80s**
The average hospital recommendation score was 87.0, with scores concentrated primarily in the mid-to-high 80s.


🧹 **Data Quality**


One important data-quality finding was that HCAHPS scores were not available for every hospital.


Of the 4,790 hospitals:


**- 3,183 hospitals (66.5%) had scores available for all seven selected measures.**
**- 1,607 hospitals (33.5%) did not have scores available for the selected measures.**


Values such as "Not Available" and "Not Applicable" were treated as missing values rather than zeros.
This distinction was important because treating unavailable scores as zero would incorrectly lower hospital performance measures.


🗃️ **SQL Analysis**


The SQL portion of this project includes:


- Dataset validation
- Hospital and measure counts
- Data-quality checks
- Missing-value analysis
- Hospital-level data transformation
- Average patient experience scores
- Correlation analysis
- Recommendation quartile analysis
- State-level comparisons
- Survey-volume analysis
The raw HCAHPS data was transformed from hospital/measure-level records into a hospital-level analytical table to support the analysis.


📈 **Tableau Dashboard**


The analysis was presented in an interactive Tableau dashboard featuring:


- Nurse communication vs. recommendation
- Recommendation score distribution
- Survey volume and recommendation comparison
- High- vs. low-recommended hospital comparison
- Key performance indicators

  
**Tableau Public**
[View the interactive Tableau dashboard](https://public.tableau.com/views/HospitalExperienceHCAHPS/HospitalExperienceDash?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)


🛠️ **Tools Used**

- **SQL / SQLite** — data preparation, transformation, validation, and analysis
- **SQLiteStudio** — database management
- **Tableau** — data visualization and dashboard development
- **GitHub** — project documentation and version control

  
⚠️** Important Note**

This analysis identifies associations, not causal relationships.
A strong correlation between an experience measure and recommendation score does not establish that improving that measure alone will cause recommendation scores to increase.
The findings are intended to identify areas that may warrant further investigation by healthcare leaders and analysts.


🎯 **Business Takeaway**


The analysis suggests that communication-related aspects of the inpatient experience—particularly nurse communication—are the most strongly associated with patients' willingness to recommend a hospital.
For healthcare leaders, these findings can help identify patient-experience areas that may deserve additional attention and deeper analysis.
