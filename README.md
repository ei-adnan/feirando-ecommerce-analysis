# Feirando: An E-commerce Marketplace Analysis
### Do late deliveries hurt customer reviews?

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat&logo=pandas&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-DuckDB-FFF000?style=flat&logo=duckdb&logoColor=black)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=flat&logo=tableau&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)
![Domain](https://img.shields.io/badge/Domain-E--commerce-112846?style=flat)
![Status](https://img.shields.io/badge/Status-Complete-2E7D32?style=flat)

**[View the dashboard on Tableau Public](https://public.tableau.com/app/profile/mohammed.adnan2171/viz/FeirandoDashboard/Dashboard1)**

Feirando is a fictional Brazilian online marketplace I created so I could work the way an analyst would inside a real company: starting from a business problem, not just a dataset. The data is the public [Olist Brazilian E-Commerce dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (2016–2018), used with credit to Olist.

## In one sentence

When an order arrives late, customers give about **2 stars less**, and most delays happen **on long routes with the delivery company**, not because of a few bad sellers.

## Key findings

| | Finding | Number |
|---|---|---|
| 1 | Late orders get much lower reviews | 4.3 stars on time vs 2.3 late |
| 2 | Even a small delay hurts | 1–3 days late already costs a full star |
| 3 | Lateness grows with distance | 4.5% late under 100 km, 12.1% over 2,000 km |
| 4 | Most delays happen after the seller ships | 72% of late orders left the seller on time |
| 5 | A few bad sellers are not the main cause | The worst 10% of sellers cause only 15% of late orders |
| 6 | Rio is the priority | Short route from most sellers, yet about 12% late |

## Recommendations

1. **Promise delivery dates Feirando can keep:** set them per route, based on how long each route really takes.
2. **Hold carriers to on-time targets:** start with Rio and the North and Northeast.
3. **Warn early when a seller hands over late:** those orders are 4× more likely to arrive late.

## How it was done

| Step | What | Where |
|---|---|---|
| Cleaning | Checked all 9 tables, logged every decision, ran 18 validation checks | `notebooks/01_cleaning.ipynb` |
| SQL analysis | Tested 5 hypotheses with DuckDB | `notebooks/02_sql_analysis.ipynb` |
| Python analysis | Significance tests, distances (haversine), seller vs carrier split | `notebooks/03_python_analysis.ipynb` |
| Dashboard | Tableau Public, built on one order-level table | link above |

The hypotheses and the thresholds that would prove them wrong were written down **before** looking at the results.

## Documents

- `docs/Feirando_Case_Study.docx`: the full story in plain English
- `docs/Feirando_Problem_Statement_and_Hypotheses.docx`: the question, the five hypotheses and their results
- `docs/Feirando_Data_Cleaning_Report.docx`: every data quality issue and how it was handled
- `docs/Feirando_Recommendations_Impact_Limitations.docx`: actions, estimated impact and limits
- `docs/Feirando_Data_Dictionary.docx`: what every table and column means

## Limits

The results show a strong connection, not proof of cause. Orders that never arrived and orders without a review are left out, which makes the real problem look slightly smaller. The data is from 2017–2018.

## Tools

Python (pandas, scipy, statsmodels) · SQL (DuckDB) · Tableau Public

## Skills demonstrated

| Area | What I did |
|---|---|
| **Business framing** | Turned a vague concern into one clear question, five testable hypotheses and pass/fail thresholds set before analysis |
| **Data cleaning & quality** | Profiled 9 tables, handled each issue with a logged rule, flagged rows instead of deleting them, and ran 18 validation checks |
| **SQL** | Multi-table joins, aggregations, `CASE` bands, `HAVING`, subqueries, `EXISTS` and time windows for a cohort-style repeat-purchase test |
| **Python** | pandas for data prep, haversine distance from coordinates, binning, and pivot tables to check confounders |
| **Statistics** | Welch's t-test and a two-proportion z-test; separating statistical significance from business significance |
| **Data visualisation** | A Tableau dashboard built around three insights, with action titles, a consistent colour system and a shared date filter |
| **Communication** | Plain-English case study, prioritised insights, recommendations with estimated impact, and openly stated limitations |

---
Case study by Mohammed Adnan