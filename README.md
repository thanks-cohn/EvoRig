# EvoRig — The Protean Drive

**Original idea and founding concept:** [thanks-cohn (@thanks-cohn)](https://github.com/thanks-cohn)  
**Founding record:** November 17, 2026  
**Project status:** Founding research specification; no working simulator or validated evolved design yet.

> **EvoRig** asks a question: what could an all-terrain truck become if its body and chassis never changed, but its four wheels, engine and gearbox could adapt within a lifetime and evolve over generations?

## The invariant

- **Permanently fixed:** truck body, frame/chassis, wheelbase, mount locations, major structural geometry and all non-drivetrain equipment.
- **Adaptable/evolvable:** exactly four wheel assemblies, the power unit (engine), and the gearbox/transmission and their internal mechanics and control parameters.
- **No magical mechanisms:** feasible motion, contact, friction, momentum, forces, power, energy, limits and component constraints must be modeled. Simplifications must be documented.
- **Two timescales:** individual lifetime adaptation versus inherited intergenerational evolution. They are distinct mechanisms.
- **API-first:** all experimentation and configuration should be operable through documented versioned APIs, with any GUI using those APIs.

## Evolutionary gauntlet

Begin with modest, simplified terrains. Increase both terrain challenge and the simulation's physical realism as the population demonstrates reliable competence. At approximately **10,000 training cycles**, the desired challenge distribution resembles the kinds of conditions encountered in human-world driving: paved and rough roads, transitions, gravel, rocks, sand, mud, hills, potholes, curbs, snow and rain effects where supportable.

**10,000 means curriculum / evolutionary training cycles to be defined by experiments — not MuJoCo solver timesteps.** Passing 10,000 cycles is not proof of global optimality, real-world safety or transfer. Validate survivors on held-out terrain and higher-fidelity settings.

The fixed chassis makes the test unusually clear: how much capability can arise entirely from the powertrain and four wheels?

## Founding documents

1. [Founding Charter](docs/FOUNDING_CHARTER.md) — original concept, scope, invariants, and open questions.
2. [Evolutionary Gauntlet](docs/EVOLUTION_GAUNTLET.md) — curriculum, selection and 10,000-cycle interpretation.
3. [MuJoCo Simulation Specification](docs/MUJOCO_SIMULATION_SPEC.md) — physical modeling and fidelity limitations.
4. [API-First Architecture](docs/API_FIRST_ARCHITECTURE.md) — subsystems, reproducibility and interfaces.
5. [Experiment and Milestone Plan](docs/EXPERIMENT_PLAN.md) — prototype sequence and acceptance criteria.
6. [Attribution and Contributions](CONTRIBUTING.md) — contribution and credit instructions.
7. [NOTICE](NOTICE) and [LICENSE](LICENSE) — original-concept credit and legally applicable attribution requirement.

## Founder attribution and license

**Original EvoRig idea and founding concept: thanks-cohn (@thanks-cohn).**

The **founding documentation is licensed CC BY 4.0**, allowing reuse, modification and commercial adaptation with attribution to its creator. The exact attribution and legal scope are in [LICENSE](LICENSE) and [NOTICE](NOTICE). Please credit the idea's origin even for implementations independently inspired by it. **Copyright licenses cannot, by themselves, require credit solely for borrowing an unprotected abstract idea.** Future software code requires its own explicit software license.

## What this repository does not claim

No claim of an invented novel material, patent rights, proven survivability, a simulator already running, a real-world autonomous vehicle, or a guarantee of an optimal design. EvoRig is a simulation and evolutionary-engineering research concept with an intended experimental protocol.
