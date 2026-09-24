# Registry

The .yaml files use the JSON-compatible subset of YAML 1.2. Each resource appears once in its registry. The root README displays these records.

- papers.yaml: title, paper URL, publication venue, scope, sensing configuration, and topics.
- datasets.yaml: dataset access URL, associated publication venue or data host, sensing configuration, and tasks.
- benchmarks.yaml: benchmark entry points.
- surveys.yaml: paper URL and publication venue.

For papers and surveys, `venue` names a verified conference or journal, or says `arXiv preprint` when no formal venue is claimed. For datasets, `publication_type` distinguishes a companion paper, dataset article, or dataset host; `publication` records its venue or host. A data host is not a conference or journal.

Scope: `core` = directly relevant wearer-centered sensing; `adapted` = a general technique useful for wearer-centered activity understanding; `bridge` = adjacent research or datasets with a clear connection. Scope is a curation tag, not a publication status.
