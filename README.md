# Real-Time 2D Fourier Epicycle Visualizer

An interactive 2D closed-curve visualizer built using **Discrete Fourier Transforms (DFT)**. This project computes complex Fourier coefficients from 2D spatial points and reconstructs the shape using a chain of relocating, rotating circles (epicycles).

It features a dual-screen, zero-latency web setup optimized for **Google Colab**, allowing you to draw on one screen while viewing real-time epicycle reconstruction on the second screen.

---

## Features

- **Dual-Screen Layout**:
  - **Screen 1 (Input)**: Draw any custom 2D closed curve using mouse or touch inputs.
  - **Screen 2 (Reconstruction)**: Watch a chain of relocating tip-to-tail rotating circles (epicycles) trace out your drawing in real time.
- **Dynamic Harmonics Control**: Adjust the number of Fourier modes (1–100) live via a slider to observe how higher frequencies add fine detail.
- **Python / Google Colab Ready**: Includes both a pure Python Matplotlib solution (`matplotlib.animation`) and a zero-latency embedded HTML5/JS canvas solution for Google Colab.
- **Automatic Center Alignment**: Re-centers sampled coordinate points automatically to ensure stable orbit centers.

---

## Math Overview

A 2D closed curve can be represented on the complex plane as a continuous function $z(t) = x(t) + i \cdot y(t)$ for $t \in [0, 2\pi]$.

1. **Sampling**: The curve is sampled into $N$ discrete points $z_k = x_k + i \cdot y_k$.
2. **Discrete Fourier Transform (DFT)**: The Fourier coefficient $c_n$ for frequency $n$ is calculated as:
   $$c_n = \frac{1}{N} \sum_{k=0}^{N-1} z_k \, e^{-i \frac{2\pi n k}{N}}$$
3. **Epicycle Representation**: Each term $c_n e^{i n t}$ represents a circle with radius $R_n = \vert{}c_n\vert{}$ rotating at frequency $n$ with initial phase $\phi_n = \arg(c_n)$. Arranging these vectors tip-to-tail creates the rotating epicycle chain.

---

## Getting Started

### 1. Running in Google Colab (Real-Time HTML5 Visualizer)

Open a new notebook in **Google Colab**, paste the embedded HTML/JavaScript code into a cell, and run it. 

- **Draw**: Click and drag on **Screen 1** to draw a custom shape.
- **Watch**: **Screen 2** instantly starts computing the DFT and animating the epicycles.
- **Adjust**: Slide the **Harmonics** control to change the number of active circles driving the tip.

### 2. Running Locally with Python

To run the offline Python Matplotlib script:

#### Prerequisites
Make sure you have Python 3.8+ installed along with the required dependencies:

```bash
pip install numpy matplotlib ipython
├── README.md
├── fourier_epicycles.py        # Python/Matplotlib animation script
└── colab_interactive.py        # HTML5/JS real-time widget script for Colab
