
# 🏆 Premier League Rank Predictor

<!-- Badges -->
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/release/python-390/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange.svg)](https://scikit-learn.org/)

This project uses a machine learning model to **predict the final rank** of Premier League teams based on:

- 📊 Previous season rank and points
- 💸 Transfer spending in the summer
- 🔢 Points in the current season (optional)

---

## 📌 Table of Contents
1.  [Project Description](#-project-description)
2.  [Dataset](#-dataset)
3.  [Installation](#-installation)
4.  [Model Details](#-model-details)
5.  [Usage](#-usage)
6.  [Evaluation](#-evaluation)
7.  [Example Prediction](#-example-prediction)
8.  [Contribution Guidelines](#-contribution-guidelines)
9.  [License](#-license)

---

## 📝 Project Description

This project aims to predict the final ranking of Premier League teams using machine learning techniques. By analyzing historical data, including previous season performance, transfer spending, and current season points, the model provides insights into potential team performance. This tool can be used for informational purposes, fantasy football analysis, or to explore the factors influencing team success in the Premier League.

---

## 📁 Dataset

The dataset includes historical data of Premier League teams and their performance.

| Column Name        | Description                                                                                                                                |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| `Club`             | Name of the football team                                                                                                                  |
| `Year`             | Season year                                                                                                                                |
| `Previous`         | Previous season rank                                                                                                                       |
| `Previous_point`   | Points earned in the previous season                                                                                                       |
| `Pts`              | Current season points .  Use `0` if predicting before the season starts or early in the season when points are negligible. |
| `Transfer`         | Money spent in the summer transfer window (in Euros)                                                                                       |
| `#`              | Final league rank (target variable)                                                                                                      |

✔️ Data is cleaned and sorted in descending order by year.

> **Note:** The dataset is not included in this repository due to size constraints. You can create your own dataset or find a suitable dataset online. Some potential sources include:
>
> *   **[Kaggle](https://www.kaggle.com/)**: Search for "Premier League" datasets.
> *   **[Football-Data.co.uk](https://www.football-data.co.uk/)**: Offers historical Premier League data in CSV format.
> *   **Web scraping**: You can scrape data from websites like [FBref](https://fbref.com/en/) or [Wikipedia](https://www.wikipedia.org/).
>
> Remember to preprocess the data accordingly to match the format described above.

---

## 🛠️ Installation

To run this project, you need to install the following dependencies:

> The model is trained using the Gradient Boosting algorithm from the scikit-learn library. Gradient Boosting is an ensemble learning method that combines multiple weak learners (decision trees) to create a strong predictive model.

---

## ⚙️ Usage

bash
    > git clone <repository_url>
    > cd <repository_directory>
    | Metric    | Value  |
|-----------|--------|
| MAE       | 3.81   |
| MSE       | 24.31  |
| R² Score  | 0.10   |

-   **MAE (Mean Absolute Error)**: The average absolute difference between the predicted and actual ranks.
-   **MSE (Mean Squared Error)**: The average squared difference between the predicted and actual ranks.
-   **R² Score (Coefficient of Determination)**: Represents the proportion of the variance in the dependent variable that is predictable from the independent variables.

python
# Load the trained model (assuming it's saved as 'model.pkl')
model = joblib.load('model.pkl')

# Example input data
input_data = pd.DataFrame({
    "Previous": [3],
    "Previous_point": [69],
    "Transfer": [120_000_000],
    "Pts": [85]
})

# Make prediction
prediction = model.predict(input_data)
print(f"Predicted Rank: {round(prediction[0], 1)}")
> **Note:**  Before running the example, ensure you have a trained model saved as `model.pkl` in the same directory as your script, or provide the correct path to the saved model.  You can save a trained model using `joblib.dump(model, 'model.pkl')` after training.

---

## 🤝 Contribution Guidelines

We welcome contributions to improve this project! Here's how you can contribute:

1.  **Fork the repository.**
2.  **Create a new branch** for your feature or bug fix.
3.  **Make your changes** and ensure they are well-documented.
4.  **Test your changes** thoroughly.
5.  **Submit a pull request** with a clear description of your changes.

> Please adhere to the existing code style and conventions.

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:
