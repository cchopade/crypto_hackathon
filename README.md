# Coinberg Cryptocurrency Hackathon

## Bitcoin Fear & Greed Index
***

### Introduction
***
This is an attempt to create a sentiment index for Bitcoin. This sentiment index can be used for the purpose of trading into bitcoins and also as an indicator of overall mood. I have broadly divided the components of this index in two categories as follows.

**Market Sentiment**
 - Momentum
 - Implied Volatility (VIX)
 - Price / MA
 - Simulated Price (using Geometric Brownian Motion)
 
**Social Sentiment**
 - Google search trend
 - News
 - Reddit

### Methoodology
***
- **Momentum**: Momentum is calculated as $\frac{90dEMA - 30dEMA}{90dEMA}$


- **Implied Volatility**: Volatility Index is calculated using forecasted volatility using GARCH(1,1) model. Forecast for next 24 periods of volatility is made and calculated as $$\left ( \frac{VIX_t}{100} \right )^2 = \frac{1}{n}\sum_{k=1}^{n}E_{t}^{Q}\left [ \tilde{h}_{t+\frac{\tau_0 k}{n}} \right ]$$

  Refrence: Hao, J., & Zhang, J. E. (2013). GARCH option pricing models, the CBOE VIX, and variance risk premium. Journal of Financial Econometrics, 11(3), 556-580.


- **Price / 125d MA**


- **Google Search Trend**: Interest over time from google trends for the keyword 'bitcoin'


- **News**: Sentiment analysis using vaderSentiment api of news articles with 'bitcoin' keyword in their title


- **Reddit**: Top posts titles in subreddit r/bitcoin are captured and sentiment analysis using vaderSentiment is performed

