<p align="center">
  <h1 align="center"> 🚁 Beyond Clean Data: An Open, Comprehensive Benchmark for Robustness Evaluation in UAV-Oriented Object Detection</h1>
  <p align="center">
    <strong>Ao Gong</strong> · <strong>Chenlin Fu</strong> · <strong>Hao Yu</strong> · <strong>Yingying Zhu</strong>
  </p>
  <p align="center">
        <a href="./Supplementary_Material.pdf"><img src='https://img.shields.io/badge/Paper-Supplementary_Material-red?logo=adobeacrobatreader' alt='Supplementary PDF'></a>
        <a href='#dataset-access'><img src='https://img.shields.io/badge/Dataset-CODrone--C-yellow?logo=databricks' alt='CODrone-C Dataset'></a>
        <a href='https://2026.acmmm.org/'><img src='https://img.shields.io/badge/Status-Submitted_to_ACM_MM_2026-blue?logo=acm' alt='ACM MM 2026'></a>
  </p>
</p>

> **🎉 News:** This repository is the official project page for our Dataset Track submission to **ACM Multimedia 2026**.

**😊 TL;DR**

We introduce **CODrone-C** and **CODrone-C-L**, a comprehensive dual-benchmark suite featuring 17 decoupled stress tests explicitly parameterized to systematically evaluate the robustness of UAV-oriented object detectors.

<div align="center">
  <img src="img/Teaser.jpg" width="800" alt="CODrone-C Teaser"/>
</div>

---

## ⭐ Key Contributions

- **Comprehensive Dual-Benchmark Suite:** We construct CODrone-C (spanning 17 hazard types at five severities for exhaustive vulnerability diagnosis) and CODrone-C-L (a lightweight proxy for rapid model screening), bridging the critical gap between idealized training and physical UAV deployment.
- **Scene-Adaptive Modulation Protocol:** We introduce an illumination-dependent protocol to strictly calibrate corruption intensities across day and night regimes, effectively preventing non-physical visual artifacts.
- **Deep Robustness Insights:** Through extensive benchmarking of 9 SOTA UAV-OOD models, we uncover critical insights, notably a severe **day-night asymmetry** where low-light conditions fundamentally amplify model vulnerability to unstructured noise and high-frequency spatial degradations.

---

## 📄 Supplementary Material (Appendix)

Due to the strict 6-page limit of the ACM MM Dataset Track, we provide a comprehensive technical whitepaper to support our main findings. 

👉 **[Click here to view the Supplementary Material PDF](./Supplementary_Material.pdf)**

Inside the Supplementary Material, you will find:
- **[Sec. A]** Exact attenuation parameters ($\alpha$) for our Scene-Adaptive Modulation Protocol and the curation details of the **Real-Adv135** real-world subset.
- **[Sec. B]** Exhaustive model training configurations and hyperparameter settings.
- **[Sec. C]** Complete benchmarking tables under the highly stringent **$\text{AP}_{75}$** metric and detailed **Corruption-Augmented Training (CAT)** results.
- **[Sec. D]** High-resolution qualitative visualizations demonstrating the orthogonal diagnostic stress of all 17 corruptions.

---

## 📥 Dataset Access

The dataset is structured to seamlessly integrate with standard Oriented Object Detection toolkits (e.g., MMRotate, DOTA format).

*Note: The full dataset is currently being uploaded. A comprehensive sample subset (including Real-Adv135) is available below for immediate review.*

- [Google Drive Link (Sample Subset)](#) - [Baidu Pan Link (Sample Subset)](#) ### Directory Structure

```shell
CODrone-C_Benchmark/
├── CODrone-C/               # Full diagnostic variant
│   ├── Weather/             # Snow, Frost, Fog, Spatter
│   │   ├── 1/               # Severity Level 1
│   │   ├── ...
│   │   └── 5/               # Severity Level 5
│   ├── Blur/
│   ├── Noise/
│   └── Digital/
├── CODrone-C-L/             # Lightweight proxy variant
├── Real-Adv135/             # Real-world adverse evaluation subset
└── annotations/             # DOTA-style TXT annotations (RBox)
