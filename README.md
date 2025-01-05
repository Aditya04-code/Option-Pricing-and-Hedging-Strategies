# Option Pricing and Hedging Strategies Project

This project investigates option pricing and hedging strategies based on WBA stock. It covers key concepts including **Put-Call Parity**, **Implied Volatility**, **Delta Hedging**, and **Volatility Spreads**.

---

## 1. Put-Call Parity

Put-Call Parity is a fundamental concept in finance that defines the relationship between European call and put options with the same expiration date and strike price. When violated, it provides arbitrage opportunities.

### Key Findings:
- **Equation 1:** \( S + P > C + Ke^{-rT} \)  
  Strategy: Buy a call, sell a put, and short the stock or lend money at the risk-free rate.  
- **Equation 2:** \( S + P < C + Ke^{-rT} \)  
  Strategy: Buy a put, sell a call, buy the stock, or borrow money at the risk-free rate.

### Risks to Estimates:
- **Risk-Free Rate Assumptions**: May not reflect actual rates during the option's lifetime.  
- **Time to Expiration**: Small errors could distort discount factors.  
- **Transaction Costs**: Ignoring commissions, bid-ask spreads, etc., could reduce or eliminate profits.  
- **Liquidity**: Illiquid options might hinder execution.  
- **Model Limitations**: Assumes European-style options in a perfect market.  

---

## 2. Implied Volatility

Implied Volatility (IV) represents the market's expectation of future price volatility. It is forward-looking compared to historical volatility, which is backward-looking.

### Methodology:
1. Used the **Black-Scholes Formula** to calculate theoretical option prices.
2. Employed the `Goal Seek` function to adjust IV until the theoretical price matched the trading price.

### Observations:
- **Volatility Smile**:  
  - For **put options**, IV is lowest at at-the-money (ATM) strikes and increases for in-the-money (ITM) and out-of-the-money (OTM) options.  
  - Similar behavior was observed for **call options**.  
  - The downward slope for high IV and upward slope for low IV reflects mean reversion.

### Inconsistencies in IV:
Factors like **put-call parity violations**, **market performance**, and **investor sentiment** contributed to variations in IV.

---

## 3. Delta Hedging

Delta Hedging is an options trading strategy to mitigate price change risks in the underlying asset.

### Methodology:
1. Calculated Delta (\( \Delta \)) using \( \Delta_{Call} = N(d1) \).
2. Adjusted the portfolio daily to remain delta-neutral by buying or selling shares as Delta changed.
3. Compared two approaches:
   - **Using Implied Volatility**
   - **Using Historical Volatility (22-day)**

### Costs Considered:
- **Cost of Shares**: Price paid or received for hedging.  
- **Cumulative Costs**: Includes interest (4.7%) for borrowed shares.  

### Key Insights:
- Daily rebalancing ensured minimal risk.  
- The two approaches yielded different profit and loss results, highlighting the impact of volatility estimation.

---

## 4. Volatility Trade

A volatility trade was constructed by comparing **historical volatility** (22-day) with **option implied volatility**.

### Steps:
1. Constructed a **volatility spread** using both calls and puts.
2. Plotted the payoff function for the spread.
3. Calculated the payoff on the option's expiry.

### Observations:
- **Call Spreads** and **Put Spreads** were compared for cost-effectiveness.  

---

## Conclusion

This project provided insights into the application of advanced financial concepts for real-world trading scenarios. Key learnings included:
- Identifying arbitrage opportunities through **Put-Call Parity**.
- Using **Implied Volatility** to understand market sentiment.
- Implementing dynamic **Delta Hedging** to minimize risk.
- Constructing effective **Volatility Spreads** for profitable trades.

By addressing risks and model limitations, the analysis demonstrates the complexity and challenges of financial modeling in live markets.

---

