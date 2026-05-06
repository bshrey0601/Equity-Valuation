# Equity Intrinsic Value Calculator — DCF & Comparable Company Analysis

## Overview

This project is an equity valuation toolkit designed to estimate the intrinsic value of a publicly listed company using a combination of Discounted Cash Flow (DCF) valuation and Comparable Company Analysis. The project includes both a Python-based valuation notebook and an interactive browser-based web application.

The original analysis focuses on Reliance Industries Limited (`RELIANCE.NS`) as of December 30, 2022. The notebook performs the full valuation process step by step, while the web application converts the model into an interactive tool where users can adjust assumptions and immediately see updated valuation results.

> **Disclaimer:** This project is for academic and educational purposes only. It is not investment advice, and the results should not be used as the sole basis for any investment decision.

---

## Project Files

| File | Description |
|---|---|
| `Equity_Valuation_Reliance_Industries.ipynb` | Python notebook containing the full Reliance Industries valuation model, including historical financials, DCF valuation, sensitivity analysis, peer comparison, football field chart, and investment recommendation. |
| `index.html` | Standalone interactive web app that allows users to run a DCF and comparable multiples valuation directly in the browser. |

---

## Key Features

### 1. Historical Financial Analysis

The notebook uses Reliance Industries' FY2018–FY2022 financial data to analyze revenue growth, profitability, CapEx intensity, depreciation and amortization, debt, cash, and equity. These historical values serve as the foundation for the forecast assumptions used in the DCF model.

### 2. Discounted Cash Flow Valuation

The DCF model projects five years of future free cash flow under three revenue growth scenarios:

| Scenario | Growth Assumption | Purpose |
|---|---:|---|
| Bear Case | 10% | Conservative case with slower growth and macro headwinds |
| Base Case | 14% | Moderate case reflecting Jio, Retail, and O2C contributions |
| Bull Case | 18% | Optimistic case with stronger growth from 5G, Retail, and new energy |

The model calculates:

- Revenue forecast
- EBIT
- NOPAT
- Depreciation and amortization
- Capital expenditure
- Change in net working capital
- Free cash flow
- Present value of free cash flows
- Terminal value using the Gordon Growth Method
- Enterprise value
- Equity value
- Intrinsic value per share

### 3. Sensitivity Analysis

The notebook and web app include a WACC × terminal growth sensitivity table. This helps show how the intrinsic value changes when discount rate and terminal growth assumptions are adjusted.

### 4. Comparable Company Analysis

The notebook values Reliance using peer trading multiples from selected Indian large-cap energy, utility, and conglomerate peers. The peer set includes companies such as ONGC, IOC, BPCL, NTPC, Adani Enterprises, and Tata Motors.

The notebook applies four valuation multiples:

- EV/EBITDA
- EV/Revenue
- P/E
- P/B

The web app uses a simplified comparable valuation approach based mainly on EV/EBITDA and P/E inputs.

### 5. Football Field Chart

The football field chart summarizes valuation ranges across multiple methods, including:

- 52-week trading range
- Comparable company multiples
- DCF sensitivity range
- DCF scenario range

This gives users a quick view of whether the current market price is near the low, middle, or high end of the valuation range.

### 6. Investment Recommendation

The final recommendation is based on the blended intrinsic value compared with the current market price.

The project uses the following logic:

| Upside / Downside | Recommendation |
|---:|---|
| Greater than +15% | Strong Buy |
| +5% to +15% | Buy |
| -5% to +5% | Hold |
| -15% to -5% | Reduce |
| Less than -15% | Sell |

---

## Main Results for Reliance Industries

As of December 30, 2022, the model uses a current market price of **₹2,547** per share.

### DCF Valuation Results

| Scenario | Intrinsic Value / Share | Upside / Downside |
|---|---:|---:|
| Bear Case | ₹2,274 | -10.7% |
| Base Case | ₹2,711 | +6.4% |
| Bull Case | ₹3,210 | +26.0% |

### Comparable Company Valuation Results

| Method | Implied Price / Share | Upside / Downside |
|---|---:|---:|
| EV/EBITDA | ₹1,364 | -46.5% |
| EV/Revenue | ₹552 | -78.3% |
| P/E | ₹963 | -62.2% |
| P/B | ₹1,486 | -41.7% |

### Final Blended Valuation

| Metric | Result |
|---|---:|
| Current Market Price | ₹2,547 |
| Blended Intrinsic Value | ₹2,225 |
| Implied Downside | -12.6% |
| Final Recommendation | Reduce |

The blended valuation indicates that Reliance Industries was modestly overvalued relative to the model's assumptions as of December 30, 2022. The final recommendation is **Reduce**.

---

## Methodology

### Free Cash Flow Formula

```text
Free Cash Flow = EBIT × (1 - Tax Rate) + D&A - CapEx - Change in Net Working Capital
```

### Enterprise Value Formula

```text
Enterprise Value = Present Value of Forecast FCFs + Present Value of Terminal Value
```

### Terminal Value Formula

```text
Terminal Value = Final Year FCF × (1 + Terminal Growth Rate) / (WACC - Terminal Growth Rate)
```

### Equity Value Formula

```text
Equity Value = Enterprise Value - Net Debt
```

### Intrinsic Value Per Share Formula

```text
Intrinsic Value Per Share = Equity Value / Shares Outstanding
```

### Blended Intrinsic Value

The notebook combines DCF and comparable company valuation using a weighted approach:

```text
Blended Intrinsic Value = 70% × DCF Base Case Value + 30% × Average Comparable Valuation
```

This gives more weight to the DCF because Reliance has multiple business segments and long-term growth drivers that may not be fully captured by peer multiples alone.

---

## How to Run the Notebook

### Requirements

Install the following Python libraries:

```bash
pip install pandas numpy matplotlib seaborn
```

### Steps

1. Open `Equity_Valuation_Reliance_Industries.ipynb` in Jupyter Notebook, JupyterLab, Google Colab, or VS Code.
2. Run the cells from top to bottom.
3. Review the historical financial analysis, DCF output, sensitivity matrix, peer comparison, football field chart, and final recommendation.
4. Modify assumptions such as WACC, terminal growth, revenue growth, EBIT margin, or peer multiples to test alternative valuation views.

---

## How to Run the Web App

The web app is fully contained in a single `index.html` file.

### Steps

1. Download or save `index.html`.
2. Open the file in any modern web browser such as Chrome, Edge, Firefox, or Safari.
3. Select one of the available presets or choose `Custom`.
4. Adjust the financial inputs and valuation assumptions.
5. Review the updated intrinsic value, recommendation, DCF scenario chart, football field chart, projection table, and sensitivity table.
6. Click **Export PDF** to print or save the valuation output as a PDF.

No server, database, signup, API key, or internet connection is required once the file is saved locally.

---

## Web App Inputs

The web app allows users to change the following inputs:

### Company Profile

- Company name
- Revenue
- Total debt
- Cash
- Shares outstanding
- Current share price

### Operating Assumptions

- Bear case growth
- Base case growth
- Bull case growth
- EBIT margin
- Depreciation and amortization percentage
- CapEx percentage
- Tax rate

### Discounting Assumptions

- WACC
- Terminal growth rate

### Comparable Multiples

- EV/EBITDA
- P/E

---

## Current Limitations

1. **The preset financial data is historical.**  
   The Reliance preset is based on December 2022 assumptions. It should be updated for current valuation work.

2. **The web app does not pull live market data.**  
   If a user wants to value another company such as Apple, Microsoft, or Tesla, the latest financial data must be entered manually.

3. **Comparable company valuation is simplified in the web app.**  
   The notebook uses four multiples, while the web app uses fewer comparable inputs for simplicity.

4. **Working capital assumptions are simplified.**  
   Change in net working capital is modeled as a percentage of incremental revenue.

5. **The model depends heavily on assumptions.**  
   WACC, terminal growth, revenue growth, and margins can significantly affect the final intrinsic value.

---

## Possible Future Improvements

- Add live financial data using an API such as Yahoo Finance, Alpha Vantage, Financial Modeling Prep, or Polygon.io.
- Add support for U.S. companies with dollar-based formatting.
- Add a ticker search function.
- Add automatic peer selection by sector.
- Add revenue segment forecasting for conglomerates like Reliance.
- Add downloadable Excel output.
- Add scenario saving and comparison.
- Add charts for historical revenue, margins, and free cash flow.
- Add support for multiple currencies.

---

## Educational Value

This project is useful for learning:

- Equity research workflow
- DCF valuation mechanics
- Comparable company analysis
- Sensitivity analysis
- Football field valuation presentation
- Investment recommendation logic
- Python financial modeling
- Browser-based financial dashboard development

---

## Conclusion

This project combines a detailed Python valuation model with a clean interactive web application. The notebook explains the full valuation process for Reliance Industries, while the web app makes the model easier to use by allowing users to adjust assumptions in real time.

The final output for Reliance Industries as of December 30, 2022, shows a blended intrinsic value of **₹2,225** per share compared with a current market price of **₹2,547**, implying **-12.6% downside** and a final recommendation of **Reduce**.

Because the app does not use live data, users should update all financials, market prices, and peer multiples before using the model for any current company valuation.
