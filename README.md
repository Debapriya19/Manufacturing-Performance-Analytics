# Manufacturing Performance Analytics (work in progress)

Finding out why a four-line food packaging plant misses its output target, using SQL, Python, forecasting, AI and Power BI.

**Status:** in progress. I am building this step by step; the commit history shows each stage.

## Plan

1. Profile the raw plant data and log every data-quality issue
2. Clean the data in Python and validate the result
3. Analyse OEE, downtime and quality with SQL and charts
4. Forecast OEE to year end and generate an AI insight summary
5. Build a Power BI dashboard (Power Query, DAX)
6. Present findings and recommendations to plant leadership

## Data

Six months (Apr to Sep 2026) of synthetic exports from a fictional plant's MES, quality and ERP systems, with realistic data-quality problems. See [docs/data_dictionary.md](docs/data_dictionary.md).
