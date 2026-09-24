# Registry

The .yaml files use the JSON-compatible subset of YAML 1.2, so they can be parsed without a YAML dependency. Each resource appears once in its registry, with a direct url field. Markdown pages are views of these records.

- papers.yaml: papers, including scope, sensing configuration, and topics.
- datasets.yaml: datasets and their supported tasks.
- benchmarks.yaml: benchmark entry points.

Scope: core = wearer-centered activity understanding; adapted = technique directly transferred to body-centric sensing; bridge = related method or dataset with a clear technical connection. Add only verified primary links.
