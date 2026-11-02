# Project Documentation — NYC Taxi Data Analysis & Visualization

## 1. Executive overview

This project uses Seaborn's `taxis` dataset to demonstrate an end-to-end exploratory data analysis workflow. It inspects trip records, treats missing values, explores fare and trip patterns, and communicates results through ten analytical visualizations.

The analysis is descriptive. It is intended to demonstrate data analyst workflow and communication, not to estimate causal effects or predict future taxi demand.

## 2. Business context and questions

Taxi operations generate data across time, location, distance, fare, tips and payment method. Exploring these fields can help frame operational questions such as:
- How do fare levels vary over time?
- Which pickup boroughs account for the largest total fare in this sample?
- What is the recorded payment-method mix?
- How are trip distance and fare associated?
- How do tips and fares vary across groups?

The dataset supports descriptive exploration only; it does not establish why a pattern occurs or prove that it will persist.

## 3. Dataset and analytical scope

- **Source interface:** Seaborn built-in dataset, loaded with `sns.load_dataset("taxis")`.
- **Domain:** taxi trips in New York City.
- **Fields used:** pickup timestamp, pickup borough, pickup zone, payment, distance, fare, tip, tolls and total.
- **Access:** the first dataset load may require internet access.
- **Scope:** cleaned sample available through the Seaborn dataset at execution time.

## 4. Data quality and preparation

1. Inspect dataset dimensions, sample records, data types and null counts.
2. Quantify missing values by field and display a missingness heatmap.
3. Parse the pickup timestamp using `pd.to_datetime(..., errors="coerce")`.
4. Remove rows with missing/invalid pickup timestamps because a valid timestamp is required for time-series analysis.
5. Fill remaining numeric nulls with each column's median.
6. Fill remaining categorical/text nulls with each column's mode when a mode exists.
7. Report remaining null counts and rows removed.

**Interpretation caution:** median and mode imputation are simple assignment techniques. They may reduce variability or alter group distributions and correlations. They should be documented, not treated as ground truth.

## 5. Analysis and visualization design

| Chart | Measure / grouping | Purpose |
|---|---|---|
| Missing-value heatmap | Null pattern by field and row | Inspect data completeness |
| Line chart | Daily average fare | Explore fare movement over pickup dates |
| Bar chart | Sum of fare by pickup borough | Compare aggregate fare contribution |
| Pie chart | Trip count by payment method | Show payment-method share |
| Histogram | Trip distance | Inspect distribution and skew |
| Box plot | Tip by pickup borough | Compare spread and outliers |
| Count plot | Trips by pickup borough | Compare trip volume |
| Scatter plot | Distance vs fare, colored by borough | Explore relationship and group patterns |
| Correlation heatmap | Distance, fare, tip, tolls, total | Inspect pairwise linear associations |
| Pair plot | Distance, fare, tip, total; hue by pickup zone | Compare multivariate patterns across common zones |
| Violin plot | Fare by payment method | Compare fare distributions |

The pair plot is restricted to the five most frequent pickup zones to improve legibility. This restriction applies only to that chart.

## 6. Key findings report

When the notebook runs, it calculates and writes `outputs/KEY_FINDINGS.md`. The report includes:
- cleaned trip count and date range;
- median distance, fare and tip;
- highest total-fare pickup borough;
- most common recorded payment method and its percentage;
- distance–fare Pearson correlation;
- strongest absolute correlation among selected numeric fields;
- top-five pickup-zone trip counts;
- business considerations and limitations.

This design keeps numerical claims tied to the dataset run rather than inserting unverified values into documentation. Refresh the report by executing the notebook after any data or cleaning change.

## 7. Business interpretation framework

When presenting the results:
- Compare total fare with trip count; a larger total may reflect more trips rather than higher fares per trip.
- Treat distance–fare correlation as an association, not proof of a pricing mechanism.
- Consider medians and distributions alongside means and totals because outliers can distort averages.
- Interpret payment-method shares in light of missing payment records.
- Use borough and pickup-zone comparisons as exploratory signals, not as stand-alone allocation decisions.

## 8. Reproducibility

1. Install dependencies from `requirements.txt`.
2. Start Jupyter Notebook.
3. Open `notebooks/01_data_visualization_assignment.ipynb`.
4. Execute all cells from top to bottom.
5. Review the generated PNGs and `outputs/KEY_FINDINGS.md`.

The GitHub Actions workflow performs notebook execution and verifies that expected chart images are present and valid.

## 9. Limitations

- The Seaborn dataset's scope and collection context may not represent every taxi trip, period or current operating condition.
- Removing records without valid pickup timestamps can affect the sample composition.
- Median/mode imputation affects downstream statistics.
- Pearson correlation captures linear association and is sensitive to outliers.
- No causal inference, statistical significance testing or predictive modelling is performed.
- The five-zone pair plot is a readable subset, not a complete location comparison.

## 10. Conclusion

The project demonstrates a reproducible workflow from data inspection and cleaning to visualization and business-oriented interpretation. Its value is in showing how a data analyst can turn a tabular dataset into clear exploratory evidence while communicating assumptions, limitations and appropriate next questions.
