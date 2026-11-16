# AGHRI resource manifest

This record identifies the published AGHRI dataset and the two public code repositories associated with the paper. The dataset is published as version 4. The public `main` branch commit hashes below were verified on 14 November 2026.

## Dataset

- **Record:** [AGHRI at the University of Lincoln repository](https://repository.lincoln.ac.uk/articles/dataset/AGHRI_A_dataset_for_multimodal_robot_perception_of_humans_in_agricultural_and_off-road_environments/32982638).
- **Current published version:** [10.24385/lincoln.32982638.v4](https://doi.org/10.24385/lincoln.32982638.v4), published on 11 November 2026, licensed under CC BY 4.0.
- **Version-independent DOI:** [10.24385/lincoln.32982638](https://doi.org/10.24385/lincoln.32982638).
- **Published files:** `dataset_summary.csv`, `occlusion_log.csv`, `calibration.zip`, and `dataset_part1.zip` through `dataset_part10.zip`. The calibration archive contains `calibration/intrinsics.json` and `calibration/extrinsics.json`.
- **Sequence metadata:** The locally documented split comprises 65 sequences: 52 training, 7 validation, and 6 test sequences. The version 4 release notes confirm that its published `dataset_summary.csv` includes participant global IDs and dataset split assignments (train, val, or test) for each recording.
- **Version 4 changes:** `calibration.zip` was updated to correct a minor error in `extrinsics.json`; `dataset_summary.csv` was updated to add participant global IDs and dataset split assignments.

## Code

| Repository | Public `main` commit (14 November 2026) |
| --- | --- |
| [AGHRI-dataset-tools](https://github.com/LCAS/AGHRI-dataset-tools) | [`bfe4d6d742de5cf47fd30dc5800597834b9ae6de`](https://github.com/LCAS/AGHRI-dataset-tools/commit/bfe4d6d742de5cf47fd30dc5800597834b9ae6de) |
| [AGHRI-dataset-benchmark](https://github.com/LCAS/AGHRI-dataset-benchmark) | [`c042f0358787e23599d77b620d83997854c510ff`](https://github.com/LCAS/AGHRI-dataset-benchmark/commit/c042f0358787e23599d77b620d83997854c510ff) |
