---
title: AI 投資日報系統（AI Investment Daily Briefing）
tags: [AI, 自動化, GitHub Actions, Claude API, LINE, 投資, 系統架構]
created: 2026-05-14
updated: 2026-05-14
source: raw/ai-investment-wiki.html
---

## 摘要（Summary）

AI 投資日報是一個以 GitHub Actions 排程、Claude Haiku API 分析、LINE Messaging API 推播的全自動投資資訊系統。每天早上 08:00 自動抓取台積電/NVIDIA/ETF/總經四類新聞，由 Claude 判讀利多/利空/今日關注，直送 LINE 通知。Phase 0 月費約 $0.03 USD。

> 先讓每天真的會用的 workflow 跑起來，比做最炫技的 agent system 重要很多。

## 系統架構

```
GitHub Actions（每天 08:00 台灣時間，UTC 00:00）
  ↓
RSS 抓取新聞（Google News）
  ├─ 台積電 / TSMC
  ├─ NVIDIA / AI 晶片
  ├─ ETF（0050 / 00878）
  └─ Fed / 總經
  ↓
Claude Haiku API 分析（利多 / 利空 / 今日關注）
  ↓
LINE Messaging API 推播
```

## 技術元件

| 元件 | 用途 | 備註 |
|------|------|------|
| GitHub Actions | 排程執行（週一到五） | cron: `0 0 * * 1-5` |
| Claude Haiku | 新聞分析 | `claude-haiku-4-5-20251001`，月費 ~$0.03 USD |
| LINE Messaging API | 推播通知 | LINE Notify 已於 2025/03/31 關閉，需改用此 API |
| feedparser | RSS 抓取 | Python 套件 |

## 關鍵設定要點

**GitHub Secrets**（三個，名稱大小寫必須完全一致）：
- `ANTHROPIC_API_KEY`
- `LINE_CHANNEL_ACCESS_TOKEN`
- `LINE_USER_ID`

**常見錯誤**：
- env 縮排放在 job 層而非 step 層 → Python 讀不到環境變數
- 本機測試：`export` 等號後不能有空格
- LINE 推播 403 → 尚未對 LINE Official Account 加好友

## 升級路線圖

| 階段 | 功能 | 技術 |
|------|------|------|
| **Phase 0**（現在） | 每日新聞摘要 + LINE 推播 | Python + GitHub Actions + Claude Haiku + LINE |
| Phase 1 | Notion 存檔、歷史查詢 | Notion API 作為 AI Memory Layer |
| Phase 2 | 多 Agent 分工 | n8n orchestration：Macro / Chip / ETF / Sentiment Agent |
| Phase 3 | 向量記憶 + 趨勢分析 | Supabase + LangGraph + Vector DB，長期記憶與跨時間趨勢 |

## 與 Wiki 其他節點的對應

| 節點 | 關聯 |
|------|------|
| [[Agentic_AI]] | 本系統是 Agentic AI 的實際落地案例：Claude 執行多步驟分析任務 |
| [[AI生產力循環]] | 系統監控的核心標的（台積電、NVIDIA、AI 供應鏈）即循環的核心指標 |
| [[AI半導體供應鏈]] | 台積電/NVIDIA 新聞是本系統的主要資訊來源 |
| [[RAG]] | Phase 3 的向量記憶架構即 RAG 的實際應用 |
| [[LLM_Wiki]] | 本系統本身就是一個 LLM Wiki 的實踐：用 Claude 將新聞轉為結構化判讀 |
| [[思考槓桿]] | 系統提供「一手資訊」（財報/新聞來源）的自動化過濾，對應思考槓桿中的資訊品質管理 |
| [[納瓦爾式學習]] | Code & Media 槓桿的具體實踐：寫一個 script，每天自動產出投資判讀 |

## 關聯（Links）

### 相關節點
- [[Agentic_AI]] — 本系統是 Claude API 作為分析 agent 的最小可行實作
- [[AI生產力循環]] — 監控標的與循環指標高度重疊
- [[RAG]] — Phase 3 向量記憶是 RAG 的完整落地
- [[思考槓桿]] — 自動化過濾資訊，守護注意力資源
- [[納瓦爾式學習]] — Code 槓桿：自動產出分析，邊際成本趨零

### 上層概念
- [[Agentic_AI]] — 本系統是 Agentic AI 的最小落地實作

### 下層概念
- 無（具體技術見 [[RAG]]、[[LLM_Wiki]]）
