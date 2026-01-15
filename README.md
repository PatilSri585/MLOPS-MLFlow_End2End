# MLOps: MLFlow End-to-End

A comprehensive guide and practical examples demonstrating MLFlow's end-to-end workflow for machine learning operations. This repository covers experiment tracking, model logging, artifact management, and integration with DagsHub.

## Overview

This project showcases how to use MLFlow for:
- **Experiment Tracking**: Log and compare different model runs with metrics and parameters
- **Model Logging**: Save trained models with metadata and dependencies
- **Artifact Management**: Store and version model artifacts, visualizations, and scripts
- **Remote Tracking**: Connect to MLFlow tracking servers for centralized monitoring
- **Integration**: Integrate with DagsHub for collaborative ML workflows

## Project Structure

```
main/
├── mlflow_demo.py              # Basic MLFlow example with local tracking
├── mlflow_autolog.py           # MLFlow autolog feature demonstration
├── mlflow_with_dagshub.py      # MLFlow integrated with DagsHub for remote tracking
└── data.ipynb                  # Data exploration and analysis notebook

mlartifacts/                    # Local MLFlow artifacts storage
```

## Scripts Description

### 1. `mlflow_demo.py`
**Purpose**: Demonstrates basic MLFlow usage with local tracking server

**Features**:
- Loads the Wine dataset using scikit-learn
- Trains a Random Forest classifier
- Logs parameters: `max_depth`, `n_estimators`
- Logs metrics: model accuracy
- Generates and logs confusion matrix visualization
- Logs the source code as an artifact
- Logs the trained model with scikit-learn integration
- Tags runs with metadata (Author, Project)

**Usage**:
```bash
python mlflow_demo.py
```

### 2. `mlflow_autolog.py`
**Purpose**: Demonstrates MLFlow's automatic logging feature

**Features**:
- Uses `mlflow.autolog()` to automatically track parameters and metrics
- Integrates with DagsHub for remote tracking
- Reduces boilerplate code by automatically logging sklearn experiments
- Trains Random Forest on Wine dataset with automatic metric tracking

**Usage**:
```bash
python mlflow_autolog.py
```

### 3. `mlflow_with_dagshub.py`
**Purpose**: Shows how to integrate MLFlow with DagsHub for collaborative ML workflows

**Features**:
- Uses DagsHub initialization for remote tracking
- Configures MLFlow to use DagsHub as the remote tracking URI
- Logs experiments to a remote DagsHub repository
- Enables team collaboration and experiment sharing

**Usage**:
```bash
python mlflow_with_dagshub.py
```

### 4. `data.ipynb`
**Purpose**: Jupyter notebook for data exploration and analysis

## Requirements

- Python 3.7+
- mlflow
- scikit-learn
- matplotlib
- seaborn
- pandas
- dagshub (for remote tracking examples)

## Getting Started

1. **Clone the repository**:
```bash
git clone <repository-url>
cd MLOPS-MLFlow_End2End
```

2. **Install dependencies**:
```bash
pip install mlflow scikit-learn matplotlib seaborn pandas dagshub
```

3. **Start MLFlow Tracking Server** (for local tracking):
```bash
mlflow ui
```
The tracking server will be available at `http://localhost:5000`

4. **Run a demo script**:
```bash
cd main
python mlflow_demo.py
```

5. **View Results**:
- Open `http://localhost:5000` in your browser to see tracked experiments
- Check the `mlartifacts/` directory for locally stored artifacts

## MLFlow Concepts Demonstrated

- **Experiments**: Organize related runs under named experiments
- **Runs**: Individual training executions with their own metrics, parameters, and artifacts
- **Parameters**: Hyperparameters and model configuration settings
- **Metrics**: Model performance measurements (accuracy, loss, etc.)
- **Artifacts**: Output files like models, visualizations, and code
- **Tags**: Metadata to organize and filter runs
- **Model Registry**: Store and version trained models

## Output Structure

All runs are stored in the `mlartifacts/` directory with the following structure:
```
mlartifacts/
└── <experiment_id>/
    └── <run_id>/
        ├── artifacts/
        │   ├── MLmodel
        │   ├── conda.yaml
        │   ├── python_env.yaml
        │   └── requirements.txt
        ├── metrics/
        └── params/
```

## Author

Harsha

## License

See LICENSE file for details.
