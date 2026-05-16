# Manufacturing Performance Analysis Project

## 1. Introduction

Manufacturing companies collect large amounts of machine data every day. This data can help identify production performance, machine efficiency, quality problems, and maintenance risk. In this project, Python was used to analyze a manufacturing dataset and convert raw machine records into useful insights, charts, and recommendations.

The project uses Pandas for data cleaning and analysis, and Matplotlib for data visualization.

## 2. Project Objective

The main objective of this project is to analyze manufacturing machine performance and identify patterns related to:

- production speed
- machine efficiency
- operation mode
- defect rate
- error rate
- predictive maintenance score
- high-risk machines

The final goal is to support better decision-making for manufacturing operations and maintenance planning.

## 3. Dataset Description

The dataset was taken from the Excel workbook `Manufacturing.xlsx`.

Dataset details:

- Sheet name: `Thales_Group_Manufacturing`
- Total records analyzed: 100,000
- Number of machines: 50
- Time period: 2025-01-01 to 2025-12-02
- Missing values after cleaning: 0
- Duplicate rows: 0

Important columns used in the analysis:

| Column | Description |
| --- | --- |
| Date | Date of machine record |
| Timestamp | Time value recorded in Excel format |
| Machine_ID | Unique machine identifier |
| Operation_Mode | Current machine operation mode |
| Temperature_C | Machine temperature in Celsius |
| Vibration_Hz | Machine vibration reading |
| Power_Consumption_kW | Power used by the machine |
| Network_Latency_ms | Network delay in milliseconds |
| Packet_Loss_% | Percentage of network packet loss |
| Quality_Control_Defect_Rate_% | Defect rate found by quality control |
| Production_Speed_units_per_hr | Production speed per hour |
| Predictive_Maintenance_Score | Maintenance risk/health score |
| Error_Rate_% | Machine error rate |
| Efficiency_Status | Machine efficiency category |

## 4. Tools and Technologies Used

- Python
- Pandas
- Matplotlib
- Excel data source
- CSV output files
- Markdown report

## 5. Data Cleaning Process

The raw Excel file had mixed date formats. Some dates were stored as Excel serial numbers, while others were stored as text dates. The program handled both formats and converted them into a single proper date column.

The cleaning process included:

1. Standardizing column names.
2. Converting mixed date formats into valid dates.
3. Converting Excel time values into readable time.
4. Creating a combined `datetime` column.
5. Extracting the hour from the datetime column.
6. Converting category columns into category data type.
7. Saving the cleaned dataset as a CSV file.

After cleaning, the dataset had 0 missing values and 0 duplicate rows.

## 6. Exploratory Data Analysis

The analysis calculated:

- total records
- missing values
- duplicate rows
- number of machines
- most common efficiency status
- most common operation mode
- average production speed by efficiency status
- average defect rate by efficiency status
- correlation of production speed with other numeric variables
- top high-risk machines

## 7. Visualizations

### 7.0 Complete Visualization Dashboard

![Manufacturing Visualization Dashboard](charts/manufacturing_visualization_dashboard.png)

This dashboard combines the most important charts into one view. It is useful for quickly presenting the project results.

### 7.1 Efficiency Status Distribution

![Efficiency Status Distribution](charts/01_efficiency_status_distribution.png)

This chart shows the number of records under each efficiency status. The most common efficiency status is Low.

### 7.2 Average Production Speed by Operation Mode

![Average Production Speed by Operation Mode](charts/02_avg_speed_by_operation_mode.png)

This chart compares the average production speed across operation modes such as Active, Idle, and Maintenance.

### 7.3 Defect and Error Rate by Efficiency Status

![Defect and Error Rate by Efficiency Status](charts/03_defect_error_by_efficiency.png)

This chart compares quality defect rate and error rate for different efficiency statuses.

### 7.4 Temperature vs Production Speed

![Temperature vs Production Speed](charts/04_temperature_vs_speed.png)

This scatter plot checks whether machine temperature has a visible relationship with production speed.

### 7.5 Maintenance Score vs Error Rate

![Maintenance Score vs Error Rate](charts/05_maintenance_score_vs_error_rate.png)

This chart compares predictive maintenance score with error rate.

### 7.6 Hourly Production Speed

![Hourly Production Speed](charts/06_hourly_production_speed.png)

This line chart shows the average production speed for each hour of the day.

### 7.7 Top 10 Machines by Error Rate

![Top Error Machines](charts/07_top_error_machines.png)

This chart identifies machines with the highest average error rates.

## 8. Key Findings

1. The dataset contains 100,000 manufacturing records.
2. The cleaned dataset has no missing values and no duplicate records.
3. Low efficiency is the most common efficiency status.
4. Active is the most common machine operation mode.
5. High efficiency records have the highest average production speed.
6. Low efficiency records have the highest average defect rate.
7. Machines 25, 22, 29, 47, and 31 show higher average error rates and should be reviewed first.
8. Production speed has very weak direct correlation with the other numeric variables, which means machine performance should be evaluated using multiple metrics together.

## 9. High-Risk Machines

| Machine ID | Average Speed | Average Error Rate | Average Defect Rate | Average Maintenance Score | Records |
| --- | ---: | ---: | ---: | ---: | ---: |
| 25 | 273.001 | 7.711 | 5.018 | 0.504 | 1998 |
| 22 | 278.124 | 7.659 | 5.095 | 0.502 | 2031 |
| 29 | 273.272 | 7.648 | 4.899 | 0.504 | 2044 |
| 47 | 275.203 | 7.640 | 5.093 | 0.500 | 2001 |
| 31 | 282.414 | 7.624 | 5.079 | 0.487 | 1933 |

## 10. Recommendations

1. Review high-error machines first, especially machines 25, 22, 29, 47, and 31.
2. Monitor defect rate together with production speed because fast production is not useful if quality is poor.
3. Use predictive maintenance score and error rate together for maintenance planning.
4. Track hourly production speed to detect unusual production patterns.
5. Build a regular reporting process so machine issues can be identified early.

## 11. Conclusion

This project shows how Python can be used to analyze manufacturing data and create meaningful business insights. The analysis cleaned the raw Excel data, generated charts, identified high-risk machines, and produced a final report.

The main conclusion is that manufacturing performance should not be judged by production speed alone. A better decision should include efficiency status, defect rate, error rate, and maintenance score together.
