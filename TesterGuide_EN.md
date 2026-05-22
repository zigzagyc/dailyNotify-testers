# dailyNotify (PNCC關懷) - Internal closed-loop Tester Guide 🌟

Welcome to the **dailyNotify** internal testing group! 

<!-- LATEST_RELEASE_START -->
### 📥 Latest Beta Download Links
* **Release Time**: 2026-05-22 13:55:32
* **Release Notes**: Beta Release - 2026-05-22 13:55
* **🤖 Android APK Download**: [Click here to download from Firebase](https://appdistribution.firebase.dev/i/9fb3e0a381cc30ee)
* **🍏 iOS IPA Installation**: [Click here to join TestFlight (or Firebase Ad-Hoc)](https://appdistribution.firebase.dev/i/9fb3e0a381cc30ee)
<!-- LATEST_RELEASE_END -->

---

## 🎯 Core Testing Concept (Dual-Roles & Multi-Device Testing)

> [!NOTE]
> **💡 Key Clarification: Why is every device "both a Caregiver and a Care Receiver" at the same time?**
> You have a very sharp eye! In our app architecture, **every single phone running the app has both roles built-in simultaneously**. 
> You can switch between these two identities instantly using the two tabs at the bottom of the screen:
> 1. **"My Care" Tab (Senior / Care Receiver side)**: Displays your personal safety state (Green or Yellow) and allows you to perform check-ins.
> 2. **"People I Care For" Tab (Caregiver side)**: Shows your caregiver dashboard where you monitor other seniors, view active alerts, and perform remote resets.

### Then why do we still need multiple devices and multiple accounts?
Although a single phone can easily switch tabs to view both interfaces, **a single user profile cannot pair with itself or trigger alert notifications to itself**.
To test real **cross-device data synchronization, QR-code pairing, and instant emergency alert updates**, you need a "closed-loop multi-device test":
* You will need **two separate devices** (e.g., your primary phone A and a backup phone B).
* Both devices must be logged in under **different accounts** (e.g., Account A and Account B).
* By pairing these two different accounts, you establish a real-time care link across space.

---

## 🔑 Device & Account Recommendations
To avoid account conflicts and ensure a clean experience when the app goes live:

*   **Primary Phone (Device A)**: Log in with your **main personal account** (Apple/Google ID).
    *   **Future Role**: When the app is officially released, this phone will be your actual **Caregiver device**.
    *   **During Testing**: Focus on using the **"People I Care For"** tab on this phone to scan QR codes and monitor your backup device.
*   **Backup Device (Device B)**: Log in with a **secondary/test account**.
    *   **Future Role**: Simulated **"Senior" / "Care Receiver"**.
    *   **During Testing**: Focus on using the **"My Care"** tab on this phone to trigger safety check-ins or let the timer run down to test alert escalations.

---

## 📱 WeChat Group Sharing & Installation Guide

Please share these instructions in your WeChat group so other testers can get set up easily:

### 🍏 For iPhone (iOS) Users:
1. Tap the **TestFlight Public Invitation Link** shared in the WeChat group.
2. **The Safari Redirection (Crucial) 💡**: WeChat's in-app browser blocks direct TestFlight deep-linking. 
   * Once the link opens inside WeChat, tap the **three dots `...`** in the top-right corner.
   * Select **"Open in Safari" (在 Safari 瀏覽器中打開)**.
3. Safari will automatically launch the **TestFlight** app (download it first from the App Store if you don't have it).
4. Tap **Accept** and then **Install** to download **PNCC關懷**.

### 🤖 For Android Users:
* **Direct APK Install**: The administrator will send the `app-release.apk` file directly in the WeChat group.
  * Simply tap the APK file in your WeChat chat window, download it, and select **Install**.
  * *Note*: If prompted by your phone's security, enable "Allow installation from this source" for WeChat.
* **Firebase Link**: If using the Firebase link, tap the link in WeChat, select the **three dots `...`** and click **"Open in Browser" (在瀏覽器中打開)** to download the APK via Chrome.

---

## 👥 First-Time Setup & Device Separation (Multi-Profile Selection)
When launching the app on your testing devices, our **Multi-Profile Architecture** ensures that each device has a unique identity:

1. On your **Primary Phone**: Create/Select your personal profile.
2. On your **Backup/Test Phone**: Create/Select a separate profile (e.g. named "Test Senior").
3. This isolates your active profiles perfectly even if the devices share the same iCloud or Google credentials!

---

## ⚙️ Senior Device Configuration & Settings Guide
To set up your simulation correctly, go to the **Settings** screen on your **Backup Phone (Device B / Senior)** and adjust the following parameters:

### 1. Edit Personal Information (Profile Settings)
* **How-to**: Tap the **"Edit"** icon next to the profile avatar at the top of the Settings screen.
* **Configurations**:
  * **Display Name**: Set your senior's test name (e.g., "User A", "Test Senior").
  * **Preferred Contact Method**: Choose SMS, Phone Call, WhatsApp, Line, or WeChat, and input the respective contact ID or phone number.

### 2. Configure Safety Timers
* **How-to**: Scroll down to the **"Monitoring Configuration"** section.
* **Configurations**:
  * **Check-In Frequency**: The app's default check-in frequency is **1440 minutes (1 day)**. Tap to open the dialog and set a shorter testing interval (e.g., set to `2` minutes).
  * **Alert Timeout**: Tap to set the warning countdown duration (e.g., set to `1` minutes).
  * *💡 Testing Tip*: Keep these set to **1 or 2 minutes** during testing to avoid waiting hours to trigger alerts!

### 3. Enable Fall Detection
* **How-to**: Scroll down to the **"Sensors"** section.
* **Configurations**:
  * Toggle the **"Enable Fall Detection"** switch to **ON**.

### 4. Switch Languages
* **How-to**: Under the **"Language"** section, tap the dropdown menu.
* **Available Options**:
  * System Default
  * English
  * Traditional Chinese (zh_Hant)
  * Simplified Chinese (zh)

### 5. Select Bible Translations
* **How-to**: Scroll down to the **"Bible Preferences"** section.
* **Configurations**:
  * **Bible Language**: Select English or Chinese (中文).
  * **Bible Version**:
    * If Chinese: select **CUV (和合本)**.
    * If English: select **NIV** or **KJV**.
  * Once saved, your devotional verses on the Read page will dynamically switch translations!

---

## 📲 Home Screen Widget Testing Guide
The Home Screen Widget allows caregivers to monitor their senior's status **in real-time without even opening the app**.

### Testing Steps:
1. **Add Widget**:
   * On your **Primary Phone (Caregiver)**, long-press the home screen.
   * Tap **"Add Widget (+)"**, search for **"PNCC關懷"** (or **dailyNotify**), and place it on your screen.
2. **Verify Safe State (OK)**:
   * Perform a check-in on the Senior device.
   * Return to your Caregiver home screen and verify the widget immediately displays **Green "OK"** status.
3. **Verify Vacation / Paused State**:
   * Set a "Pause Date Range (Vacation)" in the Senior device settings.
   * Verify the widget updates to **Grey "Paused"** status.
4. **Verify Overdue Alert State (Expired)**:
   * Let the Senior device miss its check-in until the emergency alert triggers (red alert banner displays).
   * Return to your Caregiver home screen and verify the widget immediately switches to a prominent **Red "Expired"** status.

---

## 🔔 Push Notification Testing Guide
Our notification system handles background check-in reminders, warnings, and sensor impacts.

### Testing Scenarios:

1. **Check-In Reminder Notification**
   * **How to trigger**: In the Senior settings, set the Check-In Frequency to `2` minutes. Close the app or put it in the background.
   * **Verification**: When there are 2 minutes remaining before check-in is due, the Senior phone should receive a notification: *“Are you okay? It's been a while since we heard from you. Please tap to check in.”*

2. **Overdue Emergency Warning Notification**
   * **How to trigger**: Let the Senior device timer completely expire (after the grace period).
   * **Verification**: The Senior phone should receive an urgent reminder: *“You missed your check-in! Please open the app immediately to cancel or send alerts.”*

3. **Fall Detection Impact Notification 🚨**
   * **How to trigger**:
     1. Ensure **"Enable Fall Detection"** is toggled **ON** in the Senior settings.
     2. With the app running (or in the background), **gently tap or quickly shake** the Senior device to simulate a sudden physical impact.
   * **Verification**:
     * The Senior phone must instantly display a high-priority red notification: *“Severe impact detected. Sending emergency alerts in 30 seconds. Tap to Cancel.”*
     * A loud sirens/alert sound should play.
     * **Test Cancel Action**: Tap the notification or hit "Cancel" in the app within 30 seconds, and verify that the countdown stops and no emergency alert is sent to the Caregiver's dashboard.

---

## 🔄 Closed-Loop Test Scenarios to Verify

Please run through these scenarios and provide detailed feedback to the development team:

### Test Scenario A: Care Group Pairing (QR Code Scan) 🔗
1. **Primary Phone (Device A)**: Go to the **"People I Care For"** tab, tap **Add Senior / Pair**. A custom QR Code will appear.
2. **Backup Phone (Device B)**: Go to the **"My Care"** tab settings or pairing screen, open the QR scanner, and scan Device A's screen.
3. **Verification**: The profiles should pair instantly. The simulated Senior must show up on Device A's caregiver dashboard list in real time.

### Test Scenario B: Active Check-In Sync (Green State) 🟢
1. **Backup Phone (Device B)**: In the **"My Care"** tab, view the green dashboard. It should display a peaceful message with the next due time (no ticking countdown).
2. **Verification**: Tap the screen to check in, and verify that Device A's **"People I Care For"** list's "Last Active Time" (最後活動) updates instantly in the background.

### Test Scenario C: Grace Period & Active Alert (Yellow/Red State) 🚨
1. **Backup Phone (Device B)**: Let the check-in timer run down into the Grace Period.
   * **Verification**: The screen turns yellow/orange and starts a ticking countdown. Tap **Check In** to verify it returns to green immediately.
2. **Primary Phone (Device A)**: If Device B's timer completely expires.
   * **Verification**: Verify that a prominent **red emergency alert banner** displays on Device A's **"People I Care For"** dashboard showing the **Alert Duration** and **Last Active Relative Time**.

### Test Scenario D: Spiritual Comfort (Daily Devotional) 📖
* Switch to the **Devotional** screen on both devices. Read the daily verses to verify font scaling, readability, and content presentation.

---

## 📝 Submitting Feedback
Please document:
* Your device models (e.g. iPhone 15 Pro, Xiaomi MI 9) and OS versions.
* Screen layout issues (text wrapping, overflowing elements).
* Any delayed updates, Firestore sync lag, or application crashes.

Thank you for helping us elevate **dailyNotify** to production release standard! 🚀
