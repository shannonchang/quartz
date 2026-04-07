---
title: LLM Wiki 與 RAG 的差異分析
tags: [LLM, RAG, 知識管理, 比較分析]
created: 2026-04-07
updated: 2026-04-07
source: raw/llm_wiki_vs_rag.txt
---

## 摘要（Summary）

隨著大型語言模型（LLM）的發展，企業開始探索不同的知識管理方法。[[RAG]]（檢索增強生成）與 [[LLM_Wiki]] 是兩種主要方案：RAG 依賴[[Vector_Database|向量資料庫]]與即時檢索，將文件切分後動態組合答案；LLM Wiki 則透過預先整理知識、建立[[Knowledge_Graph|知識圖]]與雙向連結，提供結構化的靜態知識庫。兩者並非互斥，最佳實踐是結合兩者優勢：以 LLM Wiki 管理核心知識，以 RAG 處理即時或大量資料。

## 概念（Concepts）

- **RAG（檢索增強生成）**：結合檢索系統與 LLM 的架構，先從文件庫中找出相關片段，再由 LLM 生成答案
- **LLM Wiki**：利用 LLM 將原始文件轉為結構化 Markdown 知識庫，以雙向連結建立節點間關聯
- **知識碎片化**：RAG 的主要缺點，因文件被切分為獨立 chunks，缺乏全局理解能力
- **靜態知識庫**：LLM Wiki 的特性，知識預先整理固化，查詢速度快但更新需人工介入
- **互補架構**：兩種方案的最佳組合策略，以 Wiki 管核心、RAG 處理動態資料

## 比較表

| 面向 | RAG | LLM Wiki |
|------|-----|----------|
| 資料更新 | 動態，即時 | 靜態，需手動更新 |
| 查詢速度 | 需即時檢索 | 快速（預先整理） |
| 知識結構 | 碎片化 | 結構清晰 |
| 維護複雜度 | 需維護向量資料庫 | 易於人工編輯 |
| 全局理解 | 弱 | 強 |
| 適用場景 | 大量文件、即時資料 | 核心知識、概念體系 |

## 關聯（Links）

### 相關節點
- [[RAG]] — 本文比較的主要方案之一，詳細說明 RAG 的架構與特性
- [[LLM_Wiki]] — 本文比較的另一主要方案，說明 Wiki 型知識庫的運作方式
- [[Vector_Database]] — RAG 架構的核心元件
- [[Knowledge_Graph]] — LLM Wiki 的底層概念，雙向連結構成知識圖
- [[Embedding]] — RAG 流程中將文字轉為向量的關鍵技術

### 上層概念
- 知識管理架構（Knowledge Management Architecture）

### 下層概念
- [[RAG]] — RAG 方案詳述
- [[LLM_Wiki]] — LLM Wiki 方案詳述
