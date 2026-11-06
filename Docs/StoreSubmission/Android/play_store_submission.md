# PNCC Care - Google Play Store Submission Guide (Android)
## PNCC關懷 - Google Play Store 上架與審查指引 (Android)

This document provides complete metadata, asset specifications, Console declarations, Data Safety answers, and detailed instructions for submitting **PNCC Care** to the Google Play Store. It is localized in English, Simplified Chinese, and Traditional Chinese.

---

## 1. Play Store Console Metadata / 谷歌商店元數據

### 1.1 English (en-US)

| Field | Character Limit | Proposed Value |
| :--- | :--- | :--- |
| **App Name** | 30 | `PNCC Care` |
| **Short Description** | 80 | `Elder safety check-in tracker with daily scriptures & caregiver monitoring.` |

#### Full Description (up to 9900 characters)
```text
PNCC Care is an elder-friendly personal safety companion designed to bring peace of mind to seniors and their caregivers. By combining incredibly simple daily safety check-ins with beautiful typography, daily scripture devotionals, and real-time caregiver status monitoring, PNCC Care bridges the gap between senior independence and family peace of mind.

ELDER-FRIENDLY & ACCESSIBLE FEATURES:
• One-Tap Check-In: A huge, high-contrast "I'm Okay" button designed specifically for senior accessibility (conforming to a minimum 48dp touch target size). Pressing it resets the active safety countdown and auto-minimizes the app in 500ms to avoid confusion.
• Daily Devotionals: Start your morning with a curated scripture verse. Support for English (NIV, KJV) and Chinese (CUV) with offline reader functionality to read entire chapters.
• Automatic Fall Detection (Experimental): Utilizing the device's high-frequency accelerometer to detect severe mechanical impacts, paired with a 30-second cancellation warning to prevent false alarms.
• Gentle Reminders: Elegant color-coded countdown warning notifications (Amber/Orange) let you know when check-in is due, preventing false caregiver alarms.

PREMIUM CAREGIVER CONSOLE:
• Real-Time Dashboard: Track multiple cared seniors in real-time, categorized clearly by safety states (Green: Safe, Amber: Grace Period/Countdown Active, Red: Emergency Alert/Expired, Grey: Paused/Vacation).
• Remote Reset: If you verbally confirm that a senior is safe, reset their active check-in timer remotely from your console.
• Preferred Contact Channels: Instantly contact your cared seniors using their preferred methods (Phone Call, SMS, WhatsApp, Line, or WeChat) preconfigured in their profiles.
• Dynamic Secure Pairing: Establish instant care group relationships via secure QR Code scanning directly on the senior's screen. No complicated passwords or typing required.

PRIVACY & SECURITY COMMITTED:
PNCC Care treats your privacy with the utmost respect.
• High-security Firestore real-time database with strict Firestore Security Rules.
• All communications are encrypted in transit via SSL/TLS.
• Sensor checks are calculated strictly locally on-device. No GPS location tracking, keeping your battery healthy and your personal data safe.
```

---

### 1.2 Simplified Chinese / 简体中文 (zh-Hans)

| Field | Character Limit | Proposed Value |
| :--- | :--- | :--- |
| **App Name** | 30 | `PNCC关怀` |
| **Short Description** | 80 | `专为长辈设计的极简平安回报与安全守护工具，融合圣经金句与照顾者监测。` |

#### Full Description / 详细描述 (简体中文)
```text
PNCC关怀 是一款专为年长者及其照顾者量身打造的高品质安全守护应用。我们将极简的每日平安回报系统、优美的字形排版、宁静的每日圣经金句阅读，以及照顾者端实时监测看板完美融合，在保障长者独立生活的同时，让远方的家人时刻安心。

长辈端核心功能：
• 一键报平安：专为银发族优化的高对比度、大尺寸“我很好”按钮（超过 48dp 触摸热区）。轻按即可重置安全计时器并自动收起应用，无需复杂操作。
• 每日圣经金句：开启充满恩典的每一天。支持离线阅读简体中文和合本 (CUV)、英文 (NIV/KJV) 圣经，可直接展开阅读完整章节。
• 智能跌倒检测：利用设备内置的高精度加速度传感器检测严重冲击，并配备 30 秒的取消宽限期，有效避免误报。
• 溫馨状态提醒：醒目的色彩编码（橙色/黄色）优雅提醒您在警报触发前进行报平安动作。

照顾者端核心功能：
• 状态监测主控台：在一个看板上清晰掌握所有受照护长辈的实时安全状态，通过颜色分类一目了然（绿色：安全，橙色：宽限期，红色：警报触发/超时，灰色：度假/暂停监测）。
• 远端计时重置：当您通过电话或视讯确认长辈安全后，可直接在您的设备上远端重置其报平安计时器。
• 快捷联系通道：根据长辈首选的联系方式（电话、简讯、WhatsApp、Line 或 微信），一键发起直接对话。
• 极速二维码配对：直接扫描长辈设备上的专属二维码，即可建立安全的加密绑定，无需繁琐的邀请码。

隐私与数据安全：
PNCC关怀高度重视用户隐私。
• 基于 Google Firebase 的高安全性加密 Firestore 实时数据传输。
• 所有传感器分析均在设备本地完成，绝不收集或向第三方共享任何 GPS 位置轨迹或活动数据，极度省电且保护隐私。
```

---

### 1.3 Traditional Chinese / 繁體中文 (zh-Hant)

| Field | Character Limit | Proposed Value |
| :--- | :--- | :--- |
| **App Name** | 30 | `PNCC關懷` |
| **Short Description** | 80 | `專為長輩設計的極簡平安回報與安全守護工具，融合聖經金句與照顧者監測。` |

#### Full Description / 詳細描述 (繁體中文)
```text
PNCC關懷 是一款專為年長者及其照顧者量身打造的高品質安全守護應用。我們將極簡的每日平安回報系統、優美的字型排版、寧靜的每日聖經金句閱讀，以及照顧者端即時監測看板完美融合，在保障長者獨立生活的同時，讓遠方的家人時刻安心。

長輩端核心功能：
• 一鍵報平安：專為銀髮族優化的高對比度、大尺寸「我很好」按鈕（超過 48dp 觸摸熱區）。輕按即可重置安全計時器並自動收起應用，無需複雜操作。
• 每日聖經金句：開啟充滿恩典的每一天。支援離線閱讀繁體中文和合本 (CUV)、英文 (NIV/KJV) 聖經，可直接展開閱讀完整章節。
• 智能跌倒檢測：利用設備內置的高精度加速度感應器檢測嚴重衝擊，並配備 30 秒的取消寬限期，有效避免誤報。
• 溫馨狀態提醒：醒目的色彩編碼（橙色/黃色）優雅提醒您在警報觸發前進行報平安動作。

照顧者端核心功能：
• 狀態監測主控台：在一個看板上清晰掌握所有受照護長輩的即時安全狀態，透過顏色分類一目了然（綠色：安全，橙色：寬限期，紅色：警報觸發/超時，灰色：度假/暫停監測）。
• 遠端計時重置：當您透過電話或視訊確認長輩安全後，可直接在您的設備上遠端重置其報平安計時器。
• 快捷聯繫通道：根據長輩首選的聯繫方式（電話、簡訊、WhatsApp、Line 或 微信），一鍵發起直接對話。
• 極速二維碼配對：直接掃描長輩設備上的專屬二維碼，即可建立安全的加密綁定，無需繁瑣的邀請碼。

隱私與數據安全說明：
PNCC關懷高度重視用戶隱私。
• 基於 Google Firebase 的高安全性加密 Firestore 即時數據傳輸。
• 所有感應器分析均在設備本地完成，絕不收集或向第三方共享任何 GPS 位置軌跡或活動數據，極度省電且保護隱私。
```

---

## 2. Graphic Asset Requirements / 視覺資源規範

Google Play Store enforces specific requirements for icons and feature banners.

### 2.1 Google Play Store App Icon
- **Size**: `512 x 512 pixels`
- **Format**: 32-bit PNG (with alpha channel allowed, though transparent areas are not recommended; keep it square, as Google Play applies a 20% corner mask).
- **File Size**: Max `1 MB`

### 2.2 Feature Graphic (Banner)
This banner is displayed at the top of your store page and is critical for conversions.
- **Size**: `1024 x 500 pixels`
- **Format**: JPEG or 24-bit PNG (no alpha channel / transparency).
- **Design Directive**: Use a sleek glassmorphic card on a deep-blue gradient background (`#0D47A1` to deep navy). Showcase the text **PNCC Care** in gold/white modern sans-serif typography with the subtitle **Safety & Peace of Mind**. Place critical visual elements (like a phone mockup) near the center or right side; avoid putting logos or text within 15% of any border to prevent cropping.

### 2.3 Screenshot Specifications
Upload at least two screenshots of the app (max 8).

- **Phone Screens**: Min `320px` to Max `3840px` along the longest side. Recommended ratio is `9:16` or `16:9` (e.g., `1080 x 1920 pixels` or standard modern resolution `1080 x 2400 pixels`).
- **7-inch Tablet Screens (Optional)**: Upload up to 8 landscape or portrait mockups.
- **10-inch Tablet Screens (Optional)**: Upload up to 8 landscape or portrait mockups.

---

### 2.4 Proposed Visual Layout & Content (5-Screenshot Plan)
Make screenshots clean, bold, and modern to match the premium dark mode and high-contrast accessibility interface.

```carousel
#### Slide 1: One-Tap Safety (Senior Mode)
- **Graphic Visual**: Android phone mockup highlighting the glowing high-contrast safe status card, the daily Scripture text, and the large "I'm Okay" button.
- **Header Text**: "Elder Accessibility / 一鍵安全回報"
- **Detail**: "Conforms to 48dp touchscreen accessibility standards for stable operation."
<!-- slide -->
#### Slide 2: Active Grace Period Timer
- **Graphic Visual**: Showing the warm orange/amber warning screen with the active countdown "Please check in within: 24:59".
- **Header Text**: "Grace Period Alerts / 溫馨倒數提醒"
- **Detail**: "Prominent notifications prompt safe action before caregiver alerts trigger."
<!-- slide -->
#### Slide 3: Caregiver Dashboard
- **Graphic Visual**: Caregiver list showing active status monitoring, complete with color indicators (Green: Safe, Amber: Pending, Red: Expired, Grey: Paused).
- **Header Text**: "Status Console / 照顧者實時看板"
- **Detail**: "Tracks all care receivers in real-time. Remotely reset timers instantly."
<!-- slide -->
#### Slide 4: Expanded Scripture Reader
- **Graphic Visual**: Showing the expanded Scripture text screen displaying a full bible chapter in a soft paper-beige text card (`#FDFBF7`) with high contrast serif typography.
- **Header Text**: "Offline Devotionals / 離線心靈金句讀經"
- **Detail**: "Access CUV, NIV, and KJV versions with zero internet required."
<!-- slide -->
#### Slide 5: Dynamic Pairing & SOS Contacts
- **Graphic Visual**: Left side shows a QR Code; right side shows caregiver scanning it using Android's native camera stream.
- **Header Text**: "Zero-Config Pairing / 二維碼即時配對"
- **Detail**: "Scan to bond instantly. Supports preconfigured phone, SMS, WhatsApp, or WeChat channels."
```

---

## 3. Play Store Console Questionnaire & Data Safety Form

Google Console enforces a detailed compliance review. Below are the precise answers to input into the console forms.

### 3.1 Content Rating (IARC)
- **Category**: `Utility / Productivity` (or `Social / Communication`)
- **Violence**: No (The app contains no violent content).
- **Sexuality**: No.
- **Language**: No (No profanity or offensive language).
- **Controlled Substances**: No.
- **Miscellaneous**:
  - Does the app share the user's physical location? **No** (The app does not track GPS coordinates).
  - Does the app allow users to purchase digital goods? **No**.
  - Does the app allow users to communicate with others? **Yes** (Seniors can contact caregivers, but strictly via external system dialers/launchers like Phone, SMS, WhatsApp; not peer-to-peer inside the app).

### 3.2 Data Safety Questionnaire (Mandatory)
Google requires a full disclosure of collected data types. Fill in the Data Safety form as follows:

| Data Type | Collected | Shared | Purpose | Encrypted in Transit? | Ephemeral / Stored? |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Personal Info (Name, Email)** | Yes | No | Account management, authentication | Yes | Stored (Allows user deletion) |
| **Personal Info (Phone Number)** | Yes | Yes (With paired Caregivers) | Core app functionality (Caregiver direct contact) | Yes | Stored (Allows user deletion) |
| **Device or Other IDs** | Yes | No | App performance, push notifications | Yes | Stored |
| **Physical Activity / Motion** | No (Sensor processed strictly locally) | No | Fall Detection calculations | Yes | Ephemeral (Processed locally, never uploaded) |

**Q: Do you provide a way for users to request that their data be deleted?**
> **A**: Yes. Users can request account deletion by contacting support or using the delete account function under Profile Settings, which permanently removes their Firebase database documents.

### 3.3 Sensitive Permissions & Background Activity
Since we use background monitoring of activity, Google may ask about background services.
- **Foreground Service Type**: `Special Use` (or `None`). PNCC Care relies on a Flutter local timer background service strictly to verify device usage. Since it does NOT run high-frequency location tracking or active media recording, it conforms easily to standard policies.

---

## 4. Step-by-Step Google Play Store Submission Instructions

Follow this flow to build, upload, and release your Android app bundle:

### Step 1: Create a Google Developer Account & App Record
1. Go to [Google Play Console](https://play.google.com/console/) and sign in.
2. Click **Create app** in the top right.
3. Fill in the initial app details:
   - **App Name**: `PNCC Care`
   - **Default Language**: `English (United States)`
   - **App or Game**: `App`
   - **Free or Paid**: `Free`
4. Confirm declarations regarding Developer Program Policies and US export laws, then click **Create app**.

### Step 2: Set Up Store Listing & Localizations
1. In the left menu, scroll to **Grow users** -> **Main store listing**.
2. Input the localized App Name, Short Description, and Full Description for each locale (English, Simplified Chinese, Traditional Chinese).
3. Upload the required graphic assets:
   - **App Icon**: `512x512 PNG`
   - **Feature Graphic**: `1024x500 PNG/JPG`
   - **Phone Screenshots**: Drag and drop the 5 screenshots prepared.
4. Click **Save**.

### Step 3: Complete App Content Declarations
In the left menu, scroll to the bottom -> **Policy and program compliance** -> **App content**. You must complete all sections before you can release:
1. **Privacy Policy**: Link to `https://pncc-care.example.com/privacy`.
2. **Ads**: Declare that your app contains **No ads**.
3. **App Access**: Choose **All or some functionality is restricted** (Provide the demo senior and caregiver account details for the tester, similar to the iOS review).
4. **Content Rating**: Complete the IARC questionnaire.
5. **Target Audience**: Select **18 and older** (Avoids COPPA/children safety review complications).
6. **Data Safety**: Complete the questionnaire using the answers provided in Section 3.2.

### Step 4: Build and Upload the Android App Bundle (.aab)
1. Open your terminal in the project root:
   ```bash
   flutter clean
   flutter pub get
   flutter build appbundle --release
   ```
   *This compiles the optimized release bundle (`.aab`) to `build/app/outputs/bundle/release/app-release.aab`.*

### Step 5: Configure Internal/Closed Testing and Release
1. In the Play Console menu, go to **Release** -> **Testing** -> **Internal testing** (Recommended first step).
2. Click **Create new release** in the top right.
3. If prompted, let Google manage your App Signing Key (recommended).
4. Drag and drop the compiled `app-release.aab` file into the upload box.
5. Add Release Notes:
   ```text
   PNCC Care v3.0 release. Localized in English, Simplified Chinese, and Traditional Chinese. Core features include accessible check-ins, caregiver consoles, fall detection, and offline scripture reading.
   ```
6. Click **Next** -> **Save** -> **Publish release**.
7. Add test emails to the testers list, distribute the invite link, and verify runtime behavior on actual Android hardware.
8. Once testing is complete, promote the release to **Production** to make the app publicly available!
