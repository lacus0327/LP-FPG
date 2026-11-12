# LP-PFG: per-trial experiment data

Per-trial records supporting the manuscript **"Lion-Pride-Inspired Potential-Field Game for Role-Based Task Allocation of Heterogeneous Air–Ground Agricultural Robots"**.

Every table and figure in the manuscript can be regenerated from these CSV files. The full simulator, experiment drivers and figure-generation scripts will be released in this repository upon paper acceptance.

## Files

| File | Description | Supports |
|---|---|---|
| `data/results_v2.csv` | Main comparison (scenario S1): 6 strategies × 3 loads × 30 seeds — completion, makespan, energy, switches, messages | Table 3, Fig. 5 |
| `data/results_s1f.csv` | Equal-period control: all methods re-plan every 2.5 s | Table 4 |
| `data/results_s3v2.csv` | Fault-injection trials with pre-removal coverage logging (8 tasks, 30 seeds) | Table 5 |
| `data/results_snapshot.csv` | Frozen-snapshot equilibrium diagnostic (N=10 and N=50, 30 seeds each) | §5.4 |
| `data/results_eps.csv` | Sensitivity sweep over the hysteresis margin ε_h (150 runs) | Fig. 6(a)(c) |
| `data/results_delta.csv` | Sensitivity sweep over the quota-filling weight δ (180 runs) | Fig. 6(b)(d) |
| `data/results_ablation.csv` | Modality/structure ablation | Ablation table |
| `data/results_s4_30.csv` | Team-density sweep (30 seeds per scale) | §5.4 |

## Column glossary (shared by most files)

- `method` / `config`: evaluated policy (LPPFG / NSGA2 / Auction / PSO / APF / Random)
- `n_tasks` / `N`: number of concurrent tasks / number of robots
- `seed`: random seed (identical seeds across methods → paired comparisons)
- `completion`: fraction of tasks completed (1.0 = all)
- `makespan`: trial duration in seconds (capped at the 250 s horizon)
- `energy`: motion-energy proxy ∫ c·‖v‖ dt (relative, not battery measurement)
- `switches`: number of role switches
- `msgs`: per-round update messages (model-based count)
- `collision`: True if any inter-robot distance < 2 m
- `mttr`: gap-closure latency after fault injection (s), empty if not applicable

## License & citation

Data released for research purposes. If reused, please cite the manuscript above.
Simulator and code: to be added upon acceptance.
