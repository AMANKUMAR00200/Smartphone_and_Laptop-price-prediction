# 💻📱 Smartphone & Laptop Price Prediction

<p align="center">
  <b>Machine Learning | Python | Streamlit | Scikit-learn | XGBoost</b>
</p>

<p align="center">
  An interactive Machine Learning web application that predicts the estimated prices of smartphones and laptops based on their hardware specifications.
</p>

<p align="center">
  <a href="https://github.com/AMANKUMAR00200/Smartphone_and_Laptop-price-prediction">
    <img src="https://img.shields.io/badge/GitHub-Repository-black?logo=github" alt="GitHub">
  </a>
  <img src="https://img.shields.io/badge/Python-3.x-blue?logo=python">
  <img src="https://img.shields.io/badge/Streamlit-Web%20App-red?logo=streamlit">
  <img src="https://img.shields.io/badge/ML-Regression-orange">
  <img src="https://img.shields.io/badge/Status-Completed-success">
</p>

---

## 🚀 Overview

**Smartphone & Laptop Price Prediction** is a Machine Learning-based application developed using Python and Streamlit.

The main objective of this project is to estimate gadget prices based on their technical specifications, helping users understand how hardware configurations influence device prices.

The application provides two independent prediction modules:

- 📱 Smartphone Price Prediction
- 💻 Laptop Price Prediction

Users can select different device specifications and receive an estimated price in Indian Rupees (₹).

## ✨ Key Features

### 📱 Smartphone Price Prediction

Predict smartphone prices using:

- Smartphone Brand
- Operating System
- Processor Brand
- Processor Core Type
- Processor Speed
- RAM and ROM
- Rear Camera
- Screen Size
- Screen Resolution
- Pixel Density (PPI)
- 5G Connectivity
- Premium Features (Pro / Ultra / Plus / Max)
- Additional Features (NFC / IR Blaster / Vo5G)

### 💻 Laptop Price Prediction

Predict laptop prices using:

- Laptop Brand
- Laptop Type
- RAM Configuration
- Laptop Weight
- CPU Brand
- GPU Brand
- HDD Storage
- SSD Storage
- Operating System
- Screen Size
- Screen Resolution
- Pixel Density (PPI)
- Touchscreen Support
- IPS Display Support

### 🎯 Application Features

- Interactive Streamlit interface
- Separate smartphone and laptop prediction modules
- Dynamic input selection
- Automated feature engineering
- Pre-trained Machine Learning pipelines
- Instant price prediction
- Price display in Indian Rupees (₹)

---

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Core Programming Language |
| Pandas | Data Manipulation |
| NumPy | Numerical Computation |
| Scikit-learn | Machine Learning |
| XGBoost | Gradient Boosting |
| Streamlit | Interactive Web Application |
| Pickle | Model Serialization |
| Jupyter Notebook | Model Development |
| HTML / CSS | Interface Styling |

---

## 🧠 Machine Learning Approach

This project follows a Supervised Machine Learning approach using Regression algorithms.

### 1. Data Collection

Separate datasets are used for smartphone and laptop price prediction.

### 2. Data Preprocessing

- Preparing numerical and categorical features.
- Handling categorical variables.
- Transforming data into a suitable format for model training.

### 3. Feature Engineering

An additional feature, Pixel Density (PPI), is calculated using screen resolution and screen size.

Formula:

\[
PPI = \frac{\sqrt{X^2+Y^2}}{Screen\ Size}
\]

Where:

- X = Horizontal screen resolution
- Y = Vertical screen resolution

### 4. Feature Encoding

Categorical variables such as brand, operating system, processor and GPU are processed using OneHotEncoder.

### 5. Model Training

Different regression algorithms are explored during model development.

Algorithms explored include:

- Linear Regression
- Ridge Regression
- Lasso Regression
- K-Nearest Neighbors
- Decision Tree Regression
- Random Forest Regression
- Extra Trees Regression
- Gradient Boosting Regression
- AdaBoost Regression
- Support Vector Regression
- XGBoost Regression
- Voting and Stacking Regressors

**Final prediction pipelines:**

| Prediction Module | Algorithm |
|---|---|
| Laptop Price Prediction | Random Forest Regressor |
| Smartphone Price Prediction | XGBoost Regressor |

### 6. Model Serialization

Trained models and supporting datasets are saved using Python Pickle.

This allows the Streamlit application to load the existing models and make predictions without retraining them every time.

### 7. Price Prediction

The application receives user specifications, passes them through the corresponding trained pipeline and displays the estimated price.

The target price is log-transformed during model development and converted back using the exponential function during prediction.

```python
prediction = np.exp(model.predict(query)[0])
```

---

## 🏗️ Project Architecture

```text
                   USER
                     |
                     v
              STREAMLIT APP
                     |
              SELECT DEVICE
                     |
           +---------+---------+
           |                   |
           v                   v
       SMARTPHONE            LAPTOP
        MODULE               MODULE
           |                   |
           v                   v
       USER INPUT           USER INPUT
           |                   |
           v                   v
       FEATURE ENGINEERING & PREPROCESSING
           |                   |
           v                   v
       XGBOOST MODEL       RANDOM FOREST MODEL
           |                   |
           +---------+---------+
                     |
                     v
                PREDICTION
                     |
                     v
              ESTIMATED PRICE
                   (₹)
```

---

## 📂 Project Structure

```text
Smartphone_and_Laptop-price-prediction/
│
├── app.py
├── style.css
├── requirements.txt
│
├── Laptop-Price-Predictor.ipynb
├── Smartphone price predictor.ipynb
│
├── laptop_data.xls
├── smartphones - smartphones.xls
│
├── df_laptop1.pkl
├── pipe1_laptop1.pkl
│
├── df .pkl
├── pipe .pkl
│
└── README.md
```

**Note:** The Pickle files are required for running the application because they contain the saved prediction pipelines and supporting datasets. Keep the filenames consistent with the paths used in `app.py`.

---

## ⚙️ Installation & Setup

Follow these steps to run the project locally.

### Prerequisites

- Python 3.x
- Git
- pip

### Step 1: Clone the Repository

```bash
git clone https://github.com/AMANKUMAR00200/Smartphone_and_Laptop-price-prediction.git
```

### Step 2: Navigate to the Project Directory

```bash
cd Smartphone_and_Laptop-price-prediction
```

### Step 3: Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

**Windows**

```bash
venv\Scripts\activate
```

**macOS / Linux**

```bash
source venv/bin/activate
```

### Step 4: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 5: Run the Application

```bash
streamlit run app.py
```

### Step 6: Open in Browser

```text
http://localhost:8501
```

The application will now be available locally.

---

## 📦 Requirements

```text
streamlit
numpy
pandas
scikit-learn
xgboost
```

---

## 📊 How to Use

1. Clone the GitHub repository.
2. Install the required Python dependencies.
3. Start the Streamlit application.
4. Select Laptop or Mobile from the sidebar.
5. Enter the device specifications.
6. Click on the **Predict Price** button.
7. View the estimated gadget price in Indian Rupees (₹).

---

## 🔮 Future Enhancements

- Integration with real-time e-commerce pricing APIs.
- Comparison of prices across different brands.
- Prediction history and user authentication.
- Interactive analytics dashboard.
- Hyperparameter tuning and model optimization.
- Support for tablets and smartwatches.
- Cloud deployment.
- Improved user interface and mobile responsiveness.

---

## 🎯 Learning Outcomes

Through this project, I explored:

- Supervised Machine Learning.
- Regression algorithms.
- Data preprocessing and feature engineering.
- Categorical feature encoding.
- Model training and evaluation.
- Scikit-learn pipelines.
- Model serialization using Pickle.
- Integration of Machine Learning models with Streamlit.

---

## 👨‍💻 Author

**Aman Kumar**

B.Tech – Computer Science Engineering

GitHub: [@AMANKUMAR00200](https://github.com/AMANKUMAR00200)

Project Repository: [Smartphone & Laptop Price Prediction](https://github.com/AMANKUMAR00200/Smartphone_and_Laptop-price-prediction)

---

## ⭐ Support

If you find this project useful, please consider giving this repository a ⭐ on GitHub.

**Made with ❤️ using Python, Machine Learning and Streamlit.**
