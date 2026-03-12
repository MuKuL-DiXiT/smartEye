
# SmartEye Project - Violence Detection System

## Project Overview
SmartEye is a video violence detection system. The project processes raw video frames from the RWF-2000 and RLVS datasets, creating structured datasets for training and evaluating machine learning models to detect violent events in videos.


### Project Structure
```
data/
├── raw/
│   ├── RWF-2000/
│   │   ├── train/
│   │   │   ├── Fight/
│   │   │   └── NonFight/
│   │   ├── val/
│   │   │   ├── Fight/
│   │   │   └── NonFight/
│   │   └── test/
│   └── RLVS/
│       ├── train/
│       │   ├── Fight/
│       │   └── NonFight/
│       └── val/
│           ├── Fight/
│           └── NonFight/
└── processed/
  └── ... (processed data and metadata)

notebook/
├── Baseline_binary_classification.ipynb
└── Baseline_TF.ipynb
```


## Current Status

- **Datasets Used:**
  - RWF-2000 (Fight/NonFight)
  - RLVS (Fight/NonFight)
  - (UCF dataset is no longer used)

- **Task:** Violence detection in videos (anomaly detection replaced by binary violence classification)

- **Data Preparation:**
  - Raw video frames are organized by dataset, split, and class (Fight/NonFight)
  - Scripts and notebooks for preprocessing and baseline experiments are available in the `notebook/` directory

- **Modeling:**
  - Baseline models for binary classification (violence vs. non-violence) are being developed
  - Experiments are tracked in the provided notebooks

- **Next Steps:**
  - Continue improving preprocessing and data augmentation
  - Develop and evaluate advanced models for violence detection
  - Document results and update this README as progress continues
