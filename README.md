# 🎓 Apply Predictor

This project implements a simple linear regression model using TensorFlow to estimate the probability of graduate school admission based on various academic and personal profile metrics.

---

## 📘 Project Summary

Using a dataset that includes parameters commonly reviewed by university admissions committees (e.g., GRE, TOEFL scores, GPA), we train a model to predict the likelihood of admission. The target is a continuous value between 0 and 1 representing admission probability.

---

## 📊 Dataset

The dataset is composed of the following columns:

| Feature     | Description                                      | Range    |
|-------------|--------------------------------------------------|----------|
| GRE         | GRE score (out of 340)                           | 0–340    |
| TOEFL       | TOEFL score (out of 120)                         | 0–120    |
| University  | University rating (prestige)                     | 1–5      |
| SOP         | Statement of Purpose strength                    | 1–5      |
| LOR         | Letter of Recommendation strength                | 1–5      |
| CGPA        | Undergraduate GPA                                | 0–10     |
| Research    | Research experience (0 = No, 1 = Yes)            | 0 or 1   |
| Admission   | Probability of admission (target variable)       | 0–1      |

- `admission_train.csv`: Training data (320 samples)  
- `admission_test.csv`: Test data (80 samples)

---

## 🔧 Model Pipeline

- Data Loading & Inspection  
- Tensor Conversion and Manual Validation Split  
- Feature and Label Separation  
- Normalization: Implemented via a custom `Normalizer` class  
- Model Definition: A custom `LinearRegression` class based on `tf.Module`  
- Training: Using mini-batch gradient descent and Mean Squared Error (MSE) loss  
- Validation: Tracked at each epoch for performance monitoring  
- Prediction: Outputs probabilities for test data  
- Packaging: Outputs are saved in `submission.csv` and `result.zip`

---

## 📈 Final Model Performance

| Metric            | Value |
|-------------------|--------|
| Final Train MSE   | 0.004  |
| Final Val MSE     | 0.006  |

📉 The training and validation losses indicate a well-converged model.

---

## 📤 Output Files

- `apply.ipynb`: Complete notebook with code and documentation  
- `submission.csv`: Model predictions for the test set  
- `linear_regression.json`: Metadata (shape of model parameters and normalization stats)  
- `result.zip`: Final compressed archive for submission

---

## 🧪 How to Run

1. Ensure `admission_train.csv` and `admission_test.csv` are in the working directory.
2. Open `apply.ipynb` in Jupyter or Google Colab.
3. Run all cells sequentially to train the model and generate predictions.
4. The final output will be stored in `result.zip`.

---

## 📄 License

This project is licensed under the **MIT License**. See the `LICENSE` file for more details.
