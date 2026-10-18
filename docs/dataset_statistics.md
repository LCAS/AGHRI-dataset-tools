# AGHRI sequence statistics and technical validation

This page records sequence-level counts, split-attribute overlap, and technical quality-control (QC) summaries for AGHRI. The dataset has **65 sequences**: 52 training, 7 validation, and 6 test sequences.

## Sequence distribution

A sequence belongs to one environment. The environment counts therefore sum to 65.

| Environment | Sequences |
| --- | ---: |
| Inside Polytunnel | 8 |
| Outside Polytunnel | 14 |
| Inside Vineyard | 6 |
| Outside Vineyard | 8 |
| Footpath | 20 |
| Farmside | 9 |

Activities are **multi-label**: a sequence contributes once to each applicable activity, so these counts do not sum to 65.

| Activity | Sequences |
| --- | ---: |
| Walking | 40 |
| Standing | 3 |
| Talking | 4 |
| Checking | 11 |
| Pushing | 21 |
| Carrying | 9 |
| Swapping | 9 |
| Picking | 11 |

Machine-readable counts: [sequence_environment_activity_counts.csv](data/sequence_environment_activity_counts.csv). The counts correspond to the sequence-level figure; they are not frame or bounding-box counts.

## Attributes shared between splits

Each cell below is the **number of distinct attribute values** found in both named splits, not the number of shared sequences. The sequence partitions themselves are disjoint.

| Grouping factor | Train–validation | Train–test | Validation–test |
| --- | ---: | ---: | ---: |
| Recording date | 3 | 3 | 3 |
| Participant ID | 5 | 5 | 4 |
| Clothing/accessory appearance | 2 | 1 | 0 |
| Environment | 3 | 4 | 3 |
| Activity | 5 | 6 | 4 |
| Robot state (st/mv) | 2 | 2 | 2 |
| Duplicated sensor content in sequences | 0 | 0 | 0 |

Machine-readable overlap table: [split_attribute_overlap.csv](data/split_attribute_overlap.csv). Shared dates, participants, appearances, environments, activities, or robot states do not imply duplicated sensor files.

## Technical validation

The following are QC results for the AGHRI dataset.

### Camera–LiDAR time offsets

Median absolute timestamp offset across the dataset:

| Camera stream | Median offset (ms) |
| --- | ---: |
| ZED RGB | 20.3 |
| ZED depth | 20.7 |
| Front fisheye | 10.6 |
| Left fisheye | 10.3 |
| Right fisheye | 10.8 |

For the **six held-out test sequences**, matched ZED RGB–Livox pairs had a **20.2 ms median**, **64.3 ms 95th percentile**, and **99.5 ms maximum** absolute timestamp offset.

### Sensor and annotation checks

| Check | Previously reported finding |
| --- | --- |
| Sensor streams | All 390 expected sensor folders were present and nonempty. |
| Depth maps | No NaN, infinite, or negative pixel values were detected. This does not mean that zero-depth pixels were absent. |
| LiDAR point clouds | No empty or malformed PCD files and no non-finite XYZ coordinates were detected. |
| Identity and tracks | No remaining missing, invalid, or unknown participant IDs or malformed identity/track records were found among the checked records; known same-frame duplicate-ID cases were excluded. |
| Annotation sources | No annotation frames referenced a missing image or point cloud. |
| Bounding boxes | No malformed 2D or 3D bounding boxes were detected. |

Machine-readable values and their scopes: [technical_validation.csv](data/technical_validation.csv).
