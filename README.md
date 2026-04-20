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

![UI](assets/ui_demo.png)

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
