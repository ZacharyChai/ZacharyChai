## Zachary Chai

Quantitative economics background, working across financial risk, causal inference, and applied NLP. I build analysis end to end: pulling and cleaning the source data, designing the pipeline that keeps it accurate, running the model, and writing the memo that says what it means and what would break it.

Most of what follows reports a null. That is deliberate. A result that survives a placebo test, a parameter grid, and a multiple-testing correction is worth more than a significant one that was never asked a hard question.

### Featured work

| Project | The question | What I found |
|---|---|---|
| **[cre-credit-risk](https://github.com/ZacharyChai/cre-credit-risk)** | How much of a $1.6B 2017-vintage CMBS pool cannot refinance into the 2026 maturity wall? | **44.6%** of the pool sits at Elevated or Acute risk on pro-forma DSCR at estimated takeout rates. A [live app](https://cre-credit-risk.streamlit.app/) runs the same logic against any uploaded loan tape. |
| **[momentum-backtest](https://github.com/ZacharyChai/momentum-backtest)** | Does 12-1 cross-sectional momentum still work in US large caps? | No. Long-short lost **3.6% a year** net of 10 bps (Sharpe -0.17, 70% max drawdown) on 636% turnover, with Fama-French + UMD alpha of **-5.1%/yr, t = -2.6**. Losers outperformed winners. |
| **[finbert-10k-sentiment](https://github.com/ZacharyChai/finbert-10k-sentiment)** | Does 10-K risk-factor tone predict forward returns, and does a transformer beat a word list? | No to both. **0 of 25** predictive regressions significant across 376 filing-years, and FinBERT adds nothing over the Loughran-McDonald dictionary. |
| **[minwage-did](https://github.com/ZacharyChai/minwage-did)** | Did the January 2024 state minimum-wage increases cost retail and food-service jobs? | A precise zero. Best estimate **-0.6%** (roughly 39k jobs), 95% CI -86k to +8k, and the placebo test produces effects that size at random dates. |
| **[ab-test-analysis](https://github.com/ZacharyChai/ab-test-analysis)** | Did the new landing page convert better? | A well-powered null: **-0.16pp** (p = 0.19) across 290K sessions, powered to detect 0.34pp. The sample-ratio-mismatch check ran before any outcome data was read. |
| **[bridge-pipeline](https://github.com/ZacharyChai/bridge-pipeline)** | Can a macro data pipeline run unattended and prove it is still correct? | 17 FRED/ALFRED series ingested with **full revision history** and modeled in dbt as a star schema, so any mart can be queried as of an arbitrary past date. Snowflake in production, DuckDB for a no-account local build; Airflow orchestration, a read-only FastAPI layer, data-quality gates, pytest, GitHub Actions CI. |

### How I work

- The hypothesis, the primary metric, and the effect size worth caring about are fixed **before** the outcome data is looked at.
- Every study ships its own falsification test: a placebo, a permutation null, a parameter grid, or all three.
- Multiple comparisons get corrected. Twelve tests at alpha 0.05 produce a hit about half the time under a pure null, so a lone asterisk is reported next to its q-value.
- Sample construction is published. Every dropped observation is counted and the reason named, so the funnel from raw data to estimated rows is auditable.
- A null is written up as a null.

### Also here

- **[churn-prediction](https://github.com/ZacharyChai/churn-prediction)**: IBM Telco churn model — logistic regression against random forest, AUC 0.847 at 77% churn recall — shipped as a [live prediction endpoint](https://churn-prediction-8qvu.onrender.com/): one serialized sklearn pipeline behind FastAPI, Pydantic schema validation, health check, pytest suite, Docker, deployed on Render.
- **[supply-chain-diversion-risk](https://github.com/ZacharyChai/supply-chain-diversion-risk)**: semiconductor trade diversion screen for the Singapore and Hong Kong entrepot corridors, scored against UN Comtrade flows and the BIS export-control timeline.
- **[singapore-michelin-longevity](https://github.com/ZacharyChai/singapore-michelin-longevity)**: which Singapore restaurants hold Michelin stars across nine editions, and what separates them from those that lose them.
- **[GSU-Housing-Process](https://github.com/ZacharyChai/GSU-Housing-Process)**: housing check-in workflow redesigned in Bizagi, replacing four sequential in-person checkpoints with a single pre-arrival step.

### Tools

Python (pandas, scikit-learn, statsmodels, Hugging Face transformers), SQL, R, Stata, dbt, Snowflake, DuckDB, PostgreSQL, Airflow, FastAPI, Docker, Terraform, GitHub Actions, Streamlit, Tableau, Power BI

### Contact

[LinkedIn](https://linkedin.com/in/zach-chai) · [Tableau Public](https://public.tableau.com/app/profile/zachary.chai6091) · zachchainy@gmail.com
