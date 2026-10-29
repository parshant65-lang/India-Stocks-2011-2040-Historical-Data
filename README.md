# India-Stocks-2011-2040-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 2011 to 2040)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-2011-2040-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (2011 to 2040)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 2011 | `RENUKA` | Shree Renuka Sugars Limited | `RENUKA.NS` |
| 2012 | `REPCOHOME` | Repco Home Finance Limited | `REPCOHOME.NS` |
| 2013 | `REPL` | Rudrabhishek Enterprises Limited | `REPL.NS` |
| 2014 | `REPRO` | Repro India Limited | `REPRO.NS` |
| 2015 | `RESPONIND` | Responsive Industries Limited | `RESPONIND.NS` |
| 2016 | `RETAIL` | JHS Svendgaard Retail Ventures Limited | `RETAIL.NS` |
| 2017 | `RGL` | Renaissance Global Limited | `RGL.NS` |
| 2018 | `RHETAN` | Rhetan TMT Limited | `RHETAN.NS` |
| 2019 | `RHFL` | Reliance Home Finance Limited | `RHFL.NS` |
| 2020 | `RHL` | Robust Hotels Limited | `RHL.NS` |
| 2021 | `RICOAUTO` | Rico Auto Industries Limited | `RICOAUTO.NS` |
| 2022 | `RIIL` | Reliance Industrial Infrastructure Limited | `RIIL.NS` |
| 2023 | `RIR` | RIR Power Electronics Limited | `RIR.NS` |
| 2024 | `RISHABH` | Rishabh Instruments Limited | `RISHABH.NS` |
| 2025 | `RITCO` | Ritco Logistics Limited | `RITCO.NS` |
| 2026 | `RKDL` | Ravi Kumar Distilleries Limited | `RKDL.NS` |
| 2027 | `RKEC` | RKEC Projects Limited | `RKEC.NS` |
| 2028 | `RKSWAMY` | R K Swamy Limited | `RKSWAMY.NS` |
| 2029 | `RMC` | RMC Switchgears Limited | `RMC.NS` |
| 2030 | `RMDRIP` | R M Drip and Sprinklers Systems Limited | `RMDRIP.NS` |
| 2031 | `RML` | Rane (Madras) Limited | `RML.NS` |
| 2032 | `RNBDENIMS` | R&B Denims Limited | `RNBDENIMS.NS` |
| 2033 | `ROHLTD` | Royal Orchid Hotels Limited | `ROHLTD.NS` |
| 2034 | `ROLEXRINGS` | Rolex Rings Limited | `ROLEXRINGS.NS` |
| 2035 | `ROLLT` | Rollatainers Limited | `ROLLT.NS` |
| 2036 | `ROML` | Raj Oil Mills Limited | `ROML.NS` |
| 2037 | `ROSSARI` | Rossari Biotech Limited | `ROSSARI.NS` |
| 2038 | `ROSSELLIND` | Rossell India Limited | `ROSSELLIND.NS` |
| 2039 | `ROSSTECH` | Rossell Techsys Limited | `ROSSTECH.NS` |
| 2040 | `ROTO` | Roto Pumps Limited | `ROTO.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream RENUKA 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-2011-2040-Historical-Data/main/RENUKA/1m/2026/10/RENUKA_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
