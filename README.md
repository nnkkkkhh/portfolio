[← About me](https://github.com/nnkkkkhh) · **English** · [Русский](portfolio.ru.md)

# Portfolio

A catalogue of my data projects. Each project lives in its own repository
with a detailed README: the problem, the data, the methods, the result.

**Contact:** [nikitakharkvv@gmail.com](mailto:nikitakharkvv@gmail.com) · [Telegram](https://t.me/nnkkkkhh)

## 📚 Table of Contents
- [Data Engineering](#data-engineering)
- [SQL](#sql)
- [Python](#python)
- [Web](#web)
- [BI](#bi)
- [AI](#ai)
- [Machine Learning](#machine-learning)

***

# Data Engineering

| Project | Skills & Focus | Project Description | Stack |
|---|---|---|---|
| ✈️ [US Flight Delays](https://github.com/nnkkkkhh/pastoiETL) | ETL pipeline design, star-schema modelling, workflow orchestration, data-quality testing | Built an end-to-end ETL pipeline for U.S. Bureau of Transportation Statistics airline delay data (171K rows, 62.1M flights, Aug 2013 – Aug 2023). The pipeline extracts raw CSV data, cleans and transforms it with pandas, models it into a star schema in PostgreSQL, and materialises an analytical mart answering questions on delay causes by carrier, airport and season. Orchestrated with Airflow (LocalExecutor), fully containerised with Docker Compose, and covered by data-quality checks and pytest tests running inside the container. | Python, pandas, PostgreSQL, Apache Airflow, Docker Compose, pytest |

***

# SQL

| Project | Skills & Focus | Project Description | Stack |
|---|---|---|---|
| 🐱 [Cookie Cats A/B Test](https://github.com/nnkkkkhh/cookie-cats-ab-test) | A/B testing, statistical analysis, SRM checks, bootstrap, segment analysis | Analysis of a mobile-game A/B test (90,189 players) testing whether moving the first gate from level 30 to level 40 improves retention. Written in SQL — PostgreSQL and plpgsql, with Python only for loading the CSV. Includes data quality checks, a Sample Ratio Mismatch test, z-tests with confidence intervals, a bootstrap written in plpgsql, and segment analysis. The split failed the SRM check, and day-7 retention came out 0.82 pp lower in the test group, so the change is not recommended for rollout. | PostgreSQL, plpgsql, Python |

***

# Python

| Project | Skills & Focus | Project Description | Stack |
|---|---|---|---|
| 👗 [Zara Store Catalog EDA](https://github.com/nnkkkkhh/zara-eda) | EDA, statistical analysis, permutation testing, data-quality critique | Exploratory analysis of a Zara US store catalog (252 products, Feb 2024), answering business questions on which category drives revenue, whether product placement in the store and promotions affect sales, and whether price is related to sales volume. Jackets generate ~68% of revenue and take 9 of the top 10 spots, with revenue concentrated in the premium price segment. Placement, promotion, seasonality and price showed no relationship with sales volume — all differences fell within random variation under a permutation test — and I document why the `Sales Volume` column appears to be filled with random numbers. | Python, pandas, matplotlib, seaborn |

***

# Web

| Project | Skills & Focus | Project Description | Stack |
|---|---|---|---|
| 🦷 [DentalCRM](https://github.com/ijptbbt/c-avto) | Full-stack development, REST API design, JWT auth, relational data modelling, containerisation | Built a monorepo CRM for a dental clinic: an Express 5 + Prisma + PostgreSQL REST API with JWT auth and zod request validation, and a React 18 + Vite SPA with protected routes. Implemented the patients, appointments, services, analytics and profile modules on a shared TanStack Query API layer; database, migrations and seeds run in Docker Compose. | TypeScript, Node.js, Express 5, Prisma, PostgreSQL, Docker Compose, React 18, Vite, Tailwind CSS 4, Zustand, TanStack Query |
| 🛡️ [Insurance.sol](https://github.com/nnkkkkhh/insurance.sol) | LLM application design, prompt engineering, SPA state management, UX for guided learning | Interactive AI tutor that teaches insurance literacy through guided real-life scenarios (broken phone, medical claim, etc.). Each scenario is a multi-step Socratic dialogue: the user answers in plain language and an LLM tutor evaluates the reasoning, explains the underlying insurance mechanics (deductible, coverage limits, exclusions) and closes with a personalised summary of what was learned. Built as a SPA with a typed scenario engine, Zustand state store and a pluggable AI provider layer. | React 19, TypeScript, Vite, Tailwind CSS, Zustand, Framer Motion, OpenRouter LLM API |

***

# BI

| Project | Skills & Focus | Project Description | Stack |
|---|---|---|---|
| 💰 [Forbes Billionaires 1997–2024](https://github.com/nnkkkkhh/real-time-billionaires) | Data cleaning & profiling, star-schema modelling, DAX measures, wealth dynamics, list turnover, industry & geography shifts, concentration | Analysed 34,511 Forbes list records across 24 years. Profiled and fixed 8 data defects in Power Query (text-encoded net worth, 58 raw industries mapped to 14, duplicate country names, a full duplicate row), reconstructed missing birth dates to build a reliable composite person key, and modelled the data into a star schema with a full DAX layer covering turnover, retention, top-N concentration, tenure, CAGR and inflation-adjusted values. Key finding: the 11.7× nominal growth in total wealth is only 6.6× in 2024 dollars, and 105 people stayed on the list all 24 years — retention runs 84–94% in calm years. Dashboard: *in progress*. | Power Query (M), DAX, Power BI Desktop, FRED CPI |

***

# AI

| Project | Skills & Focus | Project Description | Stack |
|---|---|---|---|
| 🤖 [LLM Telegram Bot](https://github.com/nnkkkkhh/second-mcp) | Conversational AI, backend architecture, session/context management, rate limiting, structured logging | A Telegram chatbot built on grammY that forwards user messages to an LLM through the OpenRouter API and streams answers back in chat. Keeps per-user conversation history in file-backed sessions (with a `/reset` command and a rolling 20-message context window), protects the API budget with a rate limiter (3 messages / 10s), and writes structured JSONL request logs for later analysis. Written in strict TypeScript with a modular handler/service layout and bundled for production with esbuild. | TypeScript, grammY, OpenAI SDK, OpenRouter, esbuild, tsx |

***

# Machine Learning

| Project | Skills & Focus | Project Description | Stack |
|---|---|---|---|
| 📉 [Telco Customer Churn](https://github.com/nnkkkkhh/telco-churn) | Classification, EDA, feature engineering, threshold selection by cost, business impact analysis | End-to-end churn analysis on the IBM Telco dataset (7,043 customers, 21 features, 26.5% churn rate). Cleaned and feature-engineered the raw data, quantified churn drivers with effect sizes and logistic-regression odds ratios (2-year contract OR 0.26, fiber optic OR 3.00), and benchmarked logistic regression (ROC-AUC 0.846) against gradient boosting. Rather than optimising F1, I selected the classification threshold from the asymmetric cost of a missed churner vs. a wasted retention offer, and sized the resulting campaign's economic effect. Documented the methodological limits explicitly — class weighting breaks probability calibration (ranking stays valid), and the contract effect is self-selection, not causation, so uplift needs an A/B test. | pandas, NumPy, SciPy, scikit-learn, matplotlib |
