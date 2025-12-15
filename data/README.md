# Dataset Directory

This directory should contain the InSDN (Intrusion Detection in SDN) dataset required for the project.

## 📥 Download Instructions

### Dataset Source

Download the InSDN dataset from the following Google Drive link:

**[InSDN Dataset - Google Drive](https://drive.google.com/drive/folders/16bRX1uo6zyKlkMgKqZDyc4DeYuBzfOxx)**

### Required Files

After downloading, place the following file(s) in this `data/` directory:

- `48_features.csv` - Main dataset with 48 features

### File Structure

Your `data/` directory should look like this:

```
data/
├── README.md              # This file
└── 48_features.csv        # Downloaded dataset
```

## 📊 Dataset Information

The InSDN dataset contains network traffic data for Software-Defined Networks (SDN) with labeled intrusion attempts.

### Features

- **48 features** capturing various network flow characteristics
- **Label column** indicating attack type or benign traffic

### Dataset Statistics

- Multiple attack types (DDoS, probing, etc.)
- Imbalanced class distribution (handled by our focal loss implementation)
- Preprocessed and ready for ML/DL models

## ⚠️ Important Notes

1. **Do not commit dataset files to Git** - The `.gitignore` file is configured to exclude CSV files from version control
2. **Dataset size** - The dataset may be several hundred MB to GBs
3. **Privacy** - Ensure compliance with data usage terms from the original dataset creators

## 🔍 Verification

After downloading, verify the file exists:

```bash
# On Windows PowerShell
Test-Path data/48_features.csv

# On Linux/Mac
ls -lh data/48_features.csv
```

## 🆘 Troubleshooting

### Issue: File not found error when running notebook

**Solution**: Ensure `48_features.csv` is in the `data/` directory and update the `DATA_DIR` path in the notebook:

```python
DATA_DIR = Path('data')  # Update this path if needed
```

### Issue: Download link not working

**Solution**: Contact the repository maintainer or refer to the original research paper for alternative dataset sources.

## 📧 Support

If you encounter issues downloading or accessing the dataset, please:
1. Check the original paper for dataset information
2. Open an issue in this repository
3. Contact the dataset creators directly
