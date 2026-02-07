# Diamond Price Prediction

A machine learning project that predicts diamond prices based on various physical characteristics and quality attributes.

## 📋 Project Overview

This project implements an end-to-end machine learning pipeline to predict diamond prices using features such as carat, cut, color, clarity, and dimensions. The application is built with Flask and features a beautiful, modern web interface with custom CSS styling for an enhanced user experience.

## ✨ Features

- **Beautiful UI**: Modern gradient design with smooth animations and responsive layout
- **Data Ingestion**: Automated data loading and splitting into train/test sets
- **Data Transformation**: Feature engineering and preprocessing pipeline
- **Model Training**: Machine learning model training with hyperparameter tuning
- **Web Interface**: Interactive Flask web application with stunning CSS design
- **Prediction Pipeline**: Real-time prediction system for new diamond data
- **Logging**: Comprehensive logging system for debugging and monitoring
- **Exception Handling**: Custom exception handling for better error management
- **Demo Video**: Complete demonstration of the application in action



## 🔧 Technologies Used

- **Python 3.x**
- **Flask**: Web framework
- **scikit-learn**: Machine learning algorithms
- **Pandas**: Data manipulation
- **NumPy**: Numerical computations
- **Seaborn**: Data visualization

## 📥 Installation

1. Clone the repository:
```bash
git clone https://github.com/Nikhil-Singh-Bhadoriya/Diamond-Price-Prediction.git
cd Diamond-Price-Prediction/Diamond_Price_Prediction
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## 🚀 Usage

1. **Run the Flask application**:
```bash
python application.py
```

2. **Access the web interface**:
   - Open your browser and navigate to `http://localhost:5000`
   - Fill in the diamond characteristics in the form
   - Click predict to get the estimated price

3. **Input Features**:
   - **Carat**: Weight of the diamond
   - **Cut**: Quality of the cut (Fair, Good, Very Good, Premium, Ideal)
   - **Color**: Diamond color grade (D to J)
   - **Clarity**: Diamond clarity (IF, VVS1, VVS2, VS1, VS2, SI1, SI2, I1)
   - **Depth**: Total depth percentage
   - **Table**: Width of top of diamond relative to widest point
   - **X, Y, Z**: Length, width, and depth dimensions in mm

## 📊 Model Training

To retrain the model with new data:

1. Place your dataset in the appropriate location
2. Run the training pipeline:
```python
from src.pipelines.training_pipeline import TrainingPipeline
pipeline = TrainingPipeline()
pipeline.run()
```

## � Project Structure

```
Diamond_Price_Prediction/
├── application.py          # Flask application
├── static/
│   └── style.css          # Custom CSS styling
├── templates/
│   ├── index.html         # Home page
│   └── form.html          # Prediction form
├── src/
│   ├── components/        # Data ingestion, transformation, model training
│   ├── pipelines/         # Training and prediction pipelines
│   ├── logger.py          # Logging configuration
│   ├── exception.py       # Custom exceptions
│   └── utils.py           # Utility functions
├── notebooks/
│   ├── EDA.ipynb          # Exploratory Data Analysis
│   └── Model Training.ipynb
├── artifacts/             # Saved models and preprocessors
└── Demo Video.mp4         # Project demonstration

```

## 🎥 Demo Video

Watch the complete demonstration of the Diamond Price Prediction application in action: **Demo Video.mp4**

## 🎨 UI Features

- Gradient purple theme with smooth animations
- Responsive design for all screen sizes
- Interactive form with real-time validation
- Beautiful result display with price formatting
- Diamond icon and modern typography

## 📝 Notebooks

- **EDA.ipynb**: Exploratory Data Analysis with visualizations and insights
- **Model Training.ipynb**: Model development and evaluation

---
