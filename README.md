# Iris Flower Classification

**CodeAlpha Data Science Internship — Task 1**

| Project detail | Value |
|---|---|
| Student | Nour Ali Mohamed |
| Student ID | CA/DF1/414910 |
| Internship domain | Data Science |
| Project | Iris Flower Classification |

## Project Overview

This project uses supervised machine learning to classify an Iris flower as **Setosa**, **Versicolor**, or **Virginica** from four measurements: sepal length, sepal width, petal length, and petal width. The complete analysis, visualizations, model training, evaluation, and sample prediction are provided in one executed Jupyter Notebook.

## Objectives

- Inspect and understand the supplied dataset.
- Explore class balance and relationships among flower measurements.
- Prepare the data without leaking test-set information into training.
- Train a Scikit-learn classification model.
- Evaluate its performance on unseen test data.
- Demonstrate a prediction for a new flower measurement record.

## Dataset Description

- **File:** `dataset/Iris.csv`
- **Rows:** 150
- **Columns:** 6
- **Target:** `Species`
- **Measurements:** `SepalLengthCm`, `SepalWidthCm`, `PetalLengthCm`, `PetalWidthCm`
- **Identifier:** `Id`

The supplied CSV contains 50 records for each of the three classes: `Iris-setosa`, `Iris-versicolor`, and `Iris-virginica`. Inspection found no missing values and no exact duplicate rows. `Id` contains a unique identifier for each row and is excluded from the model features. The target labels are normalized to `Setosa`, `Versicolor`, and `Virginica` for readable model output.

**Dataset source:** `Iris.csv` supplied for this project by the student. No external dataset download is required.

## Technologies Used

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Workflow

1. Import the required Python libraries.
2. Load and inspect the supplied CSV file.
3. Explore descriptive statistics, missing values, duplicates, and class counts.
4. Visualize species distribution, feature distributions, pairwise relationships, and feature correlations.
5. Separate the four measurement features from the species target.
6. Split the data into training and test partitions using stratification and a fixed random seed.
7. Train a Logistic Regression classifier in a Scikit-learn pipeline.
8. Evaluate the final model on the held-out test partition.
9. Demonstrate a prediction for a sample flower.

## Machine Learning Approach

The notebook uses **Logistic Regression** as a clear multi-class classification baseline. A `Pipeline` combines `StandardScaler` with `LogisticRegression`, ensuring the scaler is fitted only on training data. The dataset is split into 80% training and 20% testing data with `stratify=y` and `random_state=42`.

A five-fold stratified cross-validation is performed on the training partition. Its mean accuracy was **0.9583** (standard deviation **0.0264**). The held-out test set is used only for the final evaluation.

## Evaluation Results

The following results are from the notebook's actual execution:

| Metric | Test result |
|---|---:|
| Accuracy | 0.9333 |
| Macro precision | 0.9333 |
| Macro recall | 0.9333 |
| Macro F1-score | 0.9333 |

The classification report showed:
- **Setosa:** precision 1.0000, recall 1.0000, F1-score 1.0000 (10 test samples).
- **Versicolor:** precision 0.9000, recall 0.9000, F1-score 0.9000 (10 test samples).
- **Virginica:** precision 0.9000, recall 0.9000, F1-score 0.9000 (10 test samples).

The model correctly classified **28 of 30** held-out test flowers. Setosa was classified perfectly in this split; the remaining errors occurred between Versicolor and Virginica. These results describe this particular stratified split and should not be interpreted as a guarantee of performance on every future dataset.

## Installation

Use Python 3.10 or newer. From a terminal opened in the project folder, create and activate a virtual environment if desired.

### Windows (PowerShell)

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

If PowerShell blocks activation, you can use Command Prompt instead:

```bat
.venv\Scripts\activate.bat
```

## How to Run the Notebook

### In VS Code

1. Open VS Code.
2. Choose **File → Open Folder** and select `Task_1_Iris_Flower_Classification`.
3. Install the Microsoft **Python** and **Jupyter** extensions if they are not already installed.
4. Open `iris_flower_classification.ipynb`.
5. Select the Python interpreter from the project's `.venv` environment using **Select Kernel** in the notebook toolbar.
6. Run **Run All**. The notebook reads `dataset/Iris.csv` using a path relative to the notebook.

### From a terminal

After installing requirements and activating the environment, run:

```bash
jupyter notebook
```

Then open `iris_flower_classification.ipynb` in the browser and run all cells.

## Project Structure

```text
Task_1_Iris_Flower_Classification/
├── iris_flower_classification.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── dataset/
    └── Iris.csv
```

## Notes

- Keep `dataset/Iris.csv` in the `dataset` folder so the notebook's relative path resolves.
- The notebook includes executed outputs and visualizations. Running all cells again will regenerate them.
- No separate Python implementation files or pre-trained model files are required.
