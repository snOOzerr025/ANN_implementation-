# 🧠 ANN Customer Churn Prediction
 
A binary classification project that predicts whether a bank customer will churn (exit) using an Artificial Neural Network built with TensorFlow/Keras.
 
---
 
## 📊 Dataset
 
- **Source:** [Churn Modelling Dataset — Kaggle](https://www.kaggle.com/datasets/shrutimechlearn/churn-modelling)
- **Size:** 10,000 rows × 14 columns
- **Target:** `Exited` (1 = churned, 0 = stayed)
---
 
## 🛠️ Tech Stack
 
| Tool | Purpose |
|---|---|
| Python 3.10+ | Core language |
| TensorFlow / Keras | ANN model |
| Keras Tuner | Hyperparameter optimization |
| Scikit-learn | Preprocessing & evaluation |
| Pandas / NumPy | Data manipulation |
| Matplotlib | Training visualizations |
| kagglehub | Dataset download |
 
---
 
## ⚙️ Preprocessing
 
- Dropped irrelevant columns (`RowNumber`, `CustomerId`, `Surname`)
- One-hot encoded `Geography` and `Gender` (drop-first to avoid multicollinearity)
- 80/20 train-test split with `random_state=0`
- Feature scaling using `StandardScaler`
---
 
## 🏗️ Model Architecture
 
```
Input(shape=(n_features,))
→ Dense(11, activation='relu')
→ Dense(7,  activation='relu')
→ Dropout(0.3)
→ Dense(6,  activation='relu')
→ Dense(1,  activation='sigmoid')
```
 
- **Loss:** Binary Crossentropy  
- **Optimizer:** Adam  
- **Callback:** EarlyStopping (`patience=20`, `restore_best_weights=True`)
---
 
## 🔍 Hyperparameter Tuning
 
Uses **Keras Tuner RandomSearch** to optimize:
 
- Number of hidden layers (2–20)
- Units per layer (32–512, step 32)
- Activation function (`relu`, `tanh`, `sigmoid`)
- Dropout rate (0.0–0.5)
- Optimizer (`Adam`, `Adagrad`, `RMSprop`)
- Learning rate (`1e-2`, `1e-3`, `1e-4`)
---
 
## 📈 Evaluation
 
- Confusion Matrix
- Accuracy Score (base model vs tuned model)
- Training / Validation accuracy plots
---
 
## 🚀 Getting Started
 
### 1. Clone the repo
```bash
git clone https://github.com/your-username/ann-churn-prediction.git
cd ann-churn-prediction
```
 
### 2. Install dependencies
```bash
pip install tensorflow keras-tuner scikit-learn pandas numpy matplotlib kagglehub
```
 
### 3. Run the notebook
```bash
jupyter notebook ANN_implementation_fixed.ipynb
```
 
> Make sure your Kaggle API credentials are configured before running — kagglehub uses them to download the dataset automatically.
 
---
 
## 📁 Project Structure
 
```
ann-churn-prediction/
├── ANN_implementation.ipynb        # Original notebook (raw)
├── ANN_implementation_fixed.ipynb  # Fixed & cleaned notebook
└── README.md
```
 
---
 
## 📝 License
 
This project is open source and available under the [MIT License](LICENSE).
