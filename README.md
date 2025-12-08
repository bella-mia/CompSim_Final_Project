# CompSim_Final_Project

Isabella Castillo
bellamiacastillo@icloud.com

Rithika Cheela
rc49479@my.utexas.edu

Michael Vielmann
mav3038@utexas.edu

# NFL Injury Financial Impact Simulation

A simulation analyzing the financial and competitive impact of player injuries on NFL teams. This project uses historical injury data to model costs, performance impacts, and risk distributions.

## Project Overview

This simulation models the economic consequences of player injuries for NFL franchises, incorporating:
- Direct salary costs of injured players
- Performance impact measured by point differential
- Fan attendance reduction during injuries
- Position-specific injury patterns and recovery times

**Key Result**: Teams can expect an average annual cost of **$208,460** due to injuries, with 30% probability of exceeding $250K in losses.

## Repository Structure

```
├── nfl_injury_sim.ipynb          # Main simulation notebook
├── combined_analysis.py          # Data parsing and analysis script
├── NFL Data.csv                  # Raw injury data (2011-2013 seasons)
├── cleaned_nfl_injury_data.csv   # Processed injury records
├── owner_report.pdf              # Executive report for team ownership
└── README.md                     # This file
```

## Data Sources

**Raw Data**: `NFL Data.csv`
- 3 NFL seasons (2011-2013)
- 55 documented injury cases
- 32 teams tracked
- Weekly team scoring data

**Position Coverage**:
- Quarterbacks (QB): 7 injuries
- Running Backs (RB): 8 injuries  
- Wide Receivers (WR): 14 injuries
- Tight Ends (TE): 13 injuries
- Kickers (K): 0 injuries


### Key Variables

| Parameter | Value | Description |
|-----------|-------|-------------|
| `lambda_team` | 0.438 | Poisson rate parameter (injuries per team per season) |
| `SEASON_GAMES` | 16 | Games per NFL season |
| `SIM_REPS` | 100 | Number of Monte Carlo iterations |
| `POINTS_PER_WIN` | 47.0 | Average points needed for victory |


## Methodology

### 1. Data Parsing (`parse_nfl_data`)
- Extracts injury records from messy CSV format
- Identifies position, injury duration, and team performance
- Calculates baseline vs. injured team scoring

### 2. Statistical Analysis (`calculate_injury_stats`)
- Computes position-specific injury rates
- Determines average games missed
- Analyzes point differential during injuries

### 3. Monte Carlo Simulation (`simulate_season`)
For each of 100 simulated seasons:
1. Sample number of injuries using Poisson distribution (λ = 0.438)
2. Randomly assign positions based on historical probabilities
3. Calculate games missed per position
4. Compute financial losses (salary × games missed)
5. Estimate fan attendance impact
6. Aggregate results across simulations






