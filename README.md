# Volodymyr Borysenko

Data Science and CS student at UC Berkeley, from Ukraine. I build GPU kernels, data pipelines and full-stack products, and I contribute to open-source geospatial, security and data tooling.

[vborysenko.com](https://vborysenko.com) · [LinkedIn](https://www.linkedin.com/in/volodymyr-borysenkooo) · [Resume](https://drive.google.com/file/d/1-Te5vAf4e73Ow701r_0d1FXeJbv-WRBA/view?usp=sharing) · volodymyr_borysenko@berkeley.edu

**What I work on**

- **GPU and performance:** CUDA C++ kernels, memory-layout tuning, benchmarks with exact parity checks against CPU references.
- **Data at scale:** crawlers and geospatial pipelines that cover whole countries, with checks that nothing is missed or duplicated.
- **Full-stack products:** Next.js, TypeScript, PostgreSQL, Python services, OAuth integrations and tested authorization.
- **Modeling:** probabilistic forecasting, Monte Carlo simulation and calibration on real outcomes.

---

## Featured projects

### [heat-risk-cuda](https://github.com/VolodymyrLinuxovich/heat-risk-cuda)
CUDA C++ kernels, compiled at runtime with NVIDIA `cuda.core`, that count heat-hazard days and their longest runs over `[scenario, location, day]` arrays.

- Profiling on a Tesla T4 showed a GPU transpose took 261 ms of the 458 ms end-to-end time. A shared-memory tiled kernel that reads the original layout removed it: **457 ms → 208 ms (2.2×)** on 187M cells.
- Every GPU result matches the NumPy reference exactly. **171 GPU tests** passed on the T4.
- Baselines: NumPy, multithreaded C++17 and PyTorch. Benchmark tables are generated from the JSON of each GPU run, and the README reports where the GPU does *not* win (end to end, it roughly ties 10 laptop CPU threads once data crosses PCIe).

`CUDA C++` `Python` `cuda.core` `NVRTC` `PyTorch` `C++17`

### [Recount](https://github.com/VolodymyrLinuxovich/recount) · [live](https://recount-nu.vercel.app) · Cal Hacks 13.0 winner
Checks a photo of a California hospital bill against the hospital's own published prices and California charity-care law, then drafts letters the patient approves. Solo project; won the Apify Best Actor award and the Convex sponsor prize.

- [Public Apify Actor](https://apify.com/enterprising_arboretum_iq2/hospital-price-and-charity-finder) (Python) that finds and streams hospital price files. Line-level price checks work for 340 of 470 California hospitals.
- [Statewide audit](https://recount-nu.vercel.app/audit) of the charity-care policies of all 470 hospitals listed by HCAI, flagging policies that conflict with state law, with the quote.
- Eval set of synthetic bills priced from real price files: 181 of 181 lines read correctly on 30 bills (synthetic data, not patient bills).

`TypeScript` `Next.js` `Convex` `Python` `Claude API` `Expo`

### [Highwater](https://github.com/VolodymyrLinuxovich/highwater) · [live](https://highwater-tau.vercel.app) · B@BHacks 2.0
Prices every Gemini daily high-temperature contract across 49 US cities by conditioning 82 GFS and ECMWF ensemble members on the temperatures already observed that day (4,000-draw Monte Carlo).

- Replayed on **978 settled markets**: Brier score 0.306 at 6 pm vs 0.477 for the forecast alone. All 2,345 contracts the observed floor ruled out settled NO.
- These are historical replays and a paper order book, not live trading results.

`TypeScript` `Next.js` `Monte Carlo` `x402`

### [LargeVCModel](https://github.com/VolodymyrLinuxovich/largevcmodel)
Research and relationship tool for investors: search Gmail, Contacts and Calendar history, score companies against a saved thesis, and draft outreach that cites its evidence.

- Google OAuth with AES-GCM encrypted tokens. Every query is scoped to the signed-in user, and nothing is sent without a second explicit confirmation.
- Python FastAPI retrieval service on PostgreSQL and pgvector (HNSW cosine search).
- CI runs the TypeScript and Python suites, including PostgreSQL integration tests and tenant-isolation tests.

`TypeScript` `Next.js` `PostgreSQL` `Prisma` `FastAPI` `pgvector`

**Also:** [Schmidt DSE climate pipeline](https://github.com/VolodymyrLinuxovich/climate_data_pipeline) (Berkeley research: xarray and Dask over downscaled CMIP6 for National Park Service maps) · [Waves](https://github.com/VolodymyrLinuxovich/mistral-waves) (heatwave risk map for Ukraine) · [SwarmDAQ](https://github.com/VolodymyrLinuxovich/swarmdaq) (task market for AI agents, WeaveHacks 2025)

---

## Open source

**57 merged pull requests in 12 external repositories** (as of Oct 27, 2026; PRs to my own repos not counted). The ones below did the most engineering work.

**[All the Places](https://github.com/alltheplaces/alltheplaces)** · 41 merged: 39 new spiders and 2 fixes. The 39 spiders reported 239,973 locations in their test crawls (crawl output, not deduplicated or checked as currently open).

- [Royal Mail](https://github.com/alltheplaces/alltheplaces/pull/19405): the API returns only the 60 nearest places, so the spider splits the UK into quadrants until each box is fully covered. 136,489 places. On a central London check it found the same 923 places as a dense grid with 78 requests instead of 390.
- [Japan Post fix](https://github.com/alltheplaces/alltheplaces/pull/19633): post box numbers repeat across regions, so the duplicate filter was dropping about 73,000 real boxes. Also fixed paging in the shared e-map crawler.
- [NTT public telephones](https://github.com/alltheplaces/alltheplaces/pull/19475): 69,357 payphones. Converted coordinates from the old Tokyo datum to WGS 84; median distance to matching OpenStreetMap phones fell from 112 m to 8 m.
- [Packeta](https://github.com/alltheplaces/alltheplaces/pull/19418): 15,929 pickup points in 5 countries, splitting geohash cells when a response hits the 100-result cap.
- [Coles fix](https://github.com/alltheplaces/alltheplaces/pull/19272): recursive search in dense areas, where the API caps results at 15. Inner Melbourne went from 58 to 146 stores, matching the exhaustive count.

**[OWASP Java Encoder](https://github.com/OWASP/owasp-java-encoder)** · 5 merged

- [`Encode.forJson`](https://github.com/OWASP/owasp-java-encoder/pull/151): a new public API for JSON string contexts (RFC 8259), with JSP and Jakarta tags. 1,865 added lines across 29 files.
- [JavaScript encoders](https://github.com/OWASP/owasp-java-encoder/pull/166) now escape DEL and C1 controls. [OSGi import ranges](https://github.com/OWASP/owasp-java-encoder/pull/174) derived from each bundle's bytecode so adapters cannot load against an older core. Plus [XML 1.1 tags](https://github.com/OWASP/owasp-java-encoder/pull/168) and a [deprecation fix](https://github.com/OWASP/owasp-java-encoder/pull/170).

**Other merged work**

- [GeoPandas #3871](https://github.com/geopandas/geopandas/pull/3871): `explode` index dtype now int64 on every platform, fixing failures on 32-bit builds.
- [rioxarray #940](https://github.com/vylor/rioxarray/pull/940): clear error for 2D spatial coordinates and a fix for `rio.shape`.
- [NVIDIA NeMo Curator #2477](https://github.com/NVIDIA-NeMo/Curator/pull/2477): boilerplate removal now handles runs at both the top and bottom of a document.
- [Kigali Sim #867](https://github.com/SchmidtDSE/kigali-sim/pull/867): operation types for the program validator.
- Smaller fixes and docs: [GeoPandas](https://github.com/geopandas/geopandas/pull/3869), [OWASP API Security Testing Framework](https://github.com/OWASP/www-project-api-security-testing-framework/pull/137), [OWASP CVE Lite CLI](https://github.com/OWASP/cve-lite-cli/pull/1203), [Dependency-Track](https://github.com/DependencyTrack/frontend/pull/1917), [PySAL mgwr](https://github.com/pysal/mgwr/pull/173), [PySAL segregation](https://github.com/pysal/segregation/pull/301), [Numerai](https://github.com/numerai/example-scripts/pull/196).

---

## Awards and research

- **[RISE Global Winner](https://www.risefortheworld.org/global-winners/)**, 2024. Schmidt Futures and Rhodes Trust.
- **[ISEF King Abdulaziz and Mawhiba Special Award](https://isef.net/project/math037-uavs-in-ground-combat-stochastic-modelling)**, 2024, for TacticSquare, a UAV combat simulator (Monte Carlo, stochastic Lanchester models, RL route planning). [Science News Explores coverage](https://www.snexplores.org/article/regeneron-isef-2024-ukraine-battle-simulator-ground-attacks).
- **[INFOMATRIX Platinum Medal](https://kman.kyiv.ua/ua/Final-Mizhnarodnoho-konkursu-INFOMATRIX-2024)**, 2024, for TacticSquare. Piloted with 10 divisions in Ukraine and [raised $50,000](https://tumo.ai/teens/report). Code not public.
- **[GENIUS Olympiad Gold](https://man.gov.ua/about/news/vihovanci-man-peremogli-na-genius-olympiad)**, Environmental Science, 2024, for FireImpactology, a wildfire air-quality and health model. Code not public.
- **[NASA Space Apps Challenge](https://www.spaceappschallenge.org/2023/find-a-team/fire-impactology/?tab=project)**, 2nd in Ukraine, 2023, for FireImpactology.
- **All-Ukrainian Programming Cup**, 3rd place and Jane Street Award, 2025.
- **Hackathons:** Agentic AI SF Hackathon, 1st place ([FireScout](https://github.com/VolodymyrLinuxovich/firescout), wildfire smoke alert agent). Cal Hacks 13.0, Apify Best Actor and Convex prize (Recount). B@BHacks 2.0, Gemini award (Highwater).
- **Research:** climate-risk analysis at Berkeley's [Eric and Wendy Schmidt Center for Data Science & Environment](https://dse.berkeley.edu/).
- **Kaggle:** [rank 7 of 566](https://www.kaggle.com/competitions/store-sales-time-series-forecasting/leaderboard) in Store Sales forecasting (Oct 2026, rolling leaderboard) and [public notebooks](https://www.kaggle.com/volodymyrborysenko/code).
