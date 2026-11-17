# EvoRig Evolutionary Gauntlet

**Original EvoRig idea:** thanks-cohn (@thanks-cohn)  
**Status:** planned research, not an executed experiment

## Cycle definition

A **training cycle** is one configured batch of environment trials, performance evaluations, evolutionary updates and curriculum scheduling. It is NOT a MuJoCo timestep. Store batch size, candidate count, episodes, durations and the actual definition in every run's manifest.

## Progressive terrain curriculum (initial proposal)

| Training cycles | World | Main selection pressures |
|---|---|---|
| 1–1,000 | Flat ground, minor slopes, simple friction | Basic stability, movement, efficient power delivery |
| 1,001–3,000 | Gravel, small stones, loose sand, gradients | Adaptive grip, torque split, gear management |
| 3,001–5,000 | Rocks, mud, steep and irregular surfaces | Recoverability, collision and durability tolerance |
| 5,001–8,000 | Terrain transitions, deterioration and adversarial combinations | Robustness under mixed challenges |
| 8,001–10,000 | Diverse terrestrial/road conditions approximating human environments | Generalization and realistic constraints |

Difficulty should rise when the candidate population achieves consistent mastery, NOT solely because a clock advanced. Increase numerical/model fidelity on a separate schedule: harder physics does not automatically mean harder terrain.

## Training protocol

1. Instantiate a population of candidate genotypes describing only the four wheels, power unit, gearbox and permitted controls.
2. Generate terrain episodes from seeded parameter distributions. Every candidate receives comparable test budgets.
3. Run episodes with adaptation active; mutations/inherited topology updates occur only between generations.
4. Calculate a multi-objective performance record: completion, stability, traction, energy, efficiency, comfort proxy, damage, reliability and adaptation costs.
5. Select candidates using Pareto-front or explicitly declared scoring; maintain an archive of novel/successful designs.
6. Mutate/recombine valid genomes. Keep the chassis invariant and enforce actuator, energy, material and geometry bounds.
7. Raise terrain complexity as performance allows, while rehearsing earlier terrain classes.
8. Save complete reproducibility and safety/validity data for every generation.

## Prevent reward hacking and false optimization

- Penalize simulator instabilities, constraint violations, collision penetration and nonphysical energy gain.
- Randomize physically defensible friction, contact, mass, actuator delays and disturbances.
- Maintain held-out terrain families and seeds; do not select on final test results.
- Compare against the same chassis with conventional fixed drivetrain and a strong hand-engineered adaptive controller.
- Test in higher-fidelity simulators and, eventually, measured hardware conditions before real-world claims.
- No inferred guarantee from 10,000 cycles; more iterations can improve search but do not prove an optimum.

## Milestone at cycle 10,000

Desired result: a documented, reproducible candidate that succeeds across a broad representative distribution of human-world terrain, including unseen configurations. Report confidence intervals and failure rates, not a claim of universal survivability.

## Future scaling

A billion cycles is a *possible research ambition* if compute/time is available, not a defined project requirement or implied feasibility. Use staged fidelity, surrogate models, parallel evaluation, quality-diversity search and protected held-out tests. See [Long-Horizon Research](LLM_AND_LONG_HORIZON_RESEARCH.md).
