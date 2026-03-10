Institutional Ownership Networks and Stock Return Comovement During Market Stress 
Varshini Narayanan

Project Description

This project studies whether firms that share large institutional investors exhibit stronger stock return comovement during periods of market stress. The research question is:
Do stocks held by the same large institutional investors move together more during periods of elevated market volatility?
The project focuses on a sample of 20 large U.S. publicly traded firms. Institutional ownership is modeled as a network in which firms are connected if they share common institutional shareholders. The strength of the connection between two firms is measured using weighted ownership overlap derived from SEC Form 13F filings.
Market stress is identified using realized volatility constructed from daily S&P 500 returns. Days in the top 10% of the volatility distribution are classified as stress days. For each quarter, pairwise stock return correlations are computed using daily returns during these stress periods. These correlations measure the degree of comovement between firm pairs when markets experience large shocks.
The ownership network is constructed quarterly. Institutional ownership is first represented as a bipartite network between firms and institutions. This is then projected into a firm–firm weighted network using matrix multiplication, where the weight reflects the degree of shared institutional ownership. The empirical analysis examines whether greater ownership overlap is associated with higher stress period return correlations. The results show a positive and statistically significant relationship between ownership overlap and return comovement during stress, consistent with my hypothesis that institutional ownership networks amplify comovement in turbulent market conditions. THis is also calculated during non stress periods 


Data


Yahoo Finance (List of Large Public Firms)
Link: https://finance.yahoo.com/
Method: Web scraping (via Jupyter notebook YahooScrape.ipynb)
Purpose: Construct list of 20 large U.S. publicly traded firms.
FRED (Federal Reserve Economic Data)
Link: https://fred.stlouisfed.org/
Method: API access (via FREDScrape.ipynb)
Purpose: Download daily S&P 500 prices to compute realized volatility and identify stress days. Output stored as stress_days.csv.
WRDS (Wharton Research Data Services)
Link: https://wrds-www.wharton.upenn.edu/
Method: Python WRDS API (via WRDSReturns.ipynb and OwnershipNetwork.ipynb)
Purpose:
CRSP daily stock returns for selected firms
Institutional ownership data from SEC Form 13F filings (Thomson Reuters S34 dataset)


Libraries:

pandas (v2.x)
numpy (v1.x)
matplotlib (v3.x)
seaborn (v0.x)
statsmodels (v0.x)
networkx (v3.x)
wrds (v3.x)
sqlalchemy (v2.x)



Repo Structure (will be organized to include a csv folder)

├── FREDScrape.ipynb
│   - Pulls S&P 500 price data from FRED API
│   - Computes daily returns and rolling volatility
│   - Identifies stress days (top 10% volatility)
│   - Outputs stress_days.csv
│
├── YahooScrape.ipynb
│   - Scrapes Yahoo Finance to identify large publicly traded firms
│   - Outputs firm_list.csv
│
├── WRDSReturns.ipynb
│   - Connects to WRDS via Python API
│   - Downloads CRSP daily stock return data for selected firms
│
├── OwnershipNetwork.ipynb
│   - Downloads institutional ownership data (13F) from WRDS
│   - Constructs firm–institution bipartite network
│   - Projects to firm–firm ownership overlap network
│   - Computes stress-period pairwise return correlations
│   - Runs regression analysis and produces visualizations
│


--NonStressNetwork.ipynb
mint data (folder)
------------├── firm_list.csv
│   - List of selected firms
│
----------├── stress_days.csv
│   - Identified market stress days
│
└------ -----── stress_volatility_institutional_data2.csv
    - Combined dataset of stress-day returns and institutional ownership
    - Uploaded as link due to file size constraints
mint slides (folder)
------------- mint 1
--------------mint 2


    
    
