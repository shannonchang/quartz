---
title: AI 工作流（AI Workflow）
tags: [topic, AI, LLM, RAG, 知識管理, 向量資料庫]
created: 2026-05-28
updated: 2026-05-28
type: topic
---

## 主題摘要

以 LLM 為核心的知識管理與 AI 工程基礎設施。本主題涵蓋兩條主線：**知識管理架構**（LLM Wiki vs RAG 的選擇框架、Knowledge Graph 的結構化表示）與 **AI 落地技術**（Embedding 的語意基礎、Agentic AI 的企業部署趨勢）。兩條主線在「如何讓 AI 有效使用人類知識」這個問題上交匯。

> 資料有了，檢索邏輯有了，生成模型有了——三者如何整合，決定了 AI 工作流的上限。

## 聚合節點

| 節點 | 核心主張 | 層次 |
|------|---------|------|
| [[LLM_Wiki]] | 以 LLM 將文件轉為結構化知識庫，透過雙向連結建立知識圖 | 知識管理架構 |
| [[RAG]] | 結合檢索系統與生成模型，適合處理大量即時更新資料 | 知識管理架構 |
| [[Knowledge_Graph]] | 以節點與邊構成的圖狀知識結構，強調概念間關聯性 | 知識表示層 |
| [[Embedding]] | 將文字轉換為稠密向量，捕捉語意相似性，是 RAG 的核心技術 | 技術基礎層 |
| [[Agentic_AI]] | Agentic AI 大規模落地：Claude +340% 滲透率，推論超越訓練 | AI 落地趨勢 |

## 跨節點綜合

### LLM Wiki vs RAG 決策框架

見 [[LLM_Wiki_vs_RAG]]（補充節點）的完整比較。簡要：
- **LLM Wiki**：知識結構化、長期累積、不需即時更新 → 適合個人知識庫
- **RAG**：大量文件、需要最新資訊、多用戶查詢 → 適合企業知識庫

### 技術堆疊層次

`
應用層：Agentic AI（推論、決策、執行）
知識層：LLM Wiki / RAG（知識組織方式）
表示層：Knowledge Graph（結構）
技術層：Embedding + Vector DB（語意索引）
`

### Agentic AI 的資源需求

[[Agentic_AI]] 的落地趨勢直接驅動 [[AI生產力循環]]（跨主題）：
推論算力需求 → CoWoS/HBM 供應鏈 → 台積電 N3 追加產能

## 關聯（Links）

### 包含節點
- [[LLM_Wiki]]
- [[RAG]]
- [[Knowledge_Graph]]
- [[Embedding]]
- [[Agentic_AI]]

### 相關主題
- [[AI生產力循環]] — Agentic AI 落地的宏觀產業影響
- [[AI投資日報系統]] — AI 工作流技術的具體實作案例
- [[LLM_Wiki_vs_RAG]] — 架構選擇的完整對比分析
