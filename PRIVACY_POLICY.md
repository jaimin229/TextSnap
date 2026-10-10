# Privacy Policy for TextSnap

**Effective Date:** October 4, 2026  
**Last Updated:** October 10, 2026  
**Application Name:** TextSnap (`com.jverse.textsnap`)  
**Developer / Legal Entity:** Jaimin Prajapati (operating as "jaimin229" / JVerse)  
**Official Repository:** [https://github.com/jaimin229/TextSnap](https://github.com/jaimin229/TextSnap)  
**Hosted Privacy Policy URLs:** [https://jaimin229.github.io/TextSnap/](https://jaimin229.github.io/TextSnap/) | [https://textsnap-puce.vercel.app/](https://textsnap-puce.vercel.app/)  

---

## Executive Summary: 100% Offline & Privacy by Design

TextSnap is engineered from the ground up as a **100% offline, privacy-first on-device text recognition and document search tool** for Android. TextSnap allows you to search text contained within your photographs (such as receipts, identity documents, Wi-Fi passwords, serial numbers, and screenshots) **without any data ever leaving your physical device**.

- **Zero Network Permissions (`tools:node="remove"`):** TextSnap declares **no** `android.permission.INTERNET` and **no** `android.permission.ACCESS_NETWORK_STATE`. Both permissions are forcefully removed from the compiled binary. The app is physically and technologically incapable of connecting to any server or transmitting data over the internet.
- **Zero Data Collection, Tracking, or Telemetry:** We do not collect, log, track, sell, or transmit your personal data, photographs, OCR extractions, search queries, or device identifiers.
- **On-Device Machine Learning:** Optical Character Recognition (OCR) is performed exclusively on your device using bundled on-device Google ML Kit models (Latin, Devanagari, and Chinese scripts). No images or text are sent to cloud inference APIs.
- **Hardware-Backed Encrypted Vault:** Sensitive documents moved to the Vault are encrypted locally using **AES-256-GCM** backed by the Android Keystore system and protected against screen capture via `FLAG_SECURE`.
- **Zero Cloud Backups:** Android cloud backups are explicitly blocked via `allowBackup="false"`, `backup_rules.xml`, and `data_extraction_rules.xml`.

---

## 1. Permissions Requested & Legal Purpose

TextSnap follows the principle of strict data minimization (GDPR Art. 5(1)(c), DPDP Act Section 5). It requests only the bare minimum Android permissions:

| Permission / Mechanism | Android Version | Purpose & Privacy Scope |
|---|---|---|
| **`READ_MEDIA_IMAGES`** | Android 13+ (API 33+) | **Core Feature / Opt-In Gallery Indexing (Google Play Photo & Video Policy Compliant).** Requested to enable automated on-device text indexing of gallery photos and documents (receipts, IDs, invoices, notes, screenshots) so you can instantly search across your library without manually selecting each image. Image data is processed 100% locally on-device by bundled ML Kit models; zero images, thumbnails, or metadata ever leave your physical device. |
| **`READ_MEDIA_VISUAL_USER_SELECTED`** | Android 14+ (API 34+) | **Privacy-Preserving Partial Access.** On Android 14+, if you prefer not to grant full gallery access, you may select a specific subset of photos or albums. TextSnap will restrict background text indexing and search strictly to those user-selected photos. |
| **System Photo Picker (`PickVisualMedia`)** | Android 13+ (API 33+) | **Zero Permission Alternative.** For users who do not grant broad gallery access, TextSnap fully supports the Android Photo Picker. You can manually pick individual photos for OCR import with zero Android permissions requested or granted. |
| **`READ_EXTERNAL_STORAGE`** | Android 8.0–12L (API 26–32) | **Legacy Gallery Fallback (`maxSdkVersion=32`).** Used strictly on legacy Android devices predating the system Photo Picker and granular media permissions to index local gallery photos. Capped at API 32. |
| **`WRITE_EXTERNAL_STORAGE`** | Android 8.0–9.0 (API 26–28) | **Legacy Export Only (`maxSdkVersion=28`).** Used solely to save user-exported photo copies to the public gallery on legacy devices. On Android 10+ (API 29+), Scoped Storage via MediaStore is used with zero storage permissions. |
| **`RECORD_AUDIO`** | All Supported Versions | **Optional Feature / On-Device Voice Search (Google Play User Data Policy Compliant).** Requested solely when you tap the microphone button in the search bar. Audio is streamed strictly in-memory to Android's on-device `SpeechRecognizer` (`EXTRA_PREFER_OFFLINE`) for real-time transcription. **Zero audio recordings are stored on disk, logged, or transmitted over any network** (network access is physically removed via `tools:node="remove"`). Microphone access is completely optional. |
| **`android.hardware.microphone`** | All Supported Versions | **Optional Hardware Feature (`required="false"`).** Declared so devices without hardware microphones (e.g., specialized tablets) remain 100% compatible on Google Play. |
| **`USE_BIOMETRIC`** | All Supported Versions | Used strictly to invoke Android's system biometric prompt (`BiometricPrompt`) to unlock your local encrypted Vault. Biometric templates remain securely inside Android's Secure Element/TEE; TextSnap never receives, accesses, or stores biometric data. |
| **Camera (System Preview)** | All Supported Versions | TextSnap utilizes Android's system `TakePicturePreview` activity contract. The app does **not** request persistent `android.permission.CAMERA`. |
| **Internet & Network State** | N/A | **Explicitly Removed.** Stripped from the binary with `tools:node="remove"`. Network transmission is technologically impossible. |
| **Cloud Backups** | All Supported Versions | **Explicitly Disabled.** `android:allowBackup="false"` and restrictive data extraction rules ensure local data is excluded from automated Google Drive cloud backups. |

---

## 2. Compliance with India DPDP Act 2023 & DPDP Rules 2025

This section constitutes the digital notice required under **Section 5(1) and Section 5(3)** of the Digital Personal Data Protection Act, 2023 (DPDP Act) and the DPDP Rules 2025 for users located in India.

### 2.1 Processing of Digital Personal Data
TextSnap operates locally on your hardware. When you scan or index documents containing personal data (such as Aadhaar numbers, PAN cards, driving licenses, UPI IDs, bank details, or contact info), this data is processed exclusively on-device within the app's sandboxed local Room/SQLite database (`/data/data/com.jverse.textsnap/`).

### 2.2 Data Principal Rights under DPDP Act 2023
As a Data Principal under Indian law, you are entitled to:
1. **Right to Access Information (Section 11):** You can directly view all indexed data, OCR extractions, and document metadata at any time directly within the application's Home, Search, and Vault screens.
2. **Right to Correction and Erasure (Section 12):**
   - *Correction:* You may rescan any document to refresh or update recognized text.
   - *Erasure:* You can erase your personal data instantly and permanently by tapping "Remove from index" on any photo, tapping "Clear index" inside Indexing Manager, deleting items from the Vault, clearing application storage in Android System Settings, or uninstalling TextSnap.
3. **Right of Grievance Redressal (Section 13):** You have the right to register grievances with our designated Grievance Officer (details below).
4. **Right to Nominate (Section 14):** You have the right to nominate any individual who, in the event of death or incapacity, shall exercise your rights as a Data Principal.
5. **Right to Withdraw Consent (Section 6(4)):** You may withdraw permission access at any time through Android System Settings (`Settings > Apps > TextSnap > Permissions`) or by toggling off background indexing in TextSnap Settings.

### 2.3 Mandatory Grievance Officer Contact Details (Section 8(9) & DPDP Rules 2025)
In compliance with Section 8(9) and Section 8(10) of the DPDP Act 2023, and Rule requirements of the DPDP Rules 2025, the contact details of the designated Grievance Officer are:

- **Grievance Officer Name:** Jaimin Prajapati
- **Designation:** Lead Developer & Data Protection Grievance Officer
- **Physical / Postal Address:** Gujarat, India
- **Dedicated Grievance & Support Email:** [jaiminadac@gmail.com](mailto:jaiminadac@gmail.com) (Subject: `[DPDP Grievance - TextSnap]`)
- **Response Timeline:** Grievances will be acknowledged within 48 hours and resolved within 30 calendar days.
- **Escalation to Data Protection Board of India (DPBI):** If you are not satisfied with the response of the Grievance Officer, or if you do not receive a response within 30 days, you have the statutory right to file a complaint with the **Data Protection Board of India (DPBI)** in accordance with the DPDP Act 2023 and applicable Rules.

### 2.4 Server Logs Clarification (DPDP Rules 2025)
Because TextSnap operates 100% on-device without remote servers or cloud databases, **no server-side traffic data, network logs, or digital processing logs are collected, held, or retained**.

---

## 3. Compliance with EU GDPR & UK GDPR

For individuals residing in the European Economic Area (EEA), United Kingdom, and Switzerland, TextSnap complies fully with Regulation (EU) 2016/679 (EU GDPR) and the UK Data Protection Act 2018 / UK GDPR.

### 3.1 Data Controller Identity
- **Data Controller:** Jaimin Prajapati (jaimin229 / JVerse)
- **Contact Email:** [jaiminadac@gmail.com](mailto:jaiminadac@gmail.com)

### 3.2 Lawful Basis for Processing (Art. 6 GDPR)
- **Performance of Contract (Art. 6(1)(b)):** Processing of selected photos and OCR extraction is performed solely to deliver the core search and indexing functionality requested by you when using the app.
- **Consent (Art. 6(1)(a)):** Optional features, including the `READ_MEDIA_VISUAL_USER_SELECTED` limited photo watching mode and periodic background indexing, are activated strictly upon your affirmative opt-in consent, which can be revoked at any time.

### 3.3 Zero International Data Transfers (Chapter V, Articles 44–50 GDPR)
TextSnap maintains a strict **zero international data transfer** policy. Because TextSnap has zero network access and transmits zero packets over the internet, no personal data is transferred across international borders or into third countries. All processing is confined to your local hardware.

### 3.4 Data Subject Rights (Articles 12–23 GDPR)
Under GDPR and UK GDPR, you have the following rights:
- **Right of Access (Art. 15):** Direct inspection of all data on-device.
- **Right to Rectification (Art. 16):** Rescanning and updating document text.
- **Right to Erasure / 'Right to be Forgotten' (Art. 17):** Immediate deletion via in-app options or OS storage clearance.
- **Right to Restriction of Processing (Art. 18):** Disabling background indexing in Settings.
- **Right to Data Portability (Art. 20):** Exporting your full database as an AES-256-GCM encrypted `.tsnap` backup or copying OCR text to clipboard.
- **Right to Object (Art. 21):** Refusing optional permissions or uninstalling the application.
- **Automated Decision-Making and Profiling (Art. 22):** TextSnap engages in zero automated decision-making and zero profiling.
- **Right to Lodge a Complaint with a Supervisory Authority (Art. 77):** You have the right to lodge a complaint with an EU Member State Data Protection Authority (DPA) in your country of residence, or with the UK Information Commissioner's Office (ICO) at [https://ico.org.uk/](https://ico.org.uk/).
- **Article 27 EU/UK Representative Exemption:** Pursuant to Article 27(2)(a) GDPR, an EU/UK representative is not designated because application operation is 100% on-device and creates zero risk to the rights and freedoms of natural persons.

---

## 4. Compliance with California CCPA / CPRA & US State Privacy Laws

This section applies to residents of California (California Consumer Privacy Act / California Privacy Rights Act - CCPA/CPRA) and states with comprehensive privacy statutes (including Virginia, Colorado, Connecticut, Utah, Texas, Oregon, Montana, and others).

### 4.1 Notice at Collection (Cal. Civ. Code § 1798.100)
The following table describes the categories of personal information under Cal. Civ. Code § 1798.140:

| Category | Collected by TextSnap? | Sold or Shared? | Retention Period |
|---|---|---|---|
| **A. Identifiers** (Name, IP address, device ID, email) | **No** | No | 0 days (Not collected) |
| **B. Personal Info under Cal. Civ. Code § 1798.80(e)** | Processed locally on-device only if present in photos you select | No | Retained locally until deleted by user |
| **C. Protected Classifications** | **No** | No | 0 days |
| **D. Commercial Information** (e.g. scanned receipts) | Processed locally on-device only | No | Retained locally until deleted by user |
| **E. Biometric Information** | **No** (Processed solely by Android OS Secure Element) | No | 0 days (App never receives biometric templates) |
| **F. Internet or Network Activity** | **No** (Zero network permissions) | No | 0 days |
| **G. Geolocation Data** | **No** | No | 0 days |
| **H. Audio / Sensory Data** | Processed locally in RAM only during active voice search; never recorded to disk | No | 0 days (Ephemeral; discarded immediately after recognition) |
| **I. Professional / Employment Info** | Processed locally only if present in photos you select | No | Retained locally until deleted by user |
| **J. Inferences drawn from Personal Info** | **No** | No | 0 days |
| **Sensitive Personal Information (SPI)** | Processed locally in encrypted Vault only upon user action | No | Retained locally until deleted by user |

### 4.2 "Do Not Sell or Share My Personal Information" Statement (Statutory Exemption)
- **We do not sell personal information.** TextSnap has never sold, rented, leased, disclosed, disseminated, transferred, or communicated personal information to third parties for monetary or valuable consideration.
- **We do not share personal information for cross-context behavioral advertising.**
- **Statutory Exemption:** Because TextSnap does not sell or share personal information, no opt-out link ("Do Not Sell or Share My Personal Information") is required on our website or inside the app.

### 4.3 Global Privacy Control (GPC) & Universal Opt-Out Preference Signals
TextSnap recognizes and honors Global Privacy Control (GPC) signals and universal opt-out mechanisms automatically by default. Because our application architecture collects zero personal data, transmits zero data across the internet, and engages in zero selling, sharing, or targeted behavioral advertising, all users—regardless of browser or device signal status—experience complete privacy isolation.

### 4.4 Texas TDPSA Compliance & SBA Small Business Exemption (Tex. Bus. & Com. Code § 531.001 et seq.)
Under the Texas Data Privacy and Security Act (TDPSA), Developer qualifies as a small business under the U.S. Small Business Administration (SBA) criteria (13 C.F.R. Part 121 / NAICS 513210). In strict compliance with Tex. Bus. & Com. Code § 531.055, Developer confirms that TextSnap does not sell, license, or commercialize sensitive personal data under any circumstances.

### 4.5 Limit the Use of Sensitive Personal Information (CPRA § 1798.121)
TextSnap uses Sensitive Personal Information (e.g., identity documents placed in the Vault) exclusively for the purpose of providing the local on-device service requested by you, within the statutory exceptions of CPRA Regulations § 7027(m).

### 4.6 Non-Discrimination (Cal. Civ. Code § 1798.125)
We will not discriminate against any user in pricing, features, or service quality for exercising any rights under CCPA/CPRA.

### 4.7 California "Shine the Light" Law (Cal. Civ. Code § 1798.83)
TextSnap does not disclose personal information to third parties for direct marketing purposes.

---

## 5. Children's Privacy (COPPA, DPDP Section 9 & Global Standards)

TextSnap is a general audience, offline utility tool. 
- We do not knowingly collect, store, or solicit personal data from children under 13 years of age (US COPPA), under 16 (GDPR-standard EEA variations), or under 18 (India DPDP Act).
- Because TextSnap does not collect any data over the internet, no personal information of any minor is ever collected, tracked, or transmitted to any server.

---

## 6. How to Exercise Your Privacy & Deletion Rights

Because TextSnap is 100% offline, you have complete, immediate autonomy over your data without needing to wait for developer intervention:

1. **Delete Individual Scanned Items:** Open any document detail screen in TextSnap, tap the overflow menu (⋮), and select **Remove from index**. The index entry and OCR text are immediately purged.
2. **Purge Entire Search Index:** Go to **Overflow (⋮) > Indexing Manager > Clear index**. This deletes all local index entries and FTS tables.
3. **Delete Vault Items:** Unlock the Vault, select any document, and tap the delete icon to permanently destroy the local AES-256 encrypted file.
4. **Export Your Data (Portability):** Go to **Settings > Encrypted Backup > Export**. You can export an AES-256-GCM encrypted `.tsnap` backup file to any directory on your device.
5. **Complete Data Erasure:** Go to Android **Settings > Apps > TextSnap > Storage & cache > Clear storage**, or simply uninstall TextSnap. All local SQLite databases, Keystore encryption keys, and private preferences are instantaneously and irreversibly erased.

---

## 7. Security Safeguards & Technical Transparency

- **AES-256-GCM Hardware Keystore Encryption:** Vault items are encrypted using Authenticated Encryption with Associated Data (AEAD) with 256-bit keys generated in the device's hardware-backed keystore.
- **FLAG_SECURE:** Screenshot and video recording protection active across Vault screens.
- **Zero Third-Party Advertising or Tracking SDKs:** No Firebase Analytics, no AdMob, no Facebook SDK, no crashlytics telemetry.

### 7.1 Google Play In-App Updates & Operating System Network Accounting Transparency
TextSnap implements the official Google Play In-App Update API (`com.google.android.play:app-update`) to notify users when a critical update or security enhancement is published on Google Play.
- **Local IPC Communication Only:** TextSnap queries update availability strictly via Android local Inter-Process Communication (IPC / AIDL Binder) directly to the on-device Google Play Store client application (`com.android.vending`). TextSnap does **not** possess, request, or require the `android.permission.INTERNET` permission.
- **Explanation of Incidental Network Footprint in System Settings:** If an advanced user inspects their device's Android System Settings (`Settings > Apps > TextSnap > Mobile data & Wi-Fi`) and observes a negligible data footprint (typically between 5 KB to 25 KB), this represents operating-system-level network accounting (Linux kernel eBPF / `xt_qtaguid`) attributed to the calling UID during the local Google Play Store service's version-check handshake or Google Play Protect malware scanning on install/launch.
- **Absolute Privacy Guarantee:** At no point does TextSnap open a network socket, connect to remote servers, or transmit any user photographs, extracted OCR text, search history, biometric data, or device identifiers. **Zero bytes of user data ever leave the device.**

### 7.2 Google Play Store Data Safety Form Declarations (2026 Reference)
In alignment with the Google Play Developer Program Policy:

| Data Safety Form Question | Response | Technical Truth & Justification |
|---|---|---|
| **Does your app collect or share user data?** | **No** | Per Google Play definitions, "collected" requires data transmitted off the device. TextSnap transmits zero data off-device. |
| **Is data shared with any third party?** | **No** | No data is transferred to any third party or external server. |
| **Are photos or videos collected?** | **No** | Media is indexed and stored 100% locally on-device. |
| **Is audio recorded or collected?** | **No** | Voice search is ephemeral, processed in-memory via on-device `SpeechRecognizer` (`EXTRA_PREFER_OFFLINE`), and never stored or transmitted. |
| **Is data encrypted in transit?** | **N/A** | TextSnap possesses zero network capabilities; no data travels over the network. |
| **Can users request data deletion?** | **Yes** | 1-tap local data purge available via **Settings > Indexing Manager > Clear index** and **Settings > Clear all data**. |

---

## 8. Contact & Legal Inquiries

If you have questions, feedback, or require assistance regarding this Privacy Policy or your legal rights, please contact:

- **Developer / Publisher:** Jaimin Prajapati (operating as "jaimin229" / JVerse)
- **Support & Developer Contact:** [jaiminadac@gmail.com](mailto:jaiminadac@gmail.com)
- **Grievance Officer (India DPDP):** Jaimin Prajapati ([jaiminadac@gmail.com](mailto:jaiminadac@gmail.com))
- **Postal Address:** Gujarat, India
- **GitHub Repository:** [https://github.com/jaimin229/TextSnap](https://github.com/jaimin229/TextSnap)
- **Website / Hosted Privacy Policy:** [https://jaimin229.github.io/TextSnap/](https://jaimin229.github.io/TextSnap/)
