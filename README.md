# Institutional Ownership Networks and Stock Return Comovement During Market Stress

**Author:** Varshini Narayanan

---
 
# Project Description

## Summary

This project studies whether firms that share large institutional investors exhibit stronger stock return comovement during periods of market stress.

The core research question is:

**Do stocks held by the same large institutional investors move together more during periods of elevated market volatility?**

Key elements of the project:

- A sample of 20 large U.S. publicly traded firms is constructed using Yahoo Finance.
- Institutional ownership is modeled as a network, where firms are connected if they share common institutional investors.
- The strength of the connection between firms is measured using weighted ownership overlap derived from SEC Form 13F filings.
- Market stress is identified using realized volatility calculated from daily S&P 500 returns.
- Days in the top 10% of the volatility distribution are classified as stress days.
- For each quarter, pairwise stock return correlations are calculated using daily returns during stress periods to measure comovement.

The ownership network is constructed quarterly:

1. Institutional ownership is first represented as a bipartite network between firms and institutions.
2. This network is then projected into a firm–firm weighted network** using matrix multiplication.
3. Edge weights represent the degree of shared institutional ownership between firms.

Empirical analysis tests whether greater ownership overlap is associated with higher return correlations during stress periods.

Results show a positive and statistically significant relationship between ownership overlap and return comovement during stress periods, supporting the hypothesis that institutional ownership networks amplify comovement during turbulent market conditions.

Additional analysis during non-stress periods shows that institutional ownership overlap also increases stock return correlations when volatility is low, but the magnitude of the effect increases substantially as market volatility rises, indicating that shared institutional ownership contributes more strongly to comovement during market stress.

---

## Additional Info

| File                   | Lines of Code |
| ---------------------- | ------------- |
| YahooScrape.ipynb      | 51            |
| FREDScrape.ipynb       | 66            |
| WRDSReturns.ipynb      | 115           |
| OwnershipNetwork.ipynb | 436           |
| NonStressNetwork.ipynb | 102           |

Total lines of code: 770 (including comments)

**Methods and Analysis:**

- Network construction from institutional ownership data
- Pairwise stock return correlation analysis
- Volatility classification using realized S&P 500 volatility
- Linear regression analysis controlling for industry effects

**Project strength:**  
A major strength of this project is the **network-based modeling of institutional ownership**, which allows the analysis to capture interconnected ownership structures across firms and link them directly to stock return dynamics.

---

# Data

| Source | Link | Collection Method | Purpose |
|------|------|------|------|
| Yahoo Finance | https://finance.yahoo.com/ | Web scraping via `YahooScrape.ipynb` | Construct list of 20 large U.S. publicly traded firms |
| FRED (Federal Reserve Economic Data) | https://fred.stlouisfed.org/ | API via `FREDScrape.ipynb` | Download daily S&P 500 prices to compute realized volatility and identify stress days |
| WRDS (Wharton Research Data Services) | https://wrds-www.wharton.upenn.edu/ | Python WRDS API via `WRDSReturns.ipynb` and `OwnershipNetwork.ipynb` | Obtain CRSP daily stock returns and institutional ownership data from SEC Form 13F filings (Thomson Reuters S34 dataset) |

Generated datasets stored in the repository include:

- `firm_list.csv` – list of selected firms
- `stress_days.csv` – identified market stress days
- `str_vol_institutional_data.csv` – merged dataset used for analysis

---

# Repository Structure
```
final-project-mint/
│
├── Data Collection and Processing/
│   ├── YahooScrape.ipynb
│   ├── FREDScrape.ipynb
│   └── WRDSReturns.ipynb
│
├── Data Analysis/
│   ├── OwnershipNetwork.ipynb
│   └── NonStressNetwork.ipynb
│
├── Mint Data/
│   ├── link to str_vol_institutional_data.csv
│   ├── stress_days.csv
│   └── firm_list.csv
│
├── Mint Slides/
│   ├── Mint1.pdf
│   └── Mint2.pdf
│
├── Project Check Ins/
│   ├── Project Check In2.pdf
│   └── Week 5 Check In.pdf
│
└── README.md
```


### Folder descriptions

- **Data Collection and Processing/** – scripts used to scrape, download, and prepare raw data sources.
- **Data Analysis/** – notebooks performing ownership network construction, return correlation analysis, and regression analysis.
- **Mint Data/** – processed datasets used in the final analysis.
- **Mint Slides/** – presentation slides for the project.
- **Project Check Ins/** – project progress reports and check-in documentation.

---

# Libraries

| Library | Version |
|------|------|
| pandas | 2.x |
| numpy | 1.x |
| matplotlib | 3.x |
| seaborn | 0.x |
| statsmodels | 0.x |
| networkx | 3.x |
| wrds | 3.x |
| sqlalchemy | 2.x |
| requests | latest |
| beautifulsoup4 | latest |
| yfinance | latest |

---

# Contributions

**Varshini Narayanan**

This project was completed individually. Responsibilities included:

- Designing the research question and empirical strategy
- Collecting firm lists via Yahoo Finance scraping (`YahooScrape.ipynb`)
- Downloading and processing market volatility data from FRED (`FREDScrape.ipynb`)
- Extracting CRSP returns and institutional ownership data through WRDS (`WRDSReturns.ipynb`)
- Constructing the institutional ownership network (`OwnershipNetwork.ipynb`)
- Performing correlation and regression analysis for stress and non-stress periods (`OwnershipNetwork.ipynb`, `NonStressNetwork.ipynb`)
- Creating visualizations and tables
- Preparing presentation slides and project documentation

Each notebook includes author information, description, and AI disclosure where applicable.

---

# AI Usage Statement

AI tools were used in limited ways to assist with formatting and coding efficiency.

**ChatGPT**

- Assisted with formatting tables and improving documentation structure.
- Helped format regression output tables in `NonStressNetwork.ipynb`.
- Assisted with visualization formatting in `FREDScrape.ipynb`.
- Helped structure and format the project README.

All analytical design, data collection, econometric analysis, and interpretation of results were completed by the author. AI tools were used only as supportive aids for formatting or minor coding assistance.

---
# Project Links
Video Overview: https://drive.google.com/file/d/1uNLa42aFLjTOTya3f6QVltG5ghI3AYme/view?usp=sharing
Class Slides: https://docs.google.com/presentation/d/1SoKvsnA9Tr8x61woTnffMO_tfaRs_nQcoesnPwvu77I/edit?usp=sharing
Updated Slides: https://docs.google.com/presentation/d/1i3HPRy_XE8VvCuIUPTBcE2sTHeBaKT5hVDdb-on_lrc/edit?usp=sharing
