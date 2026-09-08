# Drishti — Industrial Quality Control & Defect Detection

Edge AI and computer vision inspection pipeline for real-time surface flaw identification and spatial anomaly detection.

## Architecture
- `app.py`: Streamlit-based interactive operator console and real-time inspection dashboard.
- `ml_engine.py`: Computer vision defect classification models using normalized spatial feature embeddings.
- `nlq_engine.py`: Natural language query interface for querying historical inspection logs.
- `patrol.py`: Automated batch camera surveillance loop.
- `test_core.py`: Regression test suite for feature extraction and anomaly scoring.

## Prerequisites
- Python 3.10+
- OpenCV, NumPy, Scikit-learn, Streamlit

## Setup & Installation
```bash
pip install -r requirements.txt
```

## Running Tests
```bash
python -m unittest test_core.py
```

## Running the Application
```bash
streamlit run app.py
```
