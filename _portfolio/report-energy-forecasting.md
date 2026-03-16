---
title: "Ultra-short-term PV Forecasting via Machine Vision + Deep Learning (2D→3D Cloud→Shadow→Irradiance)"
excerpt: "A multi-stage forecasting pipeline from ground-based sky images to physically interpretable PV prediction: geolabeled vision features, long-horizon cloud nowcasting, 3D cloud voxelization, and shadow–irradiance mapping."
collection: portfolio
category: thesis
date: 2025-06-12
permalink: /portfolio/energy-forecasting-report/
header:
  teaser: /images/porfolio_cv.png
link: "/files/Portfolio_cv.pdf"
venue: "Shuiqing Li(李水清)‘s lab, Department of Energy and Power Engineering, THU"
project: "Energy-AI Integration Project"
---

## Research Overview
Photovoltaic (PV) generation is a key pathway to the “dual-carbon” goal, but its output is inherently volatile because cloud dynamics can change irradiance at minute-to-second scales. My thesis tackles a core bottleneck: **mapping sky visual information to PV output with both high temporal precision and explicit spatial localization**.

Instead of treating forecasting as a single black-box regression, I built a **multi-stage, physics-aware pipeline**:
**(1) machine-vision feature extraction → (2) future cloud image prediction → (3) 3D cloud reconstruction → (4) projection to site-level shadow/irradiance → (5) PV forecasting-ready inputs**.

---

## Why It Matters
Ultra-short-term PV forecasting is increasingly high-stakes for grid stability and market operations: PV output can drop sharply within seconds under fast-changing weather, raising the burden on balancing and dispatch.

A key limitation of many cloud-image-based approaches is **spatial ambiguity**: predicting a future 2D sky image does not directly yield accurate **cloud shadow placement** at the PV plant because the cloud field is fundamentally 3D.

---

## Key Contributions
### 1) Geolabeled vision pipeline for “forecasting with coordinates”
I established a machine-vision workflow that turns raw sky images into **structured, physically meaningful features**, including:
- **Pixel-to-WGS84 geolocation** and cloud position cues  
- **Sun position estimation + solar masking** (to prevent glare from corrupting cloud contour extraction)  
- **Cloud contour extraction** and cloud-base-height related reasoning for projection prerequisites

In experiments, the pixel–geolocation conversion and CBH-related calibration achieved **~100 m-level error control**.

### 2) Filling a missing dataset: shadow texture ↔ irradiance pairs
Public datasets are rich in sky images but often lack **paired shadow-texture and irradiance supervision**. I designed a real outdoor experiment to collect this missing link:
- ~**1200** high-quality “shadow” samples + **1200** “no-shadow” samples  
- each with timestamp + irradiance readings  
- rectified into **52×80** image patches for training a shadow–irradiance mapping model

### 3) Cloud semantic understanding via multimodal classification (vision + meteo)
To support downstream modeling (especially GAN-based shadow texture generation and physically meaningful categorization), I trained a **multimodal cloud classification** model:
- **5 cloud categories**, **24,000 images** total  
- weather features (e.g., temperature, wind speed, pressure) fused with visual cues  
- training: **50 epochs**, **batch 32**  
- achieved **86.70% accuracy**

### 4) Long-horizon future sky prediction: comparing three model families
I benchmarked three classes of cloud nowcasting models using a unified evaluation protocol:
- **ConvLSTM** baseline: MSE **333.1451**, MAE **10.7758**
- **PhyCell + GAN** (physics dynamics + adversarial detail): MSE **316.3073**, MAE **10.0677**
- **VQ-VAE + Transformer** (discrete latent tokens for long sequences): MSE **290.4905**, MAE **9.7149**

This supports the thesis claim: **VQVAE-Transformer is more capable of generating long time-series, higher clarity, and stronger physical consistency**, making it the preferred input for 3D reconstruction.

### 5) Extending “2D→PV” into “2D→3D→shadow→irradiance→PV”
I reframed the classical pipeline (“2D cloud prediction → PV output”) into a physically grounded chain:
**2D cloud maps → 3D cloud voxel field → site projection → dynamic shadow map → irradiance estimation → PV forecasting**.

I also explored the feasibility of adapting **Pix2Vox**-style voxel reconstruction to cloud fields and analyzed key constraints (dataset design, loss functions, interpretability), positioning this as a forward-looking step toward spatially explicit forecasting.

---

## Methodology (End-to-End Research Pipeline)
This work was executed as a complete research loop:

1. **Problem framing**: ultra-short-term PV volatility, spatial localization gap
2. **Data engineering**: sky image preprocessing, geolocation + sun position + cloud contours
3. **New data acquisition**: outdoor shadow-texture ↔ irradiance dataset collection
4. **Semantic modeling**: multimodal cloud classification
5. **Model benchmarking**: ConvLSTM vs physics-aware GAN vs VQVAE-Transformer
6. **3D reconstruction concept**: Pix2Vox-style voxel cloud field + projection to plant region
7. **System-level view**: “end–mid–end” integration for spatially explicit PV forecasting

---

## My Role (Ownership & Competence Signals)
- Designed the overall **multi-stage forecasting paradigm** from sky images to spatially meaningful PV inputs 
- Built the **vision preprocessing + geolabeling** pipeline (WGS84 mapping, sun masking, cloud contours), including error-controlled calibration
- Designed and executed the **shadow–irradiance experiment** and dataset specification
- Implemented and compared deep sequence models and reported quantitative metrics
- Proposed the **2D→3D→projection** extension and documented key research challenges and next steps

---

## How This Supports My Research Directio
This project demonstrates the RA-ready skill stack needed for PV forecasting research:
- **Data + systems thinking:** turning observational data into a deployable pipeline rather than isolated models
- **Computer vision for atmosphere:** geolabeling, sun-aware preprocessing, semantic modeling
- **Model rigor:** unified evaluation across architectures, reporting MSE/MAE trade-offs
- **Physical interpretability:** explicit reasoning about 3D cloud structure and shadow projection as the missing link to PV relevance

---

## Research Media

###  Open my final defense PPT through the link below
