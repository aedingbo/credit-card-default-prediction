# credit-card-default-prediction
A machine learning project to predict credit card default.

## Skills Demonstrated
* **Data Analysis & Visualization:** Performed in-depth Exploratory Data Analysis (EDA) using `pandas` and `matplotlib` to investigate feature distributions, data imbalances, and skewness.
* **Feature Engineering & Preprocessing:** Implemented binary encoding and one-hot encoding (`pd.get_dummies`) to transform categorical data into a model-ready format for `scikit-learn`.
* **Model Training & Evaluation:** Established baseline performance for four different tree-based models (Decision Tree, Bagging, Random Forest, Extra Trees) and evaluated them using a `classification_report`.
* **Hyperparameter Tuning:** Optimized a Random Forest Classifier by systematically tuning hyperparameters (`criterion`, `n_estimators`) to maximize the **recall** score, demonstrating an understanding of model optimization for specific business goals.
* **Critical Thinking:** Analyzed the trade-offs between key performance metrics (Accuracy vs. Recall) and understood the business impact of different types of model errors in a financial context.

## Project Workflow

The project followed a structured machine learning workflow:

1.  **Data Cleaning & EDA:** The raw data was loaded, and an initial cleaning was performed. An extensive EDA was conducted to understand the dataset's features, including investigating undocumented values in categorical columns and visualizing the heavy right-skew in numerical columns like `PAY_AMT` and `BILL_AMT`.

2.  **Preprocessing:** All features were converted into a purely numerical format. This included **binary encoding** the `SEX` column and **one-hot encoding** the multi-category `EDUCATION` and `MARRIAGE` columns to prepare the data for the `scikit-learn` library.

3.  **Baseline Modeling:** Four different tree-based models were trained and evaluated to establish a performance baseline. During this phase, **recall** was identified as the most critical metric for this business problem, as failing to predict a default is far more costly than a false alarm.

4.  **Hyperparameter Tuning:** A two-stage hyperparameter search was conducted on the Random Forest model to find the settings that maximized the recall score. This involved a broad search across different criteria and numbers of trees, followed by a more focused search around the most promising results.

## Results & Conclusion

The final analysis concluded that a simple model—a Random Forest with `n_estimators=1` (effectively a single Decision Tree) and the `'gini'` criterion—yielded the best recall score of **~0.416**. This counter-intuitive result highlights the importance of tuning for a specific metric and shows that more complex models are not always superior. The project also concluded with a reflection on the risk of "overfitting to the test set," demonstrating an understanding of the limitations of hyperparameter tuning.

## How to Run
1.  **Prerequisites:** Python 3.x, preferably via the Anaconda distribution.
2.  **Libraries:** Ensure you have the following libraries installed:
    * `pandas`
    * `numpy`
    * `matplotlib`
    * `scikit-learn`
3.  **Execution:** Place the Jupyter Notebook (`Random_Forest_Classifier.ipynb`) and the data file (`credit_card_data.xlsx`) in the same directory and run the notebook cells sequentially.

## Acknowledgments
* This project was completed as part of the curriculum for the **Applied Machine Learning Bootcamp by Columbia University**.
* The dataset used is the "Default of Credit Card Clients Dataset" from the UCI Machine Learning Repository.
