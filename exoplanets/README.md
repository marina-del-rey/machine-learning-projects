# Exoplanet Detection Using Machine Learning

This project uses machine learning to detect exoplanets from flux measurements collected by the Kepler Space Telescope. The model identifies characteristic patterns in brightness variations that indicate the potential presence of orbiting planets. This detection method, known as the **transit method**, works by monitoring a star's brightness over time and identifying periodic dips taht occur when an exoplanet passes in front of its host star from our perspective, temporarily blocking a small portion of the star's light. These dips in brightness create patterns that the model learns to detect.

## Datset

The dataset used for this project contained labelled time series data, and can be found on [Kaggle](https://www.kaggle.com/datasets/keplersmachines/kepler-labelled-time-series-data/data):

- Flux measurements for 5087 training stars and 570 test stars
- Binary classification: has exoplanet (class 2) vs. no exoplanet (class 1)

## Approach

1. **Data exploration**: Analyzed flux patterns between stars with/without exoplanets
2. **Feature engineering**: Extracted time series features using tsfresh
3. **Modeling**: Implemented Gradient Boosting and SVM classifiers with hyperparameter tuning
4. **Evaluation**: Validated performance using cross-validation and ROC AUC metrics

## Installation & setup

```bash
# create a virtual environment
python -m venv venv

# activate the virtual environment
source venv/bin/activate #linux/macOS
venv\Scripts\activate # windows

# install requirements
pip install -r requirements.txt

# run the notebook
jupyter notebook notebook.ipynb
```

## Notes

- Computational requirements: The feature extraction process using tsfresh is computationally intensive, requiring significant processing power and memory. Consider using cached features for repeated analyses.
- Class imbalance: The dataset is highly imbalanced, with a significantly larger number of stars without exoplanets than stars with exoplanets. This imbalance reflects the rarity of exoplanet detections.
