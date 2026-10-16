## Setup

The code requires only `numpy` and `matplotlib`. After cloning the repo, install them with:

```bash
pip install -r requirements.txt
```

## Results: Hypotheses Revisited

### 1. Movement reduction lowers and delays the infection peak

Reducing the movement rate `m` lowers the peak number of infected agents. With avoidance enabled (`avoid=True`) and a low movement rate, the time to peak is short, but the peak itself is very low, meaning the pandemic is effectively prevented.

![Average peak infected vs m](figures/average_peak_infected_vs_m.png)
![Average time to peak vs m](figures/average_time_to_peak_vs_m.png)

### 2. Trajectories vary with random initialization but are consistent on average

With `p=0.15` and `q=0.04`, the average trajectory over all runs looks like this:

![Average trajectory, p=0.15, q=0.04](figures/p0.15_q0.04_average.png)

Individual runs with the same parameters can look very different depending on the random initial positions. In the first run below the pandemic spreads successfully; in the second it dies out early.

![Run 1: successful spread](figures/p0.15_q0.04_version1.png)
![Run 2: early termination](figures/p0.15_q0.04_version2.png)

### 3. Resemblance to the SIR curve depends on the parameters

Depending on which parameters are included and their values, the simulated curves may or may not resemble the classic SIR curve.

![Deviation from SIR Curve with Social Distancing](figures/p0.3_q0.02_m0.3_avoid.png)
![Similar to SIR Curve without Social Distancing](figures/p0.3_q0.02_m0.6.png)

## AI Use Statement

[Describe how AI tools were used, following your course's policy.]