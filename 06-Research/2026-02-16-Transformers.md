---
title: "Transformer 深度解析：注意力機制與架構原理"
type: research
source: "論文：Attention Is All You Need (arXiv:1706.03762)"
tags: [topic/tech-trends, ai, ml, transformer]
status: completed
created: 2026-02-16
updated: 2026-02-16
related: []
---

## 摘要

Transformer 是 2017 年由 Google Brain、Google Research 和 University of Toronto 共同發表的深度學習架構，首次發表於論文《Attention Is All You Need》。它完全基於注意力機制（Attention Mechanism），摒弃了傳統的循環神經網路（RNN）和卷積神經網路（CNN），成為現代大型語言模型的基礎架構。

## 核心概念

### 1. 注意力機制（Attention Mechanism）

注意力機制讓模型在處理序列數據時，能夠動態關注輸入序列的不同部分：

- **Self-Attention（自注意力）**：輸入序列中每個詞可以關注序列中的所有其他詞
- **權重計算**：透過 Query、Key、Value 三個向量計算注意力權重
- **並行處理**：不同於 RNN 的順序處理，注意力機制可以並行計算，大幅提升訓練效率

### 2. 多頭注意力（Multi-Head Attention）

Transformer 使用多個注意力頭（Attention Heads）：

- 每個頭學習不同的注意力模式
- 標準配置：8 個頭
- 每個頭獨立的 Query、Key、Value 權重矩陣
- 最終合併所有頭的輸出

### 3. 位置編碼（Positional Encoding）

因為 Transformer 沒有循環結構，需要注入位置資訊：

- 使用正弦和餘弦函數
- 讓模型理解詞彙的順序關係
- 可擴展到任意長度序列

## 架構組成

### Encoder（編碼器）

1. **Multi-Head Self-Attention**
2. **Add & Norm**（殘差連接 + 層歸一化）
3. **Feed Forward Network**（前饋神經網路）
4. 重複 6 層

### Decoder（解碼器）

1. **Masked Multi-Head Self-Attention**
2. **Encoder-Decoder Attention**
3. **Add & Norm**
4. **Feed Forward Network**
5. 重複 6 層

## 運作流程

```
Input → Embedding → Positional Encoding
         ↓
    Encoder Stack
    (6 layers)
         ↓
    Decoder Stack
    (6 layers)
         ↓
   Linear + Softmax
         ↓
   Output Probabilities
```

## 關鍵創新

| 創新點 | 說明 |
|--------|------|
| 純注意力架構 | 摒弃 RNN/CNN，更易並行 |
| 多頭注意力 | 學習多種關係模式 |
| 殘差連接 | 訓練更深層網路 |
| 層歸一化 | 穩定訓練過程 |

## 優勢

1. **並行計算**：訓練速度大幅提升
2. **長距離依賴**：解決 RNN 的梯度消失問題
3. **可擴展性**：成為 GPT、BERT 等模型的基礎
4. **通用性**：適用於翻譯、文本生成、分類等多種任務

## 劣勢

1. **計算複雜度**：O(n²) 複雜度，長序列計算量大
2. **記憶體需求**：注意力矩陣需要大量記憶體
3. **順序感知**：需要額外的位置編碼

## 影響與應用

- **GPT 系列**：生成式預訓練變壓器
- **BERT**：雙向編碼器表示
- **Llama、Claude**：大型語言模型
- **Vision Transformer (ViT)**：影像處理

## 來源

- [Attention Is All You Need - arXiv](https://arxiv.org/abs/1706.03762)
- [Google AI Blog](https://ai.googleblog.com/2017/08/transformer-novel-neural-network.html)
