# PNCC Care (dailyNotify) - v1.1.3 Store Submission & Release Guide 🚀

本文件彙整 **PNCC關懷 (PNCC Care)** 升級至 **v1.1.3 (Build 21)** 後，發布至 **Google Play Store**、**Apple App Store (App Store Connect)** 與 **APKPure** 所需之全部套件資訊、中英文更新日誌 (Release Notes / What's New)、商店元數據 (Metadata) 與審核備註。

---

## 📦 1. 編譯產物與版本號 (Build Artifacts & Version)

| 平台 / 通路 | 檔案路徑 | 檔案類型 | 用途 |
| :--- | :--- | :--- | :--- |
| **Google Play Store** | `build/app/outputs/bundle/release/app-release.aab` (60.4 MB) | Android App Bundle (.aab) | Google Play Console 上架發布 |
| **APKPure / 官網直載 / 測試庫** | `build/app/outputs/flutter-apk/app-release.apk` (79.4 MB) | Universal APK (.apk) | APKPure 開發者後台 / GitHub 測試發布 |
| **Apple App Store** | `build/ios/archive/Runner.xcarchive` / `build/ios/ipa/*.ipa` | iOS App Archive / Package | App Store Connect / TestFlight / 審核上架 |

### 核心版本參數 (Version Attributes):
- **Version Name (版本名稱)**: `1.1.3`
- **Build Number / Version Code (構建號 / 內部版本碼)**: `21`
- **Android Package Name (Application ID)**: `com.zigzagyc.dailynotify`
- **iOS Bundle Identifier**: `com.zigzagyc.dailyNotify`
- **Apple Team ID**: `UW6278TE85`
- **Min Android SDK**: `26` (Android 8.0 Oreo) | **Target SDK**: `36` (Android 16+)
- **Min iOS Version**: `16.0`

---

## 📝 2. 商店更新日誌 (What's New in v1.1.3)

請在各大商店的「此版本最新變更 / 新增功能 (What's New in this Version)」欄位複製以下內容：

### 2.1 繁體中文 (zh-TW / zh-HK / Traditional Chinese)
```text
【v1.1.3 最新更新內容】
1. 虛擬三鍵導航欄適配：全面優化傳統虛擬三鍵（返回/主頁/多任務）設備之底部防遮擋 SafeArea 間距，軟體資訊、版本說明與對話框按鈕完整呈現。
2. 長輩首頁平安狀態與按鈕整合：將平安狀態與超大按鈕高度融合成單一優雅卡片，消除冗餘綠色色塊，第一螢幕免滾動即可輕鬆操作。
3. 橫向旋轉雙欄響應式佈局：設備橫向旋轉時自動切換為左右雙欄佈局，平安按鈕與今日金句並排呈現，一覽無遺。
4. 桌面小工具直達模式切換：點擊長輩小工具或家屬小工具可直接跳轉至對應身份視圖，並智能推薦開啟雙模式。
5. 照護者自訂警報橫幅：照護者警報畫面提供自訂背景調色盤，可切換脈衝閃爍特效，並支援不干擾的簡潔橫幅模式。
6. 系統穩定性與背景同步效能優化。
```

### 2.2 簡體中文 (zh-CN / Simplified Chinese)
```text
【v1.1.3 最新更新内容】
1. 虚拟三键导航底栏适配：全面优化传统虚拟三键（返回/主页/多任务）设备底部防遮挡 SafeArea 间距，软件信息、版本说明与对话框按键完整呈现。
2. 长辈首页平安状态与按键整合：将平安状态与超大按键高度融合成单一优雅卡片，消除冗余绿色色块，第一屏幕免滚动即可轻松操作。
3. 横向旋转双栏响应式布局：设备横向旋转时自动切换为左右双栏布局，平安按键与今日金句并排呈现，一览无遗。
4. 桌面小组件直达模式切换：点击长辈组件或家属小组件可直接跳转至对应身份视图，并智能推荐开启双模式。
5. 照顾者自定义警报横幅：照顾者警报画面提供自定义背景调色盘，可切换脉冲闪烁特效，并支持不干扰的简洁横幅模式。
6. 系统稳定性与后台同步性能优化。
```

### 2.3 English (en-US / International)
```text
What's New in v1.1.3:
• System 3-Button Navigation Bar Inset Adaptation: Enhanced dynamic SafeArea bottom padding for devices with traditional 3-button system bars (Back/Home/Recents), ensuring version info and dialog action buttons are completely visible without occlusion.
• Consolidated Senior Safety Card: Replaced redundant status blocks with a sleek, unified card combining real-time status and giant check-in button on the first screen without scrolling.
• Responsive Landscape 2-Column Mode: Automatic side-by-side layout when rotating device horizontally so safety buttons and scriptures remain fully visible.
• Desktop Widget Deep Linking: Caregiver and Senior home screen widgets now navigate straight to their respective view with 1-tap dual-mode recommendations.
• Custom Alert Banner: Added full color picker, pulsing animation options, and clean compact banner mode for caregiver alerts.
• Stability & background synchronization enhancements.
```

---

## 🍏 3. Apple App Store (App Store Connect) 上架資訊

### 3.1 基礎元數據 (General App Information)
- **App Name (應用名稱)**: `PNCC Care`
- **Subtitle (副標題)**: `Senior Safety & Check-In Tracker` (30 字以內)
- **Primary Category (主要類別)**: `Medical` (醫療) 或 `Lifestyle` (生活風格)
- **Secondary Category (次要類別)**: `Health & Fitness` (健康與健身)
- **Copyright (版權)**: `© 2026 ZigzagYC. All rights reserved.`
- **Support URL (支援網址)**: `https://github.com/zigzagyc/dailyNotify-testers`
- **Marketing URL (行銷網址)**: `https://github.com/zigzagyc/dailyNotify-testers`
- **Privacy Policy URL (隱私權政策)**: `https://github.com/zigzagyc/dailyNotify-testers/blob/main/PrivacyPolicy.md`

### 3.2 關鍵字 (Keywords - 100 字元上限)
```text
pncc care,senior safety,elderly tracking,daily checkin,bible verse,fall detection,caregiver alert,911
```

### 3.3 App Review Information (審查登入帳號與備註)
- **Sign-In Required (是否需登入)**: `Yes`
- **Demo Account (測試帳號)**:
  - **Username / Email**: `tester_caregiver@pncc.org` (或您設定之測試帳號)
  - **Password**: `TestPass123!`
- **Notes for Reviewer (審查員說明備註)**:
```text
Dear Apple App Review Team,

This update (v1.1.3) improves accessibility and UI responsiveness for seniors:
1. One-Tap Check-In: Big touch target designed for elderly accessibility.
2. Dual-Mode Live Activities: Uses ActivityKit for non-intrusive safety countdowns and emergency notifications.
3. Apple Watch & Widgets: Supports watchOS companion apps and Lock Screen/Home Screen widgets for immediate safety status monitoring.
4. Background & Push: Uses remote background notifications and local notifications solely to track safety intervals and send urgent alerts to pre-authorized family caregivers.

Thank you for your review!
```

---

## 🤖 4. Google Play Console 上架資訊

### 4.1 核心資訊
- **App Name (應用名稱)**:
  - 英文: `PNCC Care`
  - 繁體中文: `PNCC關懷`
  - 簡體中文: `PNCC关怀`
- **Short Description (簡短說明，80 字元上限)**:
  - 英文: `Elder safety check-in tracker with daily scriptures & caregiver monitoring.`
  - 繁體中文: `專為長輩設計的極簡平安回報與安全守護工具，融合聖經金句與照顧者監測。`
  - 簡體中文: `专为长辈设计的极简平安回报与安全守护工具，融合圣经金句与照顾者监测。`

### 4.2 Play Console 上傳步驟
1. 進入 [Google Play Console](https://play.google.com/console)。
2. 選擇 **PNCC Care** -> 左側選單進入 **Release (發布)** -> **Production (正式發布)** 或 **Testing (內部測試 / 封閉測試)**。
3. 點擊 **Create new release (建立新版本)**。
4. 將 `build/app/outputs/bundle/release/app-release.aab` 拖曳上傳。
5. 在 **Release notes (版本說明)** 貼入本文件的中英文更新日誌。
6. 點擊 **Save** -> **Review release** -> **Start rollout (開始發布)**。

---

## 🌐 5. APKPure 上架資訊 (APKPure Developer Console)

若您使用 APKPure 開發者後台 (APKPure Developer Center) 發布：
1. **登入 APKPure Developer Console**: [https://developer.apkpure.com/](https://developer.apkpure.com/)
2. **選擇應用 / 新增應用**: 填寫 Package Name: `com.zigzagyc.dailynotify`。
3. **上傳 APK**: 上傳 `build/app/outputs/flutter-apk/app-release.apk` (79.4 MB)。
4. **填寫 Changelog (更新日誌)**: 複製上方 2.3 English 或 2.1 繁體中文更新內容。
5. **分類與標籤 (Tags)**: `Medical`, `Lifestyle`, `Elderly Care`, `Health`.
6. **點擊提交審核 (Submit)**。
