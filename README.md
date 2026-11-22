# Student Performance Prediction Using Machine Learning

Predicting whether a secondary-school student will pass the final exam, based on demographic, family,
social and study-related features.

## Dataset

[Student Performance Data Set](https://archive.ics.uci.edu/dataset/320/student+performance) (UCI Machine Learning Repository).
Records of students from two Portuguese schools for two subjects: Mathematics and Portuguese language.
This stage uses the Mathematics file (395 students, 33 columns).

- **Target:** `pass` = 1 if the final grade `G3 >= 10` (scale 0-20), otherwise 0
- **Features:** age, sex, parents' education and jobs, study time, past failures, absences, alcohol use, free time, internet access, and more

## Project Structure

```
student-performance-prediction/
├── data/            # dataset (downloaded automatically by the notebook)
├── notebooks/
│   └── student_performance_eda_baseline.ipynb
├── requirements.txt
└── README.md
```

## What is done (Stage 1)

- [x] Load the dataset
- [x] Inspect structure, data types and missing values
- [x] Exploratory data analysis with 4 plots
  - Distribution of final grades
  - Correlation heatmap
  - Pass rate by past failures and study time
  - G1 vs. G3 scatter plot
- [x] Baseline model: Logistic Regression (with and without `G1`/`G2`)

## How to run

```bash
git clone https://github.com/kurmand2000-dev/student-performance-prediction.git
cd student-performance-prediction
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook notebooks/student_performance_eda_baseline.ipynb
```

The notebook downloads the dataset automatically. In Google Colab, upload the notebook and run all cells.

## Results

Fill in after running the notebook:

| Model | Features | Accuracy |
|---|---|---|
| Logistic Regression (A) | All, including G1 and G2 | 0.886 |
| Logistic Regression (B) | Without G1 and G2 | 0.658 |

## Next Steps

- Decision Tree, Random Forest, Gradient Boosting
- Cross-validation and hyperparameter tuning
- Regression on the raw `G3` grade
- Feature importance with SHAP

## Tech Stack

Python, pandas, NumPy, Matplotlib, Seaborn, scikit-learn, Jupyter

## License

MIT