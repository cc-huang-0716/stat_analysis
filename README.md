# Statistical Analysis Notebooks

本專案整理了一組統計分析與機器學習練習 Notebook，內容涵蓋多元迴歸分析、分類模型、特徵工程、模型診斷與視覺化。
這些 Notebook 主要用於資料分析方法練習與模型比較，包含房價分類、棒球薪資分析與紅酒品質分析等主題。

---

## Project Overview

本專案包含三個主要分析案例：

* 房價資料分類模型比較
* 棒球打者薪資與表現指標分析
* 紅酒品質與化學特徵之迴歸分析

分析流程涵蓋：

* 資料讀取與清理
* 缺失值處理
* 特徵工程
* 相關係數分析
* 多元迴歸分析
* 分類模型訓練與比較
* 混淆矩陣與模型評估
* VIF 共線性檢測
* 殘差常態性與模型診斷

---

## Repository Structure

```text
.
├── House Pricing with Classification Models.ipynb
├── batter_csv.ipynb
├── wine.ipynb
└── README.md
```

---

## Notebook Description

### 1. `House Pricing with Classification Models.ipynb`

此 Notebook 以房價資料作為分析對象，將連續型房價轉換為分類問題，並比較多種分類模型的表現。

主要內容包含：

* 從 Google Drive 下載房價資料
* 檢查資料結構、缺失值與基本統計量
* 進行資料清理與缺失值補值
* 對類別變數進行編碼處理，包括：

  * One-hot Encoding
  * Target Encoding
  * Ordinal Mapping
* 使用相關係數與熱力圖進行 EDA
* 將房價依分位數切分為多個價格等級
* 訓練並比較多種分類模型

使用的模型包含：

* Gaussian Naive Bayes
* K-Nearest Neighbors
* Logistic Regression
* Decision Tree
* Random Forest
* Extra Tree
* Multi-layer Perceptron
* Stacking Classifier

模型評估方式包含：

* Accuracy
* Confusion Matrix
* Classification Report

---

### 2. `batter_csv.ipynb`

此 Notebook 使用棒球打者資料進行薪資分析，目標是觀察球員表現指標與薪資之間的關係。

主要內容包含：

* 讀取 `Hitters.csv` 資料集
* 處理數值型欄位缺失值
* 建立打擊相關特徵：

  * Batting Average
  * On-base Percentage
* 計算各數值變數與薪資之間的 Pearson 相關係數
* 篩選與薪資關聯較高的變數
* 建立多元線性迴歸模型
* 檢查模型解釋力與變數顯著性
* 使用 VIF 檢測多重共線性
* 使用 Shapiro-Wilk Test 檢查殘差常態性
* 使用 Rainbow Test 檢查模型線性假設

此 Notebook 主要展示如何從運動數據中建立特徵，並透過迴歸模型分析球員薪資與表現之間的關係。

---

### 3. `wine.ipynb`

此 Notebook 使用紅酒品質資料進行統計分析，目標是分析酒類化學特徵與品質評分之間的關係。

主要內容包含：

* 讀取 `wine.xlsx` 資料
* 計算各化學變數與品質分數之間的 Pearson 相關係數
* 繪製變數相關係數熱力圖
* 建立多元線性迴歸模型
* 檢查各變數對紅酒品質的解釋能力
* 使用 VIF 檢測多重共線性
* 使用 Shapiro-Wilk Test 檢查殘差常態性
* 繪製殘差圖
* 繪製 QQ Plot 檢查殘差分布
* 使用 Rainbow Test 進行模型診斷

此 Notebook 主要展示如何使用傳統統計方法分析品質評分型資料，並檢查迴歸模型假設是否合理。

---

## Methods Used

本專案使用的主要方法包括：

### Exploratory Data Analysis

* Descriptive Statistics
* Missing Value Analysis
* Correlation Analysis
* Heatmap Visualization

### Regression Analysis

* Ordinary Least Squares Regression
* Pearson Correlation
* Variance Inflation Factor
* Residual Analysis
* Shapiro-Wilk Normality Test
* Rainbow Test

### Classification Models

* Naive Bayes
* K-Nearest Neighbors
* Logistic Regression
* Decision Tree
* Random Forest
* Extra Tree
* Multi-layer Perceptron
* Stacking Ensemble

---

## Requirements

建議使用 Python 3.9 以上版本。

主要套件包含：

```text
pandas
numpy
matplotlib
seaborn
scipy
statsmodels
scikit-learn
gdown
openpyxl
jupyter
```

可以使用以下指令安裝：

```bash
pip install pandas numpy matplotlib seaborn scipy statsmodels scikit-learn gdown openpyxl jupyter
```

---

## How to Run

可以使用 Jupyter Notebook 或 Google Colab 開啟 `.ipynb` 檔案。

若在本機執行：

```bash
jupyter notebook
```

或：

```bash
jupyter lab
```

接著開啟對應的 Notebook 即可。

---

## Data Notes

本專案使用的資料來源包含：

* 房價資料：Notebook 中透過 `gdown` 從 Google Drive 下載
* 棒球打者資料：`Hitters.csv`
* 紅酒品質資料：`wine.xlsx`

部分資料檔案可能未包含於此 repo 中。若無法直接執行 Notebook，請確認對應資料檔案是否已放置於相同資料夾。

---

## Limitations

本專案主要作為統計分析與機器學習方法練習，因此仍有以下限制：

* Notebook 尚未模組化為完整 Python package
* 部分資料路徑與檔名仍需手動調整
* 模型參數多為基礎設定，尚未進行完整調參
* 部分分析以教學與練習為主，未必適合直接用於正式預測任務
* 房價分類任務將連續房價轉為分位數類別，較適合模型比較，不等同於完整房價預測系統

---

## Future Improvements

未來可進一步改善方向包括：

* 將重複的資料清理流程整理成 functions
* 建立統一的資料夾結構
* 將模型訓練與評估流程模組化
* 加入交叉驗證
* 加入超參數調整
* 增加模型比較表格
* 將 Notebook 重構為可重複執行的 Python scripts
* 補充資料來源與變數說明

---

## Disclaimer

This repository is for educational and portfolio purposes only.
The notebooks are designed for practicing statistical analysis, regression diagnostics, and machine learning model comparison.
