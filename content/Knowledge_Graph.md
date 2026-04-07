---
title: 知識圖（Knowledge Graph）
tags: [知識圖, 圖資料庫, 節點, 連結, LLM Wiki]
created: 2026-04-07
updated: 2026-04-07
source: raw/llm_wiki_vs_rag.txt
---

## 摘要（Summary）

知識圖（Knowledge Graph）是以節點（Node）與邊（Edge）構成的圖狀資料結構，用來表示現實世界中實體及其相互關係。每個節點代表一個概念或實體，邊代表兩者間的關係。在 [[LLM_Wiki]] 架構中，知識圖透過 Markdown 的 `[[...]]` 雙向連結實作，並可使用 Obsidian 等工具進行視覺化，讓使用者直觀地瀏覽概念間的關聯網絡。

## 概念（Concepts）

- **節點（Node）**：圖中的基本單位，代表一個知識概念或實體
- **邊（Edge）**：連接兩個節點的關係，在 LLM Wiki 中以 `[[...]]` 連結表示
- **雙向連結（Bidirectional Link）**：若 A 指向 B，則 B 也必須有指向 A 的連結，確保圖的完整性
- **知識密度（Knowledge Density）**：一個節點與其他節點的連結數量，反映其在知識圖中的重要程度
- **Obsidian**：支援 `[[...]]` 語法並可視覺化知識圖的 Markdown 編輯器工具

## 知識圖 vs. 其他知識表示方式

| 方式 | 特點 | 適用場景 |
|------|------|----------|
| 知識圖 | 關係豐富、可視化 | 概念體系、知識探索 |
| 關聯式資料庫 | 結構嚴謹、查詢精確 | 交易型資料 |
| [[Vector_Database]] | 語意相似、動態 | 大量文件、模糊搜尋 |

## 關聯（Links）

### 相關節點
- [[LLM_Wiki]] — 知識圖是 LLM Wiki 的核心架構，透過雙向連結實作
- [[LLM_Wiki_vs_RAG]] — 知識圖是 LLM Wiki 相較於 RAG 的主要優勢
- [[Vector_Database]] — 另一種知識表示方式，與知識圖形成對比

### 上層概念
- [[LLM_Wiki]] — 知識圖是 LLM Wiki 的底層組織原則

### 下層概念
- 節點（Node）— 知識圖的基本單位，對應各 wiki 頁面
