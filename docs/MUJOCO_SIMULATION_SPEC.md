# MuJoCo Simulation — Founding Technical Specification

**Original concept:** thanks-cohn (@thanks-cohn)  
**Status:** design only

## Why MuJoCo

Use MuJoCo as a candidate high-throughput dynamics platform for the baseline terrestrial EvoRig study. Ground contact, rigid-body dynamics, joints, actuators and control can be tested efficiently. The model must be calibrated and validated; rendering a shape does not establish physical truth.

## Body and mutable subsystems

**Frozen reference:** fixed chassis CAD proxy, mass/inertia, body, mounts, suspension interfaces, nominal payload and collision clearances.

**Genotype fields:** four wheel morphology and contact/compliance parameters; engine bounded torque/efficiency response; gearbox ratios, engagement and torque distribution; allowed controller and adaptation parameters.

**Phenotype:** a compiled valid model with these selected parameters. Continuous lifetime change should use modeled joints/actuators, compliant elements and bounded controller state. Arbitrarily rewriting mesh topology on each physics step is NOT presumed supported or physically correct.

## Recommended first fidelity level

- Invariant 4-wheel 3D chassis with contact and steering.
- Parametric wheel radius/width/contact friction and several compliance modes; simple discrete morphing segments if viable.
- Bounded torque-speed map, power/energy budget and controllable gear ratio states.
- Energy, acceleration, slips, rollover margins and impact costs measured per episode.
- Explicit actuator limits, speed, heat/thermal proxy, wear/damage proxy and self-reconfiguration overhead.
- At least three fixed-baseline designs for comparison.

Higher fidelity: flexible/compliant wheel representation, calibrated terrain models and independent finite-element/material validation of structural changes.

## Distinguish simulation validity from visual plausibility

MuJoCo fluid-force approximations do not constitute high-fidelity computational fluid dynamics. Detailed tire, wheel metamaterial and fracture processes may need external solvers or empirical models. A candidate's apparently clever shape can exploit numerical artifacts unless compared across time steps, solver settings, seeds and independent simulators.

## Logging and reproducibility

For each run: simulation engine/version, full configuration, code commit, seed, vehicle geometry, environment, rollout actions, state summaries, energy budget, constraints, fitness vectors and failure explanation. Record exactly how many physics timesteps, episodes and generations make up one training cycle.

## Acceptance

A baseline vehicle traverses a documented flat course, competes on at least three terrain types, recovers from a traction change without changing chassis geometry, and generates reproducible fitness metrics. Evolution is added only after this baseline is independently testable.

## Boundaries

A MuJoCo success alone is not a road-legal vehicle, a manufacturable design, or evidence that a deformable engine/gearbox can physically be built. Crash protection and rotor aerodynamics require additional validated models.
