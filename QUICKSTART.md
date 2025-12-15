# Quick Start Guide

Get up and running with the Enhanced SDN IDS in 5 minutes!

## ⚡ Fast Setup

### 1. Install Dependencies (2 min)

```powershell
# Navigate to project directory
cd "C:\Users\Salman\Downloads\Infosec"

# Install all required packages
pip install -r requirements.txt
```

### 2. Download Dataset (5 min)

1. Visit: https://drive.google.com/drive/folders/16bRX1uo6zyKlkMgKqZDyc4DeYuBzfOxx
2. Download `48_features.csv`
3. Place it in the `data/` folder

### 3. Run the Notebook (30+ min for training)

```powershell
# Launch Jupyter Notebook
jupyter notebook Implementation.ipynb
```

Or open in VS Code and run cells sequentially.

## 📊 What to Expect

### Training Time (approximate)
- **RFE Feature Selection**: 1-2 minutes
- **SHAP Analysis**: 2-3 minutes
- **BiLSTM Training (5-fold)**: 15-20 minutes
- **Attention CNN-LSTM (5-fold)**: 15-20 minutes

**Total**: ~35-45 minutes (with GPU, longer on CPU)

### Expected Output

The notebook will output:
1. ✅ Data loading summary
2. ✅ Selected features from RFE
3. ✅ SHAP importance rankings
4. ✅ Training progress for each fold
5. ✅ Classification reports and confusion matrices
6. ✅ Final averaged metrics (Accuracy, F1, AUC-ROC)

## 🎯 Key Metrics to Look For

| Metric | Description | Expected Range |
|--------|-------------|----------------|
| **Accuracy** | Overall correctness | 95-99% |
| **F1-Score** | Balance of precision/recall | 0.90-0.98 |
| **AUC-ROC** | Multi-class discrimination | 0.95-0.99 |

## 🚨 Troubleshooting

### GPU Not Detected
```python
# Check GPU availability in the notebook output
# If "Using device: cpu" appears but you have GPU:
# 1. Install PyTorch with CUDA: pip install torch torchvision --index-url https://download.pytorch.org/whl/cu118
# 2. Restart kernel
```

### Memory Error
```python
# Reduce batch size in the last cell:
metrics_bilstm = run_kfold_pipeline(X_selected, y, model_type='bilstm', 
                                    loss_type='focal', epochs=30, 
                                    batch_size=128)  # Changed from 256 to 128
```

### File Not Found: 48_features.csv
- Ensure the file is in `data/48_features.csv`
- Check the `DATA_DIR` variable in the notebook points to `Path('data')`

### Import Errors
```powershell
# Reinstall specific packages
pip install torch torchvision shap scikit-learn pandas numpy
```

## 📈 Understanding Results

### Confusion Matrix
- Diagonal = correct predictions
- Off-diagonal = misclassifications
- Higher diagonal values = better performance

### Classification Report
- **Precision**: Of predicted attacks, how many are real?
- **Recall**: Of real attacks, how many were detected?
- **F1-Score**: Harmonic mean of precision & recall

### SHAP Feature Importance
- Shows which features matter most
- Higher values = more important
- Helps understand model decisions

## 🔄 After Running

### Save Results
The notebook doesn't auto-save results. To save:

1. **Save metrics to CSV**:
```python
# Add this cell at the end
metrics_bilstm.to_csv('results_bilstm.csv', index=False)
metrics_attn.to_csv('results_attention_cnn_lstm.csv', index=False)
```

2. **Save the notebook**: File → Save

### Share Results
- Take screenshots of key outputs
- Copy metrics tables
- Save confusion matrices

## 🎓 Next Steps

1. ✅ Run the complete notebook
2. ✅ Review results and metrics
3. ✅ Read IMPROVEMENTS.md to understand enhancements
4. ✅ Upload to GitHub (see GITHUB_SETUP.md)
5. ✅ Submit repository link

## 📚 Documentation

- **README.md**: Full project overview
- **IMPROVEMENTS.md**: Detailed technical documentation
- **data/README.md**: Dataset information
- **GITHUB_SETUP.md**: Git and GitHub instructions

## 💡 Tips

- ⚡ Use GPU for faster training (10x speedup)
- 📊 Run with smaller epochs (10-15) for quick testing
- 🔍 Check printed outputs for each cell
- 💾 Save your work frequently
- 📸 Screenshot important results

---

**Ready to start? Run the first cell!** 🚀
