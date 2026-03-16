---
title: "A-Share Quant Dashboard: End-to-End Data→Factors→LLM Analysis→Report Generation"
collection: publications
category: entrepreneurship
permalink: /publication/2025-10-25-aifinance
excerpt: "A production-delivered Streamlit dashboard for China A-shares integrating Tsanghi fundamentals + yfinance OHLCV, factor computation (PE/PB/ROE/dividend/OBI/momentum), and an OpenAI-compatible LLM workflow for chat-based analysis and one-click research report generation."
date: 2025-10-25
venue: "Personal Project — Delivered for internal usage (course teaching / analysis workflow)"
---

## Overview
This project extends the existing open-source FinRobot framework into a complete, A-share-focused quantitative analysis workflow and delivers it as a stable, minimal-dependency dashboard. The system is implemented in **Python 3.9** and built on **Streamlit** with a three-tab product design: **(1) factor visualization**, **(2) AI analyst chat**, and **(3) one-click research report generation**. Data is fetched from the **Tsanghi API** (company profile, realtime quotes, financial statements, dividends, order-book snapshots) and augmented with **yfinance** to retrieve ~60 trading days of OHLCV history (addressing the limitation that Tsanghi daily endpoints provide only the latest day). On top of this data layer, the dashboard computes a unified set of core factors—**PE, PB, ROE (multi-year), dividend yield, OBI (order-book imbalance), momentum**—and injects these factor summaries as hidden structured context into an **OpenAI-compatible API** (e.g., DeepSeek) for grounded Q&A and report writing. The project includes significant engineering work to ensure the dashboard runs reliably under **minimal dependencies**, using optional-import patterns and Python 3.9–compatible type hints to prevent startup failures.

The dashboard was successfully delivered and adopted for internal teaching/analysis workflows, enabling users to complete the full loop: **“select ticker → fetch data → compute factors → visualize → chat analysis → generate report → download Markdown.”**

## My Contributions
- **End-to-end productization (Streamlit dashboard):** designed and implemented the three-tab UI, shared state management via `st.session_state`, and the “analyze once, reuse everywhere” data flow across tabs.
- **Data integration (A-share-ready):**
  - integrated **Tsanghi API** (token-based auth, unified key loading via `config_api_keys` and JSON registration) for fundamentals, financials, dividends, and realtime snapshots;
  - implemented a **yfinance fallback** to fetch ~60 trading days of OHLCV with exchange mapping (XSHG→`.SS`, XSHE→`.SZ`) to support K-line charts and momentum computation.
- **Quant factor engineering:** implemented a factor module that binds directly to Tsanghi’s nested JSON and outputs a consistent factor dictionary (valuation, dividend, quality, micro-structure, momentum, warnings), including ROE trend logic and operating cashflow/net profit quality ratios.
- **Interactive analytics & parameterization:** added tunable evaluation parameters (ROE threshold, momentum window, ROE-year span) with real-time recomputation and concise decision outputs that update immediately with slider changes.
- **LLM integration (grounded chat + report generation):**
  - implemented an OpenAI-compatible client with configurable `api_key`, `base_url`, and model name;
  - designed a system-prompt strategy that **injects factor summaries and report data as hidden context** to keep outputs data-grounded;
  - implemented one-click report generation that enforces a fixed Markdown structure (five sections) and enables **Markdown download**.
- **Robustness for minimal environments:** refactored multiple modules to avoid hard dependency failures by using `try/except` optional imports (e.g., `sec_api`, `praw`, `autogen/rag`, `mplfinance`, `reportlab`, `backtrader`) and fixed Python 3.9 type-annotation compatibility by replacing `X | Y` with `Union[...]` / `Optional[...]`.

## Methodology Pipeline
**Product goal definition → A-share data ingestion (Tsanghi) → historical OHLCV补齐 (yfinance) → factor computation (PE/PB/ROE/dividend/OBI/momentum) → visualization (Plotly candlestick + volume + metrics) → parameterized evaluation logic → LLM grounding (context packing) → chat-based analysis → one-click report generation (Markdown) → download/export workflow → dependency hardening & Python 3.9 compatibility fixes → internal delivery and adoption**
