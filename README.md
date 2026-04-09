<p align="center">
  <h1 align="center"> 🛸 Beyond Clean Data: An Open, Comprehensive Benchmark for Robustness Evaluation in UAV-Oriented Object Detection</h1>
  <p align="center">
    <strong>Ao Gong</strong> · <strong>Chenlin Fu</strong> · <strong>Hao Yu</strong> · <strong>Yingying Zhu</strong>
  </p>
  <p align="center">
        <a href="./Supplementary_Material.pdf"><img src='https://img.shields.io/badge/Paper-Supplementary_Material-red?logo=adobeacrobatreader' alt='Supplementary PDF'></a>
        <a href='#-the-benchmark-suite--real-world-subset'><img src='https://img.shields.io/badge/Dataset-Available_(Syncing)-brightgreen?logo=databricks' alt='Dataset'></a>
        <a href='https://2026.acmmm.org/'><img src='https://img.shields.io/badge/Status-Submitted_to_ACM_MM_2026-blue?logo=acm' alt='ACM MM 2026'></a>
  </p>
</p>

> **🎉 News:** This repository is the official project page for our Dataset Track submission to **ACM Multimedia 2026**.

## 😊 TL;DR

We introduce **CODrone-C** and **CODrone-C-L**, a comprehensive dual-benchmark suite featuring 17 decoupled stress tests explicitly parameterized to systematically evaluate the robustness of UAV-oriented object detectors.

## 📖 Abstract

Robust evaluation of UAV-oriented object detection (UAV-OOD) should go beyond clean imagery, as deployed systems routinely encounter adverse weather, motion-induced blur, and signal degradation. To bridge the gap between idealized training and physical deployment, we construct two robustness benchmarks, CODrone-C and CODrone-C-L, which subject oriented detectors to decoupled diagnostic stress tests under day and night conditions. CODrone-C spans 17 hazard types at five severities for exhaustive vulnerability diagnosis, while CODrone-C-L serves as a lightweight proxy for rapid model screening. A condition-specific Scene-Adaptive Modulation Protocol calibrates corruption intensities across illumination regimes to prevent non-physical artifacts. Extensive evaluations of nine state-of-the-art models uncover critical robustness insights, notably a severe day-night asymmetry where low-light conditions fundamentally amplify model vulnerability to unstructured noise. Furthermore, to validate the diagnostic fidelity of our benchmark, we curate Real-Adv135, a manually re-annotated real-world adverse evaluation subset. By demonstrating a strong semantic alignment between our synthetic stress tests and authentic operational failure modes via zero-shot transfer on Real-Adv135, we confirm the reliability of our diagnostic proxy. Ultimately, our dual-benchmark suite provides the community with a standardized tool to diagnose vulnerabilities and develop intrinsically resilient UAV-OOD models.

<div align="center">
  <img src="img/Fig2_Pipeline.jpg" width="900" alt="CODrone-C Construction Pipeline"/>
  <p><em>We systematically construct our decoupled diagnostic framework upon high-resolution clean UAV imagery, strictly calibrated by our Scene-Adaptive Modulation Protocol to ensure physical plausibility across day and night conditions.</em></p>
</div>

---

## 📦 The Benchmark Suite & Real-World Subset

### 📥 Dataset Downloads

> **⚠️ Important Notice Regarding Dataset Syncing:** > Due to the massive scale of the complete 17-corruption benchmark (over 700 GB in total), the full dataset is currently syncing to our cloud servers. However, the **core foundational subsets** (including `CODrone-C-L`, `Real-Adv135`, and representative corruptions from the full suite) are **fully available for immediate download and review**. 
> 
> *The remaining variants will automatically appear in these shared folders once their uploads complete. The links below are permanent.*

* **Google Drive (Recommended):** [Insert Google Drive Link Here]
* **Baidu Netdisk (Alternative for mainland China):** [Insert Baidu Link Here] (Access Code: `xxxx`)

---

Our project provides a complete ecosystem for UAV-OOD robustness evaluation, tailored for diverse diagnostic needs:

### 1. CODrone-C (Exhaustive Diagnosis Variant)
The full variant encompasses **17 decoupled hazard types** (Weather, Blur, Noise, Digital) across **5 severity levels**. It is designed for deep, fine-grained vulnerability profiling, allowing researchers to pinpoint the exact physical weaknesses of their network architectures.

### 2. CODrone-C-L (Lightweight Proxy Variant)
A rigorously quantified, sub-sampled version of the full benchmark. It drastically reduces evaluation overhead while strictly maintaining the performance ranking and diagnostic trends of the full dataset, making it ideal for rapid, iterative model screening during the training phase.

### 3. Real-Adv135 (Authentic Evaluation Subset)
To strictly validate the transferability of our synthetic stress tests, we curated and manually re-annotated 135 severely degraded real-world images (sourced from DroneVehicle, HazyDet, VisDrone, and UAVDT). All instances were meticulously re-annotated with precise Rotated Bounding Boxes (RBox).

<div align="center">
  <img src="img/Synthetic_vs_Real_Annotation.jpg" width="900" alt="Real-Adv135 Annotation Comparison"/>
  <p><em>Qualitative comparison demonstrating our precise manual RBox annotations (right) effectively rescuing targets missed or poorly enclosed by original coarse horizontal boxes (left) under extreme real-world degradations.</em></p>
</div>

### 📂 Directory Structure

Once fully downloaded, the dataset follows this organization:

```shell
CODrone-C_Benchmark/
├── CODrone-C/               # Full diagnostic variant (17 corruptions x 5 levels)
│   ├── Weather/             # Snow, Frost, Fog, Spatter
│   ├── Blur/                # Defocus, Glass, Motion, Zoom
│   ├── Noise/               # Gaussian, Shot, Impulse, Speckle
│   └── Digital/             # Brightness, Contrast, Pixelate, JPEG, Saturate
├── CODrone-C-L/             # Lightweight proxy variant
├── Real-Adv135/             # Real-world adverse evaluation subset
└── annotations/             # DOTA-style TXT annotations (RBox)
