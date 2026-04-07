---
title: Embedding（文字向量化）
tags: [Embedding, 向量, NLP, 語意, RAG]
created: 2026-04-07
updated: 2026-04-07
source: raw/llm_wiki_vs_rag.txt
---

## 摘要（Summary）

Embedding（嵌入）是將離散的符號（如文字、詞彙）轉換為連續的稠密向量（Dense Vector）的技術。透過 Embedding 模型，語意相近的文字在向量空間中的距離也會相近，使得機器能夠理解語意相似性。在 [[RAG]] 流程中，Embedding 是將文件片段與用戶查詢轉為向量的關鍵步驟，向量化後的資料才能儲存至 [[Vector_Database]] 並進行相似度搜尋。

## 概念（Concepts）

- **稠密向量（Dense Vector）**：每個維度都有數值的向量表示，維度通常為 768~4096
- **語意空間（Semantic Space）**：向量空間中，語意相近的詞彙/句子在幾何上也相近
- **Embedding 模型**：生成 Embedding 的神經網路模型，如 OpenAI `text-embedding-ada-002`、`sentence-transformers` 等
- **文件級 Embedding vs. 詞級 Embedding**：現代 RAG 主要使用句子/段落級 Embedding（如 BERT、S-BERT）
- **向量維度（Dimension）**：Embedding 的向量長度，影響資訊密度與計算成本

## Embedding 在 RAG 中的角色

```
原始文件 → [Embedding 模型] → 向量 → [Vector Database]
                                              ↓
用戶查詢 → [Embedding 模型] → 查詢向量 → 相似度搜尋 → Top-K 片段
```

## 關聯（Links）

### 相關節點
- [[RAG]] — Embedding 是 RAG 流程的核心步驟
- [[Vector_Database]] — 儲存 Embedding 向量的資料庫
- [[LLM_Wiki_vs_RAG]] — Embedding 是 RAG 架構的關鍵技術

### 上層概念
- [[RAG]] — Embedding 是 RAG 架構的基礎技術元件

### 下層概念
- [[Vector_Database]] — Embedding 的結果儲存於此
