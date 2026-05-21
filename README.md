# 2025-NFL-Win-Total---Monte-Carlo
Uses a basic Monte Carlo Simulator to "predict" win totals from the 2025 season. Each team is assigned a strength rating, derived from their net scoring margin. For every game, we compute a win probability using a logistic function of the strength differential plus the home field advantage. Runs 10K simulations to produce the full win distribution.
