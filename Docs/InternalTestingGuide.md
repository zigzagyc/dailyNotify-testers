# dailyNotify Internal Beta Testing Guide

Welcome to the **dailyNotify** Internal Testing Guide! Before releasing the app to the general public on the Apple App Store and Google Play Store, conducting internal tests with your friends and family (especially potential caregivers and senior check-in users) is crucial. 

This guide details exactly how to distribute your beta builds to testers on **iOS** and **Android** based on their daily devices.

---

## Table of Contents
1. [Summary & Quick Comparison](#summary--quick-comparison)
2. [iOS Testing: TestFlight (Apple)](#1-ios-testing-testflight-apple)
   - [Internal vs. External Groups](#internal-vs-external-groups)
   - [Step-by-Step: Uploading and Inviting via TestFlight](#step-by-step-uploading-and-inviting-via-testflight)
   - [What Your Friends Need to Do (iOS)](#what-your-friends-need-to-do-ios)
3. [Android Testing: Google Play Console (Google)](#2-android-testing-google-play-console-google)
   - [Internal Testing Track (Highly Recommended)](#internal-testing-track-highly-recommended)
   - [Closed Testing Track (20 Testers Requirement)](#closed-testing-track-20-testers-requirement)
   - [Step-by-Step: Uploading and Inviting via Play Console](#step-by-step-uploading-and-inviting-via-play-console)
   - [What Your Friends Need to Do (Android)](#what-your-friends-need-to-do-android)
4. [Alternative Method: Firebase App Distribution (Quickest Setup)](#3-alternative-method-firebase-app-distribution-quickest-setup)
5. [Recommended Testing Workflows for dailyNotify Features](#4-recommended-testing-workflows-for-dailynotify-features)

---

## Summary & Quick Comparison

| Platform | Recommended Tool | Review Required? | Limits | Invite Method | Speed to Testers |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **iOS** | **TestFlight (External)** | Yes (Lenient, ~12-24h) | 10,000 | Email or Public Link | Moderate |
| **iOS** | **TestFlight (Internal)** | No | 100 | App Store Connect account | Instant |
| **Android** | **Google Play (Internal)** | **No** | 100 | Email list | **Instant (Minutes)** |
| **Android** | **Google Play (Closed)** | Yes (Standard, ~1-3 days) | Unlimited | Email list or Google Group | Slow |
| **Both** | **Firebase App Distribution**| **No** | 500 per app | Email invitation / Link | **Instant (Minutes)** |

> [!TIP]
> **Recommended Strategy**: Use **Google Play Internal Testing** for Android users and **TestFlight (External)** for iOS users. If you want a quick, unified experience without dealing with Apple's Beta Review, set up **Firebase App Distribution** for both.

---

## 1. iOS Testing: TestFlight (Apple)

TestFlight is the official Apple platform for beta testing. It handles updates, notifications, and installation smoothly on iPhones.

### Internal vs. External Groups

*   **Internal Testers (Team Members)**: Up to 100 users. Testers must be added as "Users" in your Apple Developer team in App Store Connect (requires assigning roles like Admin, App Manager, Developer, or Customer Support).
    *   *Pros*: No Beta App Review required; builds are available immediately.
    *   *Cons*: Overkill for casual friends/family because they must join your development team account.
*   **External Testers (Friends & Family)**: Up to 10,000 users. Anyone with an email address can be invited.
    *   *Pros*: Safe, no access to your developer account settings. Very easy for friends to join.
    *   *Cons*: The first build of a version requires a basic **Beta App Review** by Apple (usually approved in 8 to 24 hours). Subsequent builds under the same version number are approved instantly.

### Step-by-Step: Uploading and Inviting via TestFlight

#### Step 1: Upload your iOS Build
1. Open your Flutter project in Xcode (`open ios/Runner.xcworkspace`).
2. Select **Any iOS Device (arm64)** as the target.
3. Choose **Product > Archive** from the top menu.
4. Once archived, the Organizer window will open. Click **Distribute App** and choose **TestFlight & App Store**.
5. Follow the prompts to sign, package, and upload the build to App Store Connect.

#### Step 2: Configure TestFlight in App Store Connect
1. Navigate to [App Store Connect](https://appstoreconnect.apple.com/) and sign in.
2. Select your app **dailyNotify** and click the **TestFlight** tab at the top.
3. Under **External Groups** on the left menu, click the **`+`** icon and create a group (e.g., "Family & Friends").
4. Click into the new group and scroll to **Builds**. Click **`+`** to select the build you just uploaded.
5. Provide the required beta description, contact details, and click **Submit for Review**. 

#### Step 3: Invite Your Friends
Once Apple approves the build (usually within 12-24 hours for the first submission):
*   **Option A (Email Invite)**: In the Group, click **`+`** next to **Testers** and select **Add New Testers**. Enter your friends' email addresses.
*   **Option B (Public Link)**: Click **Enable Public Link**. Copy the link and share it directly on WhatsApp, Line, WeChat, or iMessage. Anyone clicking this link can join instantly.

---

### What Your Friends Need to Do (iOS)

Instruct your friends with iPhones to follow these steps:

1. Download the free **TestFlight** app from the App Store on their iPhone.
2. If invited by **Email**: Open the Apple email invitation on their iPhone, tap **View in TestFlight**, then tap **Accept** or **Install**.
3. If invited by **Public Link**: Tap the shared link, which automatically launches TestFlight and prompts them to install **dailyNotify**.
4. Once installed, the beta app will show an orange dot next to its name on the home screen.

---

## 2. Android Testing: Google Play Console (Google)

Google Play Console offers multiple testing tracks. For fast testing with friends, we highly recommend the **Internal Testing Track**.

### Internal Testing Track (Highly Recommended)
*   **No Review Needed**: Uploaded builds are ready to download in **under 10 minutes**!
*   **Capacity**: Up to 100 testers per list.
*   **Best For**: Direct family members, friends, and co-developers.

### Closed Testing Track (20 Testers Requirement)
*   **Note**: If your developer account was created *after* November 2023, Google requires you to run a Closed Test with **at least 20 active testers** who opt-in continuously for **14 days** before you are allowed to publish the app to production.
*   **Review Needed**: Google reviews closed testing uploads (takes 1-3 days).

### Step-by-Step: Uploading and Inviting via Play Console

#### Step 1: Build the Release Package
In your terminal, navigate to the root directory of dailyNotify and run:
```bash
flutter build appbundle --release
```
This outputs a secure `.aab` file at `build/app/outputs/bundle/release/app-release.aab`.

#### Step 2: Upload to Internal Testing
1. Sign in to the [Google Play Console](https://play.google.com/console/).
2. Select your app. Under the **Testing** section in the left menu, select **Internal testing**.
3. Click **Create new release** in the top right corner.
4. Drag and drop the `app-release.aab` file you built. 
5. Add release notes and click **Save**, then **Review release**, and finally **Start rollout to Internal testing**.

#### Step 3: Set up and Share with Testers
1. Still under **Internal testing**, select the **Testers** tab at the top.
2. Click **Create email list** (or select an existing one).
3. Enter your friends' Google account email addresses (they must be the primary emails they use on their Android phones). Click **Save**.
4. Scroll down to **How testers join your test**. Copy the **Join on the Web** or **Join on Android** opt-in link.
5. **CRITICAL**: Send this opt-in link to all the email list members.

---

### What Your Friends Need to Do (Android)

Instruct your friends with Android devices to follow these steps:

1. Open the shared opt-in link on their Android phone.
2. Sign in with the **same Google account** they use for the Google Play Store.
3. Tap the button that says **Become a Tester** (or **Join Program**).
4. Tap **Download it on Google Play** from the link, which will launch the Play Store and display the beta app page.
5. Tap **Install** to download **dailyNotify**.

---

## 3. Alternative Method: Firebase App Distribution (Quickest Setup)

If you want a unified, super-fast way to share beta versions without waiting for App Store Review, **Firebase App Distribution** is an excellent alternative.

### How it works:
1. Enable App Distribution in your [Firebase Console](https://console.firebase.google.com/).
2. For **Android**: Upload your release `.apk` (built via `flutter build apk --release`).
3. For **iOS**: Upload your `.ipa` (requires registering testers' iPhone UDIDs in your Apple developer portal first, which is standard for Ad-hoc distribution).
4. Input your friends' emails in the Firebase console.
5. Your friends receive an email, click the link to install the "Firebase App Tester" profile, and download dailyNotify instantly.

---

## 4. Recommended Testing Workflows for dailyNotify Features

When your friends and family begin testing, ask them to verify these specific scenarios:

### Scenario A: Shared Apple Account Separation (Multi-Device Setup)
1. **Setup**: Have two testers (e.g. husband and wife) log in using the **same Apple ID** on two different physical iPhones.
2. **Behavior**: Verify that the app asks **"Who is using this device?"** on startup for the second device.
3. **Roles**: Create a **Senior / Care Receiver** profile on one device, and a **Caregiver** profile on the other device.
4. **Validation**: Check that the app successfully separates their identities, lists the Senior under the Caregiver's "People I Care For" list, and registers separate active statuses.

### Scenario B: Pairing & QR Code Scanner
1. Open the Caregiver screen on the caregiver's device.
2. Tap the **QR Code** button to display the QR Code.
3. On the senior's device, scan the QR code to establish the link.
4. Confirm the link appears immediately on the caregiver's dashboard screen.

### Scenario C: Active Check-In & Alert Escalation
1. Set the check-in frequency to a very low test value (e.g., 1 minute) in Settings.
2. Let the timer expire.
3. Confirm that the Senior receives a reminder notification.
4. If no check-in is performed within the timeout window, confirm that the Caregiver's phone receives an **Emergency Alert** notification instantly.

---

*Need help setting up developers accounts or configuring code signing certificates? Refer to the [Store Submission Guide](./StoreSubmission) for details.*
