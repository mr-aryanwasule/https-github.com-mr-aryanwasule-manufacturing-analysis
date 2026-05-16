# Manufacturing Performance Analysis Report

## Project Objective

This project analyzes manufacturing machine data to understand production performance, machine efficiency, quality issues, and maintenance risk. The goal is to convert raw Excel telemetry into useful business insights and visualizations.

## Dataset Overview

- Source file: `C:\Users\aryan\Downloads\Manufacturing.xlsx`
- Sheet used: `Thales_Group_Manufacturing`
- Total records: 100,000
- Time range: 2025-01-01 00:00:00 to 2025-12-02 23:59:00
- Duplicate rows found: 0
- Missing values found: 0
- Machines tracked: 50
- Operation modes: Active, Idle, Maintenance
- Efficiency statuses: Low, Medium, High

## Key Findings

1. The dataset is clean enough for analysis, with 0 missing values and 0 duplicate rows detected.
2. The most common efficiency status is **Low**, with 77,825 records.
3. The most common operation mode is **Active**, with 70,054 records.
4. **High** efficiency has the highest average production speed at 450.79 units per hour.
5. **Low** efficiency has the highest average defect rate at 5.02%.

## Numeric Summary

| index | temperature_c | vibration_hz | power_consumption_kw | network_latency_ms | packet_loss_pct | quality_control_defect_rate_pct | production_speed_units_per_hr | predictive_maintenance_score | error_rate_pct |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| count | 100000.0 | 100000.0 | 100000.0 | 100000.0 | 100000.0 | 100000.0 | 100000.0 | 100000.0 | 100000.0 |
| mean | 60.04 | 2.55 | 5.75 | 25.56 | 2.49 | 5.01 | 275.92 | 0.5 | 7.5 |
| std | 17.32 | 1.41 | 2.45 | 14.12 | 1.44 | 2.88 | 130.1 | 0.29 | 4.34 |
| min | 30.0 | 0.1 | 1.5 | 1.0 | 0.0 | 0.0 | 50.0 | 0.0 | 0.0 |
| 25% | 45.03 | 1.32 | 3.63 | 13.36 | 1.25 | 2.52 | 162.87 | 0.25 | 3.75 |
| 50% | 60.03 | 2.55 | 5.76 | 25.54 | 2.49 | 5.0 | 276.65 | 0.5 | 7.5 |
| 75% | 74.97 | 3.78 | 7.86 | 37.8 | 3.74 | 7.51 | 388.81 | 0.75 | 11.27 |
| max | 90.0 | 5.0 | 10.0 | 50.0 | 5.0 | 10.0 | 500.0 | 1.0 | 15.0 |

## Production Speed Relationships

The strongest correlations with production speed are:

| index | correlation |
| --- | --- |
| packet_loss_pct | -0.007 |
| error_rate_pct | 0.006 |
| quality_control_defect_rate_pct | -0.005 |
| predictive_maintenance_score | 0.004 |
| power_consumption_kw | 0.002 |
| temperature_c | 0.001 |
| vibration_hz | -0.001 |
| network_latency_ms | -0.001 |

## Highest Risk Machines

These machines have the highest average error and defect rates, so they should be reviewed first by the maintenance or process team.

| machine_id | avg_speed | avg_error_rate | avg_defect_rate | avg_maintenance_score | records |
| --- | --- | --- | --- | --- | --- |
| 25 | 273.001 | 7.711 | 5.018 | 0.504 | 1998 |
| 22 | 278.124 | 7.659 | 5.095 | 0.502 | 2031 |
| 29 | 273.272 | 7.648 | 4.899 | 0.504 | 2044 |
| 47 | 275.203 | 7.64 | 5.093 | 0.5 | 2001 |
| 31 | 282.414 | 7.624 | 5.079 | 0.487 | 1933 |

## Charts Created

- `01_efficiency_status_distribution.png`
- `02_avg_speed_by_operation_mode.png`
- `03_defect_error_by_efficiency.png`
- `04_temperature_vs_speed.png`
- `05_maintenance_score_vs_error_rate.png`
- `06_hourly_production_speed.png`
- `07_top_error_machines.png`

## Recommendations

1. Prioritize inspection of the top high-error machines listed above.
2. Compare operation modes with lower average speed to identify process delays or idle-time causes.
3. Monitor machines with high defect rates even if their production speed is acceptable, because fast production with poor quality can increase rework cost.
4. Use predictive maintenance score together with error rate rather than relying on one metric alone.
5. Track these charts daily or weekly so abnormal patterns are visible early.
