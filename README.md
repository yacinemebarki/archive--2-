# 🏆 Premier League Rank Predictor

This project uses a machine learning model to **predict the final rank** of Premier League teams based on:

- 📊 Previous season rank and points
- 💸 Transfer spending in the summer
- 🔢 Points in the current season (optional)

---

## 📁 Dataset

The dataset includes the following columns:

| Column Name        | Description                             |
|--------------------|-----------------------------------------|
| `Club`             | Name of the football team               |
| `Year`             | Season year                             |
| `Previous`         | Previous season rank                    |
| `Previous_point`   | Points earned in previous season        |
| `Pts`              | Current season points (optional input)  |
| `Transfer`         | Money spent in summer transfer window   |
| `#`                | Final league rank (target variable)     |

✔️ Data is cleaned and sorted in descending order by year.

---

## 🤖 Model Details

- **Algorithm**: `GradientBoosting`
- **Input Features**:
  - `Previous`
  - `Previous_point`
  - `Transfer`
  - `Pts` 

### 📈 Evaluation Metrics

| Metric    | Value  |
|-----------|--------|
| MAE       | 3.81   |
| MSE       | 24.31  |
| R² Score  | 0.10   |

> The model can predict a team’s rank within ~3.8 places on average.

---

## 🧪 Example Prediction

```python
input = pd.DataFrame({
    "Previous": [3],
    "Previous_point": [69],
    "Transfer": [120_000_000],
    "Pts": [85]
})

prediction = model.predict(input)
print(f"Predicted Rank: {round(prediction[0], 1)}")

