# Dataset

The dataset used in this project (`used_car_price_prediction_database.xlsx`) contains used car listings.

## How to obtain the data

1. Download the dataset from the course materials or the original source.
2. Place the file at the following path inside Google Colab:
   ```
   /content/sample_data/PSI_database.xlsx
   ```
   You can upload it manually via the Colab file browser, or mount Google Drive:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```

## Dataset columns

| Column | Type | Description |
|--------|------|-------------|
| `name` | string | Full car name (brand + model) |
| `year` | int | Year of manufacture |
| `selling_price` | int | Sale price (target variable) |
| `km_driven` | int | Total kilometres driven |
| `fuel` | categorical | Fuel type: Petrol, Diesel, CNG, LPG, Electric |
| `seller_type` | categorical | Individual / Dealer / Trustmark Dealer |
| `transmission` | categorical | Manual / Automatic |
| `owner` | categorical | First / Second / Third / Fourth & Above Owner |