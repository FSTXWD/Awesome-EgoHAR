# Registry

The `.yaml` files use the JSON-compatible subset of YAML 1.2. Each resource appears once in its registry, and the root README displays the curated view.

- `papers.yaml`: title, first author, paper URL, publication venue, sensing configuration, and topics.
- `datasets.yaml`: access URL, device and body position, modalities, participants, activities, scale, scenarios, year, companion publication or host, and a source URL for table facts. Use `null` for unverified values.
- `benchmarks.yaml`: benchmark link, source dataset, task, input modalities, and year.
- `surveys.yaml`: title, first author, paper URL, and publication venue.

For a dataset, `publication_type` distinguishes a companion paper, dataset article, or dataset host. A host is not a conference or journal. Dataset scale can mean recording hours, file size, sequences, frames, or events; keep the original unit and do not compare unlike measures as though they were the same.
