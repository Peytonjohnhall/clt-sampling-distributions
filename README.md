# Sampling Distributions and the Central Limit Theorem

A simulation study of how sample means behave under repeated sampling from a finite population of 300 employee satisfaction scores (1–7 scale).

## Question

How do the centre and spread of the sampling distribution of the mean change with sample size, and how well does the standard error formula σ/√n describe samples drawn without replacement from a finite population?

## Data

300 satisfaction responses supplied as a teaching dataset (population mean 3.9633, population SD 1.0933). The data file is not included in this repository because it contains respondent-level records.

## Methods

- Treated the 300 responses as a known population.
- Drew B = 5,000 samples without replacement for each n = 5, 10, 30, 50 and 100, and stored each sample mean.
- Compared the empirical standard error (SD of the simulated means) with the independent-draw formula σ/√n and the finite-population formula σ/√n · √((N − n)/(N − 1)).

## Results

| n | Empirical SE | σ/√n | Finite-population SE |
|---|---|---|---|
| 5 | 0.4887 | 0.4889 | 0.4857 |
| 10 | 0.3381 | 0.3457 | 0.3405 |
| 30 | 0.1896 | 0.1996 | 0.1897 |
| 50 | 0.1401 | 0.1546 | 0.1414 |
| 100 | 0.0896 | 0.1093 | 0.0894 |

The sample means centre on the population mean at every n, and their spread falls as n grows. The independent-draw formula overstates the standard error more as n becomes a larger fraction of N. The finite-population correction closely matches the simulated values, so the discrepancy comes from the without-replacement sampling design, not from a failure of the CLT.

## Limitations

- The results describe this teaching population only, not employees in general.
- For small n the sampling distribution remains visibly discrete, because the responses are bounded integer scores.
- The empirical values include Monte Carlo variation from a fixed B.

## Running the notebook

Requires Python with pandas, numpy and matplotlib. The notebook expects `satisfaction_survey.txt` (tab-separated, with a `satisfaction` column) in the same folder.

## Credit

Adapted from course starter code for SEIS 631 (Data Preparation and Analysis), University of St. Thomas, Fall 2026.
