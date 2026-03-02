# Brier Betting Mechanism — Interactive Demo

An interactive demo of the wagering mechanism described in [Lambert et al. (2015)](https://doi.org/10.1016/j.jet.2014.03.012), "An Axiomatic Characterization of Wagering Mechanisms."

## What is a wagering mechanism?

A wagering mechanism is a way of eliciting honest probability estimates from a group of people. Each participant stakes money and reports their probability for a binary event (e.g. "Will it rain tomorrow?"). After the outcome is revealed, the total pot is redistributed: more accurate forecasters gain money at the expense of less accurate ones.

Unlike prediction markets, wagering mechanisms are **budget-balanced** — no money enters or leaves the system. The pot is simply reshuffled based on forecast accuracy.

## The Brier Betting Mechanism

Lambert et al. show that the **Brier betting mechanism** is essentially the unique wagering mechanism satisfying four desirable properties:

- **Proportionality** — Your expected payoff increases with the accuracy of your forecast.
- **Anonymity** — The mechanism treats all participants identically.
- **Sybilproofness** — Splitting a wager across multiple fake accounts provides no advantage.
- **Homogeneity** — Payoffs depend only on the fraction each player contributes, not the absolute amounts.

The payoff for player *i* is:

```
π_i = (w_i / W) + (w_i / W) · Σ_{j≠i} (w_j / W) · [(p_j − x)² − (p_i − x)²]
```

where `w_i` is the wager, `W` is the total pot, `p_i` is the reported probability, and `x ∈ {0, 1}` is the realised outcome.

## Using the demo

Open `demo.html` in any browser. No installation or dependencies required.

1. **Pick a scenario** (or create your own) with players, wagers, and probability estimates.
2. **Reveal the outcome** (Yes or No).
3. **View the payoffs** — see who profits, who loses, and verify that the pot is fully redistributed.

## Reference

Lambert, N. S., Langford, J., Wortman Vaughan, J., Chen, Y., Reeves, D. M., Shoham, Y., & Pennock, D. M. (2015). An axiomatic characterization of wagering mechanisms. *Journal of Economic Theory*, 156, 389–416.
