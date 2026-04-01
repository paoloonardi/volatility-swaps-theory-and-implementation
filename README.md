# Volatility Swaps: Theory, Replication, and Valuation

**Authors:** Samir Es Sahhal, Paolo Nardi  
**Course:** MAA709 – Seminar in Mathematics  
**University:** Mälardalen University, Division of Mathematics and Physics  
**Academic Year:** 2025/2026  
**Supervisor:** Prof. Jean Paul Murara

---

## Overview

This report provides a rigorous, self-contained treatment of **volatility swaps** 
and **variance swaps** — forward contracts delivering pure exposure to realised 
volatility, free from directional equity risk.

---

## Contents

- **Variance replication** via Itô's lemma and the Carr–Madan spanning theorem
- **Model-free fair variance formula** (Demeterfi et al., 1999)
- **VIX and VVIX** indices and their connection to variance swap pricing
- **Volatility skew impact** on fair variance (linear-in-strike and linear-in-delta)
- **Practical limitations:** finite strike ranges and jump risk
- **Exotic variants:** capped, floored, and corridor variance swaps
- **Convexity bias** between volatility and variance swaps (Jensen correction)
- **Numerical implementation** in FIS Prime (Front Arena) using the Derman model

---

## Key Results

The central pathwise identity under continuous price evolution:

$$V = \frac{2}{T}\left[\int_0^T \frac{dS_t}{S_t} - \ln\frac{S_T}{S_0}\right]$$

The fair variance strike expressed model-free from market option prices:

$$K_{\text{var}} = \frac{2}{T}\left[rT + e^{rT}\int_{0}^{S^{\ast}}\frac{P(K)}{K^2}dK + e^{rT}\int_{S^{\ast}}^{\infty}\frac{C(K)}{K^2}dK + \cdots\right]$$
---

## Modelling Frameworks

| Model | Use case |
|---|---|
| Black–Scholes | Baseline, flat vol surface |
| Heston (Semi-Analytical) | Vanilla vol swaps, stochastic vol |
| Heston (Monte Carlo) | Capped/floored/corridor variants |
| Derman (Prime) | Production implementation of Demeterfi et al. |

---

## Implementation

The theoretical framework is implemented end-to-end in **FIS Prime (Front Arena)**,
covering instrument definition, context configuration, exotic events scheduling,
and real-time risk monitoring for a one-week volatility swap on Broadcom Corporation.

---

## References

- Demeterfi, Derman, Kamal & Zou (1999). *More than you ever wanted to know 
  about volatility swaps.* Goldman Sachs Quantitative Strategies Research Notes.
- Carr & Madan (1998). *Towards a theory of volatility trading.* Risk Books.
- Heston (1993). *A closed-form solution for options with stochastic volatility.*
- Neuberger (1994). *The log contract: A new instrument to hedge volatility.*

---

## Report

The full PDF report is available in the [`report/`](./report/) folder.
