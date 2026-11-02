# Visualization Outputs

This folder contains exported figures from the NYC taxi exploratory analysis.

| File | Description |
|---|---|
| `00_missing_values_heatmap.png` | Missing-value pattern before cleaning |
| `01_fare_over_time_line_chart.png` | Average fare by pickup date |
| `02_total_fare_by_borough_bar_chart.png` | Total fare grouped by pickup borough |
| `03_payment_method_pie_chart.png` | Trip share by payment method |
| `04_trip_distance_histogram.png` | Distribution of trip distance |
| `05_tip_by_borough_box_plot.png` | Tip distribution by pickup borough |
| `06_trips_by_borough_count_plot.png` | Trip count by pickup borough |
| `07_distance_vs_fare_scatter_plot.png` | Distance and fare relationship by borough |
| `08_numeric_correlation_heatmap.png` | Correlations among selected numeric fields |
| `09_pickup_zone_pair_plot.png` | Pairwise relationships across common pickup zones |
| `10_fare_by_payment_method_violin_plot.png` | Fare distribution by payment method |

Run the notebook from top to bottom to regenerate the figures. The pair plot uses the five most frequent pickup zones to keep the output readable.
