# Visual Object Tracking using Adaptive Correlation Filters (MOSSE)

## Overview

This repository implements a **real-time visual object tracking system** based on **Adaptive Correlation Filters (MOSSE)**.

The method is inspired by Bolme et al. (2010) and uses frequency-domain signal processing to achieve fast and robust tracking.

The system supports:
- Real-time video tracking
- Interactive GUI (Tkinter)
- Multi-object tracking
- PSR-based tracking reliability
- Classical baseline comparisons (template matching / cross-correlation)

---

## User Interface

The system provides an interactive GUI for easy usage.

Users can:
- Select video or webcam input
- Define ROI (Region of Interest)
- Track objects in real-time
- Monitor tracking confidence (PSR)
- Pause / resume / reset tracking


<img src="./assets/ui_demo.png" alt="demo" width="700"/>

---

## Method Overview

The tracker is based on the MOSSE adaptive correlation filter:

- Training via synthetic perturbations
- Gaussian desired response
- FFT-based correlation
- Online adaptation with learning rate
- PSR used for confidence estimation

---

## Project Structure
```
efficient-object-tracking-MOSSE/
├── common/
│   └── utils.py
│
├── core/
│   ├── controller.py
│   ├── mosse.py
│   ├── template_matching.py
│   └── matlab/
│       ├── cross_correlation.m
│       └── mesh_correlation_results.m
│
├── data/
│   ├── videos/
│   ├── matlab/
│   └── template_matching_data/
│
├── assets/
│   ├── ui_demo.png
│   └── results/
│       ├── high_psr.png
│       ├── low_psr.png
│       ├── correlation_surface.png
│       ├── kernel_response.png
│       └── tracking_example.png
├── report/
│   └── report.pdf
│
├── ui.py
├── requirements.txt
└── README.md

```

---

## Results

### High PSR Tracking Performance

Robust tracking under occlusion and rotation.

<img src="./assets/results/high_psr.png" alt="High PSR" width="200"/>

---

### Low PSR Failure Case

Tracking fails when correlation response becomes ambiguous.

<img src="./assets/results/low_psr.png" alt="Low PSR" width="200"/>


---

### Correlation Response Surface

Frequency-domain correlation visualization.

<img src="./assets/results/correlation_surface.png" alt="Correlation" width="300"/>


---

### Kernel (Learned Filter)

Visualization of learned MOSSE filter.

<img src="./assets/results/kernel_response.png" alt="Kernel" width="400"/>


---

### Tracking Output

Real-time bounding box tracking with PSR display.

<img src="./assets/results/tracking_example.png" alt="Tracking" width="400"/>


---

## Evaluation

Comparison with classical methods:

- Cross-correlation (MATLAB)
- Template matching (OpenCV)

### Key Findings:
- MOSSE is robust under occlusion and rotation
- Classical template matching fails under appearance changes
- PSR effectively measures tracking confidence

---

## Controls

- Mouse Drag → Select ROI
- Space → Pause/Resume
- C → Clear trackers
- ESC → Exit

---

## Requirements

- Python 3.7+
- OpenCV
- NumPy
- Tkinter
- Matplotlib
---

## How to Run

```bash
pip install -r requirements.txt
python ui.py
