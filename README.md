## Setup

The code requires only `numpy` and `matplotlib`. After cloning the repo, install them with:

```bash
pip install -r requirements.txt
```

## Discussion Items
Section A.iv: Sensitivity Analysis
Q. How much do individual runs differ from the average?
A. The individual runs overall are similar to the average across the 20 runs. However, when p=0.15 and q=0.04, the individual runs do differ quite visibly. Depending on the random initialization, we would sometimes see the number of recovered people greater than the number of suceptible people and, other times, see the reverse of that. 

Q. In how many runs does the outbreak die out early?
A. In 4 runs (3, 6, 14, 19), the number of recovered people plateaued below 50, effectively showing that the pandemic infected than 25% of the population. 2 of the 4 runs did not show any increase in the number of recovered people nor the peak in the number of infected individuals, demonstrating that the outbreak potentially did not occur despite the presence of infected individiduals. 

Section B.i: Introduce social distancing measures
Q. Which parameter controls the maximum number of simultaneously infected agents? Which determines whether the healthcare system is overwhelmed?
A. It seems that both the reduced movement is the more important factor. The difference between m=1 and 0.01 is greater than the difference between when the agents starts avoiding or not. Healthcare system is overwhelmed when there is a high number of simultaneously infected agents and especially if that number rises too quickly.

Section B.ii: Compare the results with and without social distancing
Q. The peak number of infected agents
A. With social distancing(avoidance), there is much less number of peak infected people for the most part. While the number is lower, the gap closes when people begin to move around, presumably as they are around infected people and are unable to "distance" themselves from the infected crowd.

Q. The time to peak, and the time until no infected agents remain
A. Tito peak without social distancing(avoidance) is not necessarily shorter. This could be due to the fact that with very effective social distancing, the pandemic is effectively prevented, leading to the absence of major peak.

Q. Total number of agents ever infected
A. The total number of agents ever infected is computed by adding the number of recovered and infected individuals at the last time point. The difference is significant. However, as mentioned above, the gap closes once people begin move around at higher frequency where this leads to a situation where it is impossible to avoid infected people.

Q. The implications for real-world public health interventions
A. In real-world situations, it is difficult to understand who to avoid exactly. Therefore, it would be important for people to not travel around. There is clearly signs that social distancing in combination with reduced movement leads to the best outcome in terms of ensuring that the peak is low and delayed as well as the total number of infected people are kept low.

Section B.iii: Strength of distancing
Q. Discuss how stricter or more relaxed distancing affects the epidemic
A. Stricter distancing is always better. Even though the average time to peak is early when people both avoid infected individuals as well as have reduced movement, the number of infected individuals at the peak is significantly lower. Therefore, the effects of distancing is monotonic - the stricter the better.

## Hypotheses Revisited

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