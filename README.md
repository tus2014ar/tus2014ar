<div align="center">
  <img height="150" src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExaXAxYmJvZ3BmaGs2MWcwMnowMTl3eTQyY2ZnY2RwNXYzcHY1MmN1YyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/LaVp0AyqR5bGsC5Cbm/giphy.gif"/>
</div>

###

<div align="center">
  <a href="https://www.linkedin.com/in/fnu-tushar-945648131/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=LinkedIn&logo=linkedin&label=&color=0077B5&logoColor=white&style=for-the-badge" height="25" alt="LinkedIn"/>
  </a>
   <a href="https://medium.com/@tusharsingh_37238" target="_blank">
    <img src="https://img.shields.io/badge/Medium-12100E?logo=medium&logoColor=white&style=for-the-badge" height="25" alt="Medium"/>
  </a>
  <a href="https://www.youtube.com/@corporateaspirant8965" target="_blank">
  <img src="https://img.shields.io/badge/YouTube-FF0000?logo=youtube&logoColor=white&style=for-the-badge" height="25" alt="Youtube"/>
</a>

<h1 align="center">Hey There 👋 Welcome to My Git </h1>

<h2 align="center">
Data Scientist • Machine Learning Engineer
</h2>

<h3 align="center">
Shipping efficient & scalable data solutions with real-world impact to production
</h3>

###

</div>

<h3 align="left">💡 What I Do</h3>

<ul>
<li>🔭 Graduate Research Assistant in Data Science, building forecasting models and analytics workflows to drive data-informed decision making.</li>
<li>⚙️ Data Science internship applying statistical analysis and AI-driven tooling to production data: automated data quality profiling across 23 tables, quantitative FinOps cost-attribution modeling, and medallion-architecture data models on Databricks.</li>
<li>📚 Strengthening expertise in Python, SQL, Statistics, Machine Learning, and BI dashboards through rigorous coursework and hands-on projects.</li>
<li>⚡ Exploring real-world datasets, developing dashboards and ML prototypes, and leveraging modern AI tools to improve productivity and model development.</li>
</ul>

###

<h3 align="left">🚀 Featured Projects</h3>

<h4 align="left">🤖 Data Science / Machine Learning</h4>

<table>
<tr>
<td width="50%" valign="top">

**[Telecom Churn Intelligence System](https://github.com/tus2014ar/telecom-churn-intelligence-system)** &nbsp; `🚧 In Progress`

End-to-end churn project on the Cell2Cell dataset: find the strongest churn driver across 58 features, validate it causally rather than by correlation, and test a retention intervention in a simulated experiment. Currently in Week 1 of a 7-week core build (EDA and driver ranking); no results yet.

- Effect-size driver ranking (not p-values) across 51K train + 20K holdout rows, cross-validated on IBM Telco
- Causal validation via propensity score matching
- Tuned XGBoost vs. logistic regression baselines with SHAP explainability
- CUPED-based simulated A/B experiment on the validated driver

`Python` `Statsmodels` `XGBoost` `SHAP` `MLflow` `CUPED`

</td>
<td width="50%" valign="top">

**[OA & RA Market Intelligence System](https://github.com/tus2014ar/oa-market-intelligence-system)** &nbsp; `🚧 In Progress`

A monthly-refreshable analytics pipeline on real IQVIA NMTA patient-visit data (7.19M+ visits, 72 months, 160 products) joined to 171 public CMS, CDC, SEC and FDA files, to track a branded injectable's share against generic pain therapies in Osteoarthritis. Profiling, cleaning, ingestion, the warehouse, EDA, feature engineering and modelling are complete; hardening and the serving layer are next.

- **Profiling:** profiled IQVIA NMTA extracts (72 months, 160 products, 50 specialties, 7.19M+ visits) and 171 public files (about 24 GB: Medicare Part B/D, geographic variation, NPPES, ASP prices, Open Payments, SEC filings, CDC PLACES, openFDA) into a documented data dictionary; surfaced a mis-coded prescriber group and a Mar-Jul 2024 volume dip (Zilretta -47%, corticosteroids -25%)
- **Cleaning:** Pandera validation gate, a 160-product treatment taxonomy and 11 quality checks against a stored baseline; problems documented and kept, not silently dropped
- **Ingestion and modelling:** re-runnable Bronze → Silver → Gold star schema (4 dimensions, 2 facts, 149K+ rows) plus a 27-table public-data constellation with 38 reconciliation checks, SHA-256 file audit, golden regression test and atomic publish; ~830 tests in CI
- **EDA:** company net sales rose (+5% in 2023, +6% in 2024) while IQVIA visits fell (-14%, -36%), so the decline cannot be quoted as a market fact; orthopedic surgery and physician assistants are 64% of the net fall; Medicare does not confirm IQVIA's specialty ranking (rank correlation 0.35 vs 0.6 needed)
- **Feature engineering:** built 7 candidate input groups with leakage tests (rewrite the future and today's features must not move), as-of dates for outside data and a feature dictionary; tested them under rules written beforehand (walk-forward, 46-48 test months, paired bootstrap, repeated run identical). Only specialty and market context helps segment share (about 0.06% of log-loss, 42 of 46 months, robust to COVID and the 2024 dip); none beats "same as last month" nationally, so price, sales and promotion do not predict monthly share
- **Modelling, rules first:** forecast the national share, each segment's share and a 30%-decline alert at 1, 3 and 6 months under a plan fixed before any model ran (walk-forward, paired bootstrap, stricter bar for longer horizons); model-level leakage tests, including a deliberately leaky case that must be caught, and a full run repeated for byte-identical output
- **Modelling, national share:** none of three trained models (ridge, two ETS) beats "same as last month" at any horizon (MAE 0.125, 0.180, 0.239 pp), so the baseline serves; the null result is reported as a finding
- **Modelling, segment share:** logistic regression beats the baseline by about 0.44% of log-loss at 1 month (better in all 46 test months) and 0.21% at 3 months, none at 6; forecasts run 5% to 18% too high, and the bias is stated beside every result
- **Modelling, decline alert:** passes its registered test (PR-AUC 0.55 against 0.23 no-skill), but a post-hoc check found one registered baseline had its sign backwards and that most of the gain is regression to the mean, so only a 1-month flag is recommended; results are stored in the warehouse with model cards

`Python` `SQLite` `SQLAlchemy` `Pandera` `pandas` `scikit-learn` `statsmodels` `GitHub Actions`

</td>
</tr>
<tr>
<td width="50%" valign="top">

**[AI Sentinel — Automated AI Compliance Monitoring](https://github.com/tus2014ar/AI-Sentinel---Automated-AI-Compliance-Monitoring-Platform)**

Autonomous compliance agents that detect AI-driven regulatory risk in real time — built for the Penn State Nittany AI Challenge 2026, with fall-monitoring technology as the first live use case.

- 5 detection rules mapped directly to CMS federal regulations (42 CFR §483)
- Hybrid architecture: deterministic rule engine + local LLM explanation layer with a 100%-deterministic fallback
- Every finding SHA-256 audit-logged for compliance traceability

`Python` `Streamlit` `Ollama (local LLM)` `SQLite`

</td>
<td width="50%" valign="top">

**[Resume–JD Matching Using Deep Learning](https://github.com/tus2014ar/Resume-Job-Description-Matching-Using-Deep-Learning)**

3-stage semantic ranking pipeline improving over keyword-based ATS matching: TF-IDF baseline → SBERT semantic embeddings → supervised neural refinement into a calibrated match probability.

- 120 resumes ranked against 2,277 job descriptions across 15 technical roles
- `all-MiniLM-L6-v2` dense embeddings (384-d) for context-aware retrieval

`Python` `PyTorch` `SBERT` `scikit-learn`

</td>
</tr>
<tr>
<td width="50%" valign="top">

**[Worldwide Sentiment Analysis of LLM-related Tweets](https://github.com/tus2014ar/Worldwide-Sentiment-Analysis-of-LLM-related-tweets)**

End-to-end NLP + geospatial pipeline tracking global sentiment toward LLMs across 305K+ tweets, surfacing regional trust signals to support AI policy decisions.

- Location-normalization pipeline cut unresolved geography from 72.8% → 43.85%
- VADER sentiment scoring mapped by region and time

`Python` `NLTK/VADER` `Plotly (geospatial)`

</td>
</tr>
</table>

<h4 align="left">⚙️ Data Engineering</h4>

<table>
<tr>
<td width="50%" valign="top">

**[Databricks Data Quality Framework](https://github.com/tus2014ar/databricks-data-quality-framework)**

Automated data quality monitoring built on Databricks DQX. 211 rule-based checks across 23 production tables, running on a scheduled bronze freshness monitor + gold rule engine.

- Surfaced that **84% of active records** carried at least one data quality issue
- Root-caused a **~39% completeness gap** in a core reporting table
- Built an LLM-assisted rule-authoring step: profiles column-level statistics and drafts candidate rules for human review before promotion
- Built an automated weekly digest routing findings to record owners

`Databricks` `PySpark` `SQL` `Python` `YAML rule engines` `LLM-assisted profiling`

</td>
<td width="50%" valign="top">

**[Databricks Cost Analytics & FinOps Framework](https://github.com/tus2014ar/databricks-cost-analytics)**

FinOps cost-attribution pipeline built on Unity Catalog system tables. Star schema spanning 9 system tables, powering a 6-tab cost governance dashboard.

- Found **85.6% of platform spend** had no identifiable owner
- Identified **~95% of tracked resources** idle 90+ days, still accruing cost
- Caught a **2x measurement error** in an AI-cost methodology before it shipped
- Automated a spend forecast (OLS regression, account + top objects), projecting **$53K–$57K annualized**

`Databricks` `PySpark` `SQL` `Star Schema` `FinOps` `Forecasting`

</td>
</tr>
<tr>
<td width="50%" valign="top">

**[Scholar Swipe — Scholarship Scraper](https://github.com/tus2014ar/Scholar-Swipe-Web-Scraping-Project)**

Automated scraping pipeline that extracts scholarship listings and aggregates them into a centralized PostgreSQL (Supabase) database, with upsert-based dedup and automated summarization.

`Python` `BeautifulSoup4` `PostgreSQL` `Supabase`

</td>
</tr>
</table>

<h4 align="left">📊 Advanced Analytics</h4>

<table>
<tr>
<td width="50%" valign="top">

**[Alzheimer's Market Overview — United States](https://github.com/tus2014ar/Alzheimer-s-Market-Overview---United-States)**

TRx-based pharmaceutical market analysis across brands, physician specialties, and sales channels — built as parallel dashboards in Python and Tableau to directly compare both platforms.

- 202,499-row dataset with brand, specialty, and channel-mix analysis
- Interactive Python Plotly dashboard exported as a standalone, shareable HTML file

`Python` `Pandas` `Plotly` `Tableau`

</td>
<td width="50%" valign="top">

**[Penn State GV Alumni Event Analysis & Forecasting](https://github.com/tus2014ar/Penn-State-GV-Alumni-Event-Performance-Analysis-Forecasting)**

Multi-year (2022–2025) alumni event performance analysis with scenario-based 2026 forecasting, moving event planning from reactive to data-informed decision-making.

- Projected **235 attendees** and **$49/attendee revenue** for 2026 via a blended trend + recency-weighted forecast
- Consolidated 6 disparate Excel sources into a unified KPI model
- 3-scenario (Conservative / Expected / Optimistic) financial forecast for stakeholder budget planning

`Python` `Pandas` `Plotly` `Forecasting`

</td>
</tr>
</table>

###

<h3 align="left">🛠 Languages & Tools</h3>

<div align="left">
  <!-- Programming -->
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" height="40" alt="python" title="Python"/>
  <img width="12"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/r/r-original.svg" height="40" alt="r" title="R"/>
  <img width="12"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" height="40" alt="java" title="Java"/>
  <img width="12"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original-wordmark.svg" height="40" alt="sql" title="SQL / MySQL"/>
  <img width="12"/>

  <!-- Data Engineering -->
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/apachespark/apachespark-original.svg" height="40" alt="pyspark" title="PySpark / Apache Spark"/>
  <img width="12"/>
  <img src="https://upload.wikimedia.org/wikipedia/commons/6/63/Databricks_Logo.png" height="40" alt="databricks" title="Databricks"/>
  <img width="12"/>

  <!-- Data Science & ML -->
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pandas/pandas-original.svg" height="40" alt="pandas" title="pandas"/>
  <img width="12"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/numpy/numpy-original.svg" height="40" alt="numpy" title="NumPy"/>
  <img width="12"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/scikitlearn/scikitlearn-original.svg" height="40" alt="scikit-learn" title="scikit-learn"/>
  <img width="12"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tensorflow/tensorflow-original.svg" height="40" alt="tensorflow" title="TensorFlow"/>
  <img width="12"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pytorch/pytorch-original.svg" height="40" alt="pytorch" title="PyTorch"/>
  <img width="12"/>

  <!-- Visualization -->
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/matplotlib/matplotlib-original.svg" height="40" alt="matplotlib" title="Matplotlib"/>
  <img width="12"/>
  <img src="https://upload.wikimedia.org/wikipedia/commons/c/cf/New_Power_BI_Logo.svg" height="40" alt="powerbi" title="Power BI"/>
  <img width="12"/>
  <img src="https://commons.wikimedia.org/wiki/Special:FilePath/Logo-seaborn.png" height="40" alt="seaborn" title="Seaborn"/>
  <img width="12"/>
  <img src="https://upload.wikimedia.org/wikipedia/commons/4/4b/Tableau_Logo.png" height="40" alt="tableau" title="Tableau"/>
  <img width="12"/>

  <!-- Cloud & Databases -->
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" height="40" alt="aws" title="AWS"/>
  <img width="12"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/azure/azure-original.svg" height="40" alt="azure" title="Azure"/>
  <img width="12"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/oracle/oracle-original.svg" height="40" alt="oracle" title="Oracle"/>
  <img width="12"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" height="40" alt="postgresql" title="PostgreSQL"/>
  <img width="12"/>

  <!-- Dev Tools -->
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" height="40" alt="git" title="Git"/>
  <img width="12"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/githubactions/githubactions-original.svg" height="40" alt="github-actions" title="GitHub Actions"/>
  <img width="12"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jupyter/jupyter-original.svg" height="40" alt="jupyter" title="Jupyter"/>
</div>

<br/>

<h3 align="left">🤖 AI Tools</h3>

<div align="left">
  <img src="https://img.shields.io/badge/ChatGPT-00A67E?style=for-the-badge&logo=openai&logoColor=white" height="28" alt="chatgpt" title="ChatGPT"/>
  <img width="8"/>
  <img src="https://img.shields.io/badge/GitHub%20Copilot-000000?style=for-the-badge&logo=github&logoColor=white" height="28" alt="copilot" title="GitHub Copilot"/>
  <img width="8"/>
  <img src="https://img.shields.io/badge/Claude%20Code-5A67D8?style=for-the-badge&logo=anthropic&logoColor=white" height="28" alt="claude-code" title="Claude Code"/>
  <img width="8"/>
  <img src="https://img.shields.io/badge/Claude%20Cowork-5A67D8?style=for-the-badge&logo=anthropic&logoColor=white" height="28" alt="claude-cowork" title="Claude Cowork"/>
  <img width="8"/>
  <img src="https://img.shields.io/badge/Claude%20Skills-5A67D8?style=for-the-badge&logo=anthropic&logoColor=white" height="28" alt="claude-skills" title="Claude Skills"/>
  <img width="8"/>
  <img src="https://img.shields.io/badge/Claude%20Projects-5A67D8?style=for-the-badge&logo=anthropic&logoColor=white" height="28" alt="claude-projects" title="Claude Projects"/>
  <img width="8"/>
  <img src="https://img.shields.io/badge/Claude%20MCP-5A67D8?style=for-the-badge&logo=anthropic&logoColor=white" height="28" alt="claude-mcp" title="Claude MCP"/>
  <img width="8"/>
  <img src="https://img.shields.io/badge/Perplexity-0A0A0A?style=for-the-badge&logo=perplexity&logoColor=white" height="28" alt="perplexity" title="Perplexity"/>
  <img width="8"/>
  <img src="https://img.shields.io/badge/Cursor%20IDE-111827?style=for-the-badge&logo=visualstudiocode&logoColor=white" height="28" alt="cursor" title="Cursor IDE"/>
  <img width="8"/>
  <img src="https://img.shields.io/badge/Antigravity%20IDE-111827?style=for-the-badge&logo=google&logoColor=white" alt="Antigravity IDE badge" title="Antigravity IDE" height="28">
  <img width="8"/>
  <img src="https://img.shields.io/badge/Julius%20AI-111827?style=for-the-badge&logo=openai&logoColor=white" height="28" alt="julius-ai" title="Julius AI"/>
  <img width="8"/>
  <img src="https://img.shields.io/badge/Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white" height="28" alt="ollama" title="Ollama (local LLM)"/>
  <img width="8"/>
  <img src="https://img.shields.io/badge/Google%20Gemini-8E75B2?style=for-the-badge&logo=googlegemini&logoColor=white" height="28" alt="gemini" title="Google Gemini"/>
</div>

<h3 align="left">🔥   My Stats :</h3>

###
<div align="center">
<img src="https://github-readme-stats-woad-sigma-44.vercel.app/api?username=tus2014ar&show_icons=true&theme=dark" />
</div>

