---
title: 向量資料庫（Vector Database）
tags: [向量資料庫, Embedding, RAG, 相似度搜尋]
created: 2026-04-07
updated: 2026-04-07
source: raw/llm_wiki_vs_rag.txt
---

## 摘要（Summary）

向量資料庫（Vector Database）是一種專門儲存和查詢向量（高維度數值陣列）的資料庫系統。在 NLP 和 AI 應用中，文字、圖像等非結構化資料會先透過 [[Embedding]] 模型轉換為向量，再儲存至向量資料庫。查詢時，系統計算查詢向量與儲存向量間的相似度（通常使用餘弦相似度或歐氏距離），找出最相近的結果。向量資料庫是 [[RAG]] 架構中不可或缺的核心元件。

## 概念（Concepts）

- **向量（Vector）**：以高維度數值陣列表示的資料，每個維度捕捉一種語意特徵
- **[[Embedding]]**：將文字轉換為向量的模型與過程
- **相似度搜尋（Similarity Search）**：在向量空間中找出與查詢最相近的向量
- **餘弦相似度（Cosine Similarity）**：衡量兩向量方向相似程度的常用指標，值域 [-1, 1]
- **ANN（近似最近鄰）**：為提高效率的近似搜尋演算法，如 HNSW、IVF 等
- **常見實作**：Pinecone、Weaviate、Chroma、Qdrant、pgvector（PostgreSQL 擴充）

## 與傳統資料庫的差異

| 面向 | 傳統關聯式資料庫 | 向量資料庫 |
|------|-----------------|-----------|
| 查詢方式 | 精確比對（SQL） | 相似度搜尋 |
| 資料型態 | 結構化表格 | 高維向量 |
| 適用場景 | 精確查詢、交易 | 語意搜尋、推薦 |

## 關聯（Links）

### 相關節點
- [[RAG]] — 向量資料庫是 RAG 架構的核心儲存元件
- [[Embedding]] — 生成向量的技術，與向量資料庫緊密配合
- [[LLM_Wiki_vs_RAG]] — 討論向量資料庫在 RAG 中的角色
- [[Knowledge_Graph]] — 知識圖是另一種知識組織方式，與向量資料庫形成對比

### 上層概念
- [[RAG]] — 向量資料庫是 RAG 流程的基礎設施

### 下層概念
- [[Embedding]] — 儲存至向量資料庫前必須先進行 Embedding
