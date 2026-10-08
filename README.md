# OntoDemer

OntoDemer is an OWL ontology for representing symbolic associations between
wheelchair users' modeled behaviors, physical disorders, illness concepts,
susceptibility categories, and preventive recommendations. This repository
provides the ontology, competency queries, recorded validation outputs,
logical control inputs, and relation-level evidence register.

## Files

- `OntoDemer.owl`: asserted ontology, including five profiles, three SWRL rules,
  and evidence annotations.
- `queries/CQ1.rq` through `CQ6.rq`: six complete SPARQL queries.
- `results/OntoDemer-materialized.owl`: asserted plus inferred axioms used for
  the recorded query execution.
- `results/CQ1.csv` through `CQ6.csv`: complete recorded query outputs.
- `results/verification.csv`: expected and actual bindings and PASS/FAIL for
  each of the 30 query/profile comparisons, including empty and unbound results.
- `results/all-checks.json`: all 45 recorded checks, including eleven logical
  controls and four artifact checks.
- `results/summary.json`, `execution.log`, and `plugin-workaround.json`: recorded
  outcome, original in-process execution log, and dependency-adjustment details.
- `tests/fixtures.owl`, `tests/no-rules.owl`: inputs for the logical controls.
- `evidence/evidence.csv`: 33 relation-level provenance records.
- `SPARQL.md`: manual query inspection instructions.
- `ENVIRONMENT.md`: recorded tool versions and scope of reproduction.
- `SHA256.csv`: package file checksums, excluding the checksum file itself.

## Validation

The recorded execution in Protege Desktop 5.6.9 passed 30 query/profile
comparisons, eleven logical controls, and four artifact checks. Query/profile
comparisons required exact equality between expected and actual binding sets.
These results assess conformance to the encoded model, not clinical validity.

Complete expected and actual bindings are available in
[verification.csv](results/verification.csv), and all recorded checks are
documented in [all-checks.json](results/all-checks.json). Artifact hashes are
provided in [SHA256.csv](SHA256.csv). The five profiles are modeled evaluation
cases; the 72 named OWL individuals do not represent 72 study participants.

## Knowledge provenance

The [evidence register](evidence/evidence.csv) documents 33 encoded relations:
ten with contextual literature support, thirteen representing symbolic modeling
choices, and ten without confirmed relation-level source attribution.

Knowledge elicitation was conducted informally at the Leme Association.
Available documentation does not permit attribution of each relation to a
specific participant. Retrospectively identified sources are distinguished
from the original elicitation process. Contextual evidence and symbolic
susceptibility categories should not be interpreted as calibrated clinical
risk estimates.

## Usage

Use [SPARQL.md](SPARQL.md) to inspect the complete queries and recorded outputs manually.
The original automated audit tool and dependency-adjustment scripts are not
distributed here. This package supports manual query inspection and re-execution
against the supplied materialized ontology, but does not by itself reproduce the
original automated audit or rebuild its tool. [ENVIRONMENT.md](ENVIRONMENT.md) documents the
recorded environment and dependency adjustment.

## License

The OntoDemer ontology is licensed under the Creative Commons
Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0).

You are free to share, adapt, and build upon this ontology only for non-commercial
purposes, provided that:

- Proper credit is given to the authors;
- Any changes are indicated;
- Derivative works are distributed under the same license.

For commercial purposes, prior authorization from the authors is required.
Contact: joaosh@unisinos.br.
