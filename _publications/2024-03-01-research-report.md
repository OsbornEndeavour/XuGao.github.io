---
title: "Structural Engineering of Pt-based Intermetallic Catalysts for PEM Fuel Cells"
collection: publications
category: reports
permalink: /publication/2024-06-pt-intermetallic-ordering-monte-carlo
excerpt: "Monte Carlo ordering simulations for Pt-based intermetallic catalysts (PtCoMn vs PtCoTi): temperature/size effects, move-strategy analysis, and design insights toward high-activity catalysts without high-temperature sintering."
date: 2024-06-15
venue: "Liang Zhang’s Lab, Center for Combustion Energy, Tsinghua University"
---

## Overview
Ordered Pt alloys (intermetallic catalysts) are promising for PEM fuel cells because higher atomic ordering is strongly associated with improved catalytic performance (e.g., higher mass activity), yet achieving ordering in practice often relies on high-temperature annealing—an approach that can induce nanoparticle sintering and degrade activity/stability. In Liang Zhang’s lab (Center for Combustion Energy, THU), I worked on a computational pathway to **probe, quantify, and potentially accelerate ordering** in Pt-based alloys using **atomistic Monte Carlo (MC) simulations** driven by structure–energy evaluation. Rather than treating “ordering” as a single yes/no outcome, the work systematically maps how ordering evolves with **temperature**, **system size**, **alloy composition** (PtCoMn vs PtCoTi), and **MC move strategy** (nearby exchange vs global exchange). The deliverable is a simulation framework plus experimentally relevant insights: which conditions favor monotonic energy decrease and ordering-degree evolution, when thermal fluctuations dominate, and how algorithmic move choices can bias ordering kinetics—providing design guidance that can be paired with HAADF-STEM characterization and electrochemical validation.

## My Contributions
- Built an extendable **MC simulation backbone** for Pt alloy ordering, including:
  - neighbor-atom search / local environment identification  
  - ordering-degree metric computation (**α**, with α = −1/3 indicating the ordered limit under the project’s definition)  
  - MC step execution, energy tracking, and convergence diagnostics  
- Designed and executed **controlled in-silico experiments** to isolate key factors:
  - **temperature** (e.g., 100 K vs 500 K) and its effect on energy and α trends  
  - **system size** (small vs larger atom-count structures) to identify finite-size sensitivity  
  - **composition** comparison (PtCoMn vs PtCoTi) to reveal composition-dependent ordering ease  
  - **move strategies** (nearby vs global exchange) to quantify how algorithmic choices affect ordering outcomes  
- Interpreted simulation outputs (energy–iteration and α–iteration curves) to extract actionable rules of thumb for “ordering-favorable” settings versus regimes where thermal motion or sampling makes trends ambiguous.
- Proposed next-stage interpretability deliverables: exporting `.xyz` snapshots to build **3D ordering animations** aligned with α evolution, and adding richer structure metrics (e.g., correlation-style descriptors) for more diagnostic ordering analysis.

## Methodology Pipeline
**Problem framing (ordering–sintering trade-off) → MC algorithm design (exchange moves + energy-based accept/reject) → Implementation (neighbor search + ordering metric α + simulation loop) → Parameter sweeps (temperature / system size / composition / move strategy) → Trend analysis (energy & α vs iteration; ordering feasibility) → Visualization & experimental guidance (XYZ snapshots, animations, structure metrics)**
---

## Poster for CCE Day
![Poster for CCE DAY]({{ site.baseurl }}/images/poster_MC.png)
- Fig1：Overview of the work's pipeline and results.

![Simulation Results]({{ site.baseurl }}/images/MC_path.png)
- Fig2：Simulated energy variation with changed trinary atom.