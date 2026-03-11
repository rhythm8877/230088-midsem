# Dataset Information

## Dataset: Synthetic Spatio-Temporal Action Dataset

### How the Dataset is Obtained
The dataset is **synthetically generated** within the notebooks using NumPy and OpenCV. No external download is required. The generation code is self-contained in `task_2.1.ipynb`.

### Description
We generate synthetic video sequences representing different "action" classes:
1. **Horizontal motion** — a bright patch moving left-to-right
2. **Vertical motion** — a bright patch moving top-to-bottom
3. **Rotation** — a bright patch rotating in place
4. **Zoom/Scale** — a bright patch expanding outward
5. **Diagonal motion** — a bright patch moving diagonally
6. **Static/Flicker** — a bright patch that flickers in place

Each video sequence consists of grayscale frames (32×32 pixels, 10 frames per clip). This creates spatio-temporal volumes that can be processed by the ISA algorithm.

### Why This Dataset
- Matches the paper's problem type: action recognition from video
- Small enough for CPU-only computation
- Controllable — allows us to test specific motion patterns that ISA should capture
- Has at least 100 samples and temporal structure

### How It Is Used
- `task_2.1.ipynb`: Dataset generation and preprocessing
- `task_2.2.ipynb`: ISA feature learning and SVM classification
- `task_2.3.ipynb`: Results comparison and visualization
- `task_3.1.ipynb`: Ablation experiments
- `task_3.2.ipynb`: Failure mode analysis

### Limitations vs. Original Paper
- The original paper uses real-world video datasets (Hollywood2, KTH, UCF, YouTube)
- Our synthetic data lacks realistic textures, backgrounds, and natural motion complexity
- Our dataset is much smaller in scale
