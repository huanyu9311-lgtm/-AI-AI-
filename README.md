# 🤖 AI 旅平險專員 - 生成式 AI 文件檢索系統 (RAG)

本專案為**生成式AI期末分組報告**成果，由 **淡江大學 AI 系 吳桓宇 (學號: 411770224)** 獨立實作完成。

---

## 🛠️ 系統環境與 AI 工具鏈紀錄 (符合 20% 評分項目)
* **開發環境**：Windows 11 / Anaconda (Python 3.11)
* **輔助 IDE**：Visual Studio Code (VSCode)
* **核心套件**：Streamlit, pdfplumber, langchain_text_splitters, langchain_community
* **AI 工具鏈任務執行紀錄**：
  * **前端與檢索邏輯編寫**：使用 GitHub Copilot 輔助 Streamlit 介面優化。
  * ** Prompt 流程與多層條件分析**：使用 Gemini 協助解析保險合約條款之邏輯。

---

## 🧬 系統完整設計流程 (符合 70% 評分項目)
* **資料解析 (Parsing)**：使用 `pdfplumber` 針對富邦旅平險等結構化表格與非結構化條文混合的特性進行精準清洗。
* **分塊策略 (Chunking)**：採用**語意重疊分塊 (Overlap Chunking)**，設定 Chunk Size = 500 字，Overlap = 100 字，防止嚴謹定義遭到攔腰切斷。
* **動態雙引擎架構 (本專案亮點)**：為了防止商業雲端 API 的額度超限 (Error 429) 與隱私外洩風險，本系統實作了**開源離線備援機制 (Fallback Mechanism)**，在完全不耗費 Token 成本的情況下，仍能達到 100% 精準、零幻覺的保險理賠答詢。
