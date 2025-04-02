
# Predicting Water Potability with an End-to-End MLOps Workflow

Hi there! 👋 This project is a hands-on example of how to apply MLOps practices to build a real-world solution that predicts if water is safe to drink. We use **MLflow** to monitor model training, **DVC** to manage data and model versions, and wrap it all up in a user-friendly desktop app built with **Tkinter**. 

## What’s This About?

- **Challenge**: Figure out if water is potable using chemical properties.
- **Goal**: Set up an efficient pipeline that tracks every experiment, keeps data organized, and lets us easily ship the final model in an app.

---

## Step-by-Step Workflow

1. **Initial Setup**: We kick off the project using a Cookiecutter template and version control with Git.
2. **Experiment Logging**: All training runs and metrics are saved via MLflow on DagsHub.
3. **Data and Pipeline Management**: DVC helps us keep track of datasets and the steps in our machine learning pipeline.
4. **Model Management**: The best model gets registered in MLflow and is ready to be used anywhere.
5. **App Deployment**: A simple desktop app is created with Tkinter, pulling the latest model directly from MLflow for instant predictions.

---

## Project Organization at a Glance

### Getting Started
- Cookiecutter helps create the initial project layout.
- GitHub is used to store and collaborate on code.

### Keeping Track of Experiments
1. **Using MLflow + DagsHub**:
   - Each run is logged with its settings and results.
   - We can compare models and see which works best.

2. **Try Different Approaches**:
   - Start with Random Forest as the baseline.
   - Test different algorithms (Logistic Regression, XGBoost).
   - Compare how mean vs. median imputation affects results.
   - Tune Random Forest parameters to squeeze out better accuracy.

### Building the Pipeline with DVC
1. **Versioning Data**:
   - DVC keeps versions of our datasets so we always know what was used when.

2. **Stages in the Pipeline**:
   - **Data Gathering**: Bring in the dataset and organize it.
   - **Preprocessing**: Fill in missing values (mean).
   - **Training**: Train the Random Forest model.
   - **Evaluation**: Log the results in MLflow.

### Registering the Model
- The best model is saved in the MLflow Registry.
- We can now use it with FastAPI, Streamlit, or in this case – a desktop app.

### The Desktop App 🖥️
- The Tkinter app is super lightweight.
- It pulls the latest model automatically and lets users input their own data to see if the water is drinkable.

---

## What Did We Find?

- **Top Performer**: Random Forest using mean for missing values.
- **Best Settings**: `n_estimators=1000`, `max_depth=None`.

---

## File and Folder Structure

```
├── LICENSE
├── Makefile             <- Commands for building, training, etc.
├── README.md            <- Project overview and setup guide
├── data/
│   ├── raw              <- Original dataset
│   ├── external         <- External sources
│   ├── interim          <- Intermediate processing
│   └── processed        <- Cleaned data for modeling
├── docs/                <- Project documentation
├── models/              <- Saved models and outputs
├── notebooks/           <- Jupyter notebooks (e.g., 1.0-jd-initial-checks)
├── references/          <- Notes, sources, references
├── reports/
│   └── figures          <- Charts and graphs
├── requirements.txt     <- Dependencies
├── setup.py             <- Installable package setup
├── src/
│   ├── __init__.py
│   ├── data/
│   │   └── make_dataset.py
│   ├── features/
│   │   └── build_features.py
│   ├── models/
│   │   ├── train_model.py
│   │   └── predict_model.py
│   └── visualization/
│       └── visualize.py
└── tox.ini              <- Testing config
```
