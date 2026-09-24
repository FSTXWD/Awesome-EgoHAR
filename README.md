# Awesome EgoHAR

A curated collection of datasets, benchmarks, papers, and resources for egocentric and body-centric human activity recognition and understanding.

Here, **egocentric** includes activity understanding from sensors carried by or attached to the wearer. We record body position, device, and sensing modality separately so readers can compare configurations across datasets and methods.

## Contents

- [Scope and taxonomy](#scope-and-taxonomy)
- [Surveys and tutorials](#surveys-and-tutorials)
- [Datasets and benchmarks](#datasets-and-benchmarks)
  - [Egocentric and multimodal datasets](#egocentric-and-multimodal-datasets)
  - [Body-worn activity datasets](#body-worn-activity-datasets)
  - [Adjacent sensing resources](#adjacent-sensing-resources)
  - [Benchmark comparison](#benchmark-comparison)
- [Research papers by topic](#research-papers-by-topic)
  - [Wearable sensing and deployment](#wearable-sensing-and-deployment)
    - [Adaptive sensing and privacy](#adaptive-sensing-and-privacy)
    - [On-device recognition](#on-device-recognition)
  - [Multimodal representation learning](#multimodal-representation-learning)
    - [Sensor fusion](#sensor-fusion)
    - [Contrastive learning and modality alignment](#contrastive-learning-and-modality-alignment)
    - [Cross-modal distillation](#cross-modal-distillation)
  - [Continuous activity understanding](#continuous-activity-understanding)
    - [Segmentation and event boundaries](#segmentation-and-event-boundaries)
    - [Temporal localization and weak supervision](#temporal-localization-and-weak-supervision)
  - [Foundation models and language](#foundation-models-and-language)
    - [Wearable motion foundation models](#wearable-motion-foundation-models)
    - [Language-grounded hand activity](#language-grounded-hand-activity)
  - [Dataset and benchmark papers](#dataset-and-benchmark-papers)
    - [Egocentric and wearable datasets](#egocentric-and-wearable-datasets)
    - [Broad multimodal testbeds](#broad-multimodal-testbeds)
- [Open challenges](#open-challenges)
- [Contributing](#contributing)
- [Citation](#citation)

## Scope and taxonomy

| Axis | Examples |
| --- | --- |
| Body position | Head, ear, neck, wrist, finger, pocket, waist, ankle, multiple positions |
| Device | Smart glasses, earables, smartwatch, smart ring, smartphone, body-worn node |
| Modality | IMU, RGB video, thermal, audio, Wi-Fi, physiological signals |
| Task | Window classification, temporal segmentation, localization, sound events, language grounding |
| Setting | Controlled, free-living, indoor, outdoor, streaming, on-device |

A smartphone is a device; its carried position is recorded separately. Related video, audio, and ambient-sensing resources are included where they provide useful methods or evaluation settings for wearer-centered activity understanding.

## Surveys and tutorials

1. **"Past, Present, and Future of Sensor-based Human Activity Recognition Using Wearables: A Surveying Tutorial on a Still Challenging Task"**. *Haresamudram et al.* IMWUT 2025. [[Paper](https://doi.org/10.1145/3729467)]
2. **"Towards Generalizable Human Activity Recognition: A Survey"**. *Cai et al.* arXiv preprint 2025. [[Paper](https://arxiv.org/abs/2508.12213)]
3. **"Temporal Action Localization in the Deep Learning Era: A Survey"**. *Wang et al.* IEEE TPAMI 2024. [[Paper](https://doi.org/10.1109/TPAMI.2023.3330794)]
4. **"Temporal Action Segmentation: An Analysis of Modern Techniques"**. *Ding et al.* IEEE TPAMI 2024. [[Paper](https://doi.org/10.1109/TPAMI.2023.3327284)]
5. **"Foundation Models for Time Series Analysis: A Tutorial and Survey"**. *Liang et al.* KDD 2024. [[Paper](https://doi.org/10.1145/3637528.3671451)]

## Datasets and benchmarks

Dataset names link to their access or project pages. **Data size / scale** uses the measure reported by each source (hours, file size, sequences, frames, or events), so values are not directly comparable. **—** means a figure was not verified for that release. Activity labels and sensor availability can vary by subset; for example, not every Ego4D recording includes IMU. The final columns give the dataset year and the companion paper venue or data host. Source pages for table facts are recorded in [assets/registry/datasets.yaml](assets/registry/datasets.yaml).

### Egocentric and multimodal datasets

| Dataset | Wearer / device | Modalities | Subjects | Activities | Data size / scale | Scenarios | Year | Publication / host |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **[WEAR](https://mariusbock.github.io/wear/)** | Head camera; wrists and ankles | Egocentric video, accelerometer | 22 | 18 sports activities | 164 GB raw | Outdoor sports; 11 locations | 2024 | IMWUT |
| **[XRF V2](https://github.com/airslab2020/XRFV2)** | Glasses, earbuds, watch, phone | IMU, Wi-Fi, video | 16 | Indoor daily activities | — | 3 indoor environments | 2025 | IMWUT |
| **[EgoADL](https://zenodo.org/records/8248159)** | Pocket smartphone | Audio, Wi-Fi, IMU | 30 (10 labeled) | Unscripted daily activities | 29.1 GB files | Free-living daily routines | 2024 | IMWUT |
| **[Ego4D](https://ego4d-data.org/docs/data/unprocessed_data/)** | Head-mounted cameras | Video; audio, gaze and other signals in subsets | 931 | Daily activities (varied) | 3,670 h video | 74 locations across 9 countries | 2022 | CVPR |
| **[Ego-Exo4D](https://docs.ego-exo4d-data.org/overview/)** | Head-worn and external cameras | Video, audio, IMU, gaze | 740 | Skilled activities | 1,286 h combined video | 123 contexts in 13 cities | 2024 | CVPR |
| **[UESTC-MMEA-CL](https://github.com/Tflowers-0129/uestc-mmea-cl)** | Smart glasses | RGB, accelerometer, gyroscope | 10 | 32 daily activities | — | Continual egocentric activity learning | 2024 | IEEE TMM |
| **[Aria Digital Twin](https://facebookresearch.github.io/projectaria_tools/docs/open_datasets/aria_digital_twin_dataset/dataset_download)** | Aria glasses | Video, IMU, gaze; 3D ground truth | — | 3D perception and human motion | 236 sequences | Apartment and office | 2023 | ICCV |
| **[Nymeria](https://huggingface.co/datasets/projectaria/Nymeria)** | Aria glasses and body sensors | Video, IMU, body motion, language | 264 | Unscripted daily motions | 300 h | 20 unscripted scenarios; 50 locations | 2024 | ECCV |
| **[EPIC-SOUNDS](https://epic-kitchens.github.io/epic-sounds/)** | Head-worn camera | Audio; egocentric video context | — | 44 sound classes | 117.5K sound events | 45 kitchens | 2023 | ICASSP |

### Body-worn activity datasets

| Dataset | Wearer / device | Modalities | Subjects | Activities | Data size / scale | Scenarios | Year | Publication / host |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **[CAPTURE-24](https://ora.ox.ac.uk/objects/uuid:99d7c092-d865-4a19-b096-cc16440cd001)** | Wrist tracker; camera-assisted labels | Accelerometer; camera labels | 151 | 206 fine-grained activity codes | 3,883 h (2,562 h annotated) | Free-living, over 24 h | 2024 | Scientific Data |
| **[Comprehensive IMU Dataset](https://doi.org/10.6084/m9.figshare.30234940)** | 17 body-worn IMUs | Accelerometer, gyroscope | 30 | 12 daily activities | 21.2 GB | Controlled activity and intensity protocols | 2026 | Scientific Data |
| **[PAMAP2](https://archive.ics.uci.edu/dataset/231/pamap2+physical+activity+monitoring)** | Chest, wrist, ankle | IMU, heart rate | 9 | 18 physical activities | — | Physical activity monitoring | 2012 | UCI Machine Learning Repository |
| **[OPPORTUNITY](https://archive.ics.uci.edu/dataset/226/opportunity+activity+recognition)** | Body, objects and environment | IMU, object and ambient sensors | 4 | 17 gestures; 5 high-level activities | — | Instrumented daily-living environment | 2012 | UCI Machine Learning Repository |
| **[UCI-HAR](https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones)** | Waist smartphone | Accelerometer, gyroscope | 30 | 6 activities | — | Controlled daily activities | 2013 | UCI Machine Learning Repository |
| **[WISDM Smartphone and Smartwatch](https://archive.ics.uci.edu/dataset/507/wisdm+smartphone+and+smartwatch+activity+and+biometrics+dataset)** | Smartphone and smartwatch | Accelerometer, gyroscope | 51 | 18 activities | 45.9 h per sensor | Scripted phone/watch activities | 2019 | UCI Machine Learning Repository |

### Adjacent sensing resources

| Dataset | Wearer / device | Modalities | Subjects | Activities | Data size / scale | Scenarios | Year | Publication / host |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **[DESED](https://github.com/turpaultn/DESED)** | Ambient microphones | Audio | — | 10 domestic sound classes | — | Real and synthetic domestic soundscapes | 2019 | DESED project repository |
| **[OctoNet](https://huggingface.co/datasets/hku-aiot/OctoNet)** | Body and environment sensors | 12 modalities incl. IMU, RGB, depth, audio, Wi-Fi, radar | 41 | 62 daily activities | 67.72M synchronized frames | Structured and free-form activities | 2025 | NeurIPS Datasets and Benchmarks |

### Benchmark comparison

| Benchmark | Source dataset | Task | Input modalities | Year |
| --- | --- | --- | --- | --- |
| **[WS-IMUBench](https://arxiv.org/abs/2602.01850)** | WEAR / XRF V2 | Weakly supervised IMU temporal action localization | IMU | 2026 |
| **[WEAR benchmark](https://mariusbock.github.io/wear/)** | WEAR | Wearable/egocentric HAR and temporal action localization | Accelerometer, video | 2024 |
| **[XRF V2](https://github.com/airslab2020/XRFV2)** | XRF V2 | Multi-device multimodal temporal activity understanding | IMU, Wi-Fi, video | 2025 |
| **[Ego4D benchmarks](https://ego4d-data.org/)** | Ego4D | Egocentric recognition, forecasting and related tasks | First-person video; subset signals | 2022 |
| **[Ego-Exo4D](https://docs.ego-exo4d-data.org/overview/)** | Ego-Exo4D | Ego-exo temporal and motion understanding | Ego/exo video, IMU, gaze | 2024 |
| **[EPIC-SOUNDS](https://epic-kitchens.github.io/epic-sounds/)** | EPIC-SOUNDS | Egocentric sound event recognition and detection | Egocentric audio | 2023 |
| **[DCASE Task 4](https://dcase.community/challenge2024/task-sound-event-detection-with-heterogeneous-training-dataset-and-potentially-missing-labels-results)** | DESED | Sound event detection with heterogeneous and incomplete labels | Domestic audio | 2024 |
| **[OctoNet](https://huggingface.co/datasets/hku-aiot/OctoNet)** | OctoNet | Heterogeneous multimodal human-centric sensing | Multimodal sensor streams | 2025 |

## Research papers by topic

Each paper appears once below. The format follows **title → first author → venue and year → paper link**. Papers introducing listed datasets are grouped together; the tables above link to the corresponding data access pages.

### Wearable sensing and deployment

#### Adaptive sensing and privacy

1. **"SAMoSA: Sensing Activities with Motion and Subsampled Audio"**. *Mollyn et al.* IMWUT 2022. [[Paper](https://doi.org/10.1145/3550284)]
2. **"HabitSense: A Privacy-Aware, AI-Enhanced Multimodal Wearable Platform for mHealth Applications"**. *Fernandes et al.* IMWUT 2024. [[Paper](https://pmc.ncbi.nlm.nih.gov/articles/PMC11879279/)]

#### On-device recognition

1. **"WatchHAR: Real-time On-device Human Activity Recognition System for Smartwatches"**. *Yeon et al.* ICMI 2025. [[Paper](https://doi.org/10.1145/3716553.3750775)]

### Multimodal representation learning

#### Sensor fusion

1. **"DeepSense: A Unified Deep Learning Framework for Time-Series Mobile Sensing Data Processing"**. *Yao et al.* WWW 2017. [[Paper](https://research.ibm.com/publications/deepsense-a-unified-deep-learning-framework-for-time-series-mobile-sensing-data-processing)]
2. **"MASTER: A Multi-modal Foundation Model for Human Activity Recognition"**. *Zhu et al.* IMWUT 2025. [[Paper](https://doi.org/10.1145/3749511)]

#### Contrastive learning and modality alignment

1. **"COCOA: Cross Modality Contrastive Learning for Sensor Data"**. *Deldari et al.* IMWUT 2022. [[Paper](https://doi.org/10.1145/3550316)]
2. **"FOCAL: Contrastive Learning for Multimodal Time-Series Sensing Signals in Factorized Orthogonal Latent Space"**. *Liu et al.* NeurIPS 2023. [[Paper](https://proceedings.neurips.cc/paper_files/paper/2023/hash/93e98ddf39a9beb0a97fbbe56a986c80-Abstract-Conference.html)]
3. **"IMU2CLIP: Language-grounded Motion Sensor Translation with Multimodal Contrastive Learning"**. *Moon et al.* Findings of EMNLP 2023. [[Paper](https://aclanthology.org/2023.findings-emnlp.883/)]
4. **"Babel: A Scalable Pre-trained Model for Multi-Modal Sensing via Expandable Modality Alignment"**. *Dai et al.* SenSys 2025. [[Paper](https://doi.org/10.1145/3715014.3722068)]

#### Cross-modal distillation

1. **"COMODO: Cross-Modal Video-to-IMU Distillation for Efficient Egocentric Human Activity Recognition"**. *Chen et al.* IMWUT 2026. [[Paper](https://doi.org/10.1145/3810218)]

### Continuous activity understanding

#### Segmentation and event boundaries

1. **"Timestamp-Supervised Wearable-Based Activity Segmentation and Recognition with Contrastive Learning and Order-Preserving Optimal Transport"**. *Xia et al.* IEEE TMC 2024. [[Paper](https://doi.org/10.1109/TMC.2024.3381171)]
2. **"Exploiting Representation Curvature for Boundary Detection in Time Series"**. *Shin et al.* NeurIPS 2024. [[Paper](https://proceedings.neurips.cc/paper_files/paper/2024/hash/0b7f639ef28a9035a71f7e0c04c1d681-Abstract-Conference.html)]

#### Temporal localization and weak supervision

1. **"WS-IMUBench: Can Weakly Supervised Methods from Audio, Image, and Video Be Adapted for IMU-based Temporal Action Localization?"**. *Li et al.* arXiv preprint 2026. [[Paper](https://arxiv.org/abs/2602.01850)]

### Foundation models and language

#### Wearable motion foundation models

1. **"RelCon: Relative Contrastive Learning for a Motion Foundation Model for Wearable Data"**. *Xu et al.* ICLR 2025. [[Paper](https://proceedings.iclr.cc/paper_files/paper/2025/hash/83eb339ed42297658fa24b5cec939285-Abstract-Conference.html)]
2. **"Scaling Wearable Foundation Models"**. *Narayanswamy et al.* ICLR 2025. [[Paper](https://proceedings.iclr.cc/paper_files/paper/2025/hash/94b25992757a549470c8f8dfe73d8df6-Abstract-Conference.html)]
3. **"Inertia-1: An Open Exploration of Wearable Motion Foundation Models"**. *Xu et al.* arXiv preprint 2026. [[Paper](https://arxiv.org/abs/2607.06617)]

#### Language-grounded hand activity

1. **"HMotionGPT: Aligning Hand Motions and Natural Language for Activity Understanding with Smart Rings"**. *Gao et al.* IMWUT 2026. [[Paper](https://doi.org/10.1145/3810222)]

### Dataset and benchmark papers

#### Egocentric and wearable datasets

1. **"WEAR: An Outdoor Sports Dataset for Wearable and Egocentric Activity Recognition"**. *Bock et al.* IMWUT 2024. [[Paper](https://doi.org/10.1145/3699776)]
2. **"XRF V2: A Dataset for Action Summarization with Wi-Fi Signals, and IMUs in Phones, Watches, Earbuds, and Glasses"**. *Lan et al.* IMWUT 2025. [[Paper](https://doi.org/10.1145/3749521)]
3. **"Multimodal Daily-Life Logging in Free-living Environment Using Non-Visual Egocentric Sensors on a Smartphone"**. *Sun et al.* IMWUT 2024. [[Paper](https://doi.org/10.1145/3643553)]
4. **"Towards Continual Egocentric Activity Recognition: A Multi-modal Egocentric Activity Dataset for Continual Learning"**. *Xu et al.* IEEE TMM 2024. [[Paper](https://doi.org/10.1109/TMM.2023.3295899)]
5. **"Aria Digital Twin: A New Benchmark Dataset for Egocentric 3D Machine Perception"**. *Pan et al.* ICCV 2023. [[Paper](https://openaccess.thecvf.com/content/ICCV2023/html/Pan_Aria_Digital_Twin_A_New_Benchmark_Dataset_for_Egocentric_3D_ICCV_2023_paper.html)]
6. **"EPIC-SOUNDS: A Large-scale Dataset of Actions that Sound"**. *Huh et al.* ICASSP 2023. [[Paper](https://arxiv.org/abs/2302.00646)]

#### Broad multimodal testbeds

1. **"OctoNet: A Large-Scale Multi-Modal Dataset for Human Activity Understanding Grounded in Motion-Captured 3D Pose Labels"**. *Yuan et al.* NeurIPS Datasets and Benchmarks 2025. [[Paper](https://proceedings.neurips.cc/paper_files/paper/2025/hash/14950adea25005f89545688fe97fe5ea-Abstract-Datasets_and_Benchmarks_Track.html)]

## Open challenges

- Choosing sensor positions and devices without sacrificing comfort or coverage.
- Aligning asynchronous modalities and recovering event boundaries from sparse labels.
- Handling changing people, devices, environments, and missing modalities.
- Reporting latency, power, privacy, and other deployment costs alongside recognition accuracy.

## Contributing

Add a resource once to the relevant file in [assets/registry](assets/registry/README.md). Use a stable ID and a direct primary URL. For papers, record the first author and publication venue. For datasets, record the sensing configuration, tasks, scale, activity labels, scenarios, year, and the source of those facts when available. Use null for unverified values. Local scripts, third-party code, and raw datasets are not part of this repository.

## Citation

When using a listed resource, cite its original paper or dataset record. A repository citation can be added when release metadata is finalized.
