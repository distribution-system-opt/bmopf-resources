# *PowerUp Conference Workshop Agenda*

For details of the upcoming PowerUp 2026 Conference workshop (September 2026), please see [here](https://github.com/distribution-system-opt/bmopf-resources/blob/main/powerup-workshop-agenda.md).

# Benchmarking Multiconductor OPF taskforce
Repository for the **draft** math and data model spec of the Benchmarking Multiconductor OPF taskforce.

This repository is being developed by the IEEE PES Task Force on Benchmarking Multiconductor OPF for Distribution Systems, and is designed to evaluate a well established version of the the Optimal Power Flow for Multiconductor distribution networks.

A draft description of the mathematical model is available in the root of this repository as `bmopf_math_and_data_model_specification_v0.2.2.pdf`.

The home of versioned data schemas is [`dsopt-schema`](https://github.com/distribution-system-opt/dsopt-schema), and the canonical home of the data semantics and math model is [`math-and-data-model-specifications`](https://github.com/distribution-system-opt/math-and-data-model-specifications). This repository holds draft and workshop material only. The copy at `draft_schema_and_networks/draft_bmopf_schema.json` is kept for the example networks beside it and remains the source of the historical v0.1.0 baseline until that import is reviewed.

The [historical v0.1.0 baseline](https://github.com/distribution-system-opt/dsopt-schema/tree/baseline/bmopf-0.1.0)
imports the Task Force schema with only its canonical location changed. The
[BMOPF v0.2.0 proposal](https://github.com/distribution-system-opt/dsopt-schema/pull/2)
builds on it and pairs with the
[specification supplement](https://github.com/distribution-system-opt/math-and-data-model-specifications/pull/39).
Both remain subject to Task Force review; neither link declares a release.

The [source and contribution record](https://github.com/distribution-system-opt/dsopt-schema/blob/baseline/bmopf-0.1.0/docs/baseline-0.1.0.md)
credits Matt Deakin's initial schema and alignment work, Frederik Geth's schema
development and review-driven changes, and Samuel Talkington's port and versioned
import. The [proposal credits](https://github.com/distribution-system-opt/dsopt-schema/blob/propose-bmopf-0.2.0/docs/contributors.md)
connect the additional documentation, review, and integration work. Existing
[source/objective discussions](https://github.com/distribution-system-opt/math-and-data-model-specifications/pull/36)
and [schema PR #21](https://github.com/distribution-system-opt/bmopf-resources/pull/21)
remain open work. Historical workshop files retain their content and status.

Community-based recommendations and contributions are welcome and encouraged. Please feel free to submit comments and questions in the [issue tracker](https://github.com/distribution-system-opt/bmopf-resources/issues).

## Upcoming Task Force activities

To be added to the mailing list to receive calendar invites for these, please contact [Matt](mailto:matthew.deakin@newcastle.ac.uk).

- Task Force Workshop, in-person, PowerUp 2026 (Colorado, USA), Friday September 11th (1.30pm local time). For full details see [here](https://github.com/distribution-system-opt/bmopf-resources/blob/main/powerup-workshop-agenda.md).
- Call for Network Model contributions - time(s) TBC. This meeting will cover the process and tools available to support efforts of the task force in development of benchmark networks.
