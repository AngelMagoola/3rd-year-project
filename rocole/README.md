# RoCoLe near-duplicate leakage study

This study asks how synthetic near-duplicate leakage affects measured MobileNetV2 performance on a fixed coffee leaf rust test set. At 40% training replacement, test accuracy rose by 6.003 percentage points on average across seeds 42, 137, and 911. Test-derived variants deliberately bias the evaluation. These results describe synthetic leakage on one split.

## Reproduce the controlled study

1. Install the packages in requirements.txt in a Python environment with TensorFlow GPU support, or open rocole_injection.ipynb in Colab.
2. Supply your own RoCoLe images and the original combined split CSV. The CSV requires image_path, split (train, val, or test), and binary_class (healthy or rust). Paths should be relative to your data root. Keep the original row order when converting paths to relative paths.
3. Set DATA_ROOT and SPLIT_CSV in the notebook and run the cells. Runs save checkpoints, histories, predictions, metrics, and replacement manifests in a new output folder. A first run may need Internet access to fetch ImageNet weights.

The original manifest and grouping code are needed to reproduce the original partitions from raw data. This package assumes those partitions as input. GPU and dependency differences may affect repeatability.

## Evidence

- results/initial_comparison.csv records the five earlier split comparisons.
- results/paired_summary.csv reports mean and sample SD for each dose against its own seed's 0% control.
- results/donor_summary.csv compares paired accuracy on donor and non-donor test photos.
- results/observed_seed_metrics.csv records the complete original and seed 911 rows available in the Colab output excerpts. The aggregate summaries include all three seeds.
- results/paired_accuracy.svg shows the mean accuracy change and sample SD.
- PROJECT_HISTORY.md records the work from Drive setup to the completed analysis.
