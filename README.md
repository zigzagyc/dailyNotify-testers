# dailyNotify (PNCC Care) 🌟

A comprehensive, cross-platform (iOS & Android) Flutter safety monitoring application for seniors and caregivers.

---

## 🚀 Key Features

### 1. 🔗 Instant Deep-Link Pairing & Multi-Channel Sharing
- **Zero-Friction Pairing**: Share invitation links (`dailynotify://pair?id=UID`) directly via **LINE, WhatsApp, SMS (Messages), or WeChat**.
- **One-Tap Auto-Pairing**: Tapping the invitation link in any chat app opens `dailyNotify` automatically and prompts the user to confirm the pairing request.

### 2. 🔍 Multi-Field Caregiver & Senior Search
- Search across multiple contact handles:
  - **Phone Number** (`+1...`)
  - **Full Name / First & Last Name**
  - **WeChat ID** (`wx_...`)
  - **LINE ID**
  - **WhatsApp Number**
  - **Email Address**
- Result items display clear contact tags (`📱 Phone`, `💬 WeChat`, `🟢 LINE`, `✉️ Email`).

### 3. 📅 Senior Multi-Range Safety Calendar View
- Inspect senior check-in history across flexible time ranges:
  - **1 Day (1D)**
  - **2 Days (2D)**
  - **3 Days (3D)**
  - **1 Week (1W / 7 Days)**
  - **1 Month (1M / 30 Days)**
- Color-coded daily indicators: 🟢 **OK (Checked in)** | 🔴 **Expired / Alert** | 🟠 **Paused / Vacation**

### 4. ⚠️ Consecutive Alert Aggregation
- Automatically consolidates consecutive missed check-in days into a single summary card:
  - *"Not responding since N days ago / 自 N 天前起未回報"*
- Prevents notification clutter and provides immediate actionable context for caregivers.

### 5. 🛡️ Caregiver-Only Mode Timer & Notification Suppression
- Profiles operating in **Caregiver-Only Mode** (`isCaregiver == true && isElderly == false`) automatically have check-in timers disabled (`checkInFrequency = 0`).
- Local check-in warning popups and persistent notifications are suppressed so caregivers are not prompted with check-in reminders intended for seniors.

### 6. 📱 Collapsible Pairing QR Code Card
- Default-collapsed QR code header on `CaregiverScreen` optimizes primary screen real estate while offering quick 1-tap share access.

---

## 🛠️ Testing & Build Instructions

### Prerequisites
- **Flutter SDK**: `^3.11.3` (Dart `^3.11`)
- **iOS**: Xcode 15+ (CocoaPods `1.15+`, deployment target `iOS 15.5`)
- **Android**: Android Studio / Gradle 8.x (SDK `34+`)

### Commands
```bash
# Run unit & logic test suite
flutter test

# Build Android Release APK
flutter build apk --release

# Build iOS IPA Bundle
flutter build ipa
```
