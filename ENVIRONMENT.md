# Recorded validation environment

The original execution was completed on 7 October 2026 inside Protege Desktop.
Packaging the recorded outputs on 8 October is not a new reasoner execution.

| Item | Recorded value |
| --- | --- |
| Application | Protege Desktop 5.6.9, official Windows distribution |
| JVM | 11.0.25 |
| OWL API | 4.5.29 |
| HermiT plug-in package | 1.4.3.456 |
| HermiT engine-reported version | 1.4.1.432 |
| SPARQL Query Plugin | 3.0.0 |
| OWLAPI RDF Library | 3.0.1, with local OSGi manifest adjustment |
| Original local audit command | OntoDemer Local Audit 1.0.0, not included here |

Distribution reference:
https://github.com/protegeproject/protege-distribution/releases/tag/protege-5.6.9

The original RDF Library failed with
`NoClassDefFoundError: com/google/common/base/Optional`. Its OSGi manifest was
adjusted with `DynamicImport-Package: com.google.common.base`; all non-manifest
entries were preserved. Original and adjusted hashes are recorded in
`results/plugin-workaround.json`. A fresh unadjusted distribution may therefore
not run the queries successfully. Adjustment scripts are in the separate full
technical package, not in this reduced package.

The original audit used the active HermiT reasoner for the principal ontology,
materialized inferred class and property assertions together with asserted
axioms, and executed queries through the installed SPARQL plug-in mechanism.
The controls used the installed HermiT factory in the same application process.
Post-processing compared exports with predefined expectations. Each query was
also inspected separately in the SPARQL interface.

The original log is retained for transparency. Its timing is not a latency or
scalability benchmark. The reduced package supplies results and inputs but not
the original automation; it must not be described as containing that tool.
