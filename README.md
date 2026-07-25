[README.md](https://github.com/user-attachments/files/30370694/README.md)
# Zain KSA (Tadawul: 7030) Stock Analysis

**16 years of daily price data. technical indicators & corporate event impact analysis**

## The Problem

Zain KSA is one of three mobile operators listed on the Saudi Stock Exchange (Tadawul),
alongside STC and Mobily. The stock has been through two major capital restructurings
(2012 and 2020), and I wanted to answer a question any analyst covering this stock
would ask: **how much risk do corporate restructurings actually add, and what do
standard technical indicators show about the stock's current state?**

## The Data

- 3,910 daily OHLCV records, March 2010 – January 2026
- Source: Kaggle (Yahoo Finance ticker 7030.SR)
- No missing values; ~5.4% of days show zero volume (normal for a mid-cap Tadawul stock,
  not a data quality issue — kept and flagged rather than dropped)

## The Approach

1. **Cleaned and structured** the data, flagging zero-volume days
2. **Built technical indicators** used in real equity analysis: SMA (20/50/200), RSI (14),
   MACD, Bollinger Bands, and 30-day rolling annualized volatility
3. **Measured volatility before vs. after** each corporate restructuring (180-day windows)
4. **Summarized yearly returns** to see the stock's longer-term pattern

## Key Findings

| Event | Volatility Before | Volatility After |
|---|---|---|
| 2012 Capital Reduction (SAR 14B → 4.8B) | 65.8% | 146.8% |
| 2020 Restructuring + Rights Issue | 30.9% | 47.3% |

1. **Corporate restructurings reliably spike volatility** — annualized volatility more
   than doubled after the 2012 event and rose ~50% after the 2020 event. Anyone holding
   or analyzing this stock around a similar corporate action should expect a
   short-term risk increase.
2. **The stock is range-bound, not trending** — the 200-day moving average shows repeated
   cycles between roughly SAR 7–13 over 16 years rather than sustained growth, typical of
   a mature telecom in a saturated 3-player market.
3. **Sharp mean-reversion after down years** — the two strongest years in the dataset
   (2012: +71%, 2023: +44%) both immediately followed down years, suggesting the stock
   tends to snap back rather than trend downward for long.

## Tools used

Python (pandas, NumPy, matplotlib) · technical indicator construction · time series
analysis · corporate event-impact analysis · data cleaning

## Files
- `notebook/zain_ksa_analysis.ipynb` — full analysis, runnable end-to-end
- `analysis.py` — standalone script version
- `data/zain_with_indicators.csv` — cleaned data with all indicators computed
- `data/yearly_returns.csv` — yearly return summary table
- `charts/` — exported chart images
