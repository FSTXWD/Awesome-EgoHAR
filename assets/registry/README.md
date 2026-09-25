# Registry

The .yaml files use the JSON-compatible subset of YAML 1.2. Each resource appears once, and the root README renders the curated view. The repository contains bibliographic and descriptive metadata; it does not contain model implementation code.

- papers.yaml: paper title, first author, venue, year, canonical paper link, and primary output group.
- paper_dimensions.yaml: one row per paper ID. Input fields distinguish wearer/device, inference-time signals, and training-only auxiliary signals; model fields record representation, supervision, and learning strategy; output records the activity task and granularity.
- datasets.yaml: access URL, device and body position, modalities, participants, activities, scale, scenarios, year, companion publication or host, and a source URL for table facts. Use null for unverified values.
- benchmarks.yaml: benchmark link, source dataset, task, input modalities, and year.
- surveys.yaml: title, first author, paper URL, and publication venue.

A dash in the paper matrix means no separate training-only input is reported. Dataset scale keeps the original unit (hours, clips, sequences, frames, or file size); unlike measures should not be compared as if they were equivalent.

Dataset publication fields identify companion papers or hosts. A dataset host is not a conference or journal.
