# **3-adic Collatz Stained Glass Evolution**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

## **3進対数螺旋空間における Collatz-3 逆写像の Voronoi 分割可視化ツール**

Hiroshi Harada - April 25, 2026

本リポジトリは、3-adic Collatz 写像（3進コラッツ問題）の逆写像（preimage tree）が形成する幾何学的トポロジーを、**base-3（3進）対数螺旋空間**と **Voronoi 分割**を用いて可視化するPython ジェネレーターです。

数論的な階層構造を、極彩色の「密充填タイル（ステンドグラス）」として描画・アニメーション化します。

---

## 🌟 **概要 (Overview)**

古典的な $3n+1$ 問題は 2-adic な性質を持ちますが、本プロジェクトでは平衡三進法（balanced ternary）に基づく **Collatz-3 写像** を対象とします。

自然数を base-3 対数螺旋空間に配置し、それぞれの数が1に到達するまでのステップ数（Depth）を計算します。

その Depth を累積分布関数（CDF）を用いて正規化し、Voronoi セルを着色することで、以下のような 3-adic 特有の隠された幾何学構造を明らかにします。

* **$9m\pm2$ 二重螺旋マガジン:** トグル構造によるコントラストの連鎖
* **$a \cdot 3^b$ ランチャー:** 放射状に伸びる合流幹
* **深層ノードの充填:** 軌道の深い数（28, 62, 98など）が空間の外周の隙間を埋める現象

詳細な数学的背景と考察については、同梱の Research Report (PDF) をご参照ください。

---

## ⚙️ **動作環境 (Prerequisites)**

本プログラムは Python 3.8 以上で動作します。実行には以下のライブラリが必要です。

```bash
pip install numpy matplotlib scipy
```

*(※ アニメーションGIFの生成には `Pillow` が内部で使用されますが、通常は `matplotlib` と共にインストールされます。外部の `ffmpeg` 等は不要です)*

---

## 🚀 **使い方 (Usage)**

本リポジトリには2つのコアスクリプトが含まれています。

### 1. 静止画ジェネレーター (高解像度 PNG)
指定した範囲（デフォルトは $n=1000$ まで）のステンドグラスを生成し、論文用の高解像度画像として保存します。

```bash
python code_01_image_collatz3_voronoi.py
```
**出力:** `collatz3_stained_glass_n1000.png`

### 2. 進化アニメーションジェネレーター (GIF)
深さ（Depth）0から順に、逆写像の連鎖が暗闇から点灯していくアニメーション動画を生成します。

```bash
python code_02_animation_collatz3_voronoi.py
```
**出力:** `collatz3_stained_glass_n1000.gif` (※ フレーム数により生成に1〜2分程度かかります。コンソールに進捗が表示されます)

---

## 📐 **数学的仕様 (Mathematical Specifications)**

**1. 写像空間 (Base-3 Logarithmic Spiral Plane)**
自然数 $n$ は以下の極座標 $(r, \theta)$ へ写像されます。

$$r = \log_3(n), \quad \theta = 2\pi \{ \log_3(n) \}$$

**2. Collatz-3 アルゴリズム**

$$f(n) = \begin{cases} n/3 & (n \equiv 0 \pmod 3) \\ (4n-1)/3 & (n \equiv 1 \pmod 3) \\ (4n+1)/3 & (n \equiv 2 \pmod 3) \end{cases}$$

**3. 色彩分布 (CDF Normalization)**
視覚的な偏りを防ぐため、深さをCDF（累積分布関数）で正規化し、色が均等に広がるようにしています（グラデーション：青→緑→黄→橙→赤）。

$$p(n) = \mathrm{CDF}(\mathrm{depth}(n))$$

---

## 📜 **ライセンス (License)**

本プロジェクトでは、用途に応じて以下のライセンスを採用しています。

* **Research documents & Images:** [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
* **Python source code:** [MIT License](https://opensource.org/licenses/MIT)

Copyright (c) 2026 Hiroshi Harada

