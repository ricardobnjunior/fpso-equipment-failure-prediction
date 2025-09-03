# FPSO Equipment Failure Prediction

A comprehensive data science framework for predicting equipment failures in FPSO (Floating Production Storage and Offloading) systems using machine learning techniques and statistical analysis.

## 📊 Project Overview

This project implements a complete failure analysis pipeline for FPSO equipment, providing predictive maintenance capabilities through advanced statistical modeling and feature engineering. The system analyzes sensor data including temperature, vibrations, frequency, and operational presets to predict equipment failures before they occur.

## 🎯 Key Results

- **Predictive Accuracy**: 97.83% AUC score with Logistic Regression
- **Failure Detection**: F1-score of 66.7% for failure identification
- **Critical Threshold**: Vibrations_Y > 121.50 indicates imminent failure
- **Primary Failure Indicators**: Y-axis vibrations (79.3% increase during failures)

## 🔧 Features

### Analysis Components
1. **Failure Pattern Analysis** - Quantifies failure frequency, duration, and temporal patterns
2. **Configuration Impact Assessment** - Identifies high-risk operational settings
3. **Root Cause Analysis** - Statistical comparison of sensor data during normal vs failure states
4. **Predictive Modeling** - Machine learning models for failure prediction
5. **Variable Importance Ranking** - Identifies most critical monitoring parameters

### Technical Features
- Temporal data handling with proper train/test splits
- Feature engineering including lag variables and rolling averages
- Statistical significance testing for all parameters
- Comprehensive visualization suite
- Production-ready model deployment framework

## 📋 Requirements

```
pandas >= 1.3.0
numpy >= 1.21.0
scikit-learn >= 1.0.0
matplotlib >= 3.4.0
seaborn >= 0.11.0
plotly >= 5.0.0
scipy >= 1.7.0
openpyxl >= 3.0.0
```

## 🚀 Quick Start

### Installation

```bash
git clone https://github.com/yourusername/fpso-equipment-failure-prediction.git
cd fpso-equipment-failure-prediction
pip install -r requirements.txt
```

### Basic Usage

```python
from fpso_analysis import FPSOEquipmentAnalysis

# Initialize analyzer
analyzer = FPSOEquipmentAnalysis('your_data.xlsx')

# Run complete analysis
analyzer.run_complete_analysis()

# Or run individual tasks
analyzer.load_data()
analyzer.task_1_count_failures()
analyzer.task_2_analyze_by_presets()
analyzer.task_3_root_cause_analysis()
analyzer.task_4_build_models()
analyzer.task_5_variable_importance()
```
