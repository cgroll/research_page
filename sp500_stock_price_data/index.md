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

## Observations per date

Most companies have no prices at the beginning of the sample period.
Hence, the number of observations gradually increases over time as
ever more companies become part of the dataset:

<p align="center">
<img src="../market_risk_analysis/pics/missing_observations-2.svg"
alt="Number of observations" width="650px"/>
</p>

The maximum number of observations is reached for nine different
companies: 

| Ticker | # observations |
|--------+----------------|
| AA     |          13526 |
| BA     |          13526 |
| CAT    |          13526 |
| DD     |          13526 |
| DIS    |          13526 |
| GE     |          13526 |
| HPQ    |          13526 |
| IBM    |          13526 |
| KO     |          13526 |

Individual companies' price series also do not tend to exhibit any
data gaps in between, so that sample size increases quite regularly
with duration to the first observation:

<p align="center">
<img src="../market_risk_analysis/pics/missing_observations-3.svg"
alt="Number of observations" width="650px"/>
</p>

Overall, the differences of the times of first observations leads to
quite distinct numbers of available observations per stock:

<p align="center">
<img src="../market_risk_analysis/pics/missing_observations-1.svg"
alt="Number of observations" width="650px"/>
</p>

<p align="center">
<img src="../market_risk_analysis/pics/missing_observations-4.svg"
alt="Number of observations" width="650px"/>
</p>

21 stocks have less than 1000 observations, 14 less than 750, and 9
even less than 500 observations:

| Ticker | First observation | # observations |
|--------+-------------------+----------------|
| ALLE   |        2013-11-18 |            466 |
| BXLT   |        2015-06-15 |             72 |
| CPGX   |        2015-06-17 |             70 |
| GOOG   |        2014-03-27 |            378 |
| KHC    |        2015-07-06 |             58 |
| NAVI   |        2014-04-17 |            363 |
| PYPL   |        2015-07-06 |             58 |
| QRVO   |        2015-01-02 |            184 |
| WRK    |        2015-06-24 |             65 |

# Raw data: descriptive analysis

# Processed data: descriptive analysis
