# SmartEye Project - Progress Summary

## Project Overview
SmartEye is a video anomaly detection project that processes raw video frames and creates a structured dataset for training machine learning models.

### Project Structure
```
data/
├── raw/
│   ├── Train/         (15 anomaly categories: Abuse, Arrest, Arson, Assault, Burglary, Explosion, Fighting, Normal, RoadAccidents, Robbery, Shooting, Shoplifting, Stealing, Vandalism)
│   └── Test/          (Similar categories to Train)
└── processed/
    └── train.csv      (Output CSV with sequence metadata)

notebook/
└── pre_processing.ipynb  (Processing script)
```

## Work Completed

### 1. Notebook Setup (Cell 1)
✅ **Status:** Complete
- Configured absolute paths for data directories
- Initialized key variables:
  - `SEQ_LEN = 16`: Minimum sequence length (frames) required for a valid sequence
  - `STRIDE = 8`: Step size for sliding window over frames
  - `rows = []`: List to store sequence metadata
  - `sequence_id = 0`: Counter for unique sequence IDs

**Paths Set:**
- Input: `/Users/mukuldixit/Desktop/projects/SmartEye/data/raw/Train`
- Output: `/Users/mukuldixit/Desktop/projects/SmartEye/data/processed/train.csv`

### 2. Frame Sequence Processing (Cell 2)
⚠️ **Status:** Executable but Issue Detected
- Iterates through each anomaly category folder
- Labels: 0 for "Normal", 1 for all other anomaly types
- For each anomaly type folder, scans for image files (.jpg, .png)
- Creates sliding window sequences with specified SEQ_LEN and STRIDE
- **Issue:** The `rows` list is empty after execution

**Possible Causes:**
1. Directory structure mismatch - code expects images directly in anomaly_type folders
2. No folders within anomaly categories contain the minimum required frames (16+)
3. Path traversal is not finding the expected folder hierarchy

### 3. CSV Output (Cell 3)
✅ **Status:** Executable
- Writes sequence metadata to CSV with columns: `sequence_id`, `folder_path`, `start_frame`, `label`
- Creates output directory if needed
- Currently outputs empty CSV because `rows` list is empty

## Next Steps / Issues to Investigate

1. **Verify data structure**: Check actual folder hierarchy in `data/raw/Train` to confirm image locations
2. **Debug frame detection**: Add logging to see if folders are being detected and how many frames each contains
3. **Validate path logic**: Ensure the code is traversing the correct directory levels for images
4. **Check file formats**: Verify images match the expected .jpg/.png extensions

## Current Variables in Kernel
- `archive_path`: Root data directory path
- `data_root`: Training data directory path
- `SEQ_LEN`, `STRIDE`: Sequence parameters
- `rows`: Sequence metadata list (currently empty)
- `sequence_id`: Counter for sequences
