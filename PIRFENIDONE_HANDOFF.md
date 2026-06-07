# Pirfenidone 專案交班單

## 專案目的

建立一份可直接開啟的 HTML，向臨床同仁解釋 pirfenidone 在 IPF 的角色，重點包含：

- Guideline 中的定位。
- AE 相關證據，並先同時涵蓋 acute exacerbation 與 adverse events 兩種可能意思。
- 與 nintedanib 的差異，以及哪些病人可能較適合 pirfenidone。

## 2026-06-08 Codex

### GitHub 發布補充

- 使用者提供 GitHub repo：`https://github.com/itrytodoit-code/pirfenidone.git`。
- 已在 `MSGH/Pirfenidone/` 初始化獨立 Git repo。
- 因 Git ownership 保護，已將本專案路徑加入 Git `safe.directory`。
- 因本機 Git 未設定作者，已在此 repo local config 設定：
  - `user.name=Codex`
  - `user.email=codex@local`
- 已設定遠端 `origin`。
- 已建立 initial commit：`02af3b8 Initial pirfenidone teaching deck`。
- 已成功 push `main` 到 GitHub。

### 本次任務

使用者要求：

- 找出先前提到的 nintedanib vs pirfenidone meta-analysis / network meta-analysis 的期刊地址。
- 查看 Claude 工作狀態。
- 接手並修正 `index.html` 中較怪或語氣過強的內容。

### 本次任務補充

使用者指出全螢幕後版面浪費太多，希望全螢幕後畫面就是一張投影片，並要求 push 到 GitHub。
使用者後續指出 topic 選擇在右側垂直排列會遮住內容，要求改為右上方平行排列。

### Claude / 協作狀態

- 已讀 `CLAUDE.md` 與本專案交班單。
- 未在 `PIRFENIDONE_HANDOFF.md` 或 `MSGH_HANDOFF.md` 看到 Claude 對 Pirfenidone 專案的正式交班紀錄。
- `index.html` 實際內容已不是交班單記錄的 14 張版本，而是擴充到 31 張左右，推測中間曾有未記錄的改動；本次未回復或刪除既有內容，只針對證據語氣與 NMA 補強。

### 已完成

- 新增一張 `Network Meta-analysis ｜ 誰比較好？` 畫面，整理 Loveman 2015、Rochwerg 2016、Skandamis 2019、Scott 2019、Wu 2024 的比較結論。
- 將 AE-IPF 相關文字改為保守語氣：
  - 不再暗示 pirfenidone 已被證明優於 nintedanib 預防 AE-IPF。
  - 將 Respir Med 2021 直接比較定位為單中心回溯性、hypothesis-generating。
  - 比較表中的 AE 行改為低確定性觀察性訊號，而非確定優勢。
- 來源頁新增 NMA 期刊連結，並改成緊湊版避免 16:9 畫面裁切。
- 調整 `index.html` 全螢幕版面：
  - `.deck` 改為 `width: 100vw` 且取消上下 padding。
  - `.slide-wrap` 改為 `height: 100vh`，每個 viewport 就是一張投影片。
  - `.slide` 改為 `width: min(100vw, 177.7778vh)` 與 `height: min(100vh, 56.25vw)`，維持 16:9 並盡量填滿全螢幕。
  - 移除投影片圓角與陰影，避免全螢幕時看起來像浮在頁面中的卡片。
- 將 topic 導覽 `.topnav` 從右側垂直排列改為右上橫向排列：
  - 使用 `flex-direction: row`、`flex-wrap: wrap`、`top: 12px`。
  - 手機寬度時置中換行。
  - 列印時隱藏 topic 導覽。

### 驗證

- 已用 PowerShell 檢查 `index.html`：
  - `section` 開合數一致。
  - `div` 開合數一致。
  - `article` 開合數一致。
  - NMA slide 存在。
  - 五個 NMA 來源連結存在。
  - 投影片頁碼仍由 JavaScript 動態填入。
  - 共 31 張 `.slide-wrap`。
  - 全螢幕 CSS 已包含 `height: 100vh`、`width: 100vw`、`width: min(100vw, 177.7778vh)` 與 `height: min(100vh, 56.25vw)`。
  - Topic 導覽已確認為橫向 CSS，HTML 結構仍正常。

### GitHub 狀態

- 工作區根目錄不是 Git repo。
- `MSGH/` 與 `MSGH/Pirfenidone/` 也不是 Git repo。
- 工作區內目前只找到 `lung_cancer_trials/database_publish_tmp/.git`，遠端為 `https://github.com/itrytodoit-code/nsclc-trials.git`，不適合放 Pirfenidone 教學頁。
- GitHub app 目前沒有列出可用 repository。
- 本機未找到 `gh` 指令。
- 因缺少 Pirfenidone/MSGH 對應的 GitHub repo 或可推送遠端，本輪尚未完成 push。

### 待注意

- 目前 HTML 實際張數多於交班單早期紀錄，若要正式報告，建議下一步做一次「全稿逐張審稿」，刪除重複或過細的頁面，固定成 20 分鐘內可講完的版本。
- 若要 push 到 GitHub，需要使用者指定目標 repo URL，或先建立一個新 repo 後提供遠端地址。

## 2026-06-07 Codex

### 本次任務補充

使用者要求將 HTML 調整成 16:9 尺寸，且每個小主題拆成數個概念，每個概念一個畫面。

### 已完成補充

- 重構 `index.html` 為 14 張 16:9 教學畫面：
  - 封面與全局地圖。
  - Guideline 角色拆成 3 個概念畫面。
  - Evidence 拆成 3 個概念畫面。
  - AE 拆成 acute exacerbation 與 adverse events 兩個概念畫面。
  - Pirfenidone vs nintedanib 拆成偏向 pirfenidone、偏向 nintedanib、比較總表 3 個概念畫面。
  - 來源畫面。
- 新增固定右下控制列，可用上一頁／下一頁按鈕翻頁。
- 新增鍵盤操作：ArrowRight/PageDown 下一頁，ArrowLeft/PageUp 上一頁，Home/End 到首末頁。
- 每張 `.slide` 以 `aspect-ratio: 16 / 9` 維持 16:9；窄螢幕時仍維持 16:9，內容過多時在單張畫面內捲動。

### 驗證補充

- 已檢查 `index.html`：
  - 共 14 個 `slide-xx` 畫面。
  - `aspect-ratio: 16 / 9` 存在。
  - 方向鍵翻頁腳本存在。
  - 上一頁／下一頁／進度顯示控制元件存在。
  - 來源連結數 6 個。
  - `section`、`div`、`article` 開合數量一致。

### 本次任務

使用者建立 `MSGH/Pirfenidone/` 資料夾，要求製作 HTML 解釋 pirfenidone 的 guideline 角色、AE 證據，以及和 nintedanib 不同處。

### 已完成

- 新增 `index.html`：一頁式繁體中文臨床解釋頁，含頁首導覽、FVC 下降斜率視覺化、guideline 角色、trial evidence、AE 說明、pirfenidone vs nintedanib 比較與來源。
- 新增 `evidence_notes.md`：可編輯的證據筆記，保留主要文字、臨床解讀與來源。
- 建立本交班單 `PIRFENIDONE_HANDOFF.md`。
- 更新 `MSGH_HANDOFF.md` 記錄本次工作。
- 更新根目錄 `HANDOFF.md` 專案列表，加入 Pirfenidone 教學頁。

### 主要來源

- 2015 ATS/ERS/JRS/ALAT IPF treatment guideline。
- 2022 ATS/ERS/JRS/ALAT IPF update and PPF guideline。
- ASCEND trial, NEJM 2014。
- CAPACITY trials, Lancet 2011。
- ESBRIET pirfenidone DailyMed label, revised 2025。
- OFEV nintedanib DailyMed label, revised 2025。

### 內容判斷

- `AE` 一詞未請使用者再次釐清，因為可合理同時涵蓋 acute exacerbation 與 adverse events。HTML 內已明確拆成兩段。
- Acute exacerbation 的語氣採保守寫法：可能有保護訊號，但不如 FVC decline 證據明確。
- 非 IPF PPF 的部分明確區分：nintedanib guideline 與適應症支持較清楚，pirfenidone 不直接外推。

### 驗證

- 已用 PowerShell 直接檢查 `index.html`：
  - 標題存在。
  - `role`、`evidence`、`ae`、`compare`、`sources` 五個主要區塊皆存在。
  - 三個 `data-target` 情境切換按鈕都有對應面板 ID。
  - 來源連結數 6 個。
  - 互動腳本 `button.addEventListener` 存在。
  - `div`、`section`、`article` 開合數量一致。
- 嘗試用 in-app browser 開啟 `file://` 被瀏覽器安全規則阻擋。
- 改用本機臨時預覽服務時，瀏覽器開啟 `127.0.0.1` 與 `localhost` 均被 `ERR_BLOCKED_BY_CLIENT` 阻擋；因此本輪未完成實際視覺截圖驗證。

### 下一步建議

- 若使用者要正式院內分享，可再補一版「5 分鐘口頭講稿」或「投影片版」。
- 若使用者確認 AE 只指 acute exacerbation，可把 adverse events 移到安全性章節，並強化 acute exacerbation 的文獻表。
- 若環境允許瀏覽器開本機頁面，下一輪可補桌面與手機寬度截圖檢查。
