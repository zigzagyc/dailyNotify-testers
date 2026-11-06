# Software Requirements Specification (SRS) - PNCC關懷 / dailyNotify
## 軟體需求規格說明書 - PNCC關懷 / dailyNotify

---

# Part 1: English Version (英文版)

## 1. Introduction
### 1.1 Purpose
This document specifies the software requirements for **PNCC關懷 (dailyNotify)**, an intelligent elder care and safety check-in application. The system enables proactive monitoring of seniors (Care Receivers) through sensor-driven activity tracking, manual safety check-ins, and fallback emergency alert notification channels for family members or professional caregivers.

### 1.2 Scope
The system consists of:
1. **Senior App (Care Receiver UI)**: A tranquil, simplified interface displaying scripture verses, a large action-oriented "I'm Okay" button, passive activity monitoring, and safety countdown timers.
2. **Caregiver App (Caregiver UI)**: A comprehensive, glassmorphic monitoring dashboard showing safety statuses, real-time alert logs, dynamic communication triggers, and remote timer controls.
3. **iOS SwiftUI Widget**: An interactive home screen widget displaying real-time status counts and individual care status lists.
4. **Cloud Backend**: A secure Cloud Firestore backend handling real-time synchronization of check-in settings, sensor updates, active warning states, and caregiver pairings.

### 1.3 Intended Audience
This document is intended for project developers, QA engineers, system administrators, and stakeholders to verify and validate the functional and non-functional requirements of the system.

---

## 2. Overall Description
### 2.1 Product Perspective
PNCC關懷 functions as a mobile safety net. Unlike standard emergency trackers that rely solely on active senior buttons or reactive fall sensors, this system operates on a **proactive heartbeat paradigm**. The app monitors both active user touches and passive mobile device motion. If neither occurs within the scheduled interval, a countdown begins; if unacknowledged, alerts are pushed to the caregiver network.

### 2.2 User Personas
1. **Care Receiver (Senior / Older Adult)**:
   - Needs a clean, high-contrast, distraction-free interface.
   - Requires minimal physical typing.
   - Appreciates spiritually supportive elements (Scripture verses) and comfortable reading environments.
2. **Caregiver (Family / Nurse)**:
   - Needs instantaneous status awareness of all seniors under their care.
   - Demands rapid, direct communication links (Phone call, SMS, Line, WhatsApp, WeChat) mapped to the senior’s preference when an emergency is detected.
   - Requires remote capabilities (e.g., remote reset of senior timers).

---

## 3. Functional Requirements

### 3.1 Senior App (Care Receiver) Features

#### 3.1.1 Safety Check-In Engine
- **FR-1.1**: The app shall track user activity based on the configured **Check-in Frequency** (e.g., 24 hours) and **Alert Timeout** (e.g., 30 minutes).
- **FR-1.2**: The app shall display a friendly next check-in target time (e.g., `Next Check-in due by: 06:00 PM`) when the user is in a safe active state, without displaying ticking countdown seconds.
- **FR-1.3**: When the check-in frequency interval is exceeded, the app shall enter the **Grace Period (Warning State)** and display a prominent countdown: `Please check in within: MM:SS` (seconds ticking down).
- **FR-1.4**: Clicking the **"I'm Okay"** button shall reset the internal check-in timer, sync the latest timestamp to the cloud database, and automatically minimize/pop the app.
- **FR-1.5**: The app shall passively reset the check-in timer upon detecting device movement/motion sensors, logging the passive active timestamp.

#### 3.1.2 Fall Detection & Pre-Alert Countdown
- **FR-2.1**: The app shall monitor onboard accelerometer and gyroscope data to detect potential fall signatures.
- **FR-2.2**: Upon fall detection, the app shall launch a high-priority, full-screen **Pre-Alert Warning Panel** with an audible alarm and a 30-second ticking countdown.
- **FR-2.3**: The user shall be able to click **"CANCEL FALL ALERT"** during the countdown to prevent false alarms from triggering caregiver notifications. If uncancelled, a critical cloud alert shall fire automatically.

#### 3.1.3 Tranquil Scripture Reader
- **FR-3.1**: The home screen shall display a curated "Daily Verse" fetched from a lightweight local or remote database.
- **FR-3.2**: The app shall include a **"Read Chapter"** button next to the daily verse.
- **FR-3.3**: Clicking "Read Chapter" shall display an offline bottom sheet presenting the entire chapter of the cited verse.
- **FR-3.4**: The scripture reader shall support offline Chinese Union Version (CUV), English New International Version (NIV), and King James Version (KJV).
- **FR-3.5**: The scripture reader shall offer customizable text scaling controls (+/- font size) for older readers.

---

### 3.2 Caregiver App Features

#### 3.2.1 Real-Time Status Center & Pairings
- **FR-4.1**: The dashboard shall display dynamic counts of cared seniors categorised in real-time by safety states:
  - **🟢 Safe (OK / 安全無虞)**: Seniors whose check-in timers have not exceeded their configured thresholds.
  - **🔴 Expired (待關懷)**: Seniors who have missed check-in times beyond the grace period, or have triggered active fall alerts.
  - **🟡 Paused (暫停監測)**: Seniors on scheduled vacation mode or whose care settings are paused.
- **FR-4.2**: Caregivers shall be able to scan a generated QR Code from the senior's device to instantly establish secure care group pairings.

#### 3.2.2 Active Emergency Banner (Big Red Box)
- **FR-5.1**: When a senior's safety timer expires or a fall is confirmed, the Caregiver App shall immediately display a prominent red emergency banner at the top of the screen.
- **FR-5.2**: The banner shall display context-rich active duration statistics instead of a standard ticking countdown:
  - **Alert Active Duration (`警報持續`)**: The elapsed duration since the cloud alert triggered (e.g., `已持續 15 分鐘`).
  - **Senior's Last Active Time (`長輩最後活動`)**: The relative duration since the senior's last passive motion or manual touch (e.g., `2 小時前活動`).
- **FR-5.3**: The banner shall display quick communication actions matching the senior's **Preferred Contact Method** (Phone, SMS, WhatsApp, Line, WeChat).
- **FR-5.4**: The banner shall feature a **"Remote Reset"** button, allowing the caregiver to remotely sync and reset the senior's check-in timer once safety is verbally confirmed.

---

### 3.3 iOS SwiftUI Widget Integration
- **FR-6.1**: The iOS Widget Extension shall share data with the main application container via a secure App Group container: `group.com.example.dailyNotify`.
- **FR-6.2**: The widget shall support small, medium, and large layouts.
- **FR-6.3**: The widget shall display real-time care metrics (counts of Safe/Expired/Paused seniors) and list-based status indicators on the iOS Home Screen.

---

## 4. Non-Functional Requirements
- **NFR-1 (Reliability)**: Critical timers and background motion trackers shall run persistently as a foreground service with low battery overhead on Android and utilizing background fetch tasks on iOS.
- **NFR-2 (A11y/Accessibility)**: Senior interfaces must strictly leverage high contrast text colors, large tap target sizes (minimum 48dp), and readable font sizes.
- **NFR-3 (Privacy)**: No continuous GPS tracking shall be recorded. Safety updates shall only communicate timestamped status changes and paired UUID identifiers.

---
---

# Part 2: Chinese Version (中文版)

## 1. 引言
### 1.1 編寫目的
本文件定義了 **PNCC關懷 (dailyNotify)** 的軟體需求規格。該系統是一款專為長者設計的智慧安全關懷與自動警報應用。藉由手機動作感應器的被動偵測、手動「我很好」報平安機制，以及多元化的即時緊急通報管道，本系統為家屬與照顧者提供了一道堅實的安全防護網。

### 1.2 系統範圍
本系統包含以下三大核心板塊：
1. **長輩端 App (受照顧者介面)**：提供字體清晰、大按鈕「我很好」的主畫面，整合每日經文、離線整章閱讀器、背景動作感應器以及單一提醒倒計時。
2. **照顧者端 App (關懷主控台)**：採用毛玻璃質感設計的高階狀態中心，即時呈現所有受照護者的安全燈號，並提供紅色緊急通報看板、偏好聯絡捷徑與遠端重置功能。
3. **iOS SwiftUI 桌面小工具**：支援桌面動態小工具，顯示當前受照護名單的安全統計與燈號明細。
4. **雲端後端**：採用安全且實時同步的 Cloud Firestore 資料庫，處理用戶回報設定、感應器回傳時間戳記及警報觸發狀態。

---

## 2. 總體描述
### 2.1 產品定位
PNCC關懷是一款「主動式」安全守護軟體。不同於傳統僅依靠被動式按鈕或跌倒感應的警報器，本系統採取**「主動回報心跳 Paradigm」**。系統同時偵測使用者的主動觸控與手機的被動位移，若在設定時間內兩者皆未發生，系統將啟動溫馨提示，並在寬限期過後自動向照顧者發出緊急通知。

### 2.2 用戶特徵
1. **長輩 (受照顧者)**：
   - 需要介面極簡、對比強烈、無多餘廣告干擾。
   - 不便輸入複雜文字。
   - 喜愛心靈支持性內容（聖經經文）與舒適的閱讀介面。
2. **照顧者 (家屬 / 護理人員)**：
   - 需要一眼掌握所有照護長輩的健康燈號。
   - 當警報觸發時，需要立即依照長輩最喜愛的方式（電話、簡訊、WhatsApp、Line、WeChat）進行一鍵聯絡。
   - 需具備遠端管理能力（例如遠端重置長輩的報平安計時器）。

---

## 3. 具體需求

### 3.1 長輩端 App 功能需求

#### 3.1.1 智慧回報與計時引擎
- **FR-1.1**：系統應依據後端同步的**「回報頻率」**（如 24 小時）與**「超時寬限期」**（如 30 分鐘）進行安全追蹤。
- **FR-1.2**：當長輩處於安全守護狀態時，介面**不得顯示滴答流逝的秒數**，僅顯示静态提示語：`下次報到時間：下午 06:00`，避免引發長輩焦慮。
- **FR-1.3**：當回報頻率時間已過，系統進入「溫馨提醒寬限期」，介面應切換為醒目的警示黃/橙色，並啟動**單一倒數計時器**：`請在 24:59 內點擊報平安`（秒數遞減）。
- **FR-1.4**：點擊**「我很好 (I'm Okay)」**按鈕後，系統應重置報平安計時器，將最新時間戳同步至 Firestore，並在 500 毫秒延遲後自動將 App 縮小/縮回背景。
- **FR-1.5**：系統應能在背景被動偵測手機位移感應器。若感應到顯著移動，應自動更新被動活躍時間戳，並更新報平安週期。

#### 3.1.2 跌倒偵測與預警倒數
- **FR-2.1**：系統應讀取手機內建加速度計與陀螺儀的感應訊號，利用演算法判定是否發生跌倒事件。
- **FR-2.2**：一旦判定跌倒，應立即全螢幕跳出高優先級的**「跌倒預警面板」**，發出警示音並啟動 30 秒倒數。
- **FR-2.3**：長輩可在倒數結束前點擊**「取消跌倒警報」**以防誤報；若 30 秒內未取消，系統將自動向雲端發送緊急警報通知照顧者。

#### 3.1.3 寧靜離線經文閱讀器
- **FR-3.1**：主畫面每日應顯示一句心靈關懷經文。
- **FR-3.2**：經文下方應提供一個醒目的 **「閱讀整章」** 按鈕。
- **FR-3.3**：點擊按鈕後，應以底部彈出式面板 (Bottom Sheet) 載入該經文所在的完整章節。
- **FR-3.4**：閱讀器必須支援完全離線閱讀，並提供繁體中文和合本 (CUV)、英文新國際版 (NIV)、英王詹姆士欽定版 (KJV)。
- **FR-3.5**：閱讀器應提供字體放大/縮小 (+/-) 的輔助控制按鈕，以貼近年長者的視力需求。

---

### 3.2 照顧者端 App 功能需求

#### 3.2.1 實時狀態中心與關懷配對
- **FR-4.1**：照顧者主控台應實時呈現受照護長輩的狀態分類與統計數據：
  - **🟢 安全無虞 (Safe / OK)**：尚在回報時限內的長輩。
  - **🔴 待關懷 (Expired)**：已超時未回報或觸發跌倒警報的長輩。
  - **🟡 暫停監測 (Paused)**：處於假期暫停狀態或設定不啟用的長輩。
- **FR-4.2**：照顧者可利用內建掃描功能，掃描長輩端產生的 QR Code，迅速建立安全的配對關聯。

#### 3.2.2 紅色緊急通報看板 (Big Red Box)
- **FR-5.1**：當受照顧的長輩超時未回報或確認跌倒時，照顧者畫面最上方應立即顯示紅色高優性的緊急通報看板。
- **FR-5.2**：看板應呈現兩項關聯性的**「黃金時間指標」**，而非重複倒數：
  - **警報持續時間 (`警報持續`)**：顯示警報自觸發以來已持續多久（例如：`已持續 15 分鐘`）。
  - **長輩最後活動 (`長輩最後活動`)**：顯示長輩最後一次產生手動點擊或手機位移的相對時間（例如：`2 小時前活動`）。
- **FR-5.3**：看板應智能解析並直接顯示長輩的**「偏好聯絡管道捷徑」**（電話、簡訊、WhatsApp、Line、WeChat），實現一鍵點選通話。
- **FR-5.4**：看板應設有**「遠端重置計時器」**按鈕，照顧者進行語音確認安全後，可直接為長輩遠端清除警報並重置計時。

---

### 3.3 iOS SwiftUI 桌面小工具整合需求
- **FR-6.1**：iOS 小工具與 App 主程式應藉由相同的 App Group ID：`group.com.example.dailyNotify` 實現安全的本地端沙盒數據共享。
- **FR-6.2**：小工具應支援 Small、Medium 與 Large 三種尺寸。
- **FR-6.3**：小工具應能在 iOS 系統桌面上實時渲染當前 Safe/Expired/Paused 的狀態數量統計，或顯示具體成員的燈號清單。

---

## 4. 非功能需求
- **NFR-1 (可靠性與後台運行)**：在 Android 平台應透過 Foreground Service（前台服務）確保感應器持續在背景運行且低耗電；在 iOS 平台應利用 Background Tasks 機制維持必要的心跳同步。
- **NFR-2 (無障礙設計 accessibility)**：介面色彩必須符合高對比度規範，所有常用交互按鈕的點擊熱區不得小於 48dp，保障手部抖動或視力退化的年長者能精準操作。
- **NFR-3 (安全與隱私防護)**：本軟體不進行連續的 GPS 軌跡追蹤。所有數據交換僅包含時間戳記、活躍狀態和匿名配對 UUID，嚴格保護長輩隱私。

---
