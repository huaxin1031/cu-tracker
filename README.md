# 🎓 CU Boulder Master's Course Tracker (ME-EM / MS)

[![GitHub Pages](https://img.shields.io/badge/Live_Demo-GitHub_Pages-CFB87C?style=for-the-badge&logo=github)](https://huaxin1031.github.io/cu-tracker/)
[![UI Theme](https://img.shields.io/badge/Theme-CU_Boulder_Black_%26_Gold-020617?style=for-the-badge)](#)
[![PWA Ready](https://img.shields.io/badge/iOS_Safari-Web_App_Ready-10b981?style=for-the-badge&logo=apple)](#)

專為 **University of Colorado Boulder (CU Boulder)** 工程管理碩士（Master of Engineering in Engineering Management, ME-EM）與相關學位打造的互動式修課進度追蹤系統。採用 CU Boulder 經典黑金配色（`#CFB87C`）與毛玻璃深色模式介面，支援多人獨立課表、跨裝置雲端同步與 iOS 主畫面 Web App 體驗。

🔗 **線上開始使用 (Live Demo)：** [https://huaxin1031.github.io/cu-tracker/](https://huaxin1031.github.io/cu-tracker/)

---

## ✨ 核心功能亮點 (Key Features)

### 📊 1. 即時學業儀表板 (Real-Time Academic Dashboard)
- **加權 GPA 自動計算**：依據已取得成績之科目（`A = 4.0`, `A- = 3.75`, `B+ = 3.25`, `B = 3.0`, `B- = 2.75`）即時計算當前 GPA 與等第長條圖分佈。
- **修課進度與學分結構**：自動統計已完成（Complete）、進行中（Ongoing）與預計修習（Expected）門數，並視覺化呈現 **必修 Core** 與 **選修 Elective** 的完成比例。
- **動態剩餘學費預估**：根據尚未完成的課程數量，自動估算剩餘學費（同時顯示 USD 美金與 NTD 新台幣參考金額）。

### 👥 2. 多人獨立檔案與預設主帳號保護 (Multi-User Profiles)
- **系統預設主帳號 (`@surihua`)**：內建完整 30 門課程修課紀錄，並受預設密碼鎖定保護；新裝置必須先通過密碼驗證才能檢視或編輯其內容。
- **建立全新獨立 ID**：其他同學或朋友可隨時建立自己的專屬 User ID（例如 `@dolly`），系統會自動分配一份 **30 門全空白進度（`Expected` / `0%` / `--`）** 的標準課表，彼此資料完全獨立不互蓋。
- **分離「臨時切換」與「裝置預設開啟 ID」**：
  - 右上角選單切換帳號僅供當下臨時瀏覽，不會改動裝置預設值。
  - 若要更改手機或電腦每次打開時預設載入的 ID，必須進入 **「帳號安全 & ID/密碼設定」** 頁面並驗證密碼後才能變更。

### 🔐 3. 帳號密碼與手機號碼救援機制 (Account & Recovery Controls)
- **前端 SHA-256 雜湊比對**：密碼與綁定之救援手機號碼均透過瀏覽器 Web Crypto API (`SHA-256`) 轉為雜湊值儲存，不以明文形式記錄。
- **敏感操作驗證**：修改密碼、變更 User ID、修改裝置預設 ID 或永久刪除帳號前，皆須輸入目前密碼進行身分確認。
- **手機號碼找回機制**：若忘記 User ID 或忘記密碼，可透過當初綁定的手機號碼查詢對應 ID 或重設新密碼。

### 📱 4. iOS PWA 主畫面支援與雲端同步 (Mobile Web App & Sync)
- **iPhone Safari 最佳化**：內建動態生成的 CU 黑金高解析度 App Icon 與安全區域（Safe Area）留白，支援「加入主畫面」全螢幕獨立開啟。
- **本機 + 雲端雙重儲存**：每次編輯課程或更新設定時，除了儲存於瀏覽器 `localStorage` 外，亦會自動推送至雲端 Key-Value 端點，方便在手機與電腦間同步最新進度。

---

## 🚀 快速上手指南 (How to Use)

1. **開啟網站**：前往 [https://huaxin1031.github.io/cu-tracker/](https://huaxin1031.github.io/cu-tracker/)。
2. **解鎖或建立帳號**：
   - 若您是主帳號擁有者，請直接輸入 `@surihua` 的專屬密碼解鎖檢視。
   - 若您是新使用者，請點擊畫面上的 **「👤 切換 / 建立其他 ID」**（或右上角帳號選單），輸入您的新 ID、姓名、自訂密碼與救援手機號碼，即可獲得專屬的 30 門空白課表。
3. **編輯課程進度**：
   - 點擊右上角 **「🔒 瀏覽模式」** 切換為 **「✏️ 編輯模式」**。
   - 點擊任一課程卡片右側的編輯圖示，即可更新修課狀態（`Complete` / `Ongoing` / `Expected`）、成績等第、完成百分比與個人學習備註，按下儲存後即自動更新圖表並同步雲端。
4. **加入 iPhone 主畫面（推薦）**：
   - 使用 iPhone Safari 開啟網址 $\rightarrow$ 點擊底部中間的「分享」按鈕 $\rightarrow$ 選擇 **「加入主畫面 (Add to Home Screen)」**，即可像原生 App 一樣隨時點開查閱。

---

## 🛠️ 技術架構 (Tech Stack)

| **類別** | **採用技術** | **說明** |
| :--- | :--- | :--- |
| **前端結構與邏輯** | HTML5 + Vanilla JavaScript (ES6+) | 單一檔案零建置依賴（Zero-build Single-File SPA），部署快速直覺 |
| **UI 樣式設計** | Tailwind CSS (CDN) + Custom Glassmorphism | 深色毛玻璃質感、響應式RWD排版與 CU Boulder 金色主題 |
| **圖示與字型** | Lucide Icons + Google Fonts (Inter) | 清晰現代的數據儀表板視覺體驗 |
| **資料儲存與加密** | `localStorage` + Web Crypto API + KVDB REST API | 本機快取搭配輕量級雲端同步，並以 SHA-256 處理密碼與手機雜湊 |

---

## ⚠️ 架構與資料安全說明 (Architecture & Security Notice)

本專案為部署於 GitHub Pages 之**純前端靜態網頁應用程式 (Client-Side Static Web App)**：
- 畫面鎖定、SHA-256 雜湊與手機號碼比對機制旨在防止日常使用時的誤觸、覆蓋與一般介面瀏覽。
- 由於未採用後端伺服器驗證（如 Firebase Auth 或自建後端資料庫），所有前端程式碼與雲端同步請求皆在瀏覽器端執行，請勿將銀行密碼或高機密個人隱私密碼設定為本系統之同步密碼。

---

## 📄 License

This project is created for personal academic tracking and educational purposes.
