# Data Annotation & Quality Assessment Project — Summary Report

**Prepared by:** Asit Kumar Singha
**Date:** [Add date]

---

## 1. Overview

This project involved annotating a sample image dataset into predefined categories,
following a self-authored SOP-style guideline, and conducting a quality assessment
pass to measure labeling consistency.

- **Dataset used:** Intel Image Classification (Kaggle)
- **Total samples annotated:** [e.g. 130 images]
- **Tool used:** Label Studio (Docker deployment)
- **Categories used:** Buildings, Forest, Glacier, Mountain, Sea, Street, Escalate, Unclear

---

## 2. Annotation Process

Each image was labeled according to a defined guideline with clear category
definitions and edge-case rules (e.g., dominant-subject rule for mixed scenes,
40% snow-coverage threshold for Mountain vs. Glacier). Images that didn't clearly
fit a category were marked **Escalate**; low-quality/unidentifiable images were
marked **Unclear**, rather than guessed.

- **Escalated samples:** [e.g. 6 images — 4.6%]
- **Unclear samples:** [e.g. 3 images — 2.3%]

---

## 3. Quality Check Findings

A random [25–30%] sample ([e.g. 35 images]) was re-checked after a delay to test
labeling consistency.

| Metric | Result |
|---|---|
| Samples re-checked | [e.g. 35] |
| Mismatches found | [e.g. 3] |
| Consistency rate | [(35−3)/35 × 100 = e.g. 91.4%] |

**Example discrepancy resolved:**
Image [img_014] was initially labeled Mountain, but re-check flagged borderline
snow coverage (~45%). Applied the 40% rule → corrected to Glacier.

---

## 4. Key Learnings

- Clear edge-case rules (e.g. dominant-subject, % thresholds) significantly reduced
  ambiguous decisions and improved consistency on re-check.
- Escalation and Unclear labels were necessary — without them, borderline images
  would have been force-fit into wrong categories, lowering accuracy.
- At larger scale, a shared guideline like this would need periodic calibration
  across annotators to keep consistency high.

---

## 5. Conclusion

This project demonstrates a practical, guideline-driven approach to data annotation:
defining clear rules upfront, applying them consistently, and validating quality
through a structured re-check process — the same core workflow used in production
annotation pipelines.
