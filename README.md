# nba-shot-prediction
Predicting NBA shot success using Kaggle dataset
This project predicts whether an NBA shot will be **made or missed** based on historical play-by-play shot data.

## Dataset
- Source: [Kaggle – NBA Shots](https://www.kaggle.com/datasets/mexwell/nba-shots)
- Seasons: 2004–2024
- ~120k rows of shot attempts

## Project Workflow
1. **Data Loading** – merge multiple season CSVs
2. **Exploratory Data Analysis (EDA)** – visualize shot distances, zones, and make rates
3. **Feature Engineering** – add contextual features (`clutch`, `is_home`, `secs_remaining`, coordinates, etc.)
4. **Modeling**
   - Logistic Regression (baseline)
   - Random Forest (nonlinear)
5. **Evaluation** – accuracy, ROC-AUC, PR-AUC, confusion matrix, ROC curves
6. **Interpretability** – feature coefficients (LogReg) and feature importances (RF)
7. **Visualization** – spatial heatmap of make rate by court location
8. **Model Saving** – trained models are stored with `joblib`

## Results
- **Accuracy / ROC-AUC:** ~0.63 for both Logistic Regression and Random Forest  
- **Baseline (majority class):** ~0.54  
- ✅ Models learned useful signal (distance, zone, shot type)  
- ⚠️ Still limited without defender / player historical context

## Future Work
- Add **player-level shooting tendencies**
- Include **defender proximity & contest data** (if available)
- Try **XGBoost / LightGBM** for boosted performance
- Deploy as a **Streamlit / Flask app**

---

### How to run
```bash
# clone repo
git clone https://github.com/your-username/nba-shot-prediction.git
cd nba-shot-prediction

# install requirements
pip install -r requirements.txt

# open notebook
jupyter notebook NBA_Shot_Prediction.ipynb
