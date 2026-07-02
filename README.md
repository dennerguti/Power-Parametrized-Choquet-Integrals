# Power-Parametrized Choquet Integrals

A reference implementation of **Power-Parametrized Choquet Integrals** for **network traffic prediction** and **anomaly detection** using adaptive fuzzy measures.

This repository implements the method proposed in our research, where the fuzzy measure is automatically parameterized according to the characteristics of the observed traffic, allowing the Choquet Integral to adapt dynamically to different traffic patterns.

## Features

- Adaptive Power-Parametrized Choquet Integral
- Dynamic fuzzy measure generation
- Sliding window prediction
- Network anomaly detection
- Evaluation through confusion matrix metrics
- Export of experimental results to CSV

---

## Repository Structure

```
.
├── data/
│   └── compilado.csv
└── Segurança_Preditor_Wiley[GIT].ipynb
```

---

## Requirements

- Python 3.10+
- pandas
- numpy

Install the dependencies with:

```bash
pip install pandas numpy
```

---

## Dataset

The notebook expects the dataset at:

```
data/compilado.csv
```

The selected feature is defined by:

```python
FEATURE_COLUMN_INDEX = 1
```

You may change this index to evaluate different traffic features.

---

## Methodology

The prediction process consists of the following stages:

1. Load the network traffic time series.
2. Create a sliding window.
3. Compute the adaptive power-based fuzzy measure.
4. Apply the Power-Parametrized Choquet Integral.
5. Predict the next traffic value.
6. Compare prediction and observation.
7. Detect attention events and attack sequences.
8. Compute evaluation metrics.

---

## Configuration

Main parameters:

```python
WINDOW_START = 57
WINDOW_END = 61

ERROR_THRESHOLD = 1.85
ATTACK_INCREMENT_THRESHOLD = 12
```

These parameters define:

- evaluated window sizes;
- prediction error threshold;
- minimum number of consecutive abnormal increments required to characterize an attack.

---

## Output

After execution, two files are generated inside the `results/` directory.

### Metrics

```
choquet_metrics.csv
```

Contains:

- Window size
- Number of detected attacks
- Attention events
- Accuracy
- Precision
- Recall
- Specificity
- F1-score

### Confusion Matrix

```
choquet_confusion_matrix.csv
```

Contains:

- TP
- FP
- FN
- TN

---

## Citation

If you use this repository in your research, please cite the corresponding publication describing the **Power-Parametrized Choquet Integral** methodology.

---

## License

This project is intended for academic and research purposes.
