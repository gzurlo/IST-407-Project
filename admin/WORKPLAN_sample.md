# WORKPLAN.md

## Active Plan

### Milestone 1: Data Acquisition
- [✅] M1.T1 — Download NYC Open Data crime dataset (Carmen)
- [✅] M1.T2 — Initial exploratory data analysis (Behr)
- [✅] M1.T5 — Identify viable crime types for prediction (Team)

### Milestone 2: Data Preparation
- [✅] M2.T1 — Clean crime data (remove nulls, standardize fields) (Carmen)
- [✅] M2.T2 — Create basic features (hour, day, month) (Behr)
- [✅] M2.T6 — Filter to violent public crimes only (Carmen)
- [✅] M2.T7 — Parse cross-street information from location field (Carmen)

### Milestone 3: Geocoding & Spatial Resolution
- [✅] M3.T1 — Geocode text addresses to coordinates (Abishek)
- [✅] M3.T2 — Acquire NYC census block shapefiles (Abishek)
- [✅] M3.T3 — Map crime coordinates to census blocks (Abishek)
- [🚫] M3.T4 — Interpolate missing locations using crime patterns (Team)
- [✅] M3.T5 — Create spatial adjacency matrix for blocks (Abishek)

### Milestone 4: Modeling Attempts
- [✅] M4.T1 — Train/test split by date (Behr)
- [✅] M4.T2 — Logistic regression baseline (Behr)
- [✅] M4.T3 — Decision tree model (Behr)
- [✅] M4.T5 — Random Forest with hyperparameter tuning (Behr)
- [⏳] M4.T6 — KNN on PCA-reduced block features (Behr)

### Milestone 5: Enhanced Data Integration
- [⏳] M5.T1 — Integrate NOAA weather data (Carmen)
- [⏳] M5.T2 — Add census demographic data (Abishek)
- [ ] M5.T3 — Add economic indicators by block (Carmen)
- [ ] M5.T4 — Get points of interest from OSM (Abishek)
- [ ] M5.T5 — Align all data sources temporally and spatially (Team)
- [ ] M5.T6 — Engineer interaction features (Behr)

### Milestone 6: Advanced Modeling
- [ ] M6.T1 — Implement spatial lag features (Abishek)
- [ ] M6.T2 — Spatial neighborhood aggregation features (Behr)
- [ ] M6.T3 — Temporal aggregation features (Behr)
- [ ] M6.T4 — Ensemble multiple approaches (Team)

### Milestone 7: Evaluation & Visualization
- [ ] M7.T1 — Comprehensive test set evaluation (Team)
- [ ] M7.T2 — Feature importance analysis (Behr)
- [ ] M7.T3 — Interactive map visualization (Carmen)
- [ ] M7.T4 — Final documentation (Team)

---

## Changelog

### 2026-09-23
- (Behr) ⏳ M1.T2 — Crime data has 35 columns, many unclear (CMPLNT_NUM, KY_CD, OFNS_DESC); found data dictionary

### 2026-09-28
- (Behr) ⏳ M2.T2 — Created temporal features, but location is just text ("CORNER OF 42 ST and 8 AVE")

### 2026-09-30
- (Behr) ⏳ M4.T2 — Logistic regression with just temporal features: 0.31 F1 score, basically random

### 2026-10-05
- (Behr) ⏳ M4.T3 — Decision tree no better (0.33 F1), realizing we need spatial information
- (Team) 🆕 M3.T1, M3.T2, M3.T3 — Added entire geocoding milestone (not in original plan!)

### 2026-10-08
- (Team) ❌ M2.T3 — Abandoned "Create crime severity scores" - focusing on occurrence not severity
- (Team) ❌ M2.T4 — Abandoned "Aggregate by precinct" - too coarse for useful predictions

### 2026-10-12
- (Team) ⏳ M1.T5 — Discovered 60+ crime types including "HARRASSMENT 2" and "PETIT LARCENY", need to filter
- (Team) 🔄 M1.T5 — Pivoted to violent public crimes only (assault, robbery, etc.)

### 2026-10-14
- (Abishek) 🚫 M3.T1 — Google Maps API rate limits (2500/day free tier), need alternative

### 2026-10-15
- (Abishek) ⏳ M3.T1 — Switched to NYC GeoClient API, but it's rejecting 30% of addresses

### 2026-10-17
- (Carmen) 🆕 M2.T7 — Added parsing step to extract cross-streets from freeform text
- (Abishek) ⏳ M3.T1 — Combining NYC GeoClient with OSM Nominatim for better coverage

### 2026-10-22
- (Abishek) ⏳ M3.T3 — Some crimes on block boundaries; assigning to nearest centroid
- (Team) ⏳ M3.T4 — Trying spatial interpolation for missing locations using kernel density

### 2026-10-24
- (Team) ❌ M3.T4 — Abandoned interpolation - introduces too much noise, will just exclude 15% missing

### 2026-10-26
- (Behr) ⏳ M4.T5 — Random Forest grid search: n_estimators [100,300,500], max_depth [6,9,12,None]
- (Behr) ⏳ M4.T5 — Best params: n_estimators=300, max_depth=12, but F1 still only 0.42

### 2026-10-27
- (Team) 🆕 M5.* — Added entire "Enhanced Data Integration" milestone - need external features!
- (Abishek) 🆕 M3.T5 — Added spatial adjacency matrix task for future spatial models

### 2026-10-30
- (Carmen) 🚫 M5.T1 — NOAA weather API changed, need to register for new key

### 2026-11-01
- (Carmen) ⏳ M5.T1 — Got NOAA access, but data is by weather station not block, need to map
- (Abishek) ⏳ M5.T2 — Census API returns data by tract, need tract-to-block crosswalk file

### 2026-11-02
- (Behr) ⏳ M4.T6 — Trying KNN on PCA-reduced block features, but sparse data giving weak results
- (Team) 🆕 M6.* — Added "Advanced Modeling" milestone - simple models insufficient

### 2026-11-03
- (Carmen) ⏳ M5.T1 — Found weather station coordinates, using nearest station for each block
- (Abishek) ⏳ M5.T2 — Downloaded Census ACS 5-year estimates: population density, median age, income

### 2026-11-04
- (Team) ❌ M4.T4 — Abandoned KNN baseline (prediction too slow with 50K+ blocks)
- (Behr) 🚫 M4.T6 — KNN/PCA modeling blocked, need more features first before continuing