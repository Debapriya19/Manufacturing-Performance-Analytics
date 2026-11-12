# Manufacturing Performance Analytics: Why Is the Plant Missing Its Output Target?

**SQL · Python (pandas) · Forecasting · AI (Claude API) · Power BI · DAX · Power Query**

> 🚧 **Work in progress.** I am building this project step by step. The checklist below and the commit history show where I am.

## The business problem

Riverside Packaging Plant (a fictional site of Harvest Lane Foods) packs snack bars, pouches, ready meals and sauce jars on **four packaging lines**, running **three shifts** a day.

- Output is regularly **missing the production plan**.
- **Overtime has become routine** to catch up.
- Leadership is considering **buying a fifth packaging line**, a major capital investment.
- Each department blames another: maintenance, operations, planning and the warehouse all point elsewhere.

Before the plant spends money on new capacity, leadership needs to know whether the existing lines are being used well.

## Questions this project answers

1. **How effective are the lines today?** Measured as OEE (Overall Equipment Effectiveness = Availability × Performance × Quality) against a 75% target.
2. **Where is production time being lost?** Which lines, shifts, machines and stop reasons cost the most hours?
3. **Is it getting better or worse?** Where will performance be by year end if nothing changes?
4. **What should leadership do first?** Which actions recover the most time for the least cost, and is a fifth line really needed?

## The data

Six months (1 April to 30 September 2026) of exports from the plant's systems, about 28,000 records:

| File | Source system | What it holds |
|---|---|---|
| `mes_production_hourly.csv` | MES (manufacturing execution) | Units produced per line per hour |
| `mes_downtime_events.csv` | MES | Every machine stop, with start, end and reason code |
| `qms_rejects_by_shift.csv` | Quality system | Rejected packs by reason, per shift |
| `erp_material_master.xlsx` | ERP (SAP export) | Products, rated machine speeds, cost and price |
| `ref_*.csv` | Reference lists | Lines, machines and downtime reason codes |

Like real plant data, the exports are messy: inconsistent names, duplicates, missing values and impossible timestamps. Cleaning them is part of the project. The data is synthetic and was generated to behave like real plant data. Full details are in [docs/data_dictionary.md](docs/data_dictionary.md).

## Approach and progress

- [ ] **1. Profile the raw data:** find and log every data-quality issue
- [ ] **2. Clean and validate:** fix each issue in Python and prove the result is correct
- [ ] **3. Analyse:** OEE, downtime and quality by line, shift and machine with SQL and charts
- [ ] **4. Forecast and summarise:** predict OEE to year end, and generate an AI-written insight summary
- [ ] **5. Dashboard:** an interactive Power BI report built with Power Query and DAX
- [ ] **6. Recommend:** sized actions and a decision for plant leadership, presented in a stakeholder deck

## Tools

| Tool | Used for |
|---|---|
| Python (pandas, matplotlib, seaborn) in Jupyter | Profiling, cleaning, exploration, charts |
| SQL (SQLite) | Business questions with joins, CTEs and window functions |
| Prophet | OEE forecasting |
| Claude API | Plain-English insight summary for leadership |
| Power BI, Power Query, DAX | Interactive dashboard |
| Git and GitHub | Version control |

## Repository structure

```
├── data/raw/      original messy exports
├── docs/          data dictionary, data issues log
├── notebooks/     Jupyter notebooks, numbered in order
├── sql/           SQL queries
├── ai/            AI summary script
├── outputs/       charts and results
└── powerbi/       dashboard file and screenshots
```

*The company, plant and data are fictional.*
