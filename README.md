# Classical Edge and Line Detection: Canny, Hough, and RANSAC

This repository presents a **focused empirical study of classical computer vision methods** for edge and line detection in road-like images.  
The goal is not to build a production-ready system, but to **analyze robustness, parameter sensitivity, and failure modes** of widely used techniques.

---

## Motivation

Despite the dominance of deep learning, classical vision pipelines remain relevant for:
- interpretability
- low-compute environments
- geometric reasoning

This project explores how traditional methods behave under controlled perturbations, providing intuition about when and why they succeed or fail.

---

## Methods Overview

The pipeline consists of three main stages:

- **Canny Edge Detection**  
  Automatic threshold selection is used to study the trade-off between noise sensitivity and edge preservation.

- **Probabilistic Hough Transform (HoughLinesP)**  
  Line segments are detected and evaluated using an edge coverage metric to assess how well dominant structures are captured.

- **RANSAC-based Dominant Line Estimation**  
  A robust fitting approach is applied to edge points to recover a single dominant scene structure under noise and fragmented edges.

---

## Key Observations

- Canny performance is highly sensitive to threshold selection, with moderate ranges providing the best balance.
- HoughLinesP reliably detects strong, continuous road lines but struggles with weak or fragmented boundaries.
- RANSAC is robust to noise and clutter, producing a stable global line model, but is limited to capturing a single dominant structure.

These observations align with known theoretical properties of each method.

---

## Scope and Limitations

This project is **analytical rather than benchmark-driven**.  
It focuses on qualitative and simple quantitative insights rather than optimizing performance metrics or comparing against deep models.

---

## Possible Extensions

- Quantitative evaluation with ground truth lane annotations
- Multi-model RANSAC for multiple line hypotheses
- Integration with learning-based edge detectors
- Hybrid pipelines combining classical and deep methods

---

## Disclaimer

This repository is intended for educational and exploratory research purposes only.
