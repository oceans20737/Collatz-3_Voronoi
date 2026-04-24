# **3-adic Collatz Stained Glass Evolution**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

> ## **Voronoi Partitioning Visualization of the Collatz-3 Inverse Map in Base-3 Logarithmic Spiral Space**

**Hiroshi Harada — April 25, 2026**

This repository provides a Python-based generator that visualizes the geometric topology formed by the preimage tree of the 3-adic Collatz mapping. By combining a **base-3 logarithmic spiral plane** with **Voronoi partitioning**, it reveals the profound number-theoretic hierarchical structure as highly saturated stained-glass dense-packing tiles and animates its evolution.

---

## 🌟 **Overview**

While the classical $3n+1$ problem exhibits strong 2-adic properties, this project focuses on the **Collatz-3 mapping**, which is based on a balanced ternary framework.

Natural numbers are plotted onto a base-3 logarithmic spiral space, and the total stopping time (Depth)—the number of steps required for each number to reach 1—is calculated. By normalizing this Depth using a Cumulative Distribution Function (CDF) and color-coding the Voronoi cells, the following hidden geometric structures unique to the 3-adic topology are revealed:

* **$9m\pm2$ Dual-Helix Magazines:** Chains of high-contrast color shifts driven by a toggle structure.
* **$a \cdot 3^b$ Launchers:** Radially expanding confluence trunks.
* **Deep-Layer Node Packing:** Numbers with exceptionally deep trajectories (e.g., 28, 62, and 98) filling the voids and gaps in the outer regions of the diagram.

For a detailed mathematical background and discussion, please refer to the included Research Report (PDF).

---

## ⚙️ **Prerequisites**

This program requires Python 3.8 or higher. Install the necessary dependencies using `pip`:

```bash
pip install numpy matplotlib scipy
```

*(Note: The `Pillow` library is used internally to generate the animated GIF, but it is typically installed alongside `matplotlib`. No external software like `ffmpeg` is required.)*

---

## 🚀 **Usage**

This repository contains two core scripts:

### 1. Static Image Generator (High-Resolution PNG)
Generates the stained glass visualization for a specified range (default is up to $n=1000$) and saves it as a high-resolution image suitable for academic papers.

```bash
python code_01_image_collatz3_voronoi.py
```
**Output:** `collatz3_stained_glass_n1000.png`

### 2. Evolution Animation Generator (GIF)
Generates an animation showing the sequential emergence of the inverse map from Depth 0 upward.

```bash
python code_02_animation_collatz3_voronoi.py
```
**Output:** `collatz3_stained_glass_n1000.gif` *(Note: Rendering may take 1-2 minutes depending on the frame count. Progress will be displayed in the console.)*

---

## 📐 **Mathematical Specifications**

**1. Mapping Space (Base-3 Logarithmic Spiral Plane)**
Natural numbers $n$ are mapped to the following polar coordinates $(r, \theta)$:

$$r = \log_3(n), \quad \theta = 2\pi \{ \log_3(n) \}$$

**2. Collatz-3 Algorithm**

$$f(n) = \begin{cases} n/3 & (n \equiv 0 \pmod 3) \\ (4n-1)/3 & (n \equiv 1 \pmod 3) \\ (4n+1)/3 & (n \equiv 2 \pmod 3) \end{cases}$$

**3. Color Distribution (CDF Normalization)**
To prevent visual bias and ensure an equal spread of colors (Gradient: Blue $\rightarrow$ Green $\rightarrow$ Yellow $\rightarrow$ Orange $\rightarrow$ Red), the depth is normalized using the Cumulative Distribution Function (CDF):

$$p(n) = \mathrm{CDF}(\mathrm{depth}(n))$$

---

## 📜 **License**

This project applies the following licenses depending on the content:

* **Research documents & Images:** [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
* **Python source code:** [MIT License](https://opensource.org/licenses/MIT)

Copyright (c) 2026 Hiroshi Harada
