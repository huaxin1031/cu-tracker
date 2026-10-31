# 🎓 CU Boulder Master's Course & GPA Tracker (`v5.4`)

[![Live Demo](https://img.shields.io/badge/Live_Demo-GitHub_Pages-CFB87C?style=for-the-badge&logo=github)](https://huaxin1031.github.io/cu-tracker/)
[![Version](https://img.shields.io/badge/Version-v5.4-10b981?style=for-the-badge)]()
[![UI Theme](https://img.shields.io/badge/Theme-CU_Boulder_Black_%26_Gold-020617?style=for-the-badge)]()
[![Mobile Ready](https://img.shields.io/badge/iOS_Web_App-Optimized-38bdf8?style=for-the-badge&logo=apple)]()

專為 **University of Colorado Boulder (CU Boulder) on Coursera** 碩士學位學程（Engineering Management `EMEA`、Data Science `DTSA`、Computer Science `CSCA`、Electrical & Computer Engineering `ECEA`、Applied Math `APPA`）打造的互動式學分進度追蹤、加權 GPA 計算、期末考目標分數反推、Coursera 作業頁快速直達與畢業學費智能規劃系統。

🌐 **線上立即體驗 (Live Demo)**：**[https://huaxin1031.github.io/cu-tracker/](https://huaxin1031.github.io/cu-tracker/)**

---

## ✨ 核心功能亮點 (`v5.4` 最新版)

### 1. 🎯 期末考目標分數反推計算機 (Final Exam Target Calculator) (`v5.4` 新增)
- **僅針對尚未取得字母 Grade 的科目顯示**：一旦科目登記了正式等第（`A`、`A-`、`B+`、`B`、`B-`），期末試算面板會自動隱藏，維持版面清爽。
- **支援兩種輸入模式切換**：
  - **模式 A（已獲總分累加 `%`）**：直接輸入目前在 Coursera Grades 頁面中「期末考以外已拿到的總分百分比」與「期末考佔比 `%`」。
  - **模式 B（平時作業平均 `%`）**：輸入目前已完成作業的平均得分率，系統自動乘上非期末權重並反推期末考所需分數。
- **主頁卡片外部直接顯示 `A` / `A-` / `B+` / `B` 四格目標分數徽章**：
  - 設定後無須點開彈窗，在主頁卡片外部即可一眼看到要拿到 `A (93%)`、`A- (90%)`、`B+ (87%)`、`B (83%)` 期末考分別需要考幾分（支援針對個別課程自訂等第門檻，並以 🟢 已穩拿 / 🩵 正常發揮 / 🟡 全力衝刺 / 🔴 超過滿分 顏色標示）。

---

### 2. 🔗 未取得 Grade 課程一鍵直達 Coursera Assignments (`v5.3+`)
- **智能判斷是否顯示連結**：
  - **尚未取得成績（`Grade` 為 `--`）**：在「主頁」與「🗺️ 畢業規劃」路線圖中，課程名稱會自動成為超連結（附帶 **`↗ Assignments`** 標籤），點擊即可在新分頁直接開啟該課程的 Coursera 成績與作業頁（`/home/assignments`）。
  - **已取得成績（已有 `A`～`B-` 等第）**：一旦登記成績，課名自動恢復為純文字標題，避免誤觸。
- **智能網址轉換與特殊改名課程對映 (`COURSERA_CUSTOM_SLUG_MAP`)**：
  - 自動濾除課名中的中文翻譯與星號評分（如 `4.9★`、`5.0★`），轉為標準 Coursera 網址。
  - **特殊改名課程專屬對映**：針對曾更新課名的 **`EMEA 5018` (`Speaking to Lead: Oral Communication for Technical Managers`)**，內建專屬 Slug 對映，確保精準連至 **`https://www.coursera.org/learn/speaking-to-a-technical-group/home/assignments`**。

---

### 3. ↕️ 智能預設排序：`Ongoing` 進行中置頂 ＋ 課程代碼次要排序 (`v5.3+`)
- **主頁與批量表格預設自動排序**：
  - 第一優先自動將狀態依 **`⏳ Ongoing (進行中)` ➔ `Expected (預計中)` ➔ `✓ Complete (已完成)`** 排列，讓正在衝刺的課程永遠置頂。
  - 同狀態下自動以 **課程代碼（科系優先序 `EMEA` → `DTSA` → `APPA` → `CSCA` → `ECEA` ＋ 課號由小到大升冪）** 作為次要排序。

---

### 4. 📊 置頂即時學業儀表板 (Real-Time Academic Dashboard)
- **精準 GPA 計算邏輯**：嚴格僅計入「已取得字母等第（`A`、`A-`、`B+`、`B`、`B-`）」的科目；同時顯示 `GPA ÷ 4.00` 換算百分比與計入科目數。
- **動態 SVG 甜甜圈圖 (Donut Chart)**：視覺化呈現 **「成績等第分佈 (僅計已有 Grade 科目)」**，即時顯示各等第門數與佔比。
- **必修 / 選修雙軌進度條 & 剩餘學費即時估算**：清晰追蹤 12 門必修 (`Core`) 與 18 門選修 (`Elective`) 完成比例，並自動估算剩餘美元 (`USD`) 與新台幣 (`NT$`) 學費預算。

---

### 5. 📋 Excel 式批量編輯表格 (Batch Editor & Multi-Column Sort)
- **篩選列與表格欄位 100% 垂直對齊**：由左至右依序為 **科系 (`Subject`) → 類別 (`Core/Elective`) → 🔍 搜尋代號或課程名稱 → 狀態 (`Status`) → 成績 (`Grade`) → 📝 篩選個人備註文字 ＋ 重置**。
- **多欄位複合排序 & 草稿即時預覽**：點擊表頭可依序疊加排序條件（`①↑`、`②↓`），修改表格時頂部儀表板即時動態試算，並內建防重複課程檢查機制。

---

### 6. 🗺️ 預計畢業時程、學分與學費智能規劃師 (Graduation & Tuition Planner)
- **對齊 CU Boulder 官方行事曆**：內建 2026–2030 每年 6 個正式 8 週學期（Spring / Summer / Fall Session 1 & 2），自動避開寒假與學期間休假空檔，智能分配每期修課清單與學費現金流。
- **唯讀模式自由試算 vs. 預設目標保護**：訪客可在唯讀模式下自由切換畢業年月進行試算；而 **「存為預設目標」** 按鈕與 **「帳號安全」** 頁面中的所有控制項在唯讀模式下均會**自動反灰鎖死 (`disabled`)**，保障帳號安全。

---

### 7. 📱 iPhone 主畫面 Web App 深度優化 & 一鍵強制重整 (`v5.4` 新增)
- **iOS 滿版安全區域適配 (`viewport-fit=cover`)**：自動適配 iPhone 動態島與底部 Home Indicator 安全距離。
- **一鍵強制重整 Web App (`v5.4 🔄`)**：在 iPhone「加入主畫面」的獨立 Web App 模式下，直接點擊左上角綠色 **`v5.4 🔄`** 標籤，即可繞過快取、強制重新載入最新部署的網頁版本！

---

## 📝 版本更新紀錄 (Changelog)

- **`v5.4` (2026-10)**：
  - 新增尚未取得 Grade 科目的 **「🎯 期末考目標分數反推計算機」**，支援設定期末考佔比與目前得分，並直接在主頁卡片外部顯示拿到 `A` / `A-` / `B+` / `B` 所需的期末考分數。
  - 新增點擊頂部 **`v5.4 🔄`** 版本徽章一鍵強制重新整理網頁功能，解決 iPhone 主畫面 Web App 快取更新問題。
- **`v5.3` (2026-10)**：
  - 新增「未取得 Grade 課程一鍵直達 Coursera Assignments (`/home/assignments`)」超連結功能，內建 `EMEA 5018` (`speaking-to-a-technical-group`) 改名網址專屬對映。
  - 主頁與批量表格預設排序改為自動將 **`Ongoing (進行中)` 置頂**，並以**課程代碼升冪**作為次要排序。
- **`v5.2` (2026-10)**：修復手機版「畢業規劃」指標卡文字截斷問題；新增切換分頁自動平滑置頂。
- **`v5.1` (2026-10)**：開放唯讀模式下直接檢視「帳號安全」頁面並將所有輸入框與按鈕反灰鎖死 (`disabled`)；鎖死唯讀模式下「畢業規劃」頁的「存為預設目標」按鈕。
