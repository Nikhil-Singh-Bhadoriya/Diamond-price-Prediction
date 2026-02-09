# Diamond Price Prediction

This project explores and models diamond prices using a Kaggle dataset. It includes an exploratory data analysis notebook and a model training notebook using scikit-learn pipelines. The details below are pulled directly from the notebook outputs.

## Notebooks

### EDA.ipynb

Highlights (actual notebook outputs):
- Dataset shape and schema (from `df.info()`): 193,573 rows, 11 columns, memory usage 16.2 MB; dtypes float64(6), int64(2), str(3).
- Missing values (from `df.isnull().sum()`): all 0 for every column.
- Duplicate records (from `df.duplicated().sum()`): 0.
- Numerical columns inferred: carat, cut, color, clarity, depth, table, x, y, z, price.
- Categorical columns inferred by dtype: none (object columns were not detected in that step).

Sample rows (first 5, before dropping `id`):

| id | carat | cut | color | clarity | depth | table | x | y | z | price |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 1.52 | Premium | F | VS2 | 62.2 | 58.0 | 7.27 | 7.33 | 4.55 | 13619 |
| 1 | 2.03 | Very Good | J | SI2 | 62.0 | 58.0 | 8.06 | 8.12 | 5.05 | 13387 |
| 2 | 0.70 | Ideal | G | VS1 | 61.2 | 57.0 | 5.69 | 5.73 | 3.50 | 2772 |
| 3 | 0.32 | Ideal | G | VS1 | 61.6 | 56.0 | 4.38 | 4.41 | 2.71 | 666 |
| 4 | 1.70 | Premium | G | VS2 | 62.6 | 59.0 | 7.65 | 7.61 | 4.77 | 14453 |

After dropping `id`, the first 5 rows are the same minus the `id` column.

Category counts (from `value_counts()`):
- Cut: Ideal 92,454; Premium 49,910; Very Good 37,566; Good 11,622; Fair 2,021.
- Color: G 44,391; E 35,869; F 34,258; H 30,799; D 24,286; I 17,514; J 6,456.
- Clarity: SI1 53,272; VS2 48,027; VS1 30,669; SI2 30,484; VVS2 15,762; VVS1 10,628; IF 4,219; I1 512.

### Model Training.ipynb

Highlights (actual notebook outputs):
- Target: `price`; features are all other columns after dropping `id`.
- Preprocessing: median imputation + standard scaling for numeric features; most-frequent imputation + ordinal encoding + scaling for categorical features.
- Train/test split: test size 0.30, random state 30.

Model evaluation (from the training cell output):

| Model | RMSE | MAE | R2 (%) |
| --- | --- | --- | --- |
| LinearRegression | 1013.9047094344004 | 674.0255115796832 | 93.68908248567512 |
| Lasso | 1013.8784226767013 | 675.0716923362165 | 93.68940971841704 |
| Ridge | 1013.9059272771611 | 674.0555800798174 | 93.68906732505941 |
| Elasticnet | 1533.4162456064046 | 1060.7368759154729 | 85.56494831165182 |

Linear regression coefficients and intercept (from notebook output):
- Coefficients: [6433.66003594, -132.75843566, -70.42922179, -1720.30971463, -499.29302619, -63.39317848, 72.44537247, -460.41604642, 650.76431652]
- Intercept: 3970.76628955

## Approach

- Load the Kaggle dataset and inspect schema, missing values, and duplicates.
- Drop the `id` column and review distributions and correlations.
- Treat `cut`, `color`, and `clarity` as ordinal categorical features.
- Build preprocessing pipelines: median imputation + standard scaling for numeric; most-frequent imputation + ordinal encoding + scaling for categorical.
- Split data into train/test sets and compare LinearRegression, Lasso, Ridge, and ElasticNet using RMSE, MAE, and R2.

## How To Run

1. Open the notebook you want to run in VS Code or Jupyter.
2. Install dependencies:
   - pandas
   - numpy
   - scikit-learn
   - seaborn
   - matplotlib
3. Update the dataset path if needed.

Notes:
- The notebooks reference `data/gemstone.csv`. In this workspace the file is at the repo root as `gemstone.csv`, so either update the path or create a `data/` folder and move the file there.

## License

Add your preferred license here.
