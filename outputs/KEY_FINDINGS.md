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

## Practical business considerations

- Review fare and trip-volume patterns together before making borough-level staffing or vehicle-allocation decisions.
- Use distance-versus-fare patterns as a diagnostic; investigate unusual trips and fare outliers rather than assuming a causal relationship.
- Monitor payment-method mix as a descriptive operational metric, while checking whether missing payment records affect the percentages.
- Compare tip and fare distributions, not only averages, because outliers can materially influence summary statistics.

These are exploratory considerations, not operational recommendations validated by causal analysis.

## Data preparation and limitations

- Rows with missing or invalid pickup timestamps were removed for time-based analysis.
- Missing numeric fields were imputed with column medians; categorical/text fields were imputed with their modes.
- Imputation can change distributions and correlations. The taxi dataset is a sample and may not represent all trips, time periods, or current operating conditions.
- Correlation does not establish causation. No hypothesis test or causal model is performed.

## Charts

See the [visualization gallery](README.md#visualization-gallery) and PNG files in this folder.
