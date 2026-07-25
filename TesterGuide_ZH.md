# PNCC關懷 (dailyNotify) - 測試人員安裝與任務指南 🌟

歡迎加入 **「PNCC關懷 (dailyNotify)」** 的內部閉環測試小組！

> [!NOTE]
> 💡 **零程式碼基礎說明（無須編譯源碼）**：
> 本測試 GitHub 倉庫專門用於提供預先編譯好的安裝包（`app-release.apk`）與測試指引。**測試人員完全不需要安裝 Flutter 或編譯任何程式碼**，只需按照以下簡單步驟即可在手機上完成安裝與測試。

---

## 📥 安裝說明 (Installation Instructions)

### 🤖 安卓手機 (Android) 使用者：

#### 方法 A：手機直接點擊安裝（最推薦、最簡單）
1. **下載安裝包**：在安卓手機瀏覽器或微信群組中點擊下載 **`app-release.apk`** 檔案。
2. **點擊安裝**：下載完成後，點擊該 APK 檔案選擇 **「安裝」**。
3. *安全性提示*：若手機顯示「不允許安裝來自未知來源的應用程式」，請點擊系統提示中的 **「設定」**，開啟 **「允許此來源安裝應用」** 後即可順利完成安裝。

#### 方法 B：使用 ADB 命令安裝（適合有電腦的開發人員模式測試）
若您習慣在電腦上使用命令列工具（`adb`），請按照以下步驟開啟手機的「開發人員模式」：
1. **開啟開發人員選項**：
   * 開啟手機的 **「設定 (Settings)」** -> 點擊 **「關於手機 (About Phone)」**。
   * 找到 **「版本號碼 (Build Number)」**，**連續快速點擊 7 次**。
   * 手機螢幕下方會彈出提示：*「您已成為開發人員 (You are now a developer!)」*。
2. **啟用 USB 調試 (USB Debugging)**：
   * 返回設定選單 -> 進入 **「系統 (System)」** -> 點擊 **「開發人員選項 (Developer Options)」**。
   * 將 **「USB 調試 (USB Debugging)」** 的開關切換為 **開啟 (ON)**。
3. **執行安裝**：
   * 使用 USB 傳輸線將安卓手機連接至電腦，手機螢幕跳出「允許 USB 調試嗎？」提示時點擊 **「允許」**。
   * 在電腦終端機（Terminal / Command Prompt）中執行以下命令：
     ```bash
     adb install -r app-release.apk
     ```

---

### 🍏 蘋果手機 (iOS / iPhone) 使用者：
1. **下載 TestFlight**：在 iPhone App Store 搜尋並下載 Apple 官方的 **[TestFlight App](https://apps.apple.com/app/testflight/id899247664)**。
2. **獲取邀請**：
   * 請將您的 **Apple ID 信箱** 提供給管理員 (`yuecheng@gmail.com`)。
   * 您的信箱將收到一封來自 Apple TestFlight 的邀請信。
3. **接受並安裝**：
   * 打開邀請信件，點擊 **「View in TestFlight」** 或測試連結。
   * TestFlight 應用程式會自動打開，點擊 **「安裝 (Install)」** 即可安裝 `PNCC Care` 測試版。

---

## 🎯 測試核心大綱與任務認領 (Master Test Task Matrix)

為了避免多名測試人員重複測試簡單功能，而導致複雜邊界情境（如跨平台、多家属照顧）無人測試，我們建立了 **[主測試任務大綱與認領表 (TEST_MATRIX.md)](./TEST_MATRIX.md)**！

### 💡 如何認領並進行測試：
1. 打開 **[TEST_MATRIX.md](./TEST_MATRIX.md)** 文件。
2. 挑選適合您設備條件的任務編號（如 `TASK-12: 安卓家屬照顧蘋果長輩` 或 `TASK-05: 1~2分鐘短倒計時測試`）。
3. 按照文件內針對該 `Task ID` 所提供的 **中文與英文 Step-by-Step 詳細步驟指引** 操作。
4. 測試完成後，按照下方格式提交測試報告或在 GitHub Issues 中填寫測試結果。

---

## 📝 測試報告提交範本 (Test Report Template)

當您完成一項任務或發現問題時，請複製以下範本並在 GitHub Issues 或測試群組中提交：

```markdown
### 📋 PNCC關懷 測試回報單

- **認領任務編號 (Task ID)**: [例如：TASK-12]
- **測試人員姓名/暱稱**: [例如：Tester Alex]
- **測試設備型號與系統版本**: [例如：Pixel 4a (Android 13) & iPhone 13 (iOS 17.4)]
- **登入帳號與身分**: [例如：tester1@gmail.com / 關懷者模式]
- **測試結果 (Test Result)**: 
  - [ ] 🟢 通過 (Pass) - 功能完全正常
  - [ ] 🔴 發現問題 (Bug Found)
- **問題描述與細節 (Description)**:
  (若發現問題，請在此詳細說明現象)
- **重現步驟 (Steps to Reproduce)**:
  1. ...
  2. ...
- **截圖或螢幕錄影 (Screenshots/Logs)**:
  (可附上截圖照片)
```

---

## 🐞 可以在 GitHub Issues 進行 Jira 式問題追蹤

我們在 GitHub 倉庫上啟用了 **GitHub Issues** 模組：
- **認領測試任務**：可以在 GitHub Issues 中點擊 **「Claim Test Task」** 來宣告您正在測試的情境。
- **提交 Bug 報告**：點擊 **「Report a Bug」**，填寫欄位後發布。開發團隊會將狀態標示為 `In Progress` 或 `Resolved`，您可以隨時查看修復進度！

感謝您的寶貴時間與協助！🚀
