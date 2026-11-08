# Matched augmentation control

At 40% replacement, the experiment compared variants of test photos with variants of the original training photos occupying the same 388 slots. Both conditions used the same saved rotation and brightness values, crop, JPEG quality, split, and initial weights within each seed. Results are paired mean changes and sample standard deviations in percentage points across seeds 42, 137, and 911.

| Metric | Test-derived minus training-derived | Training-derived minus 0% control |
|---|---:|---:|
| Accuracy | +6.319 ± 0.724 | −0.316 ± 1.095 |
| Macro-F1 | +6.353 ± 0.780 | −0.262 ± 1.013 |
| Expected calibration error | −0.365 ± 0.594 | −1.742 ± 2.087 |

The accuracy and macro-F1 gains persisted against the matched augmentation control, supporting test-photo exposure as a contributor to the higher measured scores on RoCoLe. The additional calibration difference was small relative to its variation across seeds. These comparisons use the same RoCoLe test partition, with deliberate test exposure in the test-derived condition.
