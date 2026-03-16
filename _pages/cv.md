---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======

* B.S. in **Theoretical and Applied Mechanics** & **Energy and Power Engineering**, Tsinghua University, 2025
  * Certificate of **Industrial Engineering and Data Science** issued by Department of Industrial Engineering, Tsinghua University
  * Certificate of **Artificial Intelligence Innovation and Entrepreneurship Enhancement Program** issued by Fundamental Industry Training Center, Tsinghua University

Research experience(Click to see more details)
======
* **Jan.2025-Jun.2025**: **Physics-Informed Deep Learning for Geolocatable Photovoltaic Forecasting**
  * Researcher in 李水清's lab, Department of Energy and Power Engineering, Tsinghua University
  * **Engineered a physics-informed deep learning pipeline** for ultra-short-term photovoltaic forecasting, integrating Partial Differential Equations (PDEs) via the PhyDNet architecture to model realistic cloud motion and dissipation.
  * **Developed a multi-stage framework** involving cloud classification (91% accuracy), physics-constrained future image prediction, and 3D cloud field reconstruction with enhanced spatiotemporal consistency.
  * **Pioneered a method for generating geolocatable solar irradiance maps** from 2D sky images, a novel contribution that provides actionable, high-resolution data for grid operators.
  * **Designed and built an experimental data acquisition platform** to collect synchronized all-sky images, shadow textures, and irradiance data, addressing a critical gap in existing datasets.

* **Nov.2024-Apr.2025**: **Downscaling of Long-Range Climate Prediction Models Based on Sup3r** 
  * Researcher in 张达's lab, School of Environment, Tsinghua University
  * **Led the domain adaptation and data preprocessing pipeline** for the NREL sup3r generative model, originally trained on U.S. geophysical data. Reconciled format discrepancies and processed 18 years of multi-variable Chinese climate data (temperature, wind speed at multiple altitudes, solar irradiance, humidity) for the Anhui case study.
  * **Engineered a generative adversarial network (GAN) to perform high-resolution climate downscaling.** The model ingests readily available, long-term, low-resolution data and generates high-fidelity output, enhancing spatial resolution from 100km to 30km and temporal resolution from 72 hours to 24 hours. This approach directly addresses the critical challenge of scarce and dispersed global high-resolution training data.
  * **Validated the model's utility for climate prediction post-processing.** Successfully applied the framework to downscale and refine the low-resolution outputs from multiple climate forecast models, demonstrating its versatility for producing high-resolution climate projections over decadal timescales.

* Feb.2024-Jun.2024: Structural Engineering of Pt-based Intermetallic Catalysts for Fuel
  * Researcher in 张亮's lab, Center for Combustion Energy, THU
  * Designed PtCoMn/PtCoTi trimetalli catalysts using DFT calculations and Monte Carlo simulations.
  * Validation through HAADF-STEM characterization and electrochemical test.
  
* Nov.2023-Jan.2024: Prolong Life Cycle of High Frequency Dielectric Elastomer Actuator
  * Researcher in 赵慧婵's lab, Department of Mechanical Engineering, THU
  * Investigation on basic principles of DEAs and soft, flexible bioaterials and electronics.

* Sep.2022-May.2023: Cage-shaped Self-folding Mechanical Metamaterials
  * Researcher in 陈常青's lab, Department of Aerospace Engineering, THU
  * Validation through theories, Abaqus and otherrelevant techniques.
  * Experiments: set experiment environment, lab design, and data simulation, etc.
  * Writing part of the paper and edit & reviewing. 

* Mar.2022-Jun.2022: Analysis of the Power System for Electric Unmanned Aerial Vehicles
  * Researcher in 胡尊严's lab, School of Vehicle and Mobility, THU
  * Overview of UAV power systems and simulation experiments of fixed-wing UAV power systems.

Skills
======
* Abaqus, 3D print, Solidworks: Calibration & Validation
* Coding
  * Python for machine learning: Pytorch, Tensorflow
  * Web construct: React, Flask, SQL
  * Ai application: RAG, agent
* Dedicated to dive in new area all the time

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Service and leadership
======
* Currently signed in to 43 different slack teams
