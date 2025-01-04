# Strategic HR Analytics Dshboard Milestone 2 - Basic Preprocessing and basic visualizations



## Issues Identified

### 1. Imbalanced Values
- **Column**: `BusinessTravel`
- **Issue**: Found inconsistent values such as `travel_rarely` and `TravelRarely`, which should represent the same category.

### 2. Missing Values
- **Column**: `YearsWithCurrManager`
- **Issue**: Identified 57 missing values.

## Steps Taken

### Handling Imbalanced Values
- **Problem**: The `BusinessTravel` column contained inconsistent representations of the same category.
- **Solution**:
  - Standardized all text values by creating a calculated column in Power BI using DAX:
    ```DAX
    StandardizedTravel = SWITCH(TRUE(),
        LOWER(EmployeeTable[BusinessTravel]) = "travelrarely", "travel_rarely",
        LOWER(EmployeeTable[BusinessTravel]) = "travelfrequently", "travel_frequently",
        EmployeeTable[BusinessTravel])
    ```

### Treating Missing Values
- **Column**: `YearsWithCurrManager`
- **Problem**: There were 57 missing values in this column.
- **Solution**:
  - Used a DAX calculated column to fill missing values with the median value:
    ```DAX
    FilledYearsWithManager = IF(ISBLANK(EmployeeTable[YearsWithCurrManager]),
        MEDIANX(EmployeeTable, EmployeeTable[YearsWithCurrManager]),
        EmployeeTable[YearsWithCurrManager])
    ```

## Summary of Changes

| Column               | Issue                         | Action Taken                    | Missing Values Before | Missing Values After |
|----------------------|-------------------------------|----------------------------------|-----------------------|----------------------|
| BusinessTravel       | Imbalanced values            | Standardized categories         | N/A                   | N/A                  |
| YearsWithCurrManager | Missing values (57 entries)  | Filled with median value        | 57                    | 0                    |

## Updated Dataset Insights
- **BusinessTravel**: Cleaned and standardized to three categories: `travel_rarely`, `travel_frequently`, and `non-travel`.
- **YearsWithCurrManager**: No missing values remain; the median value ensures continuity and data consistency.

## Basic Visualizations

To better understand the data, the following visualizations were created in Power BI:

1. **Bar Chart**:
   - Displayed the distribution of `BusinessTravel` categories to ensure proper standardization.

2. **Histogram**:
   - Visualized the distribution of `YearsWithCurrManager` to identify and verify the effect of filling missing values.

3. **Pie Chart**:
   - Showed the proportions of `Attrition` categories (Yes/No) to identify trends.

4. **Scatter Plot**:
   - Analyzed the relationship between `MonthlyIncome` and `Age` to observe patterns in employee demographics.

## Tools and Techniques Used
- **Power BI**:
  - Created DAX measures and calculated columns to handle imbalanced and missing values.
  - Designed interactive visualizations to gain insights into the cleaned dataset.
  - Suggested DAX measures for checking missing values:
    ```DAX
    MissingValues_Column = COUNTROWS(FILTER(EmployeeTable, ISBLANK(EmployeeTable[YearsWithCurrManager])))
    ```


## Repository Structure

```
|-- HR_Analytics.pbix                 # Power BI project file
|-- README.md                         # Documentation
|-- HR_Analytics.csv                  # Dataset
```

Thank You!!
