# Project Charter: SECOM Yield Improvement

**Project:** Semiconductor Yield Improvement (Six Sigma DMAIC)
**Author:** Jamaluddin Mohammed
**Date:** November 2026
**Status:** Define phase

## 1. Problem statement

Between July 19, 2008 and October 17, 2008 (89 days), 104 of 1,567 units
produced on a semiconductor manufacturing line failed in-house final test.
This is a fail rate of 6.6%, a yield of 93.4%, or about 66,000 defects per
million opportunities (DPMO).

The line records 590 process signals for every unit, but it is not known
which of these signals are linked to the failures. Without that knowledge,
engineers cannot target their monitoring or improvement work.

## 2. Goal

### Project goal (what this project will deliver by December 6, 2026)

1. Identify the process signals most strongly linked to failures (10 or
   fewer), each supported by a statistical test.
2. Build an early-warning model that flags likely failures before final
   test, with a balanced error rate at or below 33.5%, the best baseline
   published on the UCI dataset page.
3. Deliver control charts and a control plan for the key signals.

### Business goal (target for the fab, not a measured result)

If the fab acts on these findings, reduce the fail rate from 6.6% to 3.3%
(a 50% reduction), raising yield from 93.4% to about 96.7%.

*Note: SECOM is historical data, so this project cannot measure a real
yield change. The business goal shows the intended impact only.*

## 3. Scope

### In scope

- The 1,567 units and 590 process signals in the SECOM dataset,
  July 19 to October 17, 2008
- The pass/fail result of in-house final test
- Checking data quality (missing values, constant signals, inconsistent
  timestamps)
- Identifying the signals statistically linked to failures
- Building and testing an early-warning model
- Control charts and a control plan for the key signals
- An estimated cost of the yield loss, using stated assumptions

### Out of scope

- Changing the real process or running experiments in the fab
- Identifying what each signal physically measures (the signals are
  anonymized)
- Proving root cause: this project finds links, not proven causes
- Other products, production lines, or time periods
- Deploying the model on a live production line

### Constraints

- Historical data only (2008); no access to the fab or its engineers
- Signal names are hidden, so findings are reported by signal number
- No real cost data is available

### Assumptions

- Each row is one production unit, tested once
- Each unit has one defect opportunity (pass or fail), for DPMO
- Cost figures in the business case are illustrative estimates

## 4. Business case

Every failed unit has already used material, machine time and labor before
it is scrapped. This scrap is the main cost of poor quality (COPQ).

**Annualized volume.** The data covers 89 days. Scaled to a full year at the
same rate, the line produces about 6,426 units, of which about 427 fail.

**Estimated cost.** Real cost data is not available, so three scenarios are
shown for the cost of one failed unit:

| Cost per failed unit | Yearly loss from failures | Yearly saving if failures are halved |
|---|---|---|
| $1,000 (low) | ~$427,000 | ~$213,000 |
| $3,000 (medium) | ~$1,280,000 | ~$640,000 |
| $5,000 (high) | ~$2,133,000 | ~$1,066,000 |

Even in the low-cost scenario, halving failures would save over $200,000 a
year, which supports investing in this analysis.

*Assumptions: the 89-day production rate continues all year; costs per unit
are illustrative, not real fab figures. Calculation in
notebooks/01_explore_data.ipynb.*

## 5. Team and roles

This is a solo portfolio project. Jamaluddin Mohammed performs all analysis
and project management. The table shows how the roles would be filled in a
real fab.

| Role | Responsibility | In this project |
|---|---|---|
| Project lead (Green Belt) | Runs the DMAIC project and the analysis | Jamaluddin Mohammed |
| Sponsor | Approves the project and resources | Would be: fab operations manager |
| Process owner | Owns the line and sustains the fix | Would be: line or module manager |
| Subject-matter experts | Explain what the signals measure | Would be: process and equipment engineers |

## 6. Timeline

Each phase ends with a tollgate review, recorded as a Git tag.

| Phase | Dates | Key deliverables | Tollgate tag |
|---|---|---|---|
| Define | Nov 9 to 15, 2026 | Charter, SIPOC | v0.1-define |
| Measure | Nov 16 to 22, 2026 | Data quality report, baseline yield and DPMO | v0.2-measure |
| Analyze | Nov 23 to 29, 2026 | Signals linked to failures, Pareto chart | v0.3-analyze |
| Improve | Nov 30 to Dec 3, 2026 | Early-warning model, recommendations | v0.4-improve |
| Control | Dec 3 to 6, 2026 | Control charts, control plan, executive summary | v1.0 |