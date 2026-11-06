# PNCC Care - Apple App Store Connect Questionnaire & Review Answers 📋

This document contains the exact, copy-pasteable answers to all the required questionnaires and sections in **App Store Connect** when submitting **PNCC Care** for review.

---

## 1. App Review Information (Demo Account & Notes)
Provide these details in the **App Review Information** section to allow Apple reviewers to test the complete pairing and status tracking loops.

### Demo Account Credentials
*   **Senior Account (Cared-For senior UI)**:
    *   **Email**: `tester.senior@pncc-care.com`
    *   **Password**: `AppleReviewer2026!`
*   **Caregiver Account (Dashboard Console UI)**:
    *   **Email**: `tester.caregiver@pncc-care.com`
    *   **Password**: `AppleReviewer2026!`

### Notes for Reviewer (Copy & Paste)
```text
We have fully verified and resolved both issues reported in the previous review (Apple Sign-In is verified with the com.apple.developer.applesignin entitlement; the iPad profile picker loading freeze has been completely fixed by transitioning setState to the post-frame rendering phase). Multiple iOS devices can now log into the same senior profile simultaneously with real-time settings and timer synchronization.

To review the complete safety check-in, two-way pairing consent, and remote status loops, please log in with the Senior credentials on one iOS device and the Caregiver credentials on another iOS device.

1. On the Senior device: Log in, select the existing senior profile (verifying it loads instantly!), and select "My Caregivers" from the home screen or "My Pairing QR Code" from Settings.
2. On the Caregiver device: Log in, tap the "+" button on the Caregiver dashboard, and scan the QR code displayed on the Senior's screen.
3. On the Senior device: A real-time pending caregiver pairing request will instantly appear under "My Caregivers". Click "Accept" to grant permission.
4. Once paired, trigger check-ins on the Senior device and see their status update in real-time on the Caregiver's dashboard. 
5. Test the "Remote Check-In Reset" feature by clicking the reset button on the Caregiver dashboard, which will remotely reset the Senior's active safety timer in real-time.
```

---

## 2. Background Modes & Sensor Usage Justification
Copy and paste this into the **Reviewer Notes / Background Activity Justification** if the App Review team flags background features:

```text
PNCC Care is a personal safety and elderly care tracking application. The core feature involves passive safety monitoring where the senior user commits to checking in daily (e.g., every 24 hours). 

1. Local Motion Activity / Accelerometer: The app uses the device's accelerometer local events (registered via Flutter services) to detect severe mechanical impacts (potential falls). Fall detection is computed strictly on-device to ensure privacy and has a 30-second warning countdown to allow the senior to cancel before SMS alerts are dispatched.
2. Timer Continuity: Background tasks are registered to periodically synchronize the senior's last active timestamp to the Firebase Firestore database. If the senior does not interact with the app or if no device activity is logged, the caregiver's console will reflect the "Expired" status in real-time, allowing the caregiver to check on their well-being.
We do NOT track or record geographical coordinates, preserving maximum battery efficiency and total user privacy.
```

---

## 3. App Privacy / Data Safety Questionnaire
Answer the following questions in the **App Privacy** section of App Store Connect.

### A. Contact Info
*   **Are you collecting Contact Info?**
    *   👉 **Yes** (we collect Email and Phone Number for account creation, device authentication, and pairing).
*   **How is it used?**
    *   Check: **App Functionality** (used to uniquely identify profiles and connect seniors with their caregivers).
*   **Is it linked to the user's identity?**
    *   Check: **Yes**.
*   **Is it used for tracking purposes?**
    *   Check: **No**.

### B. Fitness & Motion
*   **Are you collecting Fitness or Motion data?**
    *   👉 **Yes** (the app reads local accelerometer sensors strictly for fall detection).
*   **How is it used?**
    *   Check: **App Functionality** (used locally to run the physical fall detection algorithm).
*   **Is it linked to the user's identity?**
    *   Check: **Yes** (associated with the user's local safety profile state).
*   **Is it used for tracking purposes?**
    *   Check: **No**.

### C. Diagnostics (Crash Logs & Performance)
*   **Are you collecting Diagnostics data?**
    *   👉 **Yes** (Firebase Crashlytics is integrated).
*   **How is it used?**
    *   Check: **App Functionality** (to analyze crashes and optimize app stability).
*   **Is it linked to the user's identity?**
    *   Check: **No** (anonymous crash logging).
*   **Is it used for tracking purposes?**
    *   Check: **No**.

---

## 4. Age Rating Questionnaire (Age 4+)
Select **"None" / "No"** for all of the following:

*   Violence, sexual content, horror, crude humor, profanity: **None**.
*   Alcohol, tobacco, or drug use: **None**.
*   Simulated gambling: **None**.
*   Unrestricted web access / open-ended communication: **No**.
*   Is this app a medical or treatment app? **No** (it is a personal safety organizer and daily wellness check-in companion).

**Resulting Rating**: **Age 4+** (suitable for all ages).

---

## 5. Export Compliance & Advertising Identifier (IDFA)

### Export Compliance
*   **Does your app use encryption?**
    *   👉 **No** (Although the app uses HTTPS/SSL to communicate with Firebase, this is considered standard industry encryption and is fully exempt from export compliance filing under Category 5, Part 2).

### Advertising Identifier (IDFA)
*   **Does this app use the Advertising Identifier (IDFA)?**
    *   👉 **No** (The app is completely free, contains zero ads, and does not use any tracking SDKs).
