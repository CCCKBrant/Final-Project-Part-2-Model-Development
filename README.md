# Final-Project-Part-2-Model-Development

# MLB Pitch Outcome Predictor

#### This project predicts whether a pitch will be a hit or an out based on key metrics.

---

## Dataset

### Source - MLB Pitch Data from the 2019 Season
### Link - https://www.kaggle.com/datasets/pschale/mlb-pitch-data-20152018?resource=download

### Description:
- 728,790 Different Pitches Recorded
- 50 Features 
- Target Variable is 'event' later simplified into hit/out
- Class Distribution 77% Outs and 23% Hits (imbalanced)

### Setup:
- Pitch metrics (start_speed, end_speed, pfx_x, pfx_z)
- Pitch location (px, pz)
- Game context (outs, balls, strikes, runners on base)
- Engineered features (total movement, speed-movement score, strike zone indicator)

### Installation
1. Clone Repository:
    ```bash
git clone https://github.com/CCCKBrant/Final-Project-Part-2-Model-Development.git
cd Final-Project-Part-2-Model-Development

2. Install Required Packages (Pandas, Matplotlib, Seaborn, Scikit-Learn, Numpy)
pip install pandas numpy matplotlib seaborn scikit-learn

### Project Structure:
Final-Project-Part-2-Model-Development/
├── README.md
├── final_project_draft.ipynb
├── data/
│   └── raw/
│       ├── 2019_pitches.csv
│       ├── 2019_games.csv
│       └── 2019_atbats.csv

## Results:

### Models Implemented:
- Random Forest Classifier
- Neural Network

### Key Findings:
- Random Forest performed the best, but was only accurately able to predict outcome by 53%
- Neural Network had an accuracy of 77%, but only because it predicted out everytime, due to the imbalance of data.
- Random Forest is what I will use for the final model, because it did learn on the data set. I will be able to improve with better and more features.