#  Used Car Price Predictor

A machine learning project that predicts the **selling price of used cars** using a neural network (MLP) trained on real-world vehicle data.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/used-car-price-predictor/blob/main/notebooks/used_car_price_predictor.ipynb)

---

##  Project Overview

Pricing a second-hand car fairly is difficult — prices depend on brand, mileage, age, fuel type, and many other factors. This project automates that process using a **Multi-Layer Perceptron (MLP)** regression model built with TensorFlow/Keras.

Three model architectures are compared:
| Model | Architecture | R² Score |
|-------|-------------|----------|
| Model 1 | Simple MLP (4×64 neurons, ReLU) | **0.72**  |
| Model 2 | MLP + Dropout (0.3) | 0.71 |
| Model 3 | MLP + Dropout + BatchNorm | 0.65  |

**Best model**: Model 1 — simple baseline MLP 

---

## Project Structure

```
used-car-price-predictor/
├── notebooks/
│   └── used_car_price_predictor.ipynb   # Main Colab notebook
├── data/
│   └── README.md                         # Instructions for obtaining the dataset
├── models/
│   ├── car_price_model_1.h5              # Trained model (best performer)
│   ├── scaler.pkl                        # StandardScaler for input features
│   ├── scaler_km.pkl                     # Scaler for km_driven column
│   └── expected_columns.pkl             # Feature column list (for API use)
├── requirements.txt                      # Python dependencies
├── .gitignore
└── README.md
```

---

##  Quick Start

### Run in Google Colab (recommended)
Click the **Open in Colab** badge at the top of this README.

Upload the dataset file `used_car_price_predction_database.xlsx` to `/content/sample_data/` inside Colab before running.

### Run locally

```bash
git clone https://github.com/YOUR_USERNAME/used-car-price-predictor.git
cd used-car-price-predictor
pip install -r requirements.txt
jupyter notebook notebooks/used_car_price_predictor.ipynb
```

---

##  Dataset

The dataset contains used car listings with the following features:

| Column | Description |
|--------|-------------|
| `name` | Car name (processed into `brand`) |
| `year` | Year of manufacture (converted to `car_age`) |
| `selling_price` | Target variable — sale price |
| `km_driven` | Mileage in kilometres |
| `fuel` | Fuel type (Petrol, Diesel, CNG, etc.) |
| `seller_type` | Individual / Dealer / Trustmark Dealer |
| `transmission` | Manual / Automatic |
| `owner` | Number of previous owners |

> **Note**: The dataset (`used_car_price_predction_database.xlsx`) is not included in this repository due to size. See `data/README.md` for download instructions.

---

## Methodology

1. **Data Cleaning** — brand extraction, age calculation, owner encoding, one-hot encoding, StandardScaler normalization
2. **Model Training** — three MLP architectures trained for 100–200 epochs with Adam optimizer and MSE loss
3. **Evaluation** — MAE, RMSE, and R² metrics on a 20% held-out test set
4. **Export** — best model saved as `.h5`, scalers as `.pkl` files for deployment

---

##  Requirements

- Python 3.8+
- TensorFlow 2.x
- scikit-learn
- pandas, numpy, matplotlib
- joblib

See `requirements.txt` for exact versions.

---

## Author

Jakub Tyliński