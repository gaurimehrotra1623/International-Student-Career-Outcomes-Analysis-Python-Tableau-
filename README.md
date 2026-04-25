# International Student Career Outcomes Analysis

## Overview
This project analyzes the career outcomes of international graduates. The goal is to explore the impact of various factors like education level, field of study, language proficiency, and GPA on their employment status, salary, and job sector. The project includes data cleaning in Python and a comprehensive dashboard created in Tableau.

## Project Structure
- `data/`: Contains the raw and cleaned datasets.
  - `student_dataset.csv`: The original, raw data.
  - `cleaned_dataset.csv`: The processed data ready for visualization.
- `notebooks/`: Contains Jupyter Notebooks used for the analysis.
  - `Graduation_data.ipynb`: Python code for exploring and cleaning the raw dataset.
- `tableau/`: Contains the Tableau workbook.
  - `International Graduate Career Outcomes Dashboard.twb`: The interactive dashboard.
- `visuals/`: Contains images of the dashboard.
  - `Dashboard.png`: A static snapshot of the completed dashboard.

## Data Dictionary
The initial dataset (`student_dataset.csv`) contains the following columns:
- **Country_of_Origin**: The student's home country.
- **Education_Level**: The highest level of education achieved (e.g., Bachelor's, Master's, PhD).
- **Field_of_Study**: The primary area of study (e.g., IT, Arts, Engineering).
- **Language_Proficiency**: The student's language skill level (e.g., Basic, Intermediate, Fluent).
- **Visa_Type**: The type of visa held (e.g., Student, Post-study, Work Visa).
- **Gender**: The student's gender.
- **University_Ranking**: The ranking category of the attended university (Low, Medium, High).
- **Region_of_Study**: The geographical region where the studies took place.
- **Age**: The student's age.
- **Years_Since_Graduation**: Number of years since completing the degree.
- **GPA**: Grade Point Average on a 5.0 scale.
- **Internship_Experience**: Indicates if the student had an internship ("Yes" or "No").
- **Employment_Status**: Current employment state (e.g., Employed, Unemployed, Continuing Education).
- **Salary**: The student's annual salary (0 if unemployed or continuing education).
- **Job_Sector**: The industry in which the student is employed.

Two new columns were engineered during data cleaning (`cleaned_dataset.csv`):
- **Age_Group**: Binned categories of age (20-25, 26-30, 31-35, 36-40).
- **GPA_Category**: Binned categories of GPA (Low, Average, Good, Very Good, Excellent).

## Data Cleaning & Transformation
The following data preprocessing steps were performed using `pandas` in `notebooks/Graduation_data.ipynb`:

1. **Handling Missing Values**: 
   - Addressed missing values in the `Job_Sector` column. 
   - Set missing `Job_Sector` values to `"Not Applicable"` for individuals whose `Employment_Status` was not `"Employed"`.
   - Remaining missing values in `Job_Sector` were filled with `"Not Specified"`.
2. **Duplicate Removal**: 
   - Checked for and removed 3 duplicate rows from the dataset.
3. **Data Standardization**: 
   - Cleaned the `Gender` column by stripping leading/trailing whitespace and formatting it to title case.
4. **Feature Engineering**: 
   - Created `Age_Group` by binning the `Age` column into categories (`20-25`, `26-30`, `31-35`, `36-40`).
   - Created `GPA_Category` by binning the `GPA` column into categories (`Low`: 0-2.5, `Average`: 2.5-3.0, `Good`: 3.0-3.5, `Very Good`: 3.5-4.0, `Excellent`: 4.0-5.0).
5. **Exporting**: 
   - Saved the preprocessed dataset as `cleaned_dataset.csv` for Tableau integration.

## Tableau Dashboard
An interactive dashboard was created to visualize the findings and provide a clear overview of international graduate outcomes based on the cleaned dataset. A static snapshot of the dashboard is available at `visuals/Dashboard.png`.

**Tableau Public Link:** 
[🔗 Click here to view the interactive dashboard on Tableau Public](https://public.tableau.com/app/profile/gauri.mehrotra/viz/InternationalGraduateCareerOutcomesDashboard/Dashboard1?publish=yes)

## Technologies Used
- **Python**: For data cleaning and manipulation (`pandas`, `numpy`).
- **Jupyter Notebook**: For interactive data exploration.
- **Tableau**: For data visualization and dashboard creation.
