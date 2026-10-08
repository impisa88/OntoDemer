# OntoDemer

This reduced package contains the ontology, competency queries, recorded
validation outputs, logical control inputs, and relation-level evidence register
for the minor revision. It does not include Python/PowerShell scripts, Java
sources, audit plug-ins, screenshots, or the Protege application.

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

## Recorded validation

The 7 October 2026 execution in Protege passed 30 query/profile comparisons,
11 logical controls, and four artifact checks. Exact binding-set equality, not
row counts alone, determines a passing query/profile comparison. These checks
establish conformance to the encoded model, not clinical validity.

The asserted ontology SHA-256 is
`8d876b424350bab287870041b1d8fa5721c6c859677d0e9d0ca9cf290dab8d31`.
Its metrics are 392 axioms, 166 logical axioms, 22 named classes, 18 object
properties, one data property, 72 named individuals, and three SWRL rules.
The 72 individuals are not 72 participants. The five profile identifiers are
`PWD_1_Paul`, `PWD_2`, `PWD_3_John`, `PWD_4`, and `PWD_5`.

## Evidence limitations

Ten records have contextual literature support, thirteen document symbolic
modeling choices, and ten lack confirmed relation-level attribution:
E01, E04, E09, E10, E11, E12, E15, E16, E20, and E23.
Knowledge elicitation was informal and conducted at the Leme Association.
The available documentation does not permit attribution of each encoded relation
to a specific participant. This package does not assign new sources or turn
unresolved records into confirmed ones.

Sources identified retrospectively must be distinguished from original records.
Changes to relations require aligned evidence annotations/register, expectations,
tests, outputs, and manuscript figures. Empty query results do not indicate
absence of clinical risk.

## Scope of this reduced package

Use `SPARQL.md` to inspect the complete queries and recorded outputs manually.
The original automated audit tool and dependency-adjustment scripts are not
distributed here. This package supports manual query inspection and re-execution
against the supplied materialized ontology, but does not by itself reproduce the
original automated audit or rebuild its tool. `ENVIRONMENT.md` documents the
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
