# Project history

1. Set up a Drive project and mounted it in Colab. The saved checks showed a 2.09 GB RoCoLe archive, no corrupt ZIP entry, and a 1,560-row annotation CSV. The exact creation date of the folder is unverified.
2. Prepared 1,389 eligible healthy and rust images. Compared random splitting with SHA-256, perceptual hash, CLIP, and combined grouping. The combined split contained 970 train, 208 validation, and 211 test images.
3. Trained and evaluated five MobileNetV2 models on the existing partitions. Those test sets differ, so their scores alone cannot isolate the effect of leakage.
4. Ran controlled 0%, 10%, 20%, and 40% same-class training replacements with synthetic test-derived variants. Kept validation and test images fixed, used 970 training slots in every condition, and matched initial weights within each seed.
5. Completed seeds 42, 137, and 911. At 40%, all 211 test photos supplied variants. Accuracy and macro-F1 increased in each seed at 40%. Lower doses varied in direction across seeds. Synthetic variants differ from naturally captured bursts.

## Planned work

Run a matched 40% augmentation control using variants generated from training photos, with the same seed and training slots as each test-derived run. External evaluation is also planned. Neither is reported as completed.
