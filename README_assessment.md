# M6-04 — YOLO Object Detection Assessment

Train, evaluate, and visualise a YOLO detector on a custom cat dataset.

---

## Reproduce

### 1. Clone & install dependencies

```bash
git clone https://github.com/d1nsrz/m6-04-assessment.git
cd m6-04-assessment
pip install ultralytics matplotlib pillow pyyaml pandas
```

### 2. Download the dataset

Download `DATA_CLEAN/` from the course Google Drive (https://drive.google.com/drive/folders/1qeGvkaK7UkNMYoESQHxGbV4DRH8EgEb0) link and place it at:

```
data/
└── DATA_CLEAN/
    ├── images/
    └── labels/
```

The `data/` folder is git-ignored and must be populated manually.

### 3. Run the notebook

Open `m6-04-assessment.ipynb` in JupyterLab (or VS Code) and run all cells top to bottom:

```bash
jupyter lab m6-04-assessment.ipynb
```

Each task is self-contained — cells print progress and save figures to the repo root.

### 4. Outputs produced

| File | Description |
|---|---|
| `data.yaml` | Ultralytics dataset config (auto-written by Task 2) |
| `data/DATA_CLEAN/train.txt` | Training split (70%) |
| `data/DATA_CLEAN/val.txt` | Validation split (15%) |
| `data/DATA_CLEAN/test.txt` | Test split (15%) |
| `runs/yolo_v1/weights/best.pt` | Best checkpoint |
| `class_distribution.png` | Per-class object counts |
| `image_sizes.png` | Width/height scatter of 100 random images |
| `training_curves.png` | Loss + mAP curves over 30 epochs |
| `task5a_predictions.png` | Predicted boxes on 6 test images |
| `task5b_pred_vs_gt.png` | Predictions vs ground truth (3 images) |
| `task5c_failures.png` | Failure case analysis (FP / FN) |

---

## Results summary

| Metric | Test set |
|---|---|
| mAP@0.5 | 92.33% |
| mAP@0.5:0.95 | 71.62% |
| Mean Precision | 90.77% |
| Mean Recall | 87.18% |

Model: `yolo11s` (YOLO26s equivalent) — 30 epochs, 640 × 640, batch 8, seed 42.

---

## Repo structure

```
.
├── m6-04-assessment.ipynb   # all tasks in one notebook
├── data.yaml                # Ultralytics dataset config
├── README_assessment.md
├── *Other Files like .png*
├── .gitignore               # excludes data/
└── data/                    # git-ignored — populate manually
    └── DATA_CLEAN/
```
