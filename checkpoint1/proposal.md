# Predicting NYC Property Sale Prices

## Team

- Justin Martinez — github: justinmartinez4040
- Matthew Cohen — github: mattcohen33
- Sam Landa — github: samlanda12
- Mitchell Austin — github: mhaustin
- Gianluca Zurlo (POC) — github: gzurlo

## Introduction

We want to build a model that predicts the sale price of a property in New York City based on features like size, location, building type, and age.

Most public tools compare average prices across neighborhoods, which is descriptive but doesn't predict anything for a specific property. We're framing this as a regression problem: training a model on past sales so it can estimate the price of a property it hasn't seen before.

If successful, this gives buyers, sellers, and agents a fast, data-backed price estimate instead of relying only on broker intuition or outdated comparables.

## Literature Review

Automated home value estimation already exists commercially — tools like Zillow's "Zestimate" use large models trained on public sales records to generate price estimates[^1]. Traditional appraisal instead relies on manually selected "comparable sales," a slower and more subjective process. A key limitation of commercial tools like Zestimate is that they are proprietary — the exact features and weighting behind the number aren't public, so users can't verify or understand the estimate.

Academic research supports moving beyond simple linear models for this task. Housing price prediction methods are commonly grouped into classical linear regression, hedonic pricing models, and more recent machine learning approaches, with evidence that ML-based methods tend to outperform simpler statistical baselines for forecasting tasks[^2]. This supports our plan to compare a linear regression baseline against more flexible models like random forests.

**Stakeholders:**
- **Home buyers** — need an independent, fair estimate of a property's worth before making an offer.
- **Sellers and real estate agents** — need to set a realistic, competitive asking price.
- **City planners and tax assessors** — need consistent, explainable valuations across boroughs for planning and assessment purposes.

## Data and Methods

### Data

We're using the NYC Department of Finance's **Rolling Sales** dataset, published separately for each borough (Bronx, Brooklyn, Manhattan, Queens, Staten Island), covering all sales from September 2025 through August 2026. Combined, this gives us roughly **82,000 property sale records** across the five files.

Each record has 21 columns, including:
- Location: borough, neighborhood, zip code, block/lot
- Property features: building class, residential/commercial units, land and gross square footage, year built
- Sale details: sale price (our target variable) and sale date

This is official city government data (NYC Department of Finance property tax roll data), so it's a reliable, authoritative source. It does not come with a separate data dictionary file, but column meanings are documented on the city's Rolling Sales webpage, and the files include notes on how building class and neighborhood are assigned.

### Methods

We'll clean the data first — handling missing or zero sale prices (some records reflect non-arm's-length transactions like family transfers, which we'll need to filter out), encoding categorical variables like borough and building class, and addressing outliers in price and square footage.

We'll start with linear regression as a baseline, then compare against more flexible models like random forests, which can better capture non-linear relationships between features like location and price. We'll evaluate using RMSE and R² on a held-out test set, checking that error is reasonably consistent across boroughs rather than skewed toward high-value areas like Manhattan.

## Project Plan

| Period | Activity | Milestone |
|---|---|---|
| 9/22 – 9/29 | Combine and clean the five borough datasets; initial EDA | Cleaned combined dataset; key data quality issues identified |
| 9/29 – 10/6 | Feature engineering; baseline linear regression model | Working baseline model with initial performance benchmark |
| 10/6 – 10/20 | Try random forest and other candidate models; compare performance | Best-performing candidate model selected |
| 10/20 – 10/28 | Refine chosen model; prepare Checkpoint 2 submission | Checkpoint 2 ready |
| 10/28 – 11/18 | Further tuning; error analysis by borough | Model performance validated across boroughs |
| 11/18 – 12/7 | Finalize results; build final presentation | Final presentation ready |
| 12/7 – 12/15 | Write up final report | Final report submitted |

## Risks

**Data quality:** Some sale prices are $0 or very low, reflecting transfers rather than real sales (e.g., between family members). Mitigation: filter these out based on sale price thresholds and cross-check against building class.

**Missing features:** The dataset doesn't include some factors that affect price, like interior condition or renovation history. Mitigation: acknowledge this limitation and focus on what's predictable from available features.

**Model underperformance:** A more complex model might not beat the baseline. Mitigation: keep the linear regression baseline as a fallback and report honestly if it remains the best-performing option.

[^1]: Zillow Group, "What is a Zestimate?", Zillow Help Center.
[^2]: "A hybrid machine learning framework for forecasting house price," ScienceDirect, 2023.
