# ST2195 Coursework Project

Coursework for ST2195 (LSE), analysing US domestic flight data (2004–2008, ~31M 
records) from the 2009 ASA Data Expo. All analysis implemented in both R and Python.

## Part 1 — Metropolis-Hastings Algorithm
Samples from a Laplace distribution using Random Walk Metropolis-Hastings, then 
checks convergence across 4 chains using the R-hat diagnostic over 1000 proposal 
standard deviations.

**Result:** Monte Carlo estimates closely matched the theoretical mean (0) and std 
(√2 ≈ 1.414) in both languages.

## Part 2 — Flight Delay & Diversion Analysis
- **(a)** Best time/day to fly, by average delay
- **(b)** Does plane age affect delays?
- **(c)** What predicts flight diversion? (logistic regression, 2004–2008)

**Key findings:** lowest delays are 0400–0800 on Saturdays; plane age alone isn't a 
reliable delay predictor; distance is the strongest predictor of diversion risk.

**Performance:** full pipeline (cleaning ~31M records + fitting 5 years of models) 
runs in seconds rather than hours, via multithreaded selective-column reads, 
year-by-year memory cleanup, and downsampling for the diversion model.

## Files
| File | Description |
|---|---|
| `Part1_Final.ipynb` / `.rmd` | Metropolis-Hastings (Python / R) |
| `Part2_Final.ipynb` / `.rmd` | Flight delay & diversion analysis (Python / R) |

## Requirements
- **R:** `data.table`, `ggplot2`, `patchwork`, `broom`
- **Python:** `pandas`, `numpy`, `scipy`, `matplotlib`, `seaborn`, `scikit-learn`
