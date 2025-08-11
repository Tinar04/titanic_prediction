## Titanic Survival Prediction

This project uses a **Logistic Regression** model to predict the survival of passengers on the Titanic based on a variety of features. The model achieves an accuracy of approximately **80.45%** on the test dataset.

---

### Dataset Overview

The dataset used is `train.csv`, which contains information on 891 passengers. The goal is to predict the `Survived` column, a binary variable (`1` for survived, `0` for not survived).

The dataset includes the following key features:
* **`PassengerId`**: A unique ID for each passenger.
* **`Survived`**: The target variable.
* **`Pclass`**: Ticket class (1, 2, or 3).
* **`Name`**: The passenger's name.
* **`Sex`**: The passenger's gender.
* **`Age`**: The passenger's age.
* **`SibSp`**: Number of siblings/spouses aboard.
* **`Parch`**: Number of parents/children aboard.
* **`Ticket`**: The ticket number.
* **`Fare`**: The fare paid.
* **`Cabin`**: The cabin number.
* **`Embarked`**: The port of embarkation (C, Q, or S).

---

### Data Preprocessing

The raw data required several preprocessing steps to be suitable for the model.

1.  **Handling Missing Values**:
    * The **`Age`** column had 177 missing values, which were filled with the **median** age.
    * The **`Embarked`** column had 2 missing values, which were filled with the **mode** (most frequent value).
    * The **`Cabin`** column had 687 missing values and was dropped entirely.

2.  **Dropping Irrelevant Columns**:
    The **`PassengerId`**, **`Name`**, **`Ticket`**, and **`Cabin`** columns were dropped as they were not useful for the predictive model.

3.  **Encoding Categorical Features**:
    The categorical features **`Sex`** and **`Embarked`** were converted into numerical values using **Label Encoding**.

4.  **Feature Scaling**:
    All numerical features were scaled using **`StandardScaler`** to standardize their range.

---

### Model and Evaluation

A **Logistic Regression** model was chosen for this binary classification problem.

* The data was split into training (80%) and testing (20%) sets.
* The model was trained on the training data and then used to make predictions on the test data.

#### Results:

The model achieved the following performance on the test set:

* **Accuracy**: $80.45\%$
* **Confusion Matrix**:

| | Predicted Not Survived | Predicted Survived |
| :--- | :--- | :--- |
| **Actual Not Survived** | 90 | 15 |
| **Actual Survived** | 20 | 54 |

The model correctly predicted **90** non-survivors and **54** survivors. The accuracy, along with a low number of false positives (15) and false negatives (20), indicates that the model is a strong baseline for this problem.
