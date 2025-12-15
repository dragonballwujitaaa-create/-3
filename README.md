經典俄羅斯方塊 (Tetris) - 雲端計分專題

這是一個基於 Web 的經典俄羅斯方塊遊戲專案，它將前端遊戲邏輯與 Google Apps Script 和 Google Sheets 結合，實現了即時、雲端儲存的排行榜功能。

🎯 專案目標與核心功能

這個專題的主要目的是結合運算思維與程式設計課程所學，實作一個完整的 Web 應用程式，並利用 Google 服務作為後端資料庫。

核心功能

雲端排行榜 (Leaderboard System):

玩家遊戲結束後，可輸入名稱並將分數透過 API（Google Apps Script）上傳。

分數資料儲存在 Google Sheets 中，實現持久化儲存。

前端可讀取並顯示排名前列的玩家數據。

動態難度調整 (Dynamic Difficulty):

遊戲的方塊掉落速度會隨著時間增加而動態調整。

每經過一分鐘，方塊的掉落速度會加倍，顯著提升遊戲難度與挑戰性。

前端技術棧: 採用純 HTML、JavaScript 和 Tailwind CSS 實現，確保輕量與快速部署（適用於 GitHub Pages）。

後端技術棧: 使用 Google Apps Script (GAS) 作為 API 閘道，將前端請求導向 Google Sheets (GS) 進行資料讀寫。

⚙️ 技術架構

組件

技術

職責

前端 (Client)

index.html (HTML, JS, Tailwind CSS)

遊戲主體、玩家介面、速度控制、POST/GET API 呼叫。

後端 (API/DB)

Code.gs (Google Apps Script)

接收前端請求 (doGet 讀取 / doPost 寫入)，並處理 Google Sheets 的資料 I/O。

資料庫 (Database)

Google Sheets

儲存玩家名稱、分數和日期時間。

🛠️ 部署指南 (重要)

要讓此專案完整運行，您需要完成兩個主要的部署步驟：

1. 部署 Google Apps Script 後端

創建專案: 在 Google Drive 中建立一個新的 Google Sheets，然後開啟 擴充功能 (Extensions) > Apps Script。

複製程式碼: 將 Code.gs 中的內容貼入您的 Apps Script 專案中。

部署為 Web 應用程式:

點擊右上角的 部署 (Deploy) > 新部署 (New Deployment)。

類型 (Type): 選擇 Web 應用程式 (Web app)。

執行身分 (Execute as): 選擇 我 (Your Google Account)。

存取權限 (Who has access): 務必選擇 任何人，即使是匿名使用者 (Anyone, even anonymous)。

完成部署後，複製產生的 Web App URL。

2. 部署前端遊戲到 GitHub Pages

更新 URL: 開啟您本地的 index.html 檔案。

找到 JavaScript 區塊中的變數 APPS_SCRIPT_URL。

將其替換為您在步驟 1 中複製的 Web App URL。

上傳: 將更新後的 index.html (以及所有相關前端檔案) 推送到您的 GitHub 專案中。

啟用 Pages: 確保您的 GitHub Pages 服務已針對該專案分支（通常是 main 或 gh-pages）啟用。

🕹️ 遊戲操作說明 (前端)

開始遊戲: 點擊「開始遊戲」按鈕。

等級與速度: 留意畫面上的「等級」顯示。每當等級提升 (每分鐘)，方塊的掉落速度會立即加倍。

上傳分數: 遊戲結束後，點擊「上傳分數」，輸入您的名字即可將成績記錄到雲端排行榜。
