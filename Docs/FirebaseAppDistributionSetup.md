# Firebase App Distribution Setup Guide

This guide walks you through setting up and using **Firebase App Distribution** to share beta builds of **dailyNotify** with your friends and family instantly.

---

## 🛠️ Step 1: Enable App Distribution in Firebase Console

1. Navigate to the [Firebase Console](https://console.firebase.google.com/).
2. Select your project: **`dailynotify-330f0`**.
3. In the left navigation sidebar under the **Release & Monitor** section, click **App Distribution**.
4. Click the **Get Started** button.
5. In the top dropdown list, verify you see your active app configurations:
   * **Android**: `1:366849813271:android:fe4596fd42afcc707d2552`
   * **iOS**: `1:366849813271:ios:cb34026fba8051a27d2552`

---

## 📦 Step 2: Compile Your Release Builds Locally

### 1. Build Android APK
Compile the Android release build as a standalone installable package:
```bash
flutter build apk --release
```
* **Output Path**: `build/app/outputs/flutter-apk/app-release.apk`
* *Note*: This APK contains everything required to run the app directly on any Android device.

### 2. Build iOS IPA (Requires Apple Developer Account)
Because Apple strictly regulates app distribution, installing a beta `.ipa` outside of TestFlight requires registering your testers' device unique IDs (UDIDs) in your Apple Developer Portal.
1. Collect the UDIDs of your testers' iPhones.
2. Register them in the [Apple Developer Devices Portal](https://developer.apple.com/account/resources/devices/list).
3. In your terminal, run the Flutter export command:
```bash
flutter build ipa --export-method ad-hoc
```
* **Output Path**: `build/ios/ipa/Runner.ipa`

---

## 🚀 Step 3: Distribute Your Builds

You can distribute builds using either the **Web Console (Zero Configuration)** or the **Firebase CLI (Terminal)**.

### Method A: Web Console (Easiest & Fastest)

This is the recommended approach for manual releases as it requires no extra tools.

1. Under the **App Distribution** page in the Firebase Console, select your app in the platform dropdown (Android or iOS).
2. Drag and drop your compiled release file (`app-release.apk` or `Runner.ipa`) into the upload area.
3. Once the upload finishes:
   * Enter your friends' email addresses in the **Add testers** field.
   * Add release notes describing the updates (e.g., *"Multi-profile support added!"*).
4. Click **Distribute to 1 tester** (or group).
5. Done! Your friends will instantly receive an invitation email.

---

### Method B: Firebase CLI (Automated Terminal Deploy)

If you prefer uploading directly from your code terminal, follow these steps:

#### 1. Install the Firebase CLI
Make sure you have Node.js installed, then run:
```bash
npm install -g firebase-tools
```

#### 2. Log In to Firebase
Run the login command and authorize using your Google Account linked to Firebase:
```bash
firebase login
```

#### 3. Define a Testers Group (Optional)
To make command line uploads easier:
1. Go to the **Testers & Groups** tab under **App Distribution** in the Firebase Console.
2. Click **Add Group**, name it `friends`, and add your testers' emails.

#### 4. Run the Upload Commands

##### For Android:
```bash
firebase appdistribution:distribute build/app/outputs/flutter-apk/app-release.apk \
  --app 1:366849813271:android:fe4596fd42afcc707d2552 \
  --groups friends \
  --release-notes "New Android release with multi-profile account support."
```

##### For iOS:
```bash
firebase appdistribution:distribute build/ios/ipa/Runner.ipa \
  --app 1:366849813271:ios:cb34026fba8051a27d2552 \
  --groups friends \
  --release-notes "New iOS release with multi-profile account support."
```

---

## 📱 Step 4: What Your Friends Will See

1. **Invitation Email**: Your friends will receive an email from *Firebase App Distribution* titled *"You've been invited to test..."*.
2. **Accept Invitation**: They must tap **Get Started** in that email on their daily device.
3. **Register Device (iOS Only)**: iOS testers will be guided to register their device UDID with you if it hasn't been added.
4. **App Installation**:
   * **Android**: They will download the **Firebase App Tester** web app or install the APK directly.
   * **iOS**: They will install the **Firebase Profile** certificate, then tap **Install** to download **dailyNotify** directly onto their home screen.
