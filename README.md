# fifamarketvalue-ml
Feature engineering on FIFA dataset with extensive text processing of player attributes, traits, and positions.

## 🔍 Project Highlights

- Cleaned and structured noisy columns like `Position`, `Work Rate`, and `Preferred Foot`
- Extracted features from natural language fields (e.g. player names, traits, special attributes)
- Parsed composite fields like `Height`, `Weight`, and `Value` into numerical formats
- Generated new custom features: skill keywords, two-footedness, position groups, etc.
- Created intermediate transformed datasets for ML modeling

---

## 📊 Libraries Used

| Purpose            | Libraries                          |
|--------------------|-------------------------------------|
| Data Handling      | Pandas, NumPy                      |
| Text Processing    | Regex, string ops, `apply()`       |
| Visualization      | Matplotlib, Seaborn                |
| Environment        | Jupyter Notebook                   |

---

## 📁 Folder Structure

```bash
fifa-feature-engineering/
├── data/                    # Original FIFA CSVs
├── notebooks/               # Main notebook(s)
│   └── feature_engineering.ipynb
├── outputs/                 # Cleaned/transformed datasets
├── requirements.txt
└── README.md
