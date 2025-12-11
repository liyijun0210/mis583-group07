# PastureMask-MTLNet: 牧草生物量多模態預測模型
### MIS583 期末專題 - 第七組 (Group 07)

## 📖 專案簡介
本專案旨在利用深度學習預測牧草生物量 (Pasture Biomass)。針對純影像預測的物理極限，我們提出了 **多模態強基線模型 (Multimodal Strong Baseline)**，將影像特徵與環境結構化數據（Metadata）進行融合。

我們提出的 **PastureMask-MTLNet** 架構結合了 **Soft Mask Attention (SMA)** 與 **多任務學習 (MTL)**，在提升預測精度的同時，也解決了背景雜訊干擾的問題。

## 檔案結構說明
本儲存庫包含不同模型架構的實驗程式碼：

| 檔案名稱 | 模型骨幹 | 輸入模態 | 說明 |
|:---|:---|:---|:---|
| `WEAK-ResNet.ipynb` | ResNet-18 | **純影像** | 弱基線模型。僅使用 CNN 提取視覺特徵，用於測試純視覺的效能天花板。 |
| `STRONG-ResNet.ipynb` | ResNet-18 | **影像 + Metadata** | 強基線模型。融合環境數據（如季節、高度），證實了結構化特徵對輕量模型的重要性。 |
| `WEAK_EFFICIENT.ipynb`| EfficientNet-B0| **純影像** | 使用更強大的 CNN 骨幹，測試高階模型在純視覺下的表現。 |
| `STRONG_EFFICIENT.ipynb`| EfficientNet-B0| **影像 + Metadata**| 測試強特徵提取器是否仍需依賴外部數據。 |

## 核心技術
1.  **Soft Mask Attention (SMA):** 輕量級注意力機制，強制模型忽略土壤與陰影，聚焦於綠色植被區域。
2.  **多任務學習 (Multi-Task Learning, MTL):** 同時預測「生物量」與「覆蓋率」，輔助模型理解牧草的空間結構。
3.  **多模態融合 (Multimodal Fusion):** 結合非結構化影像與結構化環境數值，突破單一模態的預測瓶頸。

---
**開發團隊:** MIS583 Group 07
