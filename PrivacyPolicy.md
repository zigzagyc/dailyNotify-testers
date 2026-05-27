# Privacy Policy for PNCC Care (dailyNotify) 🔒

*Last Updated: May 27, 2026*

**PNCC Care** ("we", "our", or "us") is dedicated to protecting the privacy of senior users and their caregivers. This Privacy Policy describes how we handle, collect, and safeguard your data when using the **PNCC Care** application.

---

## 1. Information We Collect and How We Use It

To deliver our core safety monitoring and real-time status features, we collect the following limited types of information:

### A. Contact Information (Email & Phone Number)
*   **Collection**: We collect your email address and optional phone number during registration.
*   **Purpose**: These are used exclusively to create your secure user profile, authenticate your account, and enable encrypted pairing between senior users and their designated caregivers. We do NOT use this information for marketing or share it with third parties.

### B. Device Motion & Sensor Data (Accelerometer)
*   **Collection**: The application accesses local device accelerometer and motion sensors.
*   **Purpose**: This data is computed **strictly on-device** to run our local physical fall detection algorithms.
*   **Privacy**: Your physical motion details, raw values, and sensor logs are never uploaded to our servers, sold, or shared. Only the local binary result ("Safe" or "Potential Fall Alert") is communicated to your paired caregiver.

### C. Diagnostics and Crash Reporting
*   **Collection**: Anonymous application crash logs and performance metrics (via Firebase Crashlytics).
*   **Purpose**: Used strictly to identify bugs, analyze crashes, and optimize stability to ensure the app remains operational during safety emergencies. These logs do not contain personally identifiable information.

---

## 2. No Location Tracking
**PNCC Care** does not access, record, or track your physical GPS coordinates or location tracks. We preserve maximum device battery life and absolute user privacy by monitoring activity purely through local motion indicators.

---

## 3. Data Storage & Security
We utilize secure, enterprise-grade cloud servers (Google Firebase) to host the encrypted pairing link and real-time status console. 
*   All communications between the app and the cloud database are encrypted in transit via SSL/TLS.
*   We implement robust Firestore security rules to ensure that only your authorized, paired caregiver can view your status console.

---

## 4. Your Rights & Data Deletion
You can edit your personal profile info at any time inside the Settings screen. If you wish to delete your account and scrub all associated pairing links and metadata from the database, you can do so directly in the app or by contacting the developer at: **yuecheng@gmail.com**.

---

## 5. Contact Us
If you have any questions or feedback regarding this Privacy Policy, please contact us at:
*   **Email**: **yuecheng@gmail.com**
*   **Support Portal**: [https://github.com/zigzagyc/dailyNotify-testers](https://github.com/zigzagyc/dailyNotify-testers)
