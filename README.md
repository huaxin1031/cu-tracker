# 🎓 CU Boulder Master's Course & GPA Tracker (`v5.3`)

[![Live Demo](https://img.shields.io/badge/Live_Demo-GitHub_Pages-CFB87C?style=for-the-badge&logo=github)](https://huaxin1031.github.io/cu-tracker/)
[![Version](https://img.shields.io/badge/Version-v5.3-10b981?style=for-the-badge)]()
[![UI Theme](https://img.shields.io/badge/Theme-CU_Boulder_Black_%26_Gold-020617?style=for-the-badge)]()
[![Mobile Ready](https://img.shields.io/badge/iOS_Web_App-Optimized-38bdf8?style=for-the-badge&logo=apple)]()

專為 **University of Colorado Boulder (CU Boulder) on Coursera** 碩士學位學程（Engineering Management `EMEA`、Data Science `DTSA`、Computer Science `CSCA`、Electrical & Computer Engineering `ECEA`、Applied Math `APPA`）打造的互動式學分進度追蹤、加權 GPA 計算、Coursera 作業頁快速直達與畢業學費智能規劃系統。

🌐 **線上立即體驗 (Live Demo)**：**[https://huaxin1031.github.io/cu-tracker/](https://huaxin1031.github.io/cu-tracker/)**

---

## ✨ 核心功能亮點 (`v5.3` 最新版)

### 1. 🔗 未取得 Grade 課程一鍵直達 Coursera Assignments (`v5.3` 新增)
- **智能判斷是否顯示連結（僅限尚未取得 Grade 科目）**：
  - **尚未取得成績（`Grade` 為 `--`）**：在「主頁」與「🗺️ 畢業規劃」路線圖中，課程名稱會自動轉為可點擊的超連結（滑鼠移過或點擊會變為 CU 金色 `#CFB87C`，後方附帶 **`↗ Assignments`** 標籤），點擊即可在新分頁直接開啟該課程的 Coursera 成績與作業頁（`/home/assignments`），方便快速讀書與推進作業進度。
  - **已取得成績（已有 `A`、`A-`、`B+`、`B`、`B-` 等第）**：一旦登記上字母成績，課程名稱連結會自動移除、恢復為一般純文字標題，版面清爽且避免誤觸。
- **智能網址轉換與特殊改名課程對映 (`COURSERA_CUSTOM_SLUG_MAP`)**：
  - 自動濾除課程名稱中的中文翻譯備註與星號評分（如 `4.9★`、`5.0★`），精準轉換為 Coursera 標準網址：
    - `Financial Forecasting and Reporting` ➔ `https://www.coursera.org/learn/financial-forecasting-and-reporting/home/assignments`
    - `Strategic Product Development 戰略產品開發 4.9★` ➔ `https://www.coursera.org/learn/strategic-product-development/home/assignments`
  - **特殊改名課程專屬對映**：針對曾更新過課名的 **`EMEA 5018` (`Speaking to Lead: Oral Communication for Technical Managers`)**，內建專屬 Slug 對映，確保精準連至 **`https://www.coursera.org/learn/speaking-to-a-technical-group/home/assignments`**。

---

### 2. ↕️ 智能預設排序：`Ongoing` 進行中置頂 ＋ 課程代碼次要排序 (`v5.3` 新增)
- **主頁與批量表格預設自動排序**：
  - 第一優先自動將狀態依 **`⏳ Ongoing (進行中)` ➔ `Expected (預計中)` ➔ `✓ Complete (已完成)`** 排列，讓正在衝刺的課程永遠顯示在最上方。
  - 同狀態下自動以 **課程代碼（科系優先序 `EMEA` → `DTSA` → `APPA` → `CSCA` → `ECEA` ＋ 課號由小到大升冪）** 作為次要排序。

---

### 3. 📊 置頂即時學業儀表板 (Real-Time Academic Dashboard)
- **精準 GPA 計算邏輯**：嚴格僅計入「已取得字母等第（`A`、`A-`、`B+`、`B`、`B-`）」的科目，絕不以修課進度百分比誤代成績；同時顯示 `GPA ÷ 4.00` 換算百分比與計入科目數。
- **動態 SVG 甜甜圈圖 (Donut Chart)**：視覺化呈現 **「成績等第分佈 (僅計已有 Grade 科目)」**，即時顯示各等第門數與佔比。
- **必修 / 選修雙軌進度條**：清晰追蹤 12 門必修 (`Core`) 與 18 門選修 (`Elective`) 的完成與進行中比例。
- **剩餘學費即時估算**：自動依據未完成門數估算剩餘美元 (`USD`) 與新台幣 (`NT$`) 學費預算。

---

### 4. 📋 Excel 式批量編輯表格 (Batch Editor & Multi-Column Sort)
- **篩選列與表格欄位 100% 垂直對齊**：
  - 篩選列由左至右依序對應下方表格：**科系 (`Subject`) → 類別 (`Core/Elective`) → 🔍 搜尋代號或課程名稱 → 狀態 (`Status`) → 成績 (`Grade`) → 📝 篩選個人備註文字 ＋ 重置**。
- **多欄位複合排序 (Multi-Column Sort)**：點擊任一表頭欄位可依序疊加排序條件（顯示 `①↑`、`②↓`、`③↑` 優先順序標籤），亦可一鍵還原預設排序（`Ongoing` 置頂 + 課程代碼升冪）。
- **草稿即時聯動預覽**：在表格內修改任何成績、狀態或類別時，頂部儀表板會**即時動態試算預覽**變化；篩選或排序狀態下編輯，未顯示的課程資料亦完整保留不遺失。
- **防重複檢查機制**：新增或批量儲存時，自動忽略空白與大小寫比對課程代號與名稱，防止誤建重複課程。

---

### 5. 🗺️ 預計畢業時程、學分與學費智能規劃師 (Graduation & Tuition Planner)
- **對齊 CU Boulder 官方行事曆**：內建 2026–2030 每年 6 個正式 8 週學期（Spring / Summer / Fall Session 1 & 2），並支援點擊 **「🌐 檢查 CU 官網更新」** 與離線保護機制（解鎖後亦可手動微調各期開學、選課截止與結課日期）。
- **自動避開寒暑假無課空檔**：自動識別年終寒假（30 天）與學期間休假緩衝期，將待修課程依「`Ongoing 進行中` → `必修 Core` → `選修 Elective`」優先順序智能分配至各個可用學期。
- **訪客自由試算 vs. 帳號預設目標保護**：
  - 在 **「🔒 瀏覽模式 (唯讀)」** 下，任何人皆可自由切換規劃頁的「畢業年、月」下拉選單來**暫時試算**每期修課配速（🟢 輕鬆穩健 / 🟡 適中緊湊 / 🔴 密集衝刺）與每期學費現金流，並顯示 `👀 暫時試算中` 與 `↺ 還原預設` 按鈕。
  - 唯讀模式下，**「🔒 存為預設目標 (唯讀鎖定)」** 按鈕會**反灰鎖死 (`disabled`)**，確保訪客試算不會覆蓋擁有者的預設畢業目標。

---

### 6. 🔒 帳號安全、唯讀反灰保護與雙裝置防衝突雲端同步
- **唯讀模式可檢視帳號安全頁（全面反灰鎖定）**：
  - 在「瀏覽模式 (唯讀)」下可直接點選進入 **「🔒 帳號安全」** 頁面檢視當前 ID、裝置預設 ID 與預計畢業年月，但頁面上所有下拉選單、輸入框與儲存按鈕均會**自動反灰鎖死 (`disabled`)**。
  - 切換回「瀏覽模式 (唯讀)」時，系統會立即註銷當次解鎖狀態，確保離開座位或借人瀏覽時 100% 安全。
- **雙裝置同步防衝突保護 (`updatedAt` Timestamp Check)**：
  - 支援多裝置雲端同步（KVDB REST `PUT` 自動重試機制）。當兩台裝置（例如 iPhone 與 Mac）同時開啟時，儲存前會自動比對雲端時間戳記，若偵測到另一台裝置有更新紀錄，會主動彈出提醒詢問是否先拉取最新進度，防止舊畫面誤蓋新資料。
- **獨立帳號空間與救援機制**：
  - 建立新帳號時自動初始化全空白進度（30 門課皆為 `Expected`、`0%`、`--`）。
  - 支援綁定救援手機號碼，可隨時透過手機號碼「找回忘記的 User ID」或「驗證重設密碼」。

---

### 7. 📱 iPhone Safari & 主畫面 Web App 深度優化
- **iOS 滿版安全區域適配 (`viewport-fit=cover`)**：自動適配 iPhone 動態島 / 瀏海與底部 Home Indicator 安全距離。
- **無遮擋自適應排版**：針對手機窄螢幕優化 4 張規劃指標卡與儀表板，數值與單位強制同行不截斷、完整顯示所有輔助說明文字，切換分頁時自動平滑捲動置頂。

---

## 🚀 快速使用指南

### 📱 在 iPhone / iPad 加入主畫面 (Web App 模式)
1. 使用 iPhone **Safari** 開啟 **[https://huaxin1031.github.io/cu-tracker/](https://huaxin1031.github.io/cu-tracker/)**。
2. 點擊底部工具列的 **「分享」** 圖示（方框向上箭頭）。
3. 向下滑動點選 **「加入主畫面 (Add to Home Screen)」**。
4. 從主畫面點擊 **CU Tracker** 圖示啟動，即可享受全螢幕原生 App 級別的操作體驗！（*註：iOS Safari 一般分頁與主畫面 Web App 的本機快取各自獨立，跨環境修改後請點擊頂部「☁️ 已同步」徽章保持雲端最新狀態*）。

---

## 🔐 模式與權限一覽表

| 功能項目 | 🔒 瀏覽模式 (唯讀) | 🔓 編輯模式 (已驗證密碼) |
| :--- | :---: | :---: |
| **主頁儀表板、搜尋、分類篩選、排序** | ✅ 可自由操作 | ✅ 可自由操作 |
| **點擊未取得 Grade 課名直達 Coursera 作業頁** | ✅ 可直接點擊前往 | ✅ 可直接點擊前往 |
| **新增 / 編輯 / 刪除單門課程** | ⛔ 隱藏 / 鎖定 | ✅ 開放編輯並同步雲端 |
| **批量表格頁 (多欄排序 / 篩選 / 批量修改)** | 🔑 點擊時提示輸入密碼解鎖 | ✅ 開放編輯與即時預覽 |
| **畢業規劃頁 — 切換年月「暫時試算」** | ✅ 開放自由試算 (不影響預設值) | ✅ 開放試算 |
| **畢業規劃頁 — 「存為預設目標並同步」** | ⛔ **反灰鎖死 (`disabled`)** | ✅ 開放儲存並同步雲端 |
| **帳號安全頁 — 檢視帳號與畢業目標資訊** | ✅ 可進入頁面檢視 | ✅ 可進入頁面檢視 |
| **帳號安全頁 — 修改畢業年月 / 密碼 / 預設 ID** | ⛔ **所有選項與按鈕反灰鎖死 (`disabled`)** | ✅ 開放修改並同步雲端 |

---

## 🛠️ 技術架構與部署說明

- **前端框架**：原生 HTML5 + Vanilla JavaScript (ES6+) + [Tailwind CSS (CDN)](https://tailwindcss.com/) + [Lucide Icons](https://lucide.dev/)
- **視覺設計**：CU Boulder 官方黑金配色 (`#CFB87C` Vegas Gold & `#020617` Slate Dark) + 毛玻璃特效 (`backdrop-filter: blur`)
- **資料儲存**：`localStorage` 離線秒開快取 + `KVDB.io` 雲端 JSON 雙向同步備份
- **密碼保護**：瀏覽器端 Web Crypto API `SHA-256` 雜湊驗證（支援純 JS Fallback 相容性保護）
- **零建置部署**：單一 `index.html` 檔案架構，直接推送至 GitHub `main` 分支即可透過 **GitHub Pages** 自動發布更新。

---

## 📝 版本更新紀錄 (Changelog)

- **`v5.3` (2026-10)**：
  - 新增「未取得 Grade 課程一鍵直達 Coursera Assignments (`/home/assignments`)」超連結功能，取得成績（`A`~`B-`）後自動移除連結；內建 `EMEA 5018` (`speaking-to-a-technical-group`) 改名網址專屬對映，並自動過濾課名中的中文備註與星號評分。
  - 主頁與批量表格預設排序改為自動將 **`Ongoing (進行中)` 置頂**，並以**課程代碼（`EMEA` → `DTSA` → `APPA` → `CSCA` → `ECEA` ＋ 課號升冪）**作為次要排序。
- **`v5.2` (2026-10)**：修復手機版「畢業規劃」指標卡文字斷行與 `...` 截斷遮擋問題；新增切換分頁自動平滑置頂。
- **`v5.1` (2026-10)**：開放唯讀模式下直接檢視「帳號安全」頁面，並將所有輸入框、下拉選單與儲存按鈕全面反灰鎖死 (`disabled`)；鎖死唯讀模式下「畢業規劃」頁的「存為預設目標」按鈕，同時保留年月下拉選單供自由試算。
- **`v4.9` (2026-10)**：調整「批量表格」篩選列順序，與正下方表格欄位（科系 → 類別 → 代號/課名 → 狀態 → 成績 → 個人備註）100% 垂直對齊。
- **`v4.8` (2026-10)**：新增雙裝置雲端同步防衝突保護 (`updatedAt` 時間戳比對)、CU 官網行事曆背景核對與手動微調學期日期功能。
- **`v4.6` (2026-10)**：新增「🗺️ 畢業規劃」分頁，支援依預計畢業年月自動避開寒暑假空檔、計算每期配速與學費現金流建議。
