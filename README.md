# Enhanced SDN Intrusion Detection System Using Deep Learning

This repository contains an improved implementation of intrusion detection in Software-Defined Networks (SDN) using deep learning approaches, building upon the research paper ["Intrusion detection in software defined network using deep learning approaches"](https://www.nature.com/articles/s41598-024-79001-1).

## 📋 Project Overview

This project implements an advanced intrusion detection system for SDN environments with significant improvements over the baseline approach, including:

- **Advanced Deep Learning Models**: BiLSTM and Attention-augmented CNN-LSTM architectures
- **Intelligent Feature Selection**: RFE (Recursive Feature Elimination) and SHAP-based feature importance
- **Robust Loss Functions**: Focal Loss and Class-Balanced Focal Loss for handling imbalanced datasets
- **Comprehensive Evaluation**: K-Fold Cross-Validation, AUC-ROC, and expanded performance metrics
- **Rich Feature Space**: Utilizing 48+ feature dimensions with automated selection

## 🎯 Key Improvements

Our implementation introduces several enhancements over traditional approaches:

1. **Feature Engineering & Selection**
   - Expanded feature space (48+ features)
   - Recursive Feature Elimination (RFE) for optimal feature selection
   - SHAP (SHapley Additive exPlanations) for interpretable feature importance

2. **Advanced Neural Architectures**
   - Bidirectional LSTM (BiLSTM) for capturing temporal patterns
   - Attention-augmented CNN-LSTM for focused feature learning
   - Batch normalization and dropout for better generalization

3. **Specialized Loss Functions**
   - Focal Loss to address class imbalance
   - Class-Balanced Focal Loss with β-weighting
   - Dynamic class weight computation

4. **Rigorous Evaluation**
   - Stratified K-Fold Cross-Validation (5 folds)
   - Multi-metric evaluation (Accuracy, Precision, Recall, F1, AUC-ROC)
   - Confusion matrices and detailed classification reports

## 📁 Repository Structure

```
Infosec/
│
├── Implementation.ipynb          # Main implementation notebook
├── README.md                      # This file
├── IMPROVEMENTS.md                # Detailed documentation of improvements
├── requirements.txt               # Python dependencies
├── LICENSE                        # Project license
├── .gitignore                     # Git ignore rules
│
└── data/                          # Dataset directory (not tracked)
    └── README.md                  # Data download instructions
```

## 🔧 Installation & Setup

### Prerequisites

- Python 3.8 or higher
- CUDA-capable GPU (recommended) or CPU
- 8GB+ RAM recommended

### Step 1: Clone the Repository

```bash
git clone <your-repository-url>
cd Infosec
```

### Step 2: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 3: Download Dataset

The InSDN dataset is required to run this implementation. Download the dataset from:

**Dataset Link**: [Google Drive - InSDN Dataset](https://drive.google.com/drive/folders/16bRX1uo6zyKlkMgKqZDyc4DeYuBzfOxx)

After downloading:
1. Create a `data/` directory in the project root
2. Extract the dataset files into the `data/` directory
3. Ensure the file `48_features.csv` is present in `data/`

Your data folder should look like:
```
data/
└── 48_features.csv
```

### Step 4: Update Data Path (if needed)

Open `Implementation.ipynb` and update the `DATA_DIR` variable to point to your data directory:

```python
DATA_DIR = Path('data')  # or your custom path
```

### Step 5: Run the Notebook

Launch Jupyter Notebook:

```bash
jupyter notebook Implementation.ipynb
```

Or use VS Code with the Jupyter extension.

## 🚀 Usage

The implementation is organized in a single comprehensive Jupyter notebook with the following workflow:

1. **Environment Setup**: Import libraries and configure GPU/CPU
2. **Data Loading**: Load and concatenate dataset files
3. **Preprocessing**: Standardization and label encoding
4. **Feature Selection**: RFE and SHAP-based selection
5. **Model Training**: K-Fold cross-validation with BiLSTM and Attention CNN-LSTM
6. **Evaluation**: Comprehensive metrics and visualization

Simply run the cells sequentially in `Implementation.ipynb`.

## 📊 Expected Results

The models are evaluated using the following metrics:

- **Accuracy**: Overall classification accuracy
- **Precision**: Weighted precision across classes
- **Recall**: Weighted recall across classes
- **F1-Score**: Weighted F1-score
- **AUC-ROC**: Area Under ROC Curve (macro-averaged)

Each model is trained for 30 epochs with 5-fold cross-validation, providing robust performance estimates.

## 🔬 Models Implemented

### 1. BiLSTM Classifier
- Bidirectional LSTM with 2 layers
- Batch normalization
- Focal loss optimization
- Hidden size: 128

### 2. Attention-Augmented CNN-LSTM
- CNN feature extraction (2 layers)
- Bidirectional LSTM
- Attention mechanism for focused learning
- Class-Balanced Focal Loss

## 📚 Dependencies

Key libraries used:
- PyTorch (Deep Learning)
- scikit-learn (ML utilities & metrics)
- SHAP (Feature importance)
- NumPy & Pandas (Data processing)
- Matplotlib (optional, for visualization)

See `requirements.txt` for complete list.

## 📖 Reference Paper

This work is inspired by:

**"Intrusion detection in software defined network using deep learning approaches"**
- Published in: *Scientific Reports*, Nature (2024)
- DOI: [10.1038/s41598-024-79001-1](https://www.nature.com/articles/s41598-024-79001-1)

## 🤝 Contributing

This is a research project developed for academic purposes. For improvements or suggestions:

1. Fork the repository
2. Create a feature branch
3. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

Research project developed as part of academic coursework focusing on cybersecurity in Software-Defined Networks.

## 🙏 Acknowledgments

- Original research paper authors for the baseline methodology
- InSDN dataset creators
- Open-source community for tools and libraries

## 📞 Contact

For questions or collaboration opportunities, please open an issue in the repository.

---

**Note**: This implementation focuses on the improvements and enhancements over the baseline approach. The base paper's methodology is referenced but not fully reproduced in this version.
