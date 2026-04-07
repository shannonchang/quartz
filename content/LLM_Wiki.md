---
title: LLM Wiki（LLM 驅動知識庫）
tags: [LLM, Wiki, 知識圖, Markdown, Obsidian]
created: 2026-04-07
updated: 2026-04-07
source: raw/llm_wiki_vs_rag.txt
---

## 摘要（Summary）

LLM Wiki 是一種利用大型語言模型（LLM）將原始文件自動轉換為結構化知識庫的方法。知識庫通常以 Markdown 格式組織，每個概念為獨立節點，節點間以雙向連結（`[[...]]`）相互關聯，形成可視化的[[Knowledge_Graph|知識圖]]。相較於 [[RAG]] 的動態檢索架構，LLM Wiki 採用靜態預整理方式，知識結構清晰，易於人工審閱與編輯，適合管理組織的核心知識體系。

## 概念（Concepts）

- **節點（Node）**：知識庫中的最小單位，每個 Markdown 檔案代表一個知識節點
- **雙向連結（Bidirectional Link）**：`[[節點名稱]]` 語法，A 連結 B 同時 B 也需回指 A，確保知識圖完整性
- **[[Knowledge_Graph]]（知識圖）**：由節點與連結構成的圖狀知識結構，是 LLM Wiki 的核心架構
- **結構化 Markdown**：以統一 Schema 組織每個節點的摘要、概念、關聯等資訊
- **Obsidian 視覺化**：透過 Obsidian 工具，可將 `[[...]]` 連結以圖形方式呈現節點間關係

## LLM Wiki 建立流程

1. 閱讀原始文件（`raw/`），理解內容
2. 提取核心概念，決定需要建立的節點
3. 依 Schema 為每個概念建立 Markdown 節點
4. 建立雙向連結，確保連結完整
5. 更新 `wiki/index.md` 索引
6. 記錄操作於 `system/log.md`

## 優缺點

**優點：**
- 知識結構清晰，可全局理解
- 可人工審閱與編輯
- 查詢速度快（預先整理）
- 可用 Obsidian 等工具視覺化

**缺點：**
- 初期整理成本高
- 更新需手動介入
- 依賴 LLM 輸出品質

## 關聯（Links）

### 相關節點
- [[LLM_Wiki_vs_RAG]] — 比較 LLM Wiki 與 RAG 的完整分析
- [[RAG]] — LLM Wiki 的替代/互補方案
- [[Knowledge_Graph]] — LLM Wiki 的底層架構概念

### 上層概念
- [[LLM_Wiki_vs_RAG]] — 本節點屬於 RAG vs LLM Wiki 比較分析的子主題

### 下層概念
- [[Knowledge_Graph]] — LLM Wiki 中節點與連結構成的圖結構
