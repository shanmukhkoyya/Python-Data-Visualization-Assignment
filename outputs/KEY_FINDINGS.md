# NYC Taxi Data Visualization — Key Findings

> Automatically generated from the cleaned Seaborn `taxis` dataset. Re-run the notebook to refresh these values and charts.

## Executive summary

This exploratory analysis reviewed **6,433 trips** across **4 pickup borough categories** from **2019-02-28** to **2019-03-31**. The median trip distance was **1.64**, median fare was **$9.50**, and median tip was **$1.70**.

## Key findings

1. **Highest total fare borough:** Manhattan (sum of fares: $59,426.42).
2. **Most common payment method:** credit card (71.8% of trips with a recorded payment method).
3. **Distance and fare:** Pearson correlation = 0.92. This describes a linear association in this dataset; it does not prove that distance alone determines fare.
4. **Strongest selected numeric correlation:** fare and total (r = 0.97).
5. **Payment-method fare comparison:** median fares are shown in the violin plot; differences should be interpreted alongside trip mix and outliers.

## Pickup-zone coverage

The pair plot focuses on the five most frequently recorded pickup zones to keep the visualization readable. This is a display choice, not a filter applied to the main cleaned dataset.

| Pickup zone | Trips |
|---|---:|
| Midtown Center | 256 |
| Upper East Side South | 211 |
| Penn Station/Madison Sq West | 210 |
| Clinton East | 208 |
| Midtown East | 198 |

## Borough-level operating KPIs

The following comparison separates trip volume from fare contribution. A high fare share alongside a high trip share does not automatically mean higher fares per trip.

| Pickup borough | Trips | Trip share | Total fare | Fare share | Average fare | Average distance |
|---|---:|---:|---:|---:|---:|---:|
' + borough_kpis.to_markdown(floatfmt='.2f') + '
## Payment mix and fare KPIs

| Payment method | Trips | Average fare | Median fare | Average tip |
|---|---:|---:|---:|---:|
' + payment_kpis.to_markdown(floatfmt='.2f') + '

## Business impact: how an operator could use this analysis

1. **Fleet and driver planning:** compare borough trip share with fare share and daily fare trends to identify areas/time windows for a deeper demand study. Do not move vehicles based on this sample alone; validate with current trip volume, driver supply, wait times and operating costs.
2. **Pricing and fare review:** use the distance–fare scatter and correlation results to flag unusual distance/fare combinations for investigation. Check applicable fare rules, surcharges and trip context before drawing conclusions.
3. **Payment operations:** use the payment-method share to understand the recorded payment mix and plan payment-system monitoring. Confirm missing/unknown payment records before using the percentages for finance decisions.
4. **Service quality and driver earnings:** compare tip distributions by borough and fare distributions by payment method. Use medians and spread, not only averages, and avoid treating tips as a guaranteed income measure.
5. **Management reporting:** track trips, total fare, fare per trip and trip share together. Total fare alone can be misleading when borough trip volumes differ.

### Recommended next business questions

- Does the borough with the highest total fare also have the highest fare per trip?
- Do weekday and weekend patterns differ?
- Which pickup zones combine high trip volume with longer distances?
- Are unusual fare outliers explained by trip distance, tolls or other recorded factors?
- Does the recorded payment mix change across boroughs or time periods?

These are decision-support opportunities, not proven savings, revenue gains or causal effects. This dataset does not include enough information to estimate profit, vehicle utilization, wait time or driver supply.

## Data preparation and limitations

- Rows with missing or invalid pickup timestamps were removed for time-based analysis.
- Missing numeric fields were imputed with column medians; categorical/text fields were imputed with their modes.
- Imputation can change distributions and correlations. The taxi dataset is a sample and may not represent all trips, time periods, or current operating conditions.
- Correlation does not establish causation. No hypothesis test or causal model is performed.

## Charts

See the [visualization gallery](README.md#visualization-gallery) and PNG files in this folder.
