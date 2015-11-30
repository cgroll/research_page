---
layout: default
---

# Data origin and access time

SP500 stock price data is downloaded from Yahoo!Finance. The list of
SP500 components is based on the Wikipedia table of ticker symbols of
all components. For future references, the original Wikipedia table is
stored [here](wikipedia_table.html). Ticker symbols and data were
accessed on September 29th, 2015.

In addition, the Wikipedia table also contains information about
industrial affiliation, which also was accessed and downloaded on
September 29th, 2015.

# Raw data: number of observations

Data was downloaded from **1962-01-02** to **2015-09-24** for **505**
different ticker symbols listed on
[Wikipedia](https://en.wikipedia.org/wiki/List_of_S%26P_500_companies). 

The unusual number of 505 stocks comes from the fact that 5 of the 500
different companies have two different stocks listed (in fact, some
have even more, but only two of them where included into the list of
S&P500 constituents).

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
<img src="https://rawgit.com/cgroll/market_risk_analysis/master/pics/missing_observations-2.svg"
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
<img src="https://rawgit.com/cgroll/market_risk_analysis/master/pics/missing_observations-3.svg"
alt="Number of observations" width="650px"/>
</p>

Overall, the differences of the times of first observations leads to
quite distinct numbers of available observations per stock:

<p align="center">
<img src="https://rawgit.com/cgroll/market_risk_analysis/master/pics/missing_observations-1.svg"
alt="Number of observations" width="650px"/>
</p>

A more detailed look at the tail region of critically low numbers of
observations: 

<p align="center">
<img src="https://rawgit.com/cgroll/market_risk_analysis/master/pics/missing_observations-4.svg"
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

# Raw data: returns of zero

The dataset contains a lot of returns that are equal to zero, hence
representing days without price movements. From overall **6,831,135**
possible observations (number of dates $$\times$$ number of assets)
only **3,215,398** are not missing, which amounts to **52.9%** missing
values. Taking all available observations, in turn, another **5.7%**
of them are zero.

The number of zero returns differs over assets:

<p align="center">
<img src="https://rawgit.com/cgroll/market_risk_analysis/master/pics/zero_returns-1.svg"
alt="Number of observations" width="650px"/>
</p>

Making a more meaningful comparison, however, requires an adjustment
to the different number of observations per stock. Looking at relative
frequencies of zero returns, individual companies still differ:

<p align="center">
<img src="https://rawgit.com/cgroll/market_risk_analysis/master/pics/zero_returns-2.svg"
alt="Number of observations" width="650px"/>
</p>

There does exist a pattern, however, as stocks with first available
observations dating back for a longer time tend to have a higher
frequency of zero returns:

<p align="center">
<img src="../market_risk_analysis/pics/zero_returns-3.svg"
alt="Number of observations" width="650px"/>
</p>

The reason for the differences between assets is a changing minimum
tick size over time, as larger minimum tick sizes imply more returns
of zero. The following tick size changes did occur during the sample
period: 

- June 24, 1997: change from 1/8$ to 1/16$
- January 29, 2001: change from 1/16$ to 1/100$ [[Spada et al., 2010,
  rv_spad_farm_2010_tick]](#refs) 

The consequences of tick size changes on zero return frequencies best
can be seen by looking at zero return frequencies for each day.
Relative frequency thereby is measured with regards to the number of
available observations at that given day, hence excluding any missing
observations.

<p align="center">
<img src="../market_risk_analysis/pics/zero_returns-4.svg"
alt="Number of observations" width="650px"/>
</p>

In numbers, the following zero return frequencies exist per time
period: 

| period                  | zero return frequency |
|-------------------------+-----------------------|
| 1962-01-03 - 1997-06-23 |              0.132529 |
| 1997-06-24 - 2001-01-28 |             0.0454137 |
| 2001-01-28 - 2015-09-24 |             0.0097912 |

The tick size changes hence cause non-stationary time series, as the
statistical properties of the data clearly change over time. Still,
however, we will neglect this non-stationarity, as positive and
negative small returns should get shrinked to zero in a similar
manner, and hence roughly cancel out. Nevertheless, this
simplification might entail some danger, as some assets have more than
10% zero returns, with a maximum frequency of zero returns of almost
25% for one asset.

## Volatility vs zero return frequency

As increasing volatility diminishes the probability of returns being
close to zero, we should expect a negative relation between volatility
and zero return frequencies. In order to test this hypothesis, the
S&P500 index was downloaded from Yahoo!Finance, and its underlying
volatility series was estimated with a GARCH(1,1) model with
*t*-distributed innovations.

As the zero return frequency series contains structural breaks, the
relation between volatility and zero return frequencies must be
examined for each tick size regime separately. Calculating the
correlation between both time series gives the following values:

| period                  | zero return frequency |
|-------------------------+-----------------------|
| 1962-01-03 - 1997-06-23 |           -0.00663718 |
| 1997-06-24 - 2001-01-28 |             -0.223812 |
| 2001-01-28 - 2015-09-24 |             -0.187395 |

One would expect that correlations should be decreasing in absolute
size, since volatility should have less effects the smaller the tick
size gets. An explanation could be, that the first regime (especially
in the beginning) consists of only very few assets, for whom the
S&P500 volatility might be a bad approximation if they do not follow
general market patterns closely.

In order to get more detailed insights, the following graphics shows
the estimated S&P500 volatility series, standardized to mean zero and
standard deviation of one, together with a smoothed estimator for the
standardized zero return frequencies. The smoothed estimator is
plotted with negative sign, in order to translate the negative
relation between both lines into a positive one.

<p align="center">
<img src="../market_risk_analysis/pics/zero_returns-5.svg"
alt="Number of observations" width="650px"/>
</p>

<p align="center">
<img src="../market_risk_analysis/pics/zero_returns-6.svg"
alt="Number of observations" width="650px"/>
</p>

<p align="center">
<img src="../market_risk_analysis/pics/zero_returns-7.svg"
alt="Number of observations" width="650px"/>
</p>

All graphics show some indication of co-movement between both lines,
and the relation between both lines gets stronger starting
approximately 1975.

# Raw data: descriptive analysis

# Processed data: descriptive analysis


# References

<iframe src="../refs/html_refs/sp500_index.html" width="600" height="200"></iframe>
