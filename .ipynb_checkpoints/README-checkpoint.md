# MLB 球員下一年薪資預測

使用 2013–2023 年大聯盟打者與投手表現數據，預測下一年薪資（log(salary) 為目標變數）。

## 目前進度 (2026/02)
- 完成資料前處理、年資計算、one-hot status
- 打者模型：XGBoost + 正則化優化，測試集 R² = 0.2933（訓練 R² 0.7186）
- 投手模型：正在訓練中
- 特徵選擇：使用 RF 重要度 + 共線性處理（刪除 G、xFIP、FIP 等冗餘特徵）

## 技術堆疊
- 資料：pybaseball, pandas
- 模型：XGBoost
- 視覺化：matplotlib, seaborn
- 版本控制：Git + GitHub

## 目前結果
- **打者**：測試 R² 0.2933，RMSE 1.0692（log scale）
- **過擬合改善**：訓練-測試差距從 0.626 → 0.425
- **最重要特徵**：service_time (38%) → 年資對薪資影響極大

## 優化方向
- 加入 lag_1_log_salary（前一年薪資）預期大幅提升
- 訓練 投手模型
- 開發 Streamlit 互動預測 App

## 執行方式
1. `git clone https://github.com/joshninjatw/mlb-salary-prediction.git`
2. 開啟 `MLB_Salary_Prediction.ipynb`
3. 執行所有 cell

歡迎 issue 或 PR！  
林加 | Email: [a89931891@gmail.com] | 