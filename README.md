# Fitness Customer Churn Analysis

An exploratory analysis of customer retention for a fitness subscription app using practice data. The project combines account, support and activity records to investigate which customer segments have more recorded cancellations and what the business could test next.

## Approach

- **Python and pandas** for checking customer identifiers, parsing dates and documenting missing values.
- **SQL and DuckDB** for aggregating support tickets and activity events before joining them to accounts. This preserves one row per customer and avoids double-counting.
- **Matplotlib** for comparing recorded cancellations by plan, observed activity and support experience.

## Findings and next decision

Accounts with no recorded activity showed a higher share of recorded cancellations. Among customers with support tickets, average resolution time per customer was higher for accounts with a cancellation marker. These patterns suggest starting with an experiment focused on engagement.

The proposed pilot would randomly assign confirmed active subscribers with low recent activity to a re-engagement group or a control group. Compare 30-day retention between the groups. The available data do not establish when cancellations occurred, so the observed patterns cannot establish cause and effect or provide a monthly churn rate.

## Files and local execution

Open [`fitness_customer_churn.ipynb`](fitness_customer_churn.ipynb) to read the analysis, SQL and saved charts. The three source CSV files are required to rerun the notebook and are kept local.

1. Place your authorized copies of `da_fitly_account_info.csv`, `da_fitly_customer_support.csv` and `da_fitly_user_activity.csv` in a `data/` folder next to the notebook.
2. From the repository folder, install the dependencies and start JupyterLab. The notebook was checked with Python 3.13.9.

   ```sh
   python -m pip install -r requirements.txt
   python -m jupyterlab
   ```

3. Open the notebook and choose **Run → Run All Cells**. The generated charts are saved in `figures/`.
