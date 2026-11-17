# Founding Experiment Plan

**Originator:** thanks-cohn (@thanks-cohn)

## Phase 0 — Baselines

Document physical limits and the static chassis geometry. Define standard non-morphing wheel/engine/gearbox baselines and measurable success criteria. Verify MuJoCo version and save a minimal deterministic reproducibility example.

## Phase 1 — Fixed-body, mutable drivetrain

Prototype wheel stiffness/traction adjustment, bounded engine torque curves, selectable gearbox ratios and all-wheel torque coordination. Verify energy accounting and baseline episodes before introducing morphology search.

## Phase 2 — Lifetime adaptation

Give each wheel a bounded per-episode adaptation policy with latency, cost and finite energy. Compare adaptation ON versus OFF under identical conditions, seeds and disturbance budgets.

## Phase 3 — Generational evolution

Search inherited drivetrain configurations, preserve ancestry, keep chassis immutability as an automated assertion, and select using a transparent multiobjective fitness scheme. Check repeatability across seeds.

## Phase 4 — 10,000-cycle progressive gauntlet

Advance smoothly through terrain diversity toward plausible human-world conditions, contingent on competence; preserve previous terrains. Hold back entire terrain families for final testing.

## Phase 5 — Independent validation

Challenge winners with changed time steps, physics settings, random seeds and more sophisticated tire/structural simulation. Track success, energy, occupant comfort proxy, stability and failure rates; compare with non-evolving baselines.

## Phase 6 — Research extensions, not modifications to base claim

- **EvoRig Guardian:** lock the winning drivetrain; evolve a distinct occupant-protection structure with safe crash-energy management and known vehicle regulatory constraints.
- **EvoRotor:** independent helicopter/rotorcraft family exploring robust emergency descent, autorotation, landing energy absorption and optionally permitted aerodynamic transformations, using a validated rotorcraft flight-dynamics model.
- **LLM-guided search and long-horizon scale:** external proposal generator with physical evaluation and honest compute budgets.

## Completion gates

Do not label Phase 0–5 complete without logs, runnable reproduction instructions, quantitative comparisons and archived result artifacts. Do not claim crashworthiness, vehicle road legality, airworthiness or a guaranteed survival percentage from simulation alone.
