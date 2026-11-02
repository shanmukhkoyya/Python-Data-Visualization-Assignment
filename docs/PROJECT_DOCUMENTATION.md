# Project Documentation — NYC Taxi Data Visualization

## 1. Project summary
This project applies exploratory data analysis (EDA) and visualization to Seaborn's built-in `taxis` dataset. It follows the supplied Python Data Visualization Assignment 2 brief and uses Pandas, Matplotlib, and Seaborn.

## 2. Objectives
- Load and inspect a real-world tabular dataset.
- Identify and handle missing values using suitable methods.
- Select chart types that answer analytical questions.
- Compare trip patterns across pickup boroughs, pickup zones, and payment methods.
- Examine distributions, relationships, and correlations.
- Communicate findings without overstating what the data supports.

## 3. Dataset and fields
The notebook loads the dataset with `sns.load_dataset("taxis")`. Analysis uses pickup timestamp, pickup borough, pickup zone, payment method, distance, fare, tip, tolls, and total. Seaborn retrieves the dataset on first use, so an internet connection may be required.

## 4. Data preparation
1. Inspect dataset shape, sample rows, data types, and missing-value counts.
2. Convert the pickup field to datetime.
3. Remove records with a missing or invalid pickup timestamp because the time-series analysis depends on it.
4. Fill missing numeric values with the column median.
5. Fill missing categorical/text values with the most frequent category (mode).
6. Review missing values after treatment and report rows removed.

Imputation is a practical assignment choice, not a claim that imputed values are the true values. Its effect should be considered when interpreting distributions and correlations.

## 5. Visualization plan
| # | Chart | Analytical question |
|---:|---|---|
| 1 | Line chart | How does average fare vary over pickup time? |
| 2 | Bar chart | Which pickup borough has the greatest sum of fares? |
| 3 | Pie chart | What share of trips uses each payment method? |
| 4 | Histogram | How are trip distances distributed? |
| 5 | Box plot | How does tip distribution vary by pickup borough? |
| 6 | Count plot | How many trips are recorded for each pickup borough? |
| 7 | Scatter plot | How are distance and fare related across boroughs? |
| 8 | Correlation heatmap | How strongly are selected numeric variables associated? |
| 9 | Pair plot | How do distance, fare, tip, and total vary across common pickup zones? |
| 10 | Violin plot | How does fare distribution vary by payment method? |

A missing-value heatmap is also used as a data-quality diagnostic.

## 6. Interpretation framework
For each chart, state the question, describe the visible pattern using the chart or computed summary, include relevant category comparisons, avoid causal claims, and note limitations such as imputation, outliers, sample coverage, and restricted pair-plot categories.

## 7. Reproducibility
Install packages from `requirements.txt`, launch Jupyter, and run the notebook from the first cell to the last. The notebook creates an `outputs/` directory and saves chart images when executed.

## 8. Quality standards
- Meaningful chart titles and axis labels.
- Readable figure dimensions and tick labels.
- Consistent plotting style.
- Findings supported by computed values or visible chart evidence.
- Notebook JSON and Python code-cell syntax checked in GitHub Actions.

## 9. Limitations
This is an educational exploratory analysis, not a causal study or production taxi-demand model. Imputation can affect distributions and correlations. The pair plot is restricted to the five most frequent pickup zones for readability. The dataset's sample and collection context limit generalization.
