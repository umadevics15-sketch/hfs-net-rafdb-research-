# HFS-Net / RAF-DB Facial Expression Recognition Experiments

This repository organises the RAF-DB RGB facial-expression recognition experiments supplied in the project archive.

> **Research status:** The associated conference-paper manuscript has not been accepted or published. Results and claims should be described as the authors' experimental results or manuscript-reported results, not as peer-reviewed findings.

## Repository contents

- `notebooks/` — five experiment notebooks:
  - `raf-color-bpm.ipynb` — baseline CNN experiment
  - `raf-color-hybrid.ipynb` — hybrid Fire/SqueezeNet-style experiment using separable convolutions
  - `raf-color-kaa.ipynb` — hybrid Fire/SqueezeNet-style experiment with channel shuffle
  - `raf-color-shuffle.ipynb` — ShuffleNet-style channel-shuffle experiment
  - `raf-color-squeeze.ipynb` — SqueezeNet-style model with a subtle attention block
- `models/` — selected saved Keras model files (the large `raf_3cnn_model.keras` file was excluded from this prepared GitHub package because it exceeds GitHub's regular 100 MB per-file limit).
- `history/` — training history JSON files for plotting training/validation accuracy and loss.

## Dataset

The original ZIP included a large RAF-DB image folder. It has intentionally **not** been copied into this repository.

Obtain RAF-DB through its official access process and follow its licence/terms. Arrange the local dataset in the folder structure expected by the notebooks:

```text
Dataset/
└── DATASET/
    ├── train/
    │   ├── 1/
    │   ├── 2/
    │   └── ...
    └── test/
        ├── 1/
        ├── 2/
        └── ...
```

The notebooks currently use relative paths such as `Dataset\\DATASET\\train` and `Dataset\\DATASET\\test`. Update those paths if running in a different environment.

## Environment

The notebooks use Python with TensorFlow/Keras, NumPy, Pandas, Matplotlib, Seaborn, Pillow, and scikit-learn. A starter dependency list is provided in `requirements.txt`. Exact package versions may need adjustment to match the environment used to train the saved models.

## Run

1. Obtain the dataset through the authorised source.
2. Create and activate a Python virtual environment.
3. Install dependencies from `requirements.txt`.
4. Open a notebook under `notebooks/`.
5. Confirm the dataset paths and class-folder mapping before training or evaluation.

## Model files and GitHub

The included `.keras` files are each below GitHub's 100 MB regular file limit. If you later add larger checkpoints, use Git LFS or an approved model-hosting service. Confirm that sharing trained weights is permitted by your dataset terms, institution, and project collaborators before making this repository public.

## Reproducibility notes

- The original ZIP contained 15,339 image files; these are excluded from this repository.
- Jupyter `.ipynb_checkpoints` duplicates are excluded.
- `raf_3cnn_model.keras` (about 114.4 MB) is excluded from this package due to GitHub's regular per-file limit.
- This prepared repository is an organised source/model snapshot, not a guarantee that every notebook runs without local path or dependency adjustments.
