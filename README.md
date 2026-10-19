<h1 align="center">Volodymyr Borysenko</h1>

<p align="center">
  Software Engineering + AI/ML | Data Science @ UC Berkeley | RISE Global Winner
</p>

---

### 👨‍💻 About

- 🔭 Building **TacticSquare** for UAV coordination simulation and **FireImpactology** for wildfire exposure analysis.
- 🎯 Focus: multi-agent RL, stochastic combat models, graph optimization, remote sensing.
- 🛰 Working with Sentinel-2 and ERA5 data, downscaled climate projections and geospatial pipelines.
- 🇺🇦 From Ukraine; my projects span heat risk, wildfire exposure and UAV coordination.
- 📈 Kaggle: [rank 5 of 564](https://www.kaggle.com/competitions/store-sales-time-series-forecasting/leaderboard) in Store Sales forecasting, top 1% in Housing Prices, 40+ [public notebooks](https://www.kaggle.com/volodymyrborysenko/code).

---

### 🚀 Selected projects

- **[Waves](https://github.com/VolodymyrLinuxovich/mistral-waves)** ([live demo](https://waves-nine-gold.vercel.app)) - FastAPI heatwave map for Ukraine with deterministic personal-risk scoring and Mistral-generated bilingual action plans under privacy and medical-safety guardrails.
- **[heat-risk-cuda](https://github.com/VolodymyrLinuxovich/heat-risk-cuda)** - custom CUDA C++ kernels compiled at runtime with NVIDIA `cuda.core`, verified for exact parity with NumPy and PyTorch references (171 GPU tests) and benchmarked on a Tesla T4: a shared-memory tiled kernel cut end-to-end time 2.2× and runs about 5× faster than the PyTorch baseline.
- **[SwarmDAQ](https://github.com/VolodymyrLinuxovich/swarmdaq)** ([live demo](https://swarmdaq.vercel.app)) - performance exchange for AI agents built at WeaveHacks 2025: agents bid on tasks, a market maker routes work to the best swarm, and reputation updates after every run, with W&B Weave tracing and Redis memory.
- **[LargeVCModel](https://github.com/VolodymyrLinuxovich/largevcmodel)** - Next.js + PostgreSQL platform for relationship search, company research, investor-fit scoring and secure Google integrations.
- **[TacticSquare](https://isef.net/project/math037-uavs-in-ground-combat-stochastic-modelling)** - AI combat simulator for UAV coordination, route planning and attrition forecasts using RL, graph search and Bayesian Monte Carlo; field-tested in Ukraine with 10 divisions and backed by external funding.
- **[FireImpactology](https://www.spaceappschallenge.org/2023/find-a-team/fire-impactology/?tab=project)** - wildfire analytics pipeline: MODIS/VIIRS/Sentinel-2 + ERA5 + Gaussian plume to map PM2.5/PM10 and health risk.
- **[Schmidt DSE Climate Pipeline](https://github.com/VolodymyrLinuxovich/climate_data_pipeline)** - xarray and Dask workflows for downscaled CMIP6 analysis and National Park Service climate-risk maps at the [Eric and Wendy Schmidt Center for Data Science & Environment](https://dse.berkeley.edu/).
- **[DEMI](https://github.com/VolodymyrLinuxovich/demi)** - wearable prototype with gas sensors, microcontroller and CV backend that detects TVOC spikes and automatically triggers a deodorizing spray.

---

### 🌐 Open source

42 merged pull requests across 11 established open source projects:

| Project | Merged | Highlights |
|---|:---:|---|
| **[OWASP Java Encoder](https://github.com/OWASP/owasp-java-encoder)** | 5 | Added the new [`Encode.forJson`](https://github.com/OWASP/owasp-java-encoder/pull/151) API, [escaped DEL and C1 controls](https://github.com/OWASP/owasp-java-encoder/pull/166) in the JavaScript encoders, [added XML 1.1 tags and EL functions](https://github.com/OWASP/owasp-java-encoder/pull/168), [propagated the forUri deprecation](https://github.com/OWASP/owasp-java-encoder/pull/170) and [fixed OSGi import ranges](https://github.com/OWASP/owasp-java-encoder/pull/174) |
| **[GeoPandas](https://github.com/geopandas/geopandas)** | 2 | [Made the explode index dtype consistent](https://github.com/geopandas/geopandas/pull/3871) across platforms and [removed a dead testing helper](https://github.com/geopandas/geopandas/pull/3869) |
| **[All the Places](https://github.com/alltheplaces/alltheplaces)** | 27 | [Fixed missing Coles stores](https://github.com/alltheplaces/alltheplaces/pull/19272), [fixed duplicate Japan Post refs](https://github.com/alltheplaces/alltheplaces/pull/19633) and added 25 spiders including [Royal Mail](https://github.com/alltheplaces/alltheplaces/pull/19405), [NTT public telephones](https://github.com/alltheplaces/alltheplaces/pull/19475), [Packeta](https://github.com/alltheplaces/alltheplaces/pull/19418), [Curves](https://github.com/alltheplaces/alltheplaces/pull/19811) and [Mizuho Bank](https://github.com/alltheplaces/alltheplaces/pull/19624), covering 234,000+ locations |
| **[NVIDIA NeMo Curator](https://github.com/NVIDIA-NeMo/Curator)** | 1 | [Allowed boilerplate removal at both the top and bottom of documents](https://github.com/NVIDIA-NeMo/Curator/pull/2477) |
| **[rioxarray](https://github.com/vylor/rioxarray)** | 1 | [Raised an informative error for 2D spatial coordinates and fixed `rio.shape`](https://github.com/vylor/rioxarray/pull/940) |
| **[Kigali Sim](https://github.com/SchmidtDSE/kigali-sim)** | 1 | [Added operation types to the program validator](https://github.com/SchmidtDSE/kigali-sim/pull/867) |
| **[PySAL mgwr](https://github.com/pysal/mgwr)** | 1 | [Fixed the search method values in the bandwidth selector docs](https://github.com/pysal/mgwr/pull/173) |
| **[OWASP CVE Lite CLI](https://github.com/OWASP/cve-lite-cli)** | 1 | [Refactored the install command](https://github.com/OWASP/cve-lite-cli/pull/1203) |
| **[OWASP API Security Testing Framework](https://github.com/OWASP/www-project-api-security-testing-framework)** | 1 | [Read requestBody from inline config endpoints](https://github.com/OWASP/www-project-api-security-testing-framework/pull/137) |
| **[Dependency-Track](https://github.com/DependencyTrack/frontend)** | 1 | [Pointed the About dialog to the v5 docs](https://github.com/DependencyTrack/frontend/pull/1917) |
| **[PySAL segregation](https://github.com/pysal/segregation)** | 1 | [Fixed a duplicate table row and updated the community link](https://github.com/pysal/segregation/pull/301) |

In review at [OWASP DependencyCheck](https://github.com/dependency-check/DependencyCheck/pull/8819), [GeoPandas](https://github.com/geopandas/geopandas/pull/3879) and [Newton](https://github.com/newton-physics/newton/pull/4600).

---

### 🏅 Achievements

- **[RISE Global Winner](https://www.risefortheworld.org/global-winners/) (Schmidt Futures & Rhodes Trust), 2024**  
  Top 100 of 50,000+ from 170+ countries with scholarship and project funding.

- **[King Abdulaziz and Mawhiba Award](https://isef.net/project/math037-uavs-in-ground-combat-stochastic-modelling), 2024**  
  Top 10 of 1,500 finalists for a combat-operations simulator using Monte Carlo and cellular automata.

- **[Genius Olympiad Gold](https://man.gov.ua/about/news/vihovanci-man-peremogli-na-genius-olympiad) (Environmental Science), 2024**  
  "FireImpactology" for wildfire, air quality and health impact modeling.

- **[INFOMATRIX International Platinum Medal](https://kman.kyiv.ua/ua/Final-Mizhnarodnoho-konkursu-INFOMATRIX-2024), 2024**  
  1st place among 300 participants for advanced combat simulation with stochastic Lanchester models and RL-aided route planning.

- **All-Ukrainian Programming Cup, 3rd place and Jane Street Award, 2025**

- **[NASA Space Apps Challenge](https://www.spaceappschallenge.org/2023/find-a-team/fire-impactology/?tab=project), 2nd place in Ukraine, 2023**  
  FireImpactology wildfire and air quality pipeline.

- **[Venture and deployment](https://tumo.ai/teens/report)**  
  $50,000 raised to scale TacticSquare pilots with 10 divisions and international visibility.

---

### 🧰 Tech stack

<p align="left">
  <img src="https://skillicons.dev/icons?i=python,cpp,ts,js,bash,matlab,r" />
  <img src="https://skillicons.dev/icons?i=pytorch,tensorflow,sklearn,opencv" />
  <img src="https://skillicons.dev/icons?i=postgresql,fastapi,nodejs,docker,git,github" />
</p>

Core domains: CUDA and GPU computing, RL (DQN, PPO), multi-agent systems, Monte Carlo, stochastic processes, graph algorithms, geospatial and remote sensing (GeoPandas, Rasterio, rioxarray, GDAL), time series, simulation.

---

### 📊 Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=VolodymyrLinuxovich&show_icons=true&include_all_commits=true&count_private=true&hide_title=true" height="150" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=VolodymyrLinuxovich&layout=compact&hide_title=true&langs_count=8" height="150" />
</p>

<p align="center">
  <img src="https://streak-stats.demolab.com?user=VolodymyrLinuxovich" height="150" />
</p>

---

### 🔗 Links

- Resume: [View PDF](https://drive.google.com/file/d/1-Te5vAf4e73Ow701r_0d1FXeJbv-WRBA/view?usp=sharing)
- Website: [vborysenko.com](https://vborysenko.com)
- LinkedIn: [Volodymyr Borysenko](https://www.linkedin.com/in/volodymyr-borysenkooo)
- Email: volodymyr_borysenko@berkeley.edu
