# Strategic HR Analytics Dshboard Milestone 2 - Basic Preprocessing and basic visualizations


## Issues Identified


### Replacing Numeric Values with Descriptive Strings
Several columns had numeric values representing categories. These were replaced with descriptive string values using DAX calculated columns in Power BI:

1. **Education**:
   ```DAX
   EducationCategory = SWITCH(EmployeeTable[Education],
       1, "Below College",
       2, "College",
       3, "Bachelor",
       4, "Master",
       5, "Doctor")
   ```

2. **EnvironmentSatisfaction**:
   ```DAX
   EnvSatisfactionCategory = SWITCH(EmployeeTable[EnvironmentSatisfaction],
       1, "Low",
       2, "Medium",
       3, "High",
       4, "Very High")
   ```

3. **JobInvolvement**:
   ```DAX
   JobInvolvementCategory = SWITCH(EmployeeTable[JobInvolvement],
       1, "Low",
       2, "Medium",
       3, "High",
       4, "Very High")
   ```

4. **JobSatisfaction**:
   ```DAX
   JobSatisfactionCategory = SWITCH(EmployeeTable[JobSatisfaction],
       1, "Low",
       2, "Medium",
       3, "High",
       4, "Very High")
   ```

5. **PerformanceRating**:
   ```DAX
   PerformanceCategory = SWITCH(EmployeeTable[PerformanceRating],
       1, "Low",
       2, "Good",
       3, "Excellent",
       4, "Outstanding")
   ```

6. **RelationshipSatisfaction**:
   ```DAX
   RelationshipCategory = SWITCH(EmployeeTable[RelationshipSatisfaction],
       1, "Low",
       2, "Medium",
       3, "High",
       4, "Very High")
   ```

7. **WorkLifeBalance**:
   ```DAX
   WorkLifeBalanceCategory = SWITCH(EmployeeTable[WorkLifeBalance],
       1, "Bad",
       2, "Good",
       3, "Better",
       4, "Best")
   ```


## Summary of Changes

| Column               | Issue                         | Action Taken                    | Missing Values Before | Missing Values After |
|----------------------|-------------------------------|----------------------------------|-----------------------|----------------------|
| Education            | Numeric values               | Replaced with descriptive text  | N/A                   | N/A                  |
| EnvironmentSatisfaction | Numeric values            | Replaced with descriptive text  | N/A                   | N/A                  |
| JobInvolvement       | Numeric values               | Replaced with descriptive text  | N/A                   | N/A                  |
| JobSatisfaction      | Numeric values               | Replaced with descriptive text  | N/A                   | N/A                  |
| PerformanceRating    | Numeric values               | Replaced with descriptive text  | N/A                   | N/A                  |
| RelationshipSatisfaction | Numeric values           | Replaced with descriptive text  | N/A                   | N/A                  |
| WorkLifeBalance      | Numeric values               | Replaced with descriptive text  | N/A                   | N/A                  |

## Updated Dataset Insights
- **Categorical Columns**: Numeric codes replaced with meaningful descriptive strings for better readability.

## Basic Visualizations

To better understand the data, the following visualizations were created in Power BI:

1. **Line Chart**:
   - Analyzed the relationship between `EmployeeCount` and `Age` to observe patterns in employee age.

2. **Histogram**:
   - Visualized the distribution of `JobRole` with respect to  `EmployeeCount`.

3. **Pie Chart**:
   - Showed the proportions of `Attrition` categories (Yes/No) to identify trends.

4. **Scatter Plot**:
   - Analyzed the relationship between `MonthlyIncome` and `Age` to observe patterns in employee demographics.




## Repository Structure

```
|-- HR_Analytics.pbix                 # Power BI project file
|-- README.md                         # Documentation
|-- HR_Analytics.csv                  # Dataset
```
Thank You!!
