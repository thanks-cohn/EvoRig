# EvoRig Founding Charter

**Originator / original concept:** thanks-cohn (@thanks-cohn)  
**Date:** 2026-11-17  
**Status:** Founding requirements (not claims of tested engineering)

## 1. Original thought experiment

Picture a truck, unchanged externally throughout an experiment, whose drivetrain is biologically inspired and composed of individually advanced, modular mechanisms. Each of the four wheels, together with the engine and gearbox, can deform, restructure or retune itself in response to the conditions it experiences. Over generations, those same mutable parts can acquire inherited adaptations through selection.

The chassis remains the same throughout. The experiment asks whether demanding environments can select a powertrain that is unusually good not just at moving, but at changing itself when conditions change.

This is the **EvoRig** concept. The mutable powertrain may be called the **Protean Drive**.

## 2. Strict scope

### Fixed for the entire training program
- Chassis/frame, body, wheelbase, suspension mounts, drivetrain interface locations, cabin/payload geometry and outer structural envelope.
- Number of driven/contact wheel assemblies: four. Their allowed external morphology can vary only within documented clearance and attachment constraints.
- Test vehicle's non-evolving reference hardware and sensors, except for intentionally modeled sensor noise.
- Equivalent base payload and environmental interaction rules across competitor vehicles.

### May adapt within a simulated lifetime
- Four wheel assemblies: geometry through permitted articulated/deformable degrees of freedom, stiffness, compliance, pressure analogs, contact patterns and local control.
- Power unit: modeled output/efficiency curves, internal operating modes, torque response and control, within energy and material bounds.
- Gearbox/transmission: ratios, engagement, torque split and behavior; internal arrangement only if valid in the model representation.
- Coordination policy: communication, local control, and strategies for self-reconfiguration using a defined resource budget.

### May evolve between generations
- Heritable encoding of only the wheel, engine and gearbox architecture and controller parameters.
- Mutation, crossover or other evolutionary operators acting on permitted genotype fields.
- Mechanism complexity, regulatory behavior, response to terrain, tradeoffs among energy, traction, durability and robustness.

**Not allowed:** body or chassis mutation, adding legs in place of the fixed four wheel assemblies without an explicit change to the charter, teleportation, infinite force, unbounded materials or free energy.

## 3. Two mechanisms; do not conflate them

**Lifetime adaptation:** one individual senses conditions and actively changes its allowable parameters/shape in operation. This may be rule-based or learned. Adaptation has costs, delays and failure modes.

**Intergenerational evolution:** after fitness evaluations, inherited designs vary and are selected. The next generation may be physically different. Evolution need not be literally biological; bio-inspired selection and plasticity suffice.

A mutation is not a within-lifetime adaptation. An adaptation should not silently rewrite the inherited genome.

## 4. Physical and experimental integrity

- Conservation-aware dynamics and explicit energy, torque, temperature/thermal proxy, stress and damage budgets.
- Contact and friction properties with randomized credible ranges; no reward for exploiting numerical bugs.
- Fixed and published episode/reset conditions, seeds and evaluation surfaces.
- Fair comparisons with ordinary fixed-tire / fixed-gearbox baseline trucks.
- Maintain functional performance on easy terrain even after advancing to hard terrain.
- Hall-of-fame checkpoints and archived ancestors prevent regressions and enable reconstruction.

## 5. Research outcome

We seek a robust, generally capable *simulated* all-terrain powertrain under a fixed truck architecture, evaluated under unfamiliar terrestrial terrain conditions. We do not assume it is globally optimal or that a simulated design is manufacturable.

## 6. Decisions not yet fixed

- Exact real-world vehicle dimensions and mass.
- Whether wheel geometry is modeled by compliant segments, discrete morphing elements or expensive flexible meshes.
- Engine simulation: combustion, electric, or abstract bounded energy/torque converter.
- How faithfully thermal/damage/aging processes are represented.
- Population size, selection algorithm and compute budget.
- How often model complexity/fidelity is increased independently of terrain difficulty.
- Specific definition of the proposed 10,000 training cycles; a cycle is **not** a single physics step.
- Whether independent wheel specialization emerges or is rewarded; it must not be preordained.

These decisions should be captured as reproducible experiment configuration, not hidden assumptions.
