# Awesome EgoHAR

A curated collection of datasets, benchmarks, methods, systems, and resources for egocentric and body-centric human activity recognition and understanding.

In computer vision, “egocentric” often means first-person vision. Here it has a broader wearer-centered meaning: sensing from devices carried by or attached to a person. The unit of analysis is the sensing configuration — **position × device × modality** — together with task, supervision, temporal setting, and deployment constraints.

> Sense → Align → Fuse → Understand → Act

**Start here:** [Papers](docs/papers.md) · [Datasets](docs/datasets.md) · [Benchmarks](docs/benchmarks.md) · [Ego sensing](docs/sensing.md) · [Multimodal learning](docs/multimodal-learning.md) · [Temporal understanding](docs/temporal-understanding.md)

## Landscape and taxonomy

| Axis | Examples |
| --- | --- |
| Position | head, ear, neck, chest, wrist, finger, waist, ankle, foot, multiple body positions |
| Device | smart glasses, smartwatch, ring, earable, smartphone, chest strap, custom node |
| Raw modality | IMU, RGB, audio, PPG, ECG, pressure, Wi-Fi, barometer |
| Task | window HAR, segmentation, TAL, SED, streaming, language grounding |
| Learning | inference-time fusion, training-time alignment, distillation, flexible modality |
| Deployment | power, latency, privacy, comfort, missing sensors |

A smartphone is a **device**, not a body position; its carrying position can be pocket, hand, waist, bag, or unknown. Derived representations such as pose and transcripts are separate from raw modalities.

## Research timeline

Wearable HAR → multi-sensor HAR → multimodal wearer-centered sensing → cross-modal representation → continuous event understanding → foundation models and language. This is a conceptual map, not a claim that one line replaced another.

## Surveys and tutorials

[Survey index](docs/surveys.md) — accepting verified papers with canonical links.

## Datasets

- [WEAR](https://mariusbock.github.io/wear/) (2024) · core
- [XRF V2](https://arxiv.org/abs/2501.19034) (2025) · core
- [EgoADL](https://zenodo.org/records/8248159) (2023) · core
- [Ego4D](https://ego4d-data.org/docs/data/unprocessed_data/) · core
- [Ego-Exo4D](https://docs.ego-exo4d-data.org/overview/) · core
- [EPIC-SOUNDS](https://arxiv.org/abs/2302.00646) (2023) · core
- [PAMAP2](https://archive.ics.uci.edu/dataset/231/pamap2+physical+activity+monitoring) (2012) · core

[Full dataset catalog](docs/datasets.md)

## Benchmarks

- [WS-IMUBench](https://arxiv.org/abs/2602.01850) — Weakly supervised IMU temporal action localization
- [WEAR benchmark](https://mariusbock.github.io/wear/) — Wearable/egocentric HAR and temporal action localization
- [XRF V2](https://arxiv.org/abs/2501.19034) — Multi-device multimodal temporal activity understanding
- [Ego4D benchmarks](https://ego4d-data.org/) — Egocentric recognition, forecasting and related tasks
- [Ego-Exo4D](https://docs.ego-exo4d-data.org/overview/) — Ego-exo temporal and motion understanding
- [EPIC-SOUNDS](https://arxiv.org/abs/2302.00646) — Egocentric sound event recognition and detection

[Full benchmark catalog](docs/benchmarks.md)

## Ego sensing

Position, device, and modality are independent indices. [Browse the sensing index](docs/sensing.md).

## Multimodal learning

- [DeepSense: A Unified Deep Learning Framework for Time-Series Mobile Sensing Data Processing](https://research.ibm.com/publications/deepsense-a-unified-deep-learning-framework-for-time-series-mobile-sensing-data-processing) (2017) · core
- [SAMoSA: Sensing Activities with Motion and Subsampled Audio](https://doi.org/10.1145/3550284) (2022) · core
- [IMU2CLIP: Language-grounded Motion Sensor Translation with Multimodal Contrastive Learning](https://aclanthology.org/2023.findings-emnlp.883/) (2023) · core
- [FOCAL: Contrastive Learning for Multimodal Time-Series Sensing Signals in Factorized Orthogonal Latent Space](https://proceedings.neurips.cc/paper_files/paper/2023/hash/93e98ddf39a9beb0a97fbbe56a986c80-Abstract-Conference.html) (2023) · core
- [Babel: A Scalable Pre-trained Model for Multi-Modal Sensing via Expandable Modality Alignment](https://doi.org/10.1145/3715014.3722068) (2025) · adapted
- [COMODO: Cross-Modal Video-to-IMU Distillation for Efficient Egocentric Human Activity Recognition](https://arxiv.org/abs/2503.07259) (2026) · core

[Full learning index](docs/multimodal-learning.md)

## Activity understanding

- [WEAR: An Outdoor Sports Dataset for Wearable and Egocentric Activity Recognition](https://mariusbock.github.io/wear/) (2024) · core
- [WS-IMUBench: Can Weakly Supervised Methods from Audio, Image, and Video Be Adapted for IMU-based Temporal Action Localization?](https://arxiv.org/abs/2602.01850) (2026) · core
- [Timestamp-Supervised Wearable-Based Activity Segmentation and Recognition with Contrastive Learning and Order-Preserving Optimal Transport](https://arxiv.org/abs/2310.09114) (2024) · core
- [EPIC-SOUNDS: A Large-scale Dataset of Actions that Sound](https://arxiv.org/abs/2302.00646) (2023) · core

[Full temporal index](docs/temporal-understanding.md)

## Foundation models and language

[Browse foundation models](docs/foundation-models.md).

## Systems and deployment

[Browse systems](docs/systems.md).

## Robustness and generalization

[Browse generalization](docs/generalization.md).

## Related research paradigms

[Browse bridge work](docs/related-paradigms.md).

## Applications

[Browse applications](docs/applications.md).

## Open challenges

Sensor placement, asynchronous modalities, missing devices, event boundaries, deployment cost, and evaluation across people and environments.

## Tools and resources

The public catalog is stored in [YAML registries](assets/registry/README.md). Links in every paper and dataset title open an external paper, dataset, or project page. This repository lists research resources; it does not mirror their code or raw data.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Please verify the primary link and describe the sensing configuration and task.

## Citation

When using a listed resource, cite its original paper or dataset record. A repository citation will be added after release metadata is finalized.
