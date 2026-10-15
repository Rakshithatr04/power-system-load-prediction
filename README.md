# Power System Load Type Prediction Using Machine Learning

## Project Overview

This project uses supervised machine learning to classify power system load conditions into three categories: `Light_Load`, `Medium_Load`, and `Maximum_Load`, based on historical electricity consumption and power-related measurements.

The goal is to build and evaluate classification models that can identify different load conditions using historical data.

## Objectives

- Analyze electricity consumption data through exploratory data analysis (EDA).
- Handle missing values and prepare features for machine learning.
- Build and compare multiple classification models.
- Evaluate performance using accuracy, precision, recall, F1-score, and a confusion matrix.
- Reserve the final available month of data for testing.

## Dataset Features

The dataset contains the following information:

- `Date_Time` — date and time of observation
- `Usage_kWh` — electricity consumption
- `Lagging_Current_Reactive.Power_kVarh` — lagging reactive power
- `Leading_Current_Reactive_Power_kVarh` — leading reactive power
- `CO2(tCO2)` — CO₂ measurement
- `Lagging_Current_Power_Factor` — lagging power factor
- `Leading_Current_Power_Factor` — leading power factor
- `NSM` — number of seconds from midnight
- `Load_Type` — target classification label

Additional time-based features were created from the timestamp.

## Technologies Used

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Google Colab
- GitHub

## Methodology

1. Load and inspect the dataset.
2. Perform exploratory data analysis and visualize load-type distribution.
3. Parse timestamps and sort observations chronologically.
4. Handle missing numerical values using median imputation fitted on training data.
5. Create time-based features.
6. Split the data chronologically, using January–November 2018 for training and the available December 2018 observations for testing.
7. Train and compare Random Forest, Extra Trees, Gradient Boosting, and Hist Gradient Boosting classifiers.
8. Tune Random Forest hyperparameters using time-aware cross-validation on the training data.
9. Evaluate model performance on the December test set.

## Model Comparison

| Model | Test Accuracy | Macro F1-score |
|---|---:|---:|
| Random Forest | 93.99% | 0.9293 |
| Hist Gradient Boosting | 92.81% | 0.9206 |
| Gradient Boosting | 92.44% | 0.9103 |
| Extra Trees | 91.94% | 0.8994 |

Random Forest achieved the highest test accuracy among the four initially compared models.

The tuned Random Forest achieved 93.85% test accuracy and a macro F1-score of 0.9301. The original Random Forest had slightly higher accuracy, while the tuned model had a slightly higher macro F1-score.

## Evaluation Metrics

- **Accuracy:** Overall proportion of correct predictions.
- **Precision:** Correctness of predictions for each load category.
- **Recall:** Ability to identify observations belonging to each category.
- **F1-score:** Harmonic mean of precision and recall.
- **Confusion Matrix:** Visualizes correct and incorrect classifications.

## Results and Conclusion

The initial model comparison showed that Random Forest performed best in overall accuracy, achieving approximately 93.99% on the December 2018 test set.

The results demonstrate how machine learning can be applied to power system load classification. Further work could explore additional feature engineering, systematic hyperparameter optimization, and model interpretability.

## How to Run

1. Open the Jupyter Notebook in Google Colab.
2. Upload the required CSV dataset as `load_data.csv`.
3. Run the notebook cells in order.
4. Review the visualizations, model comparison, and evaluation results.

**Note:** The dataset is not included in this repository. You must provide the CSV file separately to run the notebook.

## Project Structure

- `Power_System_Load_Type_Prediction.ipynb` — data analysis, preprocessing, model training, and evaluation.
- `README.md` — project documentation.

## Author

Rakshitha T R
