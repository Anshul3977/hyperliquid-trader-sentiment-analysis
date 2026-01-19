# Hyperliquid Trader Behavior & Bitcoin Sentiment Analysis

**Assignment for Junior Data Scientist – PrimeTrade.ai**

**Key Findings**
- Traders achieve highest **average PnL per trade** in **Extreme Greed** (~$68.6) and **Fear** (~$55.8) regimes.
- **Win rates** peak in **Extreme Greed** (92.8%) and are lowest in **Greed** (87.4%) → possible sign of overconfidence/FOMO.
- **Cumulative PnL** accelerates strongly during fear periods → contrarian entries appear profitable.
- Highest **total realized PnL** occurs in **Fear** phases despite fewer trades → bigger reward per opportunity.
- Traders are most active in **Greed** phases (highest trade count), but profitability per trade suffers.
- Statistical test (ANOVA) shows significant differences in PnL across sentiment categories (p < 0.05).

**Limitations & Next Steps**
- Dataset ends May 2025 → recent months missing
- All trades appear to be on one symbol (check `@107` coin)

**How to run**
```bash
pip install -r requirements.txt
jupyter notebook analysis.ipynb
