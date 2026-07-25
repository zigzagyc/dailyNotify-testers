# dailyNotify (PNCC Care) - Tester Installation & Task Guide 🌟

Welcome to the **dailyNotify (PNCC Care)** internal testing group!

> [!NOTE]
> 💡 **No Technical Background Required (No Code Compilation)**:
> This repository is dedicated to serving pre-compiled application packages (`app-release.apk`) and testing guides. **Testers do not need Flutter, Xcode, or any coding tools**. Simply follow the step-by-step instructions below to install and test on your mobile devices.

---

## 📥 Installation Instructions

### 🤖 For Android Users:

#### Method A: Direct Phone Installation (Recommended & Simplest)
1. **Download Package**: Tap and download **`app-release.apk`** directly from your phone browser or chat group.
2. **Tap Install**: Once downloaded, tap the APK file and select **Install**.
3. *Security Note*: If prompted with "Installation from unknown sources disabled", tap **Settings** in the popup and toggle **"Allow from this source"** to ON.

#### Method B: Installation via ADB (For Testers with Computer Developer Mode)
If you are using command-line tools (`adb`) on a computer, follow these steps to enable Developer Mode:
1. **Enable Developer Options**:
   * Go to phone **Settings** -> Tap **About Phone**.
   * Locate **Build Number** and **tap it 7 times continuously**.
   * A toast notification will pop up: *"You are now a developer!"*.
2. **Enable USB Debugging**:
   * Return to main Settings -> **System** -> **Developer Options**.
   * Toggle **USB Debugging** to **ON**.
3. **Execute Installation**:
   * Connect your phone to your computer via USB and accept the *"Allow USB debugging?"* prompt.
   * Run the following command in your terminal:
     ```bash
     adb install -r app-release.apk
     ```

---

### 🍏 For iPhone (iOS) Users:
1. **Install TestFlight**: Download Apple's official **[TestFlight App](https://apps.apple.com/app/testflight/id899247664)** from the iPhone App Store.
2. **Get Invitation**:
   * Share your **Apple ID email** with the admin (`yuecheng@gmail.com`).
   * You will receive a TestFlight email invitation from Apple.
3. **Accept & Install**:
   * Open the email on your iPhone and tap **"View in TestFlight"**.
   * TestFlight will open automatically. Tap **"Install"** to install `PNCC Care`.

---

## 🎯 Master Test Task Matrix & Task Signup

To prevent multiple testers from redundantly testing simple features while leaving complex scenarios (e.g. cross-platform, N-on-1 care) untouched, we established the **[Master Test Task Matrix (TEST_MATRIX.md)](./TEST_MATRIX.md)**!

### 💡 How to Claim & Execute a Test Task:
1. Open **[TEST_MATRIX.md](./TEST_MATRIX.md)**.
2. Choose a Task ID suitable for your device setup (e.g., `TASK-12: Android Caregiver ↔ iOS Senior` or `TASK-05: 1~2 Min Short Safety Timer`).
3. Follow the **Step-by-Step bilingual instructions** specified for that Task ID.
4. After completing the test, submit a test report using the template below or file a report on GitHub Issues.

---

## 📝 Test Report Template

When submitting feedback or reporting a bug, copy and complete this form:

```markdown
### 📋 PNCC Care Test Feedback Form

- **Claimed Task ID**: [e.g. TASK-12]
- **Tester Name / Handle**: [e.g. Tester Alex]
- **Device Models & OS Versions**: [e.g. Pixel 4a (Android 13) & iPhone 13 (iOS 17.4)]
- **Account Email & Mode**: [e.g. tester1@gmail.com / Caregiver Mode]
- **Test Result**: 
  - [ ] 🟢 Pass (All functions working cleanly)
  - [ ] 🔴 Bug Found
- **Problem Description**:
  (If a bug is found, describe the exact behavior observed)
- **Steps to Reproduce**:
  1. ...
  2. ...
- **Screenshots / Video Clips**:
  (Attach screenshots or screen recordings)
```

---

## 🐞 Jira-Like Issue Tracking on GitHub

We have enabled **GitHub Issues** on this repository for Jira-like task and bug management:
- **Claim Test Task**: Click **"Claim Test Task"** on GitHub Issues to sign up for a task scenario.
- **File Bug Report**: Click **"Report a Bug"** to fill in problem details. The development team will mark status as `In Progress` or `Resolved` so you can track progress transparently!

Thank you for your valuable time and effort! 🚀
