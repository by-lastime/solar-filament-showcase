# Solar Filament Segmentation

### Research on instance segmentation in solar Hα images

[中文](README.md) · [Research route, Chinese](docs/research-route.md) · [Technical overview, Chinese](docs/technical-overview.md)

This project studies how to separate solar filament instances while preserving thin boundaries and connectivity. It combines segmentation baselines, controlled ablations, candidate analysis, local mask refinement, and reproducible experiment workflows.

This repository is a documentation-only project showcase. It contains no datasets, sample images, annotations, model weights, experimental result files, or training implementation.

## Research questions

- How do input resolution and mask representation affect thin structures?
- Can instance and semantic predictions complement each other without introducing harmful changes?
- How can local refinement improve boundaries while preserving connectivity?
- How should disagreements between annotation sets affect training supervision?
- Why are useful candidates sometimes missed by the selection stage?

## Work carried out

| Area | Work |
|---|---|
| Baselines | Instance segmentation and patch-based semantic segmentation |
| Ablations | Input resolution, ROI mask grids, fusion, refinement, and supervision changes |
| Refinement | Instance-conditioned processing at native image resolution |
| Candidate analysis | Coverage, selection errors, quality features, and ranking objectives |
| Validation | Time-group splits, teacher provenance, and cross-fitting |
| Engineering | Metric consistency, checkpoint recovery, cache reuse, numerical equivalence, and archive verification |

The research branches are evaluated separately; they are not all components of a single final model.

## What we have learned

Some development comparisons show promising effects from higher resolution, conservative fusion, and native-resolution refinement. Those effects must be considered alongside false positives, morphology, and runtime.

Other tested approaches improved an intermediate quantity without improving the final output. Negative results and shape failures remain part of the research record. Increasing resolution, adding candidates, or using a more complex scorer is not sufficient by itself.

These are project-specific development observations. This showcase makes no claim of independent blind-test performance, leaderboard leadership, or publication acceptance. Detailed numerical results and evidence remain internal.

## Technology

Python · PyTorch / torchvision · Mask R-CNN · semantic segmentation · instance-conditioned refinement · COCO RLE · time-group validation · cross-fitting

## Status

As of **7 November 2026**, multiple baseline, ablation, and diagnostic studies have been completed, and an experiment documentation resource has been assembled. Current priorities are method consolidation, morphology assessment, and research writing.
