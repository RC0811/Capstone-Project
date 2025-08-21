# Multimodal Deepfake Detection via Lip–Speech Alignment

A compact **audio–visual** deepfake detector that asks a simple question:
**do the lips and the audio tell the same story in time?**

**Pipeline (TL;DR):**  
Mouth ROI → **ResNet-18** visual features + waveform → **Wav2Vec2** audio features → **WhisperX** phoneme↔frame alignment → **BiLSTM** sequence classifier → REAL/FAKE.

> This repo accompanies a thesis; the notebook demonstrates a small proof-of-concept run and exports figures (training curves, confusion matrix).

---

## Results (small validation split)

Curated talking-head set: **7 real / 7 fake**, split **11 train / 3 val**.

| Metric (best epoch) | Score  |
|---|---|
| Accuracy | **66.7%** |
| Weighted F1 | **0.53** |

> Notes: validation is **n=3**, so percentage swings are large; use public datasets (FF++, Celeb-DF, DFDC) for stable estimates.

Figures (exported by the notebook to `figs/`):
- ![Training curves](figs/training_curves.png)
- ![Confusion matrix](figs/confusion_matrix.png)
<!-- If you generated it: ![ROC curve](figs/roc_curve.png) -->

---

## Repo layout

