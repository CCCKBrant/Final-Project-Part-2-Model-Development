# MLB Pitch Outcome Predictor

#### This project predicts whether a pitch will result in a hit or an out using machine learning and MLB pitch data.

---

## Dataset

### Source
MLB Pitch Data (2019 Season)  
https://www.kaggle.com/datasets/pschale/mlb-pitch-data-20152018?resource=download

### Description
- 728,790 pitches recorded  
- ~50 original features  
- Target variable: `event` → simplified to **hit vs out**  
- Class distribution: **77% outs, 23% hits (imbalanced)**  

---

## Feature Engineering

To improve model performance, several domain-specific features were created:

- **Pitch movement features**
  - `total_movement`
  - `speed_movement_score`

- **Strike zone feature**
  - `strike_zone_indicator`

- **Game situation features**
  - `outs`
  - `runners_in_scoring_position`
  - `high_pressure` (2 outs + runners in scoring position)

These features help the model better understand both pitch characteristics and game context.

---

## Installation

1. Clone repository:

```bash
git clone https://github.com/CCCKBrant/Final-Project-Part-2-Model-Development.git
cd Final-Project-Part-2-Model-Development
```

2. Install Libraries/Packages:

```
pip install pandas numpy matplotlib seaborn scikit-learn
```
3. Add dataset from kaggle:
 - Download 2019_pitchers.csv
 - Place inside:
    - data/raw/

## Project Structure

Final-Project-Part-2-Model-Development/
├── README.md
├── final_project_draft.ipynb
├── data/
│   └── raw/
│       ├── 2019_pitches.csv
│       ├── 2019_games.csv
│       └── 2019_atbats.csv

## Models Implemented
 - Optimized Random Forest
 - PCA + Random Forest

## Final Results:
| Model | Accuracy | Training Time |
|------|----------|---------------|
| Optimized Random Forest | 59.40% | 843 seconds |
| PCA + Random Forest | 59.45% | 375 seconds |

## Key Insights
 - Pitch Location is the most important factor in determining pitch outcome (hit or out)
 - Pitch Movement is also a strong indicator
 - Pitch Speed w/ Movement is the third contributing factor
 - The model is better at predicting outs than hits, showing hits are harder to predict than outs.

 ## Model Comparison
 - Both models performed about the same, only differentiating by 0.45%.
 - PCA reduced the training time by half
 - Random Forest is more interpretable (feature importance)
 - PCA is more efficient but less interpretable

 ## Final Reccomendation
The PCA + Random Forest model is the best for deployment because it preforms about the same as the optimized model, but reduces training time by hald. This makes it more efficient for real world application.

## Limitations
 - Model accuracy is only 6% better than 50/50 guessing
 - Struggle to predict hits due to data imbalance between hits and outs.
 - Trained on 2019 data, which may not be applicable in modern day baseball
 - Many other factors that aren't included contribute to pitch outcome

## Future Improvements
 - Use recent data
 - Use segmentation models to group by pitcher type
 - Incorporate batter specific features
 - Improve feature engineering for better hit prediction
