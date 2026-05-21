# NFL Win Total Monte Carlo Simulator — 2025 Season

Simulates the 2025 NFL regular season 10,000 times and compares results against both the preseason betting market and actual final records.

## What made 2025 unusual

The 2025 season was one of the most chaotic on record relative to preseason expectations:

- **Seattle Seahawks** (6.5 O/U) went 14-3 and won Super Bowl LX
- **New England Patriots** (5.5 O/U) went 14-3 and reached the Super Bowl — the biggest over-performance on the board at +8.5W
- **Kansas City Chiefs** (11.5 O/U) went 6-11 — a -5.5W miss and historic collapse
- Three teams (SEA, NE, DEN) tied for the best record at 14-3
- The preseason market's RMSE was 3.25 wins per team; the PPG model's RMSE was 1.61 (with the unfair advantage of using final-season data)

## Method

`P(home wins) = sigmoid(k * (strength_home - strength_away + HFA))`

- Strength = `ppg_for - ppg_against` from the final 2025 regular season
- `k = 0.12`, `HFA = 2.5` points
- Schedule structure: 6 division + 4 same-conf + 4 cross-conf + 3 rank-based = 17 games per team (verified)

## Biggest market misses

| Team | O/U | Actual | Diff |
|------|-----|--------|------|
| New England Patriots | 5.5 | 14 | +8.5 |
| Seattle Seahawks | 6.5 | 14 | +7.5 |
| Jacksonville Jaguars | 7.5 | 13 | +5.5 |
| Kansas City Chiefs | 11.5 | 6 | -5.5 |
| Arizona Cardinals | 8.5 | 3 | -5.5 |

## What's inside

1. Team data — 2025 final records, PPG stats, and ESPN Bet preseason O/U lines
2. Win probability model
3. Schedule construction (verified 17 games per team)
4. 10,000 simulations
5. Three-way comparison: simulated vs market vs actual
6. Biggest upsets vs preseason market
7. Win distributions for the four surprise teams
8. Model calibration: PPG model vs market accuracy
9. Summary statistics with over/under flags
10. The 2025 story in numbers


## Requirements

```bash
pip install numpy pandas matplotlib seaborn scipy jupyter
```

## Run it

```bash
jupyter notebook nfl_win_totals_2025.ipynb
```

---
*Stats from champsorchumps.us. Preseason O/U from ESPN Bet (March 2025). Seattle Seahawks won Super Bowl LX, 29-13.*
