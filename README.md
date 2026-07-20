# Portfolio Selection Models 📊

Three factor-based portfolio selection models built in Python, backtested on Brazilian equities (IBOVESPA constituents, 2002–2012). Each model ranks stocks by a combination of fundamental and technical factors (ROIC, ROE, momentum, volatility, price-to-book, etc.) and evaluates the resulting portfolio against the IBOVESPA benchmark.

## Models

1. **Model 1 — Highest Return**: selects the factor combination with the best cumulative return. Best result: **ROIC + 6-month Momentum**, 2104% cumulative return vs. 323% for IBOVESPA over the period (32.75% annualized vs. 14.13%).
2. **Model 2 — Best Return/Volatility (Sharpe-like)**: optimizes for return per unit of risk. Best result: **6-month Momentum + Volatility**, 1958% cumulative return with lower volatility (17.96%) than the benchmark (24.82%) and a statistically significant alpha (20.6%, p < 0.01).
3. **Model 3 — Best Alpha/Beta (Treynor-like)**: optimizes for return per unit of systematic (market) risk. Best result: also **6-month Momentum + Volatility**, confirming it as the most consistently efficient factor pair across all three ranking criteria.

For each model, single factors are ranked first, then all pairwise factor combinations are backtested and ranked by the target metric (return, return/volatility, or alpha/beta), with correlation analysis to explain which individual factors drive each outcome.

## Data

⚠️ The two source datasets (`Aula-DB-Acoes.csv` — monthly stock fundamentals/prices, and `Aula-DB-Indices.csv` — index returns) were provided as part of a university course ("Introdução à Computação no Mercado Financeiro") and are **not included** in this repository, as they aren't mine to redistribute. To reproduce the analysis, place both files in the project root before running the notebook.

## Tech Stack

- Python 3
- NumPy, Pandas — data manipulation and time series
- Matplotlib — charts and visualizations
- Statsmodels — OLS regression for Alpha/Beta
- python-dateutil — date arithmetic

## Getting Started

```bash
pip install -r requirements.txt
jupyter notebook Portfolio_Models.ipynb
```

## License

MIT — see [LICENSE](LICENSE).

---
> Developed as part of the "Introdução à Computação no Mercado Financeiro" course.
