# API-First Architecture — EvoRig

**Founding concept:** thanks-cohn (@thanks-cohn)  
**Design rule:** the simulation and evolutionary machinery are headless, deterministic when possible, scriptable and inspectable; any GUI must use the same public API.

## Independent modules

- **Vehicle reference model:** immutable chassis, masses, attachment points and permissible drivetrain interfaces.
- **Wheel genome adapter:** independent per-wheel morphology, contact and adaptation choices.
- **Power unit adapter:** bounded torque, energy source, efficiency map and adaptation modes.
- **Gearbox adapter:** transmission and torque-distribution states.
- **Lifetime controller:** sensing, coordinated adaptation, failure recovery and adaptation-cost accounting.
- **Physics runtime:** MuJoCo terrestrial scenarios; adapters for higher-fidelity collision/material solvers.
- **Evolution service:** selection, mutation, diversity archive, lineage and immutable ancestry.
- **Curriculum service:** challenge generation, mastery thresholds and retained earlier terrains.
- **Evaluation and audit:** held-out tests, validity monitors, baselines, standardized reports.

## Proposed versioned interfaces

These are design contracts, not working routes:

- `POST /v1/experiments` — create reproducible experiment from documented spec.
- `POST /v1/experiments/{id}/cycles` — request a bounded synchronous/asynchronous job in the eventual implementation.
- `GET /v1/experiments/{id}` — current configuration, status, complete lineage.
- `GET /v1/experiments/{id}/candidates` — ranked/Pareto candidates and failure metadata.
- `GET /v1/candidates/{id}/genome` — versioned genetic parameters and chassis compatibility report.
- `POST /v1/candidates/{id}/evaluate` — measured fitness on specified environments, including held-out option access controls.
- `GET /v1/experiments/{id}/report` — reproducible metrics and quality checks.

Safety-specific and rotorcraft research are **separate experiment families** with different models and validation requirements, not silently inherited endpoints.

## Minimum structured manifest

```json
{
  "schema_version": "1.0",
  "experiment_family": "evorig-drivetrain",
  "founding_concept_credit": "thanks-cohn (@thanks-cohn)",
  "fixed_chassis_revision": "baseline-v1",
  "model_version": "prototype",
  "population_size": 100,
  "training_cycles_requested": 10000,
  "cycle_definition": "one generation with multiple terrain episodes",
  "seed": 1,
  "fitness_spec": "multiobjective-v1",
  "physics_fidelity_tier": "rigid-parametric-v1"
}
```

## Rules

- Invalid genomes fail validation instead of being silently corrected.
- Each experiment receives immutable config and checkpoint hashes.
- Selection, reward weights and failure taxonomy remain inspectable.
- No fake success status: validated episode outputs only.
- Expose provenance and original idea credit in documentation and published experiment reports.
- Do not let an LLM declare physical validation; it can propose candidates, code and experiments, but validated execution determines results.

This is a founding interface proposal, not a commitment that API routes have been implemented.
