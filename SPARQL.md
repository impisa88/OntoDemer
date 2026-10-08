# Competency queries

Use the complete files `queries/CQ1.rq` through `CQ6.rq` without changing their
IRIs. The reported outputs were obtained against
`results/OntoDemer-materialized.owl`, not just the asserted root ontology.

## Manual inspection in Protege

1. Use a working SPARQL Query Plugin installation with the environment described
   in `ENVIRONMENT.md`.
2. Open `results/OntoDemer-materialized.owl` in Protege.
3. Enable Window > Tabs > SPARQL Query.
4. Paste a complete query file and execute it.
5. Compare the returned tuples with the corresponding `results/CQ*.csv` and the
   expected/actual sets in `results/verification.csv`.

The SPARQL tab does not automatically incorporate HermiT inferences from the
asserted document. Interface labels can differ from the exact IRIs preserved
in CSVs. The materialized copy permits inspection of the published bindings;
it is not a replacement for documenting or repeating materialization.

| Query | Scope | Recorded rows |
| --- | --- | ---: |
| CQ1 | Modeled behavior-illness associations | 7 |
| CQ2 | Associated illnesses and susceptibility categories, where bound | 7 |
| CQ3 | Associations matching the encoded high-category filter | 6 |
| CQ4 | Individual recommendations from explicitly modeled conditions | 3 |
| CQ5 | Illness catalog associated with the modeled physical disorder | 21 |
| CQ6 | Recommendation catalog associated with the modeled physical disorder | 4 |

CQ2 retains an unbound susceptibility for John's obesity. CQ3 excludes that
row because the required high category is not modeled. CQ6 is a catalog query,
not a statement that every returned profile received an individual SWRL output.
These results represent encoded associations, not clinical predictions.
