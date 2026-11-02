# PNCC關懷 (dailyNotify) - 內部閉環測試中心 🌟

歡迎來到 **PNCC關懷 (dailyNotify)** 的內部測試下載與任務管理中心！

> [!IMPORTANT]
> 💡 **測試人員說明**：
> 本倉庫為預先編譯測試發布中心，**完全無須安裝開發環境或編譯程式碼**。您只需下載安裝包或透過 TestFlight 即可開始測試。

---

## 📥 最新測試版下載 (Latest Beta Release v1.1.5 Build 25)

- **🤖 Android APK 下載**: [下載 app-release.apk (Direct APK Download)](./app-release.apk)
- **🍏 iOS App Store 下載**: [Apple App Store 搜尋「PNCC care」下載](https://apps.apple.com/app/pncc-care/id6742517865)
- **⌚️ Apple Watch 手錶應用**: 於 iPhone 的「Watch」應用程式之「可用的 App」列表，一鍵安裝「PNCC care Watch App」至 Apple Watch！

### ✨ v1.1.5 更新亮點 (What's New in v1.1.5):
1. **⌚️ Apple Watch 獨立手錶伴侶應用 (Apple Watch Companion App)**:
   - 全新獨立 watchOS 應用程式，可在手錶上獨立查看長輩平安狀態、今日經文，並支援手錶一鍵「我很好 / I'm OK」打卡。
   - 雙向即時同步（WatchConnectivity）：手錶與手機隨時無縫同步平安狀態與緊急警報。
   - 支援 iPhone「Watch」App 內自動探索與一鍵安裝。
2. **虛擬三鍵導航欄適配 (Navigation Bar Adaptation)**: 針對小米 Mi 9 等配備傳統虛擬三鍵（返回/主頁/多任務）之設備，全面優化底部防遮擋 SafeArea 間距，軟體資訊與彈窗按鈕完整可見。
3. **長輩首頁平安狀態與按鈕整合 (Compact Senior Safety Card)**: 將平安狀態與超大按鈕高度融合為單一卡片，消除冗餘綠色色塊，第一螢幕免滾動即可完整操作。
4. **橫向旋轉雙欄響應式佈局 (Landscape Responsive Layout)**: 設備橫向旋轉時自動切換為左右雙欄佈局，平安按鈕與今日金句並排呈現，一覽無遺。
5. **桌面小工具直達模式切換 (Desktop Widget Deep Linking)**: 點擊長輩小工具或家屬小工具可直接跳轉至對應身份視圖，並智能推薦開啟雙模式。
6. **照護者自訂警報橫幅 (Custom Alert Banner)**: 照護者警報畫面提供自訂背景調色盤，可切換脈衝閃爍特效，並支援不干擾的簡潔橫幅模式。

---

## 🚀 測試指南與任務認領 (Tester Guides & Task Signup)

為了確保各項功能與跨平台邊界（Android / iOS）皆得到充分測試，請參閱以下文件：

1. **[主測試任務大綱與認領表 (TEST_MATRIX.md)](./TEST_MATRIX.md)**
   - 包含 `TASK-01` 至 `TASK-18` 的詳細中英文步驟操作指引。
   - 測試人員可挑選適合的情境填寫名字認領。
2. **[中文測試指南 (TesterGuide_ZH.md)](./TesterGuide_ZH.md)**
   - 包含安卓安裝（含 ADB 開發者模式開啟教程）、iOS 安裝、測試報告撰寫範本。
3. **[English Tester Guide (TesterGuide_EN.md)](./TesterGuide_EN.md)**
   - Step-by-step installation and testing guidelines in English.

---

## 🐞 Jira 式 Bug 回報與任務管理 (GitHub Issues)

您可以在本倉庫的 **GitHub Issues** 頁面：
- **認領測試任務**：點擊 **Claim Test Task** 註冊您欲測試的 Task ID。
- **回報問題**：點擊 **Report a Bug** 提交問題與截圖，隨時查看開發團隊的修復進度。
