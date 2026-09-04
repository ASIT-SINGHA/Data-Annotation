# Data Annotation & Quality Assessment Project

A guideline-driven image annotation project built to demonstrate a practical, production-style labeling workflow — from writing an SOP-style annotation guideline through to a structured quality/consistency check.

## Overview

This project involved annotating a sample of images from the **Intel Image Classification** dataset (Kaggle) into predefined scene categories, following a self-authored guideline with explicit edge-case rules, and then running a quality assessment pass to measure labeling consistency.

- **Dataset:** [Intel Image Classification (Kaggle)](https://www.kaggle.com/datasets/puneet6060/intel-image-classification)
- **Total samples annotated:** [e.g. 130 images]
- **Annotation tool:** [Label Studio](https://labelstud.io/) (Docker deployment)
- **Categories:** Buildings, Forest, Glacier, Mountain, Sea, Street, Escalate, Unclear

## Annotation Process

Each image was labeled according to a defined guideline with clear category definitions and edge-case rules, for example:

- **Dominant-subject rule** for images with mixed scene elements
- **40% snow-coverage threshold** for distinguishing Mountain vs. Glacier

Images that didn't clearly fit a category were marked **Escalate** rather than force-fit into the wrong label. Low-quality or unidentifiable images were marked **Unclear**.

| Metric | Result |
|---|---|
| Escalated samples | [e.g. 2 images — 0.75%] |
| Unclear samples | [e.g. 1 images — 0.5%] |

## Quality Check

A random 25–30% sample of annotations ([e.g. 35 images]) was re-checked after a delay to measure labeling consistency.

| Metric | Result |
|---|---|
| Samples re-checked | [e.g. 35] |
| Mismatches found | [e.g. 3] |
| Consistency rate | [e.g. 91.4%] |

**Example discrepancy resolved:** Image `img_014` was initially labeled *Mountain*, but the re-check flagged borderline snow coverage (~45%). Applying the 40% rule corrected the label to *Glacier*.

## Key Learnings

- Clear edge-case rules (dominant-subject, percentage thresholds) significantly reduced ambiguous decisions and improved re-check consistency.
- Escalation and Unclear labels were essential — without them, borderline images would have been force-fit into the wrong category, lowering accuracy.
- At larger scale, a shared guideline like this would need periodic calibration across annotators to maintain consistency.

## Repository Structure

```
.
├── README.md                          # This file
├── guideline.md                       # Annotation SOP / category definitions & edge-case rules
├── annotations/                       # Raw and reviewed annotation outputs
├── quality_check/                     # Re-check sample, results, and discrepancy log
└── Data_Annotation_Summary_Report.md  # Full project summary report
```

## Tech / Tools Used

- **Label Studio** — annotation interface, run via Docker
- **Python** — for sampling, consistency-rate calculation, and report generation

## Conclusion

This project demonstrates a practical, guideline-driven approach to data annotation: defining clear rules upfront, applying them consistently, and validating quality through a structured re-check process — the same core workflow used in production annotation pipelines.

---

**Author:** Asit Kumar Singha
