---
title: RAG（檢索增強生成）
tags: [RAG, 檢索, 生成模型, 向量資料庫, NLP]
created: 2026-04-07
updated: 2026-04-07
source: raw/llm_wiki_vs_rag.txt
---

## 摘要（Summary）

RAG（Retrieval-Augmented Generation，檢索增強生成）是一種結合資訊檢索系統與大型語言模型的架構。其核心思想是：在生成答案前，先從外部文件庫中動態檢索出最相關的片段，再將這些片段作為上下文提供給 LLM 生成最終答案。RAG 特別適合需要處理即時資料或大量文件的場景，但因文件被切分為獨立片段，容易導致知識碎片化，缺乏全局理解能力。

## 概念（Concepts）

- **Chunks（文件片段）**：原始文件被切分為多個較小的單位，是 RAG 處理的基本單元
- **[[Embedding]]（向量嵌入）**：使用 Embedding 模型將文字轉換為稠密向量，捕捉語意資訊
- **[[Vector_Database]]（向量資料庫）**：儲存所有文件片段的向量表示，支援相似度搜尋
- **語意檢索（Semantic Retrieval）**：根據查詢向量，從向量資料庫中找出語意最相近的片段
- **上下文注入（Context Injection）**：將檢索到的片段與用戶問題一起送入 LLM，引導其生成準確答案

## RAG 處理流程

1. 將文件切分為多個片段（Chunks）
2. 使用 [[Embedding]] 模型將每個片段轉為向量
3. 將向量儲存至 [[Vector_Database]]
4. 接收用戶查詢，將查詢也轉為向量
5. 從向量資料庫中檢索語意最相近的 Top-K 片段
6. 將片段 + 查詢一起送入 LLM，生成最終答案

## 優缺點

**優點：**
- 可處理即時更新的資料
- 適合大量文件的場景
- 無需重新訓練模型即可擴展知識

**缺點：**
- 知識碎片化，缺乏全局理解
- 依賴向量資料庫的維護
- 檢索品質影響最終答案品質

## 關聯（Links）

### 相關節點
- [[LLM_Wiki_vs_RAG]] — 比較 RAG 與 LLM Wiki 的完整分析
- [[LLM_Wiki]] — RAG 的替代/互補方案
- [[Vector_Database]] — RAG 架構中儲存向量的核心元件
- [[Embedding]] — RAG 流程中文字向量化的關鍵技術

### 上層概念
- [[LLM_Wiki_vs_RAG]] — 本節點屬於 RAG vs LLM Wiki 比較分析的子主題

### 下層概念
- [[Vector_Database]] — RAG 使用的儲存系統
- [[Embedding]] — RAG 使用的向量化技術
