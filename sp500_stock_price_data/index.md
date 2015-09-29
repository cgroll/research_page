---
layout: default
---

# Data origin and access time

SP500 stock price data is downloaded from Yahoo!Finance. The list of
SP500 components is based on the Wikipedia table of ticker symbols of
all components. For future references, the original Wikipedia table is
stored [here](wikipedia_table.html). Ticker symbols and data were
accessed an September 29th, 2015.

In addition, industrial constituents

# Raw data: number of observations

Data was downloaded from **1962-01-02** to **2015-09-24** for **505**
different ticker symbols listed on
[Wikipedia](https://en.wikipedia.org/wiki/List_of_S%26P_500_companies). 

The unusual number of 505 stocks comes from the fact that 5 of the 500
different companies have two different stocks listed. (In fact, some
have even more, but two of them where included into the list of S&P500
constituents)

| Company                          | Ticker |
|----------------------------------+--------|
| Comcast A Corp                   | CMCSA  |
| Comcast Special Corp Class A     | CMCSK  |
| Discovery Communications-A       | DISCA  |
| Discovery Communications-C       | DISCK  |
| Google Inc Class A               | GOOGL  |
| Google Inc Class C               | GOOG   |
| News Corp. Class A               | NWSA   |
| News Corp. Class B               | NWS    |
| Twenty-First Century Fox Class A | FOXA   |
| Twenty-First Century Fox Class B | FOX    |

The maximum number of observations is reached for nine different
companies: 

<p align="center">
<table class="data-frame"><tbody><tr><th></th><th>AA</th><th>BA</th><th>CAT</th><th>KO</th><th>DD</th><th>GE</th><th>HPQ</th><th>IBM</th><th>DIS</th></tr><tr><th>1</th><td>13526</td><td>13526</td><td>13526</td><td>13526</td><td>13526</td><td>13526</td><td>13526</td><td>13526</td><td>13526</td></tr></tbody></table>
</p>

Overall, the number of available observations is quite distinct:

<p align="center">
<img src="../market_risk_analysis/pics/missing_observations-1.svg"
alt="Number of observations" height="350px" width="650px"/>
</p>

- picture distribution nObs

## Number of observations

Stocks with less than 300 observations:

<table class="data-frame"><tbody><tr><th></th><th>BXLT</th><th>CPGX</th><th>KHC</th><th>WRK</th><th>PYPL</th><th>QRVO</th></tr><tr><th>1</th><td>72</td><td>70</td><td>58</td><td>65</td><td>58</td><td>184</td></tr></tbody></table>

# Raw data: descriptive analysis

# Processed data: descriptive analysis
