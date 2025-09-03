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

## 📁 Project Structure

```
fpso-equipment-failure-prediction/
├── data/
│   └── sample_data.xlsx
├── src/
│   ├── fpso_analysis.py          # Main analysis class
│   ├── data_preprocessing.py     # Data cleaning utilities
│   ├── feature_engineering.py   # Feature creation functions
│   └── visualization.py         # Plotting utilities
├── notebooks/
│   ├── 01_exploratory_analysis.ipynb
│   ├── 02_model_development.ipynb
│   └── 03_results_visualization.ipynb
├── models/
│   └── trained_models/          # Saved model artifacts
├── results/
│   ├── reports/                 # Analysis reports
│   └── visualizations/          # Generated plots
├── tests/
│   └── test_analysis.py
├── requirements.txt
├── README.md
└── setup.py
```

## 📈 Data Format

The system expects Excel files with the following columns:

| Column | Type | Description |
|--------|------|-------------|
| cycle | int | Sequential cycle number |
| preset_1 | int | Operational configuration parameter 1 |
| preset_2 | int | Operational configuration parameter 2 |
| temperature | float | Equipment temperature readings |
| pressure | float | System pressure measurements |
| vibrations_x | float | X-axis vibration measurements |
| vibrations_y | float | Y-axis vibration measurements |
| vibrations_z | float | Z-axis vibration measurements |
| frequency | float | Operational frequency |
| fail | bool | Failure indicator (True/False) |

## 🔍 Analysis Results Summary

### Critical Findings
- **Primary Failure Indicator**: Y-axis vibrations show 79.3% increase during failures
- **Predictive Features**: Rolling averages (3-5 cycles) outperform instantaneous values
- **Failure Classification**: 48.5% mechanical, 21.2% operational, 19.7% thermal
- **Configuration Impact**: Preset combinations show varying failure rates (0-16.13%)

### Model Performance
| Model | AUC Score | F1 Score | Accuracy |
|-------|-----------|----------|----------|
| Logistic Regression | 0.9783 | 0.6667 | 92% |
| Random Forest | 0.9567 | 0.6154 | 91% |

## 🚨 Operational Thresholds

Based on statistical analysis, implement the following monitoring thresholds:

- **Critical**: Vibrations_Y > 121.50 (immediate attention required)
- **Warning**: Temperature > 106.49 (95th percentile of normal operation)
- **Monitor**: Vibrations_X > 125.41, Vibrations_Z > 114.14, Frequency > 113.29

## 🛠️ Production Deployment

### Model Deployment
```python
# Load trained model
from joblib import load
model = load('models/trained_models/best_model.pkl')

# Real-time prediction
def predict_failure(sensor_data):
    prediction = model.predict_proba([sensor_data])
    return prediction[0][1]  # Failure probability
```

### Monitoring Integration
The system provides hooks for integration with:
- SCADA systems
- Real-time dashboards
- Alert management systems
- Maintenance scheduling platforms

## 📊 Visualization Suite

The framework generates comprehensive visualizations including:
- Failure timeline analysis
- Statistical comparison plots
- Model performance curves (ROC, Precision-Recall)
- Feature importance rankings
- Correlation heatmaps

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit changes (`git commit -am 'Add new feature'`)
4. Push to branch (`git push origin feature/improvement`)
5. Create Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **Your Name** - *Initial work* - [YourGitHub](https://github.com/yourusername)

## 🙏 Acknowledgments

- Oil & Gas industry domain experts for technical guidance
- Open source data science community for tools and methodologies
- FPSO operational teams for data validation and feedback

## 📞 Support

For questions or support, please:
- Open an issue on GitHub
- Contact: your.email@company.com
- Documentation: [Project Wiki](https://github.com/yourusername/fpso-equipment-failure-prediction/wiki)

---

*This project demonstrates the application of advanced data science techniques for predictive maintenance in critical industrial equipment.*