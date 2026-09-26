# Data Quality Report

**Dataset:** Macroeconomic Indicators for Sub-Saharan Africa, 2006–2025 (WDI Extract)
**Version:** 1.0
**Date:** 29 September 2026

---

## 1. Duplicate Keys

| Check | Result |
|-------|--------|
| Key | `(country_code, year, indicator_code)` |
| Duplicates found | 0 |
| Action | None required |

The dataset has a unique composite key.

---

## 2. Impossible Values

| Variable | Rule | Result |
|----------|------|--------|
| `NY.GDP.MKTP.KD.ZG` | Flag if < −50 or > 50 | Flagged (not deleted) |
| `SL.UEM.TOTL.ZS` | Flag if < 0 or > 100 | Flagged (not deleted) |
| `FP.CPI.TOTL.ZG` | Flag extreme inflation (e.g., Zimbabwe 2019–2020) | Flagged |

Flagged values were **not deleted** because they are plausible extremes from the provider.

---

## 3. Unexpected Gaps

| Check | Result |
|-------|--------|
| Country-indicator series with < 10 years | Flagged (e.g., Eritrea, Somalia, South Sudan) |
| Consecutive missing runs | Documented, not imputed |
| End-of-period gaps (2024–2025) | Present for some indicators |

Gaps are preserved as missing and documented in `value_status`.

---

## 4. Missing vs. Zero

| Marker | Meaning |
|--------|---------|
| `..` in source | Missing → `NA` in curated dataset |
| `0` in source | True zero → retained as `0` |
| `value_status` | Explicitly encodes `observed` / `zero` / `missing` |

This satisfies the brief's requirement to distinguish missing observations from zero values.

---

## 5. Coverage Summary

| Indicator | Observed Years (approx.) |
|-----------|--------------------------|
| GDP growth | 20 |
| GDP per capita | 20 |
| Inflation | 18–20 |
| Unemployment | 20 (modelled) |
| Government consumption | 15–20 |
| Trade | 15–20 |
| FDI | 15–20 |
| Gross capital formation | 15–20 |

---

## 6. Known Limitations

- **Unemployment** is an ILO **modelled estimate**, not an observed value.
- **2025 values** may be **provisional**.
- **Country coverage** varies by indicator.
- **Comparability** may be affected by rebasing and revisions.
- **Uncertainty bounds** are not supplied by WDI for these indicators.

---

## 7. Uncertainty and Suppression

| Aspect | Status |
|--------|--------|
| Suppression flags | None in the WDI extract |
| Uncertainty bounds | Not supplied |
| Imputation | None performed |
| Rounding | None applied |

---

## 8. Recommendations to Users

1. Always filter on `value_status == "observed"` for analysis that requires reported values.
2. Use `price_basis` when comparing monetary variables.
3. Do not treat modelled unemployment as an observed labour-market statistic.
4. Report limitations explicitly in any downstream analysis.

---

**End of data quality report.**
