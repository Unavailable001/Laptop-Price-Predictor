# Laptop-Price-Predictor

This is a laptop price prediction project using machine learning.The key aspects include :

1. Dataset Overview:
- The dataset contains information about laptops including features like:
  - Company (manufacturer)
  - Type (Ultrabook, Notebook, Gaming etc.)
  - Screen size (Inches)
  - Screen resolution 
  - CPU specifications
  - RAM
  - Storage (Memory)
  - GPU
  - Operating System
  - Weight
  - Price

2. Data Preprocessing Steps:
- Removed unnecessary columns (Unnamed: 0)
- Handled units by removing 'GB', 'kg' etc.
- Created binary features for touchscreen and IPS display
- Extracted screen resolution into X and Y coordinates
- Calculated PPI (Pixels Per Inch)
- Processed CPU information to extract brand and model
- Categorized GPU brands (Intel, AMD, Nvidia)
- Simplified operating systems into categories (Windows, Mac, Others/Linux)
- Processed storage information into separate columns for HDD, SSD, Hybrid, and Flash Storage

3. Exploratory Data Analysis:
- Used various visualizations:
  - Distribution plots for price, weight, inches
  - Bar plots for categorical variables
  - Correlation analysis using heatmap
  - Scatter plots to understand relationships between variables
- Key findings from correlations with price:
  - RAM showed strong positive correlation (0.74)
  - SSD storage showed positive correlation (0.67)
  - PPI (screen quality) showed moderate correlation (0.47)
  - Weight showed weak correlation (0.21)

4. Model Development:
Multiple models were tested with their performance metrics:

a) Basic Models:
- Linear Regression (R2: 0.807, MAE: 0.210)
- Ridge Regression (R2: 0.813, MAE: 0.209)
- Lasso Regression (R2: 0.807, MAE: 0.211)
- KNN (R2: 0.802, MAE: 0.193)
- Decision Tree (R2: 0.838, MAE: 0.183)
- SVM (R2: 0.808, MAE: 0.202)

b) Advanced Ensemble Models:
- Random Forest (R2: 0.883, MAE: 0.164)
- AdaBoost (R2: 0.798, MAE: 0.228)
- Gradient Boosting (R2: 0.881, MAE: 0.160)
- XGBoost (R2: 0.877, MAE: 0.163)
- Stacking (R2: 0.881, MAE: 0.165)

5. Best Performing Models:
- Random Forest and Gradient Boosting performed the best with R² scores around 0.88
- These models achieved Mean Absolute Error of around 0.16 (on log-transformed prices)

6. Implementation Details:
- Used sklearn's Pipeline and ColumnTransformer for preprocessing
- Implemented OneHotEncoding for categorical variables
- Used log transformation on the target variable (price) to handle skewness
- Split the data into training (85%) and testing (15%) sets

The project successfully demonstrates the ability to predict laptop prices with good accuracy using machine learning models, with ensemble methods performing particularly well.
