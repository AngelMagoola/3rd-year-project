# External evaluation on JMuBEN and JMuBEN2

Nine saved RoCoLe MobileNetV2 checkpoints were scored at a fixed threshold of 0.5 on 27,319 external images. The evaluation used 18,983 healthy photos from JMuBEN2 and 8,336 rust photos from JMuBEN. An exact hash and perceptual hash screen against RoCoLe excluded one unreadable file. Neither hash check flagged a match at the chosen thresholds.

| Training condition | Seed 42 | Seed 137 | Seed 911 | Mean accuracy |
|---|---:|---:|---:|---:|
| 0% injected leakage | 13.50% | 51.30% | 74.58% | 46.46% |
| 40% training-photo edits | 76.30% | 69.14% | 78.71% | 74.72% |
| 40% test-photo edits | 32.04% | 20.12% | 66.30% | 39.49% |

At 40% replacement, training on edited RoCoLe test photos increased RoCoLe test accuracy by 6.32 percentage points compared with the matched training-photo control. On the external dataset, the same comparison reversed. Test-photo edits scored 35.23 points lower on average (sample SD 19.91 points), with a lower score in each seed. External macro-F1 fell by 27.90 points and expected calibration error rose by 18.24 points.

All nine metric rows were reproduced from the saved predictions and the image labels were checked against their folders. The seed 42 clean model classified 17,582 healthy images as rust and 6,048 rust images as healthy. This confirms the recorded errors. The cause of this unusually low result remains open. An always-healthy prediction would score 69.49% accuracy on this class mix.

[Per-model metrics and confusion counts](jmuben_external_metrics.csv) · [Figure (PNG)](JMuBEN%20Leakage%20Results.png) · [Figure (SVG)](JMuBEN%20Leakage%20Results.svg)
