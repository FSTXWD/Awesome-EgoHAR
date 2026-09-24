# Awesome EgoHAR

A curated collection of datasets, benchmarks, methods, systems, and resources for egocentric and body-centric human activity recognition and understanding.

In computer vision, “egocentric” often means first-person vision. Here it has a broader wearer-centered meaning: activity understanding from sensors carried by or attached to a person. The main unit of analysis is a **sensing configuration**: position × device × modality, together with task, supervision, temporal setting, and deployment constraints.

> Sense → Align → Fuse → Understand → Act

## Contents

- [Landscape and taxonomy](#landscape-and-taxonomy)
- [Surveys and tutorials](#surveys-and-tutorials)
- [Datasets](#datasets)
- [Benchmarks](#benchmarks)
- [Papers](#papers)
- [Open challenges](#open-challenges)
- [Contributing](#contributing)
- [Citation](#citation)

## Landscape and taxonomy

| Axis | Examples |
| --- | --- |
| Body position | head, ear, neck, chest, wrist, hand, finger, waist, thigh, shank, ankle, foot, multiple positions |
| Device | smart glasses, earable, smartwatch, ring, smartphone, chest strap, custom wearable node |
| Raw modality | IMU, RGB, thermal, audio, PPG, ECG, pressure, Wi-Fi, barometer |
| Derived representation | pose, skeleton, gaze, transcript, detected sound events |
| Task | window HAR, segmentation, temporal action localization (TAL), sound event detection (SED), streaming, language grounding |
| Learning | inference-time fusion, training-time alignment, distillation, flexible modality |
| Deployment | power, latency, privacy, bandwidth, comfort, missing sensors |

A smartphone is a **device**, not a body position; record whether it is carried in a pocket, hand, waist, bag, or unknown position. Raw modalities and derived representations are separate metadata fields.

In the registry, **core** means directly relevant wearer-centered sensing; **bridge** means adjacent research or datasets that inform this topic; **adapted** means a general method useful for wearer-centered activity understanding. These are curation tags, not publication types.

**Research timeline:** wearable HAR → multi-sensor HAR → multimodal wearer-centered sensing → cross-modal representation → continuous event understanding → foundation models and language.

## Surveys and tutorials

1. **"Past, Present, and Future of Sensor-based Human Activity Recognition Using Wearables: A Surveying Tutorial on a Still Challenging Task"**. [[Paper](https://doi.org/10.1145/3729467)] *IMWUT 2025*.
2. **"Towards Generalizable Human Activity Recognition: A Survey"**. [[Paper](https://arxiv.org/abs/2508.12213)] *arXiv preprint 2025*.
3. **"Temporal Action Localization in the Deep Learning Era: A Survey"**. [[Paper](https://doi.org/10.1109/TPAMI.2023.3330794)] *IEEE TPAMI 2024*.
4. **"Temporal Action Segmentation: An Analysis of Modern Techniques"**. [[Paper](https://doi.org/10.1109/TPAMI.2023.3327284)] *IEEE TPAMI 2024*.
5. **"Foundation Models for Time Series Analysis: A Tutorial and Survey"**. [[Paper](https://arxiv.org/abs/2403.14735)] *arXiv preprint 2024*.

## Datasets

Each [Dataset] link opens an access or project page. **Companion paper** identifies the venue of a related publication; **Dataset host** identifies an archive or project site when no publication is cited here. Ego4D modalities vary by subset; do not assume every recording has IMU.

### Wearer-centered datasets

1. **WEAR**. [[Dataset](https://mariusbock.github.io/wear/)] *Companion paper: IMWUT 2024*. head, multi-body · video, accelerometer · har, tal.
2. **XRF V2**. [[Dataset](https://github.com/airslab2020/XRFV2)] *Companion paper: IMWUT 2025*. head, ear, wrist, unknown-carried · imu, wifi, video · tal, summarization.
3. **EgoADL**. [[Dataset](https://zenodo.org/records/8248159)] *Companion paper: IMWUT 2024*. pocket · audio, imu, wifi · free-living-har.
4. **Ego4D**. [[Dataset](https://ego4d-data.org/docs/data/unprocessed_data/)] *Companion paper: CVPR 2022*. head · video, subset-dependent-audio-imu-gaze · egocentric-understanding.
5. **Ego-Exo4D**. [[Dataset](https://docs.ego-exo4d-data.org/overview/)] *Companion paper: CVPR 2024*. head · video, audio, imu, gaze · temporal-understanding, ego-exo.
6. **UESTC-MMEA-CL**. [[Dataset](https://github.com/Tflowers-0129/uestc-mmea-cl)] *Companion paper: IEEE TMM 2024*. head · rgb, accelerometer, gyroscope · continual-har.
7. **Nymeria**. [[Dataset](https://huggingface.co/datasets/projectaria/Nymeria)] *Companion paper: ECCV 2024*. head, multi-body · video, body-motion · motion-understanding.
8. **EPIC-SOUNDS**. [[Dataset](https://epic-kitchens.github.io/epic-sounds/)] *Companion paper: ICASSP 2023*. head · audio, video · sound-event-detection.
9. **CAPTURE-24**. [[Dataset](https://ora.ox.ac.uk/objects/uuid:99d7c092-d865-4a19-b096-cc16440cd001)] *Companion paper: Scientific Data 2024*. wrist · accelerometer, camera-assisted-labels · free-living-har.
10. **Comprehensive IMU Dataset**. [[Dataset](https://doi.org/10.6084/m9.figshare.30234940)] *Dataset article: Scientific Data 2026*. multi-body · accelerometer, gyroscope · sensor-placement.
11. **PAMAP2**. [[Dataset](https://archive.ics.uci.edu/dataset/231/pamap2+physical+activity+monitoring)] *Dataset host: UCI Machine Learning Repository*. chest, wrist, ankle · imu, heart-rate · har.
12. **OPPORTUNITY**. [[Dataset](https://archive.ics.uci.edu/dataset/226/opportunity+activity+recognition)] *Dataset host: UCI Machine Learning Repository*. multi-body · multisensor · har, segmentation.
13. **UCI-HAR**. [[Dataset](https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones)] *Dataset host: UCI Machine Learning Repository*. waist · accelerometer, gyroscope · window-har.
14. **WISDM**. [[Dataset](https://www.cis.fordham.edu/wisdm/dataset.php)] *Dataset host: Fordham WISDM*. wrist, unknown-carried · accelerometer, gyroscope · har.

### Related datasets

1. **Aria Digital Twin**. [[Dataset](https://facebookresearch.github.io/projectaria_tools/docs/open_datasets/aria_digital_twin_dataset/dataset_download)] *Companion paper: ICCV 2023*. head · video, imu, gaze · egocentric-3d.
2. **DESED**. [[Dataset](https://github.com/turpaultn/DESED)] *Dataset host: DESED project repository*. audio · sound-event-detection, weak-supervision.
3. **OctoNet**. [[Dataset](https://huggingface.co/datasets/hku-aiot/OctoNet)] *Companion paper: NeurIPS Datasets and Benchmarks 2025*. multi-body · multisensor · multimodal-har.

## Benchmarks

1. **WS-IMUBench**. [[Benchmark](https://arxiv.org/abs/2602.01850)]. Weakly supervised IMU temporal action localization.
2. **WEAR benchmark**. [[Benchmark](https://mariusbock.github.io/wear/)]. Wearable/egocentric HAR and temporal action localization.
3. **XRF V2**. [[Benchmark](https://arxiv.org/abs/2501.19034)]. Multi-device multimodal temporal activity understanding.
4. **Ego4D benchmarks**. [[Benchmark](https://ego4d-data.org/)]. Egocentric recognition, forecasting and related tasks.
5. **Ego-Exo4D**. [[Benchmark](https://docs.ego-exo4d-data.org/overview/)]. Ego-exo temporal and motion understanding.
6. **EPIC-SOUNDS**. [[Benchmark](https://arxiv.org/abs/2302.00646)]. Egocentric sound event recognition and detection.
7. **DCASE Task 4**. [[Benchmark](https://dcase.community/challenge2024/task-sound-event-detection-with-heterogeneous-training-dataset-and-potentially-missing-labels-results)]. Sound event detection with heterogeneous and incomplete labels.
8. **OctoNet**. [[Benchmark](https://proceedings.neurips.cc/paper_files/paper/2025/hash/14950adea25005f89545688fe97fe5ea-Abstract-Datasets_and_Benchmarks_Track.html)]. Heterogeneous multimodal human-centric sensing.

## Papers

The groups below show each paper once. The [Paper] label opens the paper or an official project page. The italic text names its publication venue and year; arXiv preprint means no journal or conference venue is claimed here. Multiple sensing and method tags are stored in [assets/registry/papers.yaml](assets/registry/papers.yaml).

### Ego sensing and wearable systems

1. **"SAMoSA: Sensing Activities with Motion and Subsampled Audio"**. [[Paper](https://doi.org/10.1145/3550284)] *IMWUT 2022*. fusion, adaptive-sensing, systems.
2. **"WatchHAR: Real-time On-device Human Activity Recognition System for Smartwatches"**. [[Paper](https://doi.org/10.1145/3716553.3750775)] *ICMI 2025*. fusion, on-device, systems.
3. **"HabitSense: A Privacy-Aware, AI-Enhanced Multimodal Wearable Platform for mHealth Applications"**. [[Paper](https://pmc.ncbi.nlm.nih.gov/articles/PMC11879279/)] *IMWUT 2024*. fusion, adaptive-sensing, privacy.
4. **"Aria Digital Twin: A New Benchmark Dataset for Egocentric 3D Machine Perception"**. [[Paper](https://openaccess.thecvf.com/content/ICCV2023/html/Pan_Aria_Digital_Twin_A_New_Benchmark_Dataset_for_Egocentric_3D_ICCV_2023_paper.html)] *ICCV 2023*. dataset, egocentric.
5. **"Towards Continual Egocentric Activity Recognition: A Multi-modal Egocentric Activity Dataset for Continual Learning"**. [[Paper](https://doi.org/10.1109/TMM.2023.3295899)] *IEEE TMM 2024*. dataset, continual-learning.
6. **"Multimodal Daily-Life Logging in Free-living Environment Using Non-Visual Egocentric Sensors on a Smartphone"**. [[Paper](https://doi.org/10.1145/3643553)] *IMWUT 2024*. dataset, free-living, fusion.
7. **"OctoNet: A Large-Scale Multi-Modal Dataset for Human Activity Understanding Grounded in Motion-Captured 3D Pose Labels"**. [[Paper](https://proceedings.neurips.cc/paper_files/paper/2025/hash/14950adea25005f89545688fe97fe5ea-Abstract-Datasets_and_Benchmarks_Track.html)] *NeurIPS Datasets and Benchmarks 2025*. dataset, fusion.

### Multimodal learning

1. **"DeepSense: A Unified Deep Learning Framework for Time-Series Mobile Sensing Data Processing"**. [[Paper](https://research.ibm.com/publications/deepsense-a-unified-deep-learning-framework-for-time-series-mobile-sensing-data-processing)] *WWW 2017*. fusion, window-har, systems.
2. **"IMU2CLIP: Language-grounded Motion Sensor Translation with Multimodal Contrastive Learning"**. [[Paper](https://aclanthology.org/2023.findings-emnlp.883/)] *Findings of EMNLP 2023*. alignment, language, foundation.
3. **"COCOA: Cross Modality Contrastive Learning for Sensor Data"**. [[Paper](https://doi.org/10.1145/3550316)] *IMWUT 2022*. alignment, self-supervised.
4. **"FOCAL: Contrastive Learning for Multimodal Time-Series Sensing Signals in Factorized Orthogonal Latent Space"**. [[Paper](https://proceedings.neurips.cc/paper_files/paper/2023/hash/93e98ddf39a9beb0a97fbbe56a986c80-Abstract-Conference.html)] *NeurIPS 2023*. alignment, self-supervised.
5. **"Babel: A Scalable Pre-trained Model for Multi-Modal Sensing via Expandable Modality Alignment"**. [[Paper](https://doi.org/10.1145/3715014.3722068)] *SenSys 2025*. alignment, missing-modality, foundation.
6. **"COMODO: Cross-Modal Video-to-IMU Distillation for Efficient Egocentric Human Activity Recognition"**. [[Paper](https://arxiv.org/abs/2503.07259)] *IMWUT 2026*. distillation, training-time-multimodal.
7. **"MASTER: A Multi-modal Foundation Model for Human Activity Recognition"**. [[Paper](https://doi.org/10.1145/3749511)] *IMWUT 2025*. fusion, missing-modality.

### Continuous and temporal understanding

1. **"WEAR: An Outdoor Sports Dataset for Wearable and Egocentric Activity Recognition"**. [[Paper](https://doi.org/10.1145/3699776)] *IMWUT 2024*. temporal-localization, fusion, dataset.
2. **"XRF V2: A Dataset for Action Summarization with Wi-Fi Signals, and IMUs in Phones, Watches, Earbuds, and Glasses"**. [[Paper](https://doi.org/10.1145/3749521)] *IMWUT 2025*. temporal-localization, multi-device, dataset.
3. **"WS-IMUBench: Can Weakly Supervised Methods from Audio, Image, and Video Be Adapted for IMU-based Temporal Action Localization?"**. [[Paper](https://arxiv.org/abs/2602.01850)] *arXiv preprint 2026*. temporal-localization, weak-supervision, benchmark.
4. **"Timestamp-Supervised Wearable-Based Activity Segmentation and Recognition with Contrastive Learning and Order-Preserving Optimal Transport"**. [[Paper](https://doi.org/10.1109/TMC.2024.3381171)] *IEEE TMC 2024*. segmentation, weak-supervision.
5. **"Exploiting Representation Curvature for Boundary Detection in Time Series"**. [[Paper](https://proceedings.neurips.cc/paper_files/paper/2024/hash/0b7f639ef28a9035a71f7e0c04c1d681-Abstract-Conference.html)] *NeurIPS 2024*. boundary-detection, segmentation.
6. **"EPIC-SOUNDS: A Large-scale Dataset of Actions that Sound"**. [[Paper](https://arxiv.org/abs/2302.00646)] *ICASSP 2023*. sound-event-detection, dataset.

### Foundation models and language

1. **"HMotionGPT: Aligning Hand Motions and Natural Language for Activity Understanding with Smart Rings"**. [[Paper](https://doi.org/10.1145/3810222)] *IMWUT 2026*. language, foundation.
2. **"RelCon: Relative Contrastive Learning for a Motion Foundation Model for Wearable Data"**. [[Paper](https://proceedings.iclr.cc/paper_files/paper/2025/hash/83eb339ed42297658fa24b5cec939285-Abstract-Conference.html)] *ICLR 2025*. foundation, self-supervised, generalization.
3. **"Scaling Wearable Foundation Models"**. [[Paper](https://proceedings.iclr.cc/paper_files/paper/2025/hash/94b25992757a549470c8f8dfe73d8df6-Abstract-Conference.html)] *ICLR 2025*. foundation, systems.
4. **"Inertia-1: An Open Exploration of Wearable Motion Foundation Models"**. [[Paper](https://arxiv.org/abs/2607.06617)] *arXiv preprint 2026*. foundation, sensor-placement.

## Open challenges

- Choosing sensor positions and devices without sacrificing comfort or coverage.
- Aligning asynchronous modalities and recovering event boundaries from sparse labels.
- Handling missing modalities, changing devices, and differences between people or environments.
- Reporting latency, power, privacy, and other deployment costs alongside recognition accuracy.

## Contributing

Add a resource once to the appropriate file in [assets/registry](assets/registry/README.md). Use a stable ID and a verified primary URL. Record body position, device, raw modality, task, scope, and a verified publication venue or dataset host. Use empty values for unknown facts. In this README, show the title in bold, followed by a Paper, Dataset, or Benchmark link. Do not upload third-party code, raw data, local scripts, or private notes.

## Citation

When using a listed resource, cite its original paper or dataset record. A repository citation can be added when release metadata is finalized.
