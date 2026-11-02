# Python Data Visualization — NYC Taxi Analysis

An exploratory data analysis and visualization assignment using the **Seaborn NYC taxi dataset**. The project demonstrates data inspection, missing-value treatment, and 10 analytical charts built with Pandas, Matplotlib, and Seaborn.

## Tools and libraries
- Python 3 and Jupyter Notebook
- Pandas and NumPy
- Matplotlib
- Seaborn

## Repository structure
```text
├── data/README.md
├── docs/PROJECT_DOCUMENTATION.md
├── notebooks/01_data_visualization_assignment.ipynb
├── outputs/README.md
├── .github/workflows/notebook-validation.yml
├── requirements.txt
└── README.md
```

## Assignment coverage
**Data preparation:** load and inspect the dataset, review missing values, remove rows without a valid pickup timestamp, impute numeric values with the median and categorical values with the mode.

**Visualizations:** line chart (average fare over time), bar chart (total fare by pickup borough), pie chart (payment method), histogram (trip distance), box plot (tips by borough), count plot (trips by borough), scatter plot (distance versus fare), correlation heatmap, pair plot (five most frequent pickup zones), and violin plot (fare by payment method).

## Run the project
```bash
git clone https://github.com/shanmukhkoyya/Python-Data-Visualization-Assignment.git
cd Python-Data-Visualization-Assignment
python -m venv .venv
pip install -r requirements.txt
jupyter notebook
```
Open `notebooks/01_data_visualization_assignment.ipynb` and run cells from top to bottom. The notebook uses `sns.load_dataset("taxis")`; the first run may require an internet connection to retrieve the dataset. Chart images are saved into `outputs/`.

## Interpretation and limitations
The notebook computes key summaries from the cleaned data. Correlation does not establish causation. Median/mode imputation affects the data distribution, and the pair plot is restricted to five common pickup zones for readability. The dataset is suitable for an educational exercise and should not be treated as a complete representation of all taxi trips.

## Quality checks
A GitHub Actions workflow validates notebook structure and parses every Python code cell for syntax errors. This automated check does not replace executing the notebook and reviewing its analytical outputs.

See [project documentation](docs/PROJECT_DOCUMENTATION.md) and [visualization output guide](outputs/README.md) for details.

---
*Practical Python data analytics portfolio project.*
