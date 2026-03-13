# diabetes-classification
About this project :-
The objective of this project is to classify whether someone has diabetes or not.
Dataset consists of several Medical Variables(Independent) and one Outcome Variable(Dependent)
<img width="1842" height="927" alt="image" src="https://github.com/user-attachments/assets/3bc4967d-e70d-470f-a51e-90f5d17f8eec" />
# 🩺 Diabetes Prediction Web Application

## 📌 Project Overview

This project presents a **complete end-to-end Machine Learning pipeline** for predicting whether a patient is likely to have **Diabetes** based on several medical diagnostic measurements. The project covers the full **Data Science workflow**, including data exploration, preprocessing, handling class imbalance, model training, evaluation, and deployment through an interactive **Streamlit web application**.

The objective of this project is to demonstrate how machine learning can assist in **early detection of diabetes**, which is a major global health issue. By analyzing patient medical attributes, the model predicts the likelihood of diabetes and provides a simple interface that allows users to interact with the trained model.

---

# 📊 Dataset

The dataset used in this project is the **Pima Indians Diabetes Dataset**, a well-known dataset commonly used for machine learning classification problems in healthcare.

### Dataset Features

The dataset contains the following medical attributes:

| Feature                  | Description                                      |
| ------------------------ | ------------------------------------------------ |
| Pregnancies              | Number of times the patient has been pregnant    |
| Glucose                  | Plasma glucose concentration                     |
| BloodPressure            | Diastolic blood pressure (mm Hg)                 |
| SkinThickness            | Triceps skin fold thickness (mm)                 |
| Insulin                  | 2-Hour serum insulin (mu U/ml)                   |
| BMI                      | Body Mass Index                                  |
| DiabetesPedigreeFunction | Diabetes hereditary influence score              |
| Age                      | Age of the patient                               |
| Outcome                  | Target variable (0 = Non-Diabetic, 1 = Diabetic) |

---

# 🔎 Exploratory Data Analysis (EDA)

Exploratory Data Analysis was conducted to understand the dataset structure and identify patterns in the data.

The following steps were performed:

* Checking dataset shape and data types
* Detecting missing or zero values
* Statistical summary of features
* Correlation analysis
* Visualizing distributions using **histograms and boxplots**
* Identifying outliers in medical measurements

Libraries used for EDA:

* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**

These analyses help understand relationships between variables and guide preprocessing decisions.

---

# ⚙️ Data Preprocessing

Several preprocessing techniques were applied to prepare the dataset for machine learning models.

### Steps Included

1. Handling invalid values (such as zeros in medical measurements).
2. Feature scaling and normalization.
3. Splitting the dataset into **training and testing sets**.
4. Addressing **class imbalance** using oversampling techniques.

### Handling Imbalanced Data

The dataset contains more non-diabetic cases than diabetic ones. To solve this issue:

**RandomOverSampler** from the `imbalanced-learn` library was applied to balance the classes and improve model performance.

---

# 🤖 Machine Learning Models

Multiple machine learning algorithms were trained and evaluated to determine the best-performing model.

### Models Used

* Logistic Regression
* Decision Tree
* Random Forest
* Gradient Boosting
* Support Vector Machine

Each model was evaluated using classification metrics.

---

# 📈 Model Evaluation

The following metrics were used to evaluate model performance:

* **Accuracy**
* **Precision**
* **Recall**
* **F1 Score**
* **Confusion Matrix**

These metrics provide insight into how well the model distinguishes between diabetic and non-diabetic patients.

The best-performing model was then **saved using Pickle** so it can be reused in the deployment stage.

Example:

```
pickle.dump(model, open('Diabetes_prediction.sav', 'wb'))
```

---

# 💾 Model Deployment

After training the machine learning model, it was deployed using **Streamlit**, a Python framework used to build interactive data science web applications.

The trained model is loaded from the saved `.sav` file and used to make predictions based on user inputs.

---

# 🌐 Streamlit Web Application

The Streamlit application provides a **user-friendly interface** where users can enter patient medical information and instantly receive a diabetes prediction.

### Application Features

✔ Interactive web interface
✔ Real-time diabetes prediction
✔ Simple input fields for medical data
✔ Prediction results displayed instantly
✔ Visual feedback using images

---

# 🧑‍💻 Streamlit Implementation

The Streamlit application loads the trained model using the **Pickle** library:

```python
Data = pickle.load(open('Diabetes_prediction.sav','rb'))
```

The web interface is built using Streamlit components:

### Title and Application Description

```python
st.title('Diabetes Prediction Web App')
st.info('Easy Application for Diabetes Prediction Disease')
```

These elements provide users with a clear description of the application.

---

### User Input Features

The application allows users to input medical data using **text input fields**:

```python
Pregnancies = st.text_input('Pregnancies')
Glucose = st.text_input('Glucose')
BloodPressure = st.text_input('BloodPressure')
SkinThickness = st.text_input('SkinThickness')
BMI = st.text_input('BMI')
DiabetesPedigreeFunction = st.text_input('DiabetesPedigreeFunction')
Age = st.text_input('Age')
```

These inputs represent the medical attributes used by the machine learning model.

---

### Creating a DataFrame for Prediction

The user inputs are converted into a **Pandas DataFrame** before being passed to the model:

```python
df = pd.DataFrame({
    'Pregnancies':[Pregnancies],
    'Glucose':[Glucose],
    'BloodPressure':[BloodPressure],
    'SkinThickness':[SkinThickness],
    'BMI':[BMI],
    'DiabetesPedigreeFunction':[DiabetesPedigreeFunction],
    'Age':[Age]
})
```

This structure matches the format used during model training.

---

### Prediction Button

A button triggers the prediction process:

```python
Con = st.sidebar.button('Predict')
```

When the user clicks the button, the model predicts whether the patient has diabetes.

---

### Prediction Logic

```python
result = Data.predict(df)
```

If the model predicts **0**, the patient is considered **non-diabetic**.
If the model predicts **1**, the patient is considered **diabetic**.

The result is displayed in the sidebar with an appropriate message and image.

Example output:

* **The patient is clear**
* **The patient has diabetes**

---

# 🚀 Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Imbalanced-Learn
* Pickle
* Streamlit

---

# 📂 Project Structure

```
Diabetes-Prediction-Project
│
├── data
│   └── diabetes.csv
│
├── notebooks
│   └── diabetes_analysis.ipynb
│
├── model
│   └── Diabetes_prediction.sav
│
├── app
│   └── streamlit_app.py
│
└── README.md
```

---

# 📌 Future Improvements

This project can be further enhanced by:

* Adding **SMOTE** instead of RandomOverSampler
* Implementing **cross-validation**
* Adding **ROC Curve & AUC score**
* Improving UI design in Streamlit
* Deploying the application online using **Streamlit Cloud**

---

# 👨‍💻 Author

**Alhussien Adel Hassan**

This project was developed as part of my **Data Science learning journey**, demonstrating my ability to build and deploy an end-to-end machine learning application.

---

⭐ If you found this project useful, feel free to **star the repository**.
