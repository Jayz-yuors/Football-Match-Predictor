# ⚽ Football Match Predictor (ML-Based League Simulation)

An end-to-end **machine learning system** that predicts football match outcomes and simulates **live league tables** based on upcoming matchdays.

The project combines:
- Historical match data
- Team & player-level features
- League table dynamics
- Trained XGBoost models per league
- Live fixtures and table updates

It supports **multiple European leagues**:
- Premier League (PL)
- La Liga (PD)
- Serie A (SA)
- Bundesliga (BL1)
- Ligue 1 (FL1)

---

## 🚀 Project Overview

This project predicts the probabilities of:
- Home Win
- Draw
- Away Win

for upcoming fixtures, and then **simulates the entire matchday** to show how the **league table would change** if those matches were played.

### Key Highlights
- League-specific ML models
- Matchday-based simulation (3–4 day window)
- Automatically updated league tables
- Clean CLI workflow
- Reusable datasets for further research

---

## 📂 Core Datasets (`data_exports/`)

All **processed datasets** are already provided so users can:
- Train models immediately
- Build their own models
- Experiment with features

### 1️⃣ `matches_unified.csv`
**Source**:
- Kaggle (historical football datasets)
- football-data.org API

**Description**:
- Match-level historical data
- Home & away teams
- Scores
- Match dates
- Competition codes

**Why important?**
- Primary source for learning match outcomes
- Used to create training labels (`home / draw / away`)

---

### 2️⃣ `player_data.csv`
**Source**:
- Understat
- Kaggle player datasets

**Description**:
- Player-level performance data
- Goals, xG, assists, minutes played

**Why important?**
- Used to enrich team strength
- Helps compute attacking & defensive power

---

### 3️⃣ `fixtures_current_season.csv`
**Source**:
- football-data.org API

**Description**:
- Upcoming fixtures
- Match dates
- Match status (SCHEDULED / TIMED / FINISHED)

**Why important?**
- Drives live predictions
- Enables matchday simulation logic

---

### 4️⃣ `team_player_features.csv`
**Source**:
- Aggregated from Understat + match history

**Description**:
- Team-level features derived from players
- Attack strength
- Defense stability
- Form metrics

**Why important?**
- Core feature set used by ML models
- Improves prediction realism

---

> **⚠️ IMPORTANT**  
> **You can use these datasets (`data_exports`) to train your own models or experiment with different ML algorithms.**

---

## 🧠 Feature Engineering Pipeline

Features are generated using:
- League table position
- Goal difference
- Team form
- Head-to-head trends
- Team/player strength indicators

All feature construction is centralized in:
