# Hyperliquid Trader Behavior & Bitcoin Sentiment Analysis

> **Assignment for Junior Data Scientist – PrimeTrade.ai**

A comprehensive analysis examining the relationship between Bitcoin Fear & Greed Index sentiment regimes and trader performance on the Hyperliquid decentralized exchange.

---

## 📊 Executive Summary

This project analyzes trader behavior across different market sentiment conditions to identify actionable patterns in profitability and risk-taking. The analysis reveals that **contrarian strategies during fear regimes** and **strategic entry during extreme greed** produce superior risk-adjusted returns.

### Key Metrics Analyzed
- **Profit & Loss (PnL)** performance across sentiment regimes
- **Win rates** and trade success patterns
- **Trade volume** and activity levels
- **Cumulative profitability** trends over time

---

## 🔍 Key Findings

### 1. Profitability by Sentiment Regime

| Sentiment Regime | Avg PnL per Trade | Win Rate | Interpretation |
|-----------------|-------------------|----------|----------------|
| **Extreme Greed** | ~$68.6 | 92.8% | Highest profitability with excellent success rate |
| **Fear** | ~$55.8 | High | Strong contrarian opportunities |
| **Greed** | Lower | 87.4% | Most active but lowest win rate → overconfidence signal |

### 2. Critical Insights

#### ✅ **Contrarian Strategy Validation**
- **Cumulative PnL accelerates during fear periods** → entering positions when others panic appears highly profitable
- **Highest total realized PnL occurs in Fear phases** despite fewer total trades
- Suggests skilled traders capitalize on market overreactions

#### ⚠️ **Overconfidence in Greed Regimes**
- **Highest trade count** observed during Greed periods
- **Lowest win rates** (87.4%) suggest FOMO-driven entries
- More activity ≠ better outcomes → discipline matters

#### 🎯 **Extreme Greed Sweet Spot**
- **Peak average PnL** (~$68.6) + **peak win rate** (92.8%)
- Suggests momentum strategies work well in euphoric markets
- Risk: These periods are typically short-lived

### 3. Statistical Validation
- **ANOVA test results**: Significant differences in PnL across sentiment categories (p < 0.05)
- Sentiment regimes are **statistically meaningful predictors** of trader performance
- Results are unlikely due to random chance

---

## 📈 Strategic Implications

### For Traders
1. **Prioritize fear-based entries** for contrarian plays with high reward potential
2. **Exercise caution during greed regimes** → avoid overtrading
3. **Capitalize on extreme greed** when momentum is strong, but use tight risk management
4. **Quality over quantity** → fewer trades in fear = higher PnL per trade

### For Algorithmic Strategies
- Incorporate **sentiment indicators** as signal filters
- Increase position sizing during fear regimes (with proper risk controls)
- Reduce trading frequency during greed periods unless strict entry criteria are met
- Monitor sentiment shifts as regime change indicators

---

## ⚠️ Limitations & Caveats

### Data Constraints
- **Dataset ends May 2025** → recent market conditions not reflected
- Missing approximately **8 months** of potential market data
- Market structure may have evolved since data cutoff

### Scope Limitations
- **Single symbol analysis** → all trades appear to be on `@107` coin
- Results may not generalize to other trading pairs or asset classes
- No cross-validation with other sentiment indicators (e.g., funding rates, open interest)

### Methodological Considerations
- **Survivorship bias** → only includes active traders who remain in dataset
- **Attribution challenge** → cannot isolate sentiment impact from other market factors
- **Regime classification** → Fear & Greed Index is a composite metric with its own limitations

---

## 🚀 Next Steps & Future Work

### Immediate Enhancements
- [ ] Update dataset with recent market data (June 2025 - present)
- [ ] Verify symbol diversity → expand beyond `@107` if data permits
- [ ] Add transaction cost analysis → impact on net profitability

### Advanced Analysis
- [ ] **Multi-symbol comparison** → generalizability testing
- [ ] **Time-series forecasting** → predict regime changes
- [ ] **Risk-adjusted metrics** → Sharpe ratio, max drawdown by regime
- [ ] **Entry/exit timing analysis** → optimal holding periods per regime
- [ ] **Cohort analysis** → beginner vs. experienced trader behavior

### Model Development
- [ ] Build **sentiment-based trading signals**
- [ ] Backtest strategies on out-of-sample data
- [ ] Incorporate **additional market features** (volatility, volume, funding rates)
- [ ] Develop **regime-switching models** for automated strategy adjustment

---

## 🛠️ Installation & Setup

### Prerequisites
- Python 3.8 or higher
- Jupyter Notebook or JupyterLab

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd hyperliquid-sentiment-analysis

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook analysis.ipynb
```

### Dependencies

```
pandas          # Data manipulation and analysis
numpy           # Numerical computations
matplotlib      # Visualization and plotting
seaborn         # Statistical data visualization
scipy           # Statistical testing (ANOVA)
```

---

## 📁 Project Structure

```
.
├── README.md              # This file
├── requirements.txt       # Python dependencies
├── analysis.ipynb        # Main Jupyter notebook with analysis
└── data/                 # Data directory (if applicable)
    └── trader_data.csv   # Trading data with sentiment labels
```

---

## 📊 Methodology

### Data Processing
1. Load trader transaction data from Hyperliquid
2. Merge with Bitcoin Fear & Greed Index timestamps
3. Classify each trade into sentiment regime

### Analysis Framework
1. **Descriptive statistics** → PnL, win rates, trade counts by regime
2. **Comparative analysis** → performance across sentiment categories
3. **Statistical testing** → ANOVA for significance validation
4. **Visualization** → trends, distributions, and regime comparisons

### Sentiment Classification
- **Extreme Fear** (0-24)
- **Fear** (25-44)
- **Neutral** (45-55)
- **Greed** (56-74)
- **Extreme Greed** (75-100)

---

## 📖 Usage Example

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load data
df = pd.read_csv('data/trader_data.csv')

# Filter by sentiment regime
fear_trades = df[df['sentiment_regime'] == 'Fear']
greed_trades = df[df['sentiment_regime'] == 'Greed']

# Compare profitability
print(f"Fear avg PnL: ${fear_trades['pnl'].mean():.2f}")
print(f"Greed avg PnL: ${greed_trades['pnl'].mean():.2f}")

# Visualize
sns.boxplot(data=df, x='sentiment_regime', y='pnl')
plt.title('PnL Distribution by Sentiment Regime')
plt.show()
```

---

## 🤝 Contributing

This is an assignment submission, but suggestions for improvement are welcome:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/enhancement`)
3. Commit your changes (`git commit -m 'Add analysis enhancement'`)
4. Push to the branch (`git push origin feature/enhancement`)
5. Open a Pull Request

---

## 📝 License

This project is created as part of an assignment for PrimeTrade.ai. All rights reserved.

---

## 👤 Author

**Junior Data Scientist Candidate**  
Assignment for PrimeTrade.ai  
January 2026

---

## 📧 Contact

For questions or feedback regarding this analysis:
- Create an issue in the repository
- Contact PrimeTrade.ai recruitment team

---

## 🙏 Acknowledgments

- **Hyperliquid** for providing decentralized trading infrastructure
- **Alternative.me** for Bitcoin Fear & Greed Index data
- **PrimeTrade.ai** for the opportunity to work on this analysis

---

**Note**: This analysis is for educational and demonstration purposes. Past performance does not guarantee future results. Always conduct your own research before making trading decisions.
