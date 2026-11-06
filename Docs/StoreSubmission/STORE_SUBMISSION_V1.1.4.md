# PNCC Care (dailyNotify) - v1.1.4 Store Submission & Release Guide 🚀

本文件彙整 **PNCC關懷 (PNCC Care)** 升級至 **v1.1.4 (Build 24)** 後，發布至 **Google Play Store**、**Apple App Store (App Store Connect)** 與 **APKPure** 所需之全部套件資訊、中英文更新日誌 (Release Notes / What's New)、商店元數據 (Metadata)、手錶伴侶應用配置與審核備註。

---

## 📦 1. 編譯產物與版本號 (Build Artifacts & Version)

| 平台 / 通路 | 檔案路徑 | 檔案類型 | 用途與說明 |
| :--- | :--- | :--- | :--- |
| **Apple App Store** | `build/ios/ipa/PNCC care.ipa` (36.7 MB)<br>`build/ios/archive/Runner.xcarchive` (230 MB) | iOS App Package (.ipa) / Xcode Archive | **內含完整 Apple Watch 獨立伴侶應用 (`Payload/Runner.app/Watch/PNCCWatch Watch App.app`)**、齊全的 AppIcon 圖像集、HealthKit 使用描述字串、WidgetExtension，以及已修復啟動崩潰的 **Flutter.framework 與 App.framework 動態函式庫**。支援 iPhone「Watch」App 內自動探索、一鍵安裝與手錶打卡。 |
| **Google Play Store** | `build/app/outputs/bundle/release/app-release.aab` (60.4 MB) | Android App Bundle (.aab) | Google Play Console 內部測試 / 正式版上架發布。 |
| **APKPure / 官網直載 / 測試庫** | `build/app/outputs/flutter-apk/app-release.apk` (79.4 MB) | Universal APK (.apk) | APKPure 開發者後台 / GitHub 測試中心直接發布。 |

### 核心版本參數 (Version Attributes):
- **Version Name (版本名稱)**: `1.1.4`
- **Build Number / Version Code (構建號 / 內部版本碼)**: `24`
- **Android Package Name (Application ID)**: `com.zigzagyc.dailynotify`
- **iOS Bundle Identifier**: `com.zigzagyc.dailyNotify`
- **watchOS Bundle Identifier**: `com.zigzagyc.dailyNotify.watchkitapp`
- **Apple Team ID**: `UW6278TE85`
- **Min Android SDK**: `26` (Android 8.0 Oreo) | **Target SDK**: `36` (Android 16+)
- **Min iOS Version**: `15.6`
- **Min watchOS Version**: `9.0` (支援 Apple Watch Series 4 ~ Series 10 / Ultra / SE)

---

## 📝 2. 商店更新日誌 (What's New in v1.1.4)

請在各大商店的「此版本最新變更 / 新增功能 (What's New in this Version)」欄位複製以下內容：

### 2.1 繁體中文 (zh-TW / zh-HK / Traditional Chinese)
```text
【v1.1.4 最新更新內容】
1. ⌚️ Apple Watch 手錶伴侶應用上線：
   - 全新獨立 watchOS 應用程式，可在 Apple Watch 上直接查看長輩平安狀態與今日經文。
   - 支援手錶一鍵「我很好 · I'm OK」打卡，長輩無需隨身攜帶手機即可隨時報平安。
   - 雙向即時同步（WatchConnectivity）：手錶與手機隨時無縫同步平安狀態與緊急警報。
   - 支援 iPhone「Watch」App 之「可用的 App」清單內自動探索與一鍵安裝。
2. 虛擬三鍵導航欄適配：全面優化傳統虛擬三鍵（返回/主頁/多任務）設備之底部防遮擋 SafeArea 間距，軟體資訊、版本說明與對話框按鈕完整呈現。
3. 長輩首頁平安狀態與按鈕整合：將平安狀態與超大按鈕高度融合成單一優雅卡片，消除冗餘綠色色塊，第一螢幕免滾動即可輕鬆操作。
4. 橫向旋轉雙欄響應式佈局：設備橫向旋轉時自動切換為左右雙欄佈局，平安按鈕與今日金句並排呈現，一覽無遺。
5. 桌面小工具直達模式切換：點擊長輩小工具或家屬小工具可直接跳轉至對應身份視圖，並智能推薦開啟雙模式。
6. 系統穩定性與背景同步效能優化。
```

### 2.2 簡體中文 (zh-CN / Simplified Chinese)
```text
【v1.1.4 最新更新内容】
1. ⌚️ Apple Watch 手表伴侣应用上线：
   - 全新独立 watchOS 应用程序，可在 Apple Watch 上直接查看长辈平安状态与今日经文。
   - 支持手表一键“我很好 · I'm OK”打卡，长辈无需随身携带手机即可随时报平安。
   - 双向实时同步（WatchConnectivity）：手表与手机随时无缝同步平安状态与紧急警报。
   - 支持 iPhone“Watch”App 内“可用的 App”列表中自动发现与一键安装。
2. 虚拟三键导航底栏适配：全面优化传统虚拟三键（返回/主页/多任务）设备底部防遮挡 SafeArea 间距，软件信息、版本说明与对话框按键完整呈现。
3. 长辈首页平安状态与按键整合：将平安状态与超大按键高度融合成单一优雅卡片，消除冗余绿色色块，第一屏幕免滚动即可轻松操作。
4. 横向旋转双栏响应式布局：设备横向旋转时自动切换为左右双栏布局，平安按键与今日金句并排呈现，一览无遗。
5. 桌面小组件直达模式切换：点击长辈组件或家属小组件可直接跳转至对应身份视图，并智能推荐开启双模式。
6. 系统稳定性与后台同步性能优化。
```

### 2.3 English (en-US / International)
```text
What's New in v1.1.4:
• ⌚️ Apple Watch Companion App Launch:
  - Brand-new companion watchOS app to view senior safety status and daily scripture right on your wrist.
  - One-tap "I'm OK · 我很好" check-in directly from Apple Watch without needing to carry the iPhone.
  - Seamless bidirectional real-time synchronization between Apple Watch and iPhone via WatchConnectivity.
  - Automatically discoverable and installable from the iPhone's "Watch" companion app under "Available Apps".
• System 3-Button Navigation Bar Inset Adaptation: Enhanced dynamic SafeArea bottom padding for devices with traditional 3-button system bars (Back/Home/Recents), ensuring version info and dialog action buttons are completely visible without occlusion.
• Consolidated Senior Safety Card: Replaced redundant status blocks with a sleek, unified card combining real-time status and giant check-in button on the first screen without scrolling.
• Responsive Landscape 2-Column Mode: Automatic side-by-side layout when rotating device horizontally so safety buttons and scriptures remain fully visible.
• Desktop Widget Deep Linking: Caregiver and Senior home screen widgets now navigate straight to their respective view with 1-tap dual-mode recommendations.
• Custom Alert Banner: Added full color picker, pulsing animation options, and clean compact banner mode for caregiver alerts.
• Stability & background synchronization enhancements.
```

---

## 🍏 3. Apple App Store (App Store Connect) 上架指引

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
pncc care,senior safety,elderly tracking,daily checkin,bible verse,apple watch,fall detection,caregiver
```

### 3.3 App Review Information (審查登入帳號與備註)
- **Sign-In Required (是否需登入)**: `Yes`
- **Demo Account (測試帳號)**:
  - **Username / Email**: `tester_caregiver@pncc.org` (或您設定之測試帳號)
  - **Password**: `TestPass123!`
- **Notes for Reviewer (審查員說明備註)**:
```text
Dear Apple App Review Team,

This update (v1.1.4) introduces the official Apple Watch companion application and enhanced UI responsiveness for seniors:
1. Apple Watch Companion App: Seniors can check in with one tap ("I'm OK") and read their daily scripture directly from their wrist. Synchronizes with iPhone via WatchConnectivity.
2. One-Tap Check-In: Giant accessible touch target on both iPhone and Apple Watch.
3. Live Activities & Widgets: Uses ActivityKit for non-intrusive safety countdowns and emergency notifications.
4. Background & Push: Uses remote background notifications and local notifications solely to track safety intervals and notify pre-authorized family caregivers.

Thank you for your review!
```

### 3.4 上傳方式 (Upload to App Store Connect)
#### 方式 A: Apple Transporter (推薦，最簡便)
1. 在 Mac 上開啟 **Transporter** 應用程式。
2. 拖曳 `build/ios/ipa/PNCC care.ipa` 到 Transporter 視窗中。
3. 點擊 **交付 (Deliver)**。

#### 方式 B: 命令列 xcrun altool
```bash
xcrun altool --upload-app --type ios -f "build/ios/ipa/PNCC care.ipa" --apiKey <YOUR_API_KEY> --apiIssuer <YOUR_ISSUER_ID>
```

---

## 🤖 4. Google Play Store 上架指引

1. 登入 [Google Play Console](https://play.google.com/console)。
2. 選擇 **PNCC Care (com.zigzagyc.dailynotify)**。
3. 進入 **正式版 (Production)** 或 **內部測試 (Internal Testing)** -> **建立新版本 (Create New Release)**。
4. 上傳 `build/app/outputs/bundle/release/app-release.aab` (Version 1.1.4, Build 24)。
5. 在「版本說明 (Release Notes)」中貼上上述第 2 節之中英文更新日誌。
6. 點擊 **檢查版本 (Review Release)** -> **推出正式版 (Start Rollout)**。

---

## 🌐 5. APKPure 上架指引

1. 登入 [APKPure Developer Console](https://developer.apkpure.com/)。
2. 進入 **PNCC Care** 應用管理頁面。
3. 選擇 **Update App / 升級版本**。
4. 上傳 Universal APK: `build/app/outputs/flutter-apk/app-release.apk`。
5. 填寫更新日誌 (貼上上述繁中/簡中/英文更新內容)。
6. 點擊提交審核。

---

## 🌟 6. 內部測試中心 (Tester Repository)
- **測試中心網址**: [dailyNotify-testers (GitHub)](https://github.com/zigzagyc/dailyNotify-testers)
- 最新 APK (`app-release.apk`) 與更新日誌已自動推送至 GitHub `main` 分支。

---

## 🛠️ 7. Build 24 緊急技術修復備忘 (iPhone 13 啟動閃退修復)
- **問題現象**：v1.1.4 (Build 22/23) 通過 Apple 審核上架後，使用者升級至 iPhone 13 發生點擊圖示後立即閃退 (Crash immediately on launch)。
- **根本原因**：
  在 `ios/Runner.xcodeproj/project.pbxproj` 整合原生 Watch App 目標時，Xcode 建置階段遺漏了 Flutter 原生瘦身與動態庫嵌入腳本 `3B06AD1E1E4923F5004D2608 /* Thin Binary */` (`xcode_backend.sh embed_and_thin`)。
  導致打包出的 IPA 缺少了 `Payload/Runner.app/Frameworks/Flutter.framework` 與 `App.framework`，使得 iOS 系統動態加載器 (`dyld`) 啟動時回報 `image not found: @rpath/Flutter.framework/Flutter` 並直接終止應用程式。
- **修復方案**：
  1. 完整修復並恢復 `project.pbxproj` 中的 `Thin Binary` 構建階段，設定於 `Embed Watch Content` 之後執行。
  2. 編譯之 `build/ios/ipa/PNCC care.ipa` 容量由 15.8 MB 增至 **36.7 MB**，經檢驗包含：
     - `Payload/Runner.app/Frameworks/Flutter.framework/Flutter` (9.0 MB)
     - `Payload/Runner.app/Frameworks/App.framework/App` (9.5 MB)
     - `Payload/Runner.app/Watch/PNCCWatch Watch App.app/` (含 watchOS 獨立架構與圖示)
     - `Payload/Runner.app/PlugIns/DailyNotifyWidgetExtension.appex/` (iOS 桌面小工具)
  3. 版本號升級至 `1.1.4 (Build 24)`，交付 Transporter 上傳即可無縫替換並修復閃退。
