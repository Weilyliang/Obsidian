---
title: "Transformer 技術摘要"
type: note
source: "論文：Attention Is All You Need (arXiv:1706.03762)"
tags: [topic/tech-trends, ai, ml, transformer]
status: completed
created: 2026-02-16
updated: 2026-02-16
related: [06-Research/2026-02-16-Transformers]
---

## 什麼是 Transformer？

2017 年 Google 發表的深度學習架構，是現在所有大型語言模型（GPT、Claude 等）的基礎。

## 核心原理

**關鍵創新：注意力機制（Attention）**

- 讓模型「同時看見」輸入的所有詞彙
- 不像舊方法（RNN）需要順序處理
- 可並行計算，訓練速度快

## 架構兩大部分

| 元件 | 功能 |
|------|------|
| Encoder | 理解輸入內容 |
| Decoder | 生成輸出內容 |
| Multi-Head Attention | 多個注意力頭，學習不同關係 |
| Positional Encoding | 理解詞彙順序 |

## 優點 vs 缺點

| 優點 | 缺點 |
|------|------|
| ✅ 訓練速度快（可並行） | ❌ 長序列計算量大 |
| ✅ 處理長距離依賴 | ❌ 記憶體需求高 |
| ✅ 成為 LLM 基礎架構 | |

## 應用場景

- 語言模型：GPT、BERT、Claude
- 翻譯、摘要、問答
- 影像：Vision Transformer (ViT)

## 資料來源

- [arXiv 論文](https://arxiv.org/abs/1706.03762)
