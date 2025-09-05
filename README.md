# Hotel Booking Cancellation Prediction - Data Preprocessing Pipeline

## Project Overview
This project focuses on building a robust data preprocessing pipeline for a hotel booking cancellation prediction model. The pipeline transforms raw data from a Property Management System (PMS) into a clean, machine-learning-ready dataset.

## Business Problem
Last-minute booking cancellations significantly impact hotel profitability. This preprocessing pipeline prepares data for a model that will predict these cancellations.

## Dataset
The dataset `hotel_bookings.csv` contains booking information with various features including:
- Booking details (lead time, arrival date, etc.)
- Guest information (adults, children, babies, country)
- Booking characteristics (meal type, market segment, etc.)
- Historical data (previous cancellations, etc.)


## Data Preprocessing Steps

### Phase 1: Exploratory Data Analysis (EDA)
- Loaded data and generated summary statistics
- Identified and visualized missing values
- Detected outliers in key numerical columns using boxplots and IQR method

### Phase 2: Data Cleaning
- Handled missing values:
  - Company and agent: Replaced missing values with 0
  - Country: Imputed with "Unknown" category
  - Children: Imputed with median value
- Removed duplicate rows
- Capped extreme values in columns like adr (above 1000 set to 1000)
- Fixed data types (date formatting, categorical conversions)

### Phase 3: Feature Engineering & Preprocessing
- Created new features:
  - total_guests = adults + children + babies
  - total_nights = stays_in_weekend_nights + stays_in_week_nights
  - is_family flag (Yes/No)
- Encoded categorical variables:
  - One-Hot Encoding for low-cardinality categories
  - Frequency encoding for high-cardinality features (like country)
- Removed data leakage columns (reservation_status and reservation_status_date)
- Split data into training and testing sets (80/20 ratio)

## How to Use
1. Ensure you have Python installed with required libraries (pandas, numpy, matplotlib, seaborn, scikit-learn)
2. Place the `hotel_bookings.csv` file in the same directory
3. Run the Jupyter notebook `data_preprocessing.ipynb`
4. The cleaned datasets (X_train.csv, X_test.csv, y_train.csv, y_test.csv) will be generated

## Key Findings
- Missing values were found in company, agent, country, and children columns
- Outliers were detected in adr and lead_time columns
- Data leakage was prevented by removing reservation_status columns

## Dependencies
- Python 3.7+
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

## Author
[Your Name]

## License
This project is for educational purposes.
