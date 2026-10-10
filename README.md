# TextSnap — On-Device Offline Document & Text Search for Android

<p align="center">
  <img src="App_Icon_512x512.png" alt="TextSnap Icon" width="128" height="128" />
</p>

<p align="center">
  <strong>100% Offline • Zero Data Collection • On-Device ML Kit OCR • Target SDK 36</strong>
</p>

<p align="center">
  <a href="https://jaimin229.github.io/TextSnap/"><img src="https://img.shields.io/badge/Privacy_Policy-Live-emerald?style=flat-square" alt="Privacy Policy" /></a>
  <a href="https://jaimin229.github.io/TextSnap/terms.html"><img src="https://img.shields.io/badge/Terms_of_Service-Live-blue?style=flat-square" alt="Terms of Service" /></a>
  <img src="https://img.shields.io/badge/Android-16_Ready_(API_36)-purple?style=flat-square" alt="Android 16 Ready" />
  <img src="https://img.shields.io/badge/License-Proprietary-darkred?style=flat-square" alt="Proprietary License" />
</p>

---

## 📱 About TextSnap

**TextSnap** (`com.jverse.textsnap`) is a premium Android productivity utility engineered by **Jaimin Prajapati** (`jaimin229` / JVerse) that brings lightning-fast, privacy-first full-text search to your local photo library and scanned documents.

Search through receipts, invoices, Wi-Fi credentials, business cards, serial numbers, identity documents, and lecture notes **without a single byte of data ever leaving your physical device**.

### 🌟 Key Features
- **100% On-Device OCR**: Optical Character Recognition is powered locally by bundled Google ML Kit models (Latin, Devanagari, and Chinese scripts). Zero remote servers, zero cloud APIs.
- **Hardware-Backed AES-256-GCM Vault**: Encrypt sensitive files locally using keys generated inside your device's hardware Secure Element / Trusted Execution Environment (TEE).
- **Biometric Security**: Native Android `BiometricPrompt` authentication with `FLAG_SECURE` screen recording defense.
- **Offline Full-Text Search (FTS4)**: Sub-second search indexing across thousands of local images with fuzzy match, regex detection, and entity extraction.
- **Zero Network Permissions**: The app binary explicitly removes `android.permission.INTERNET` and `ACCESS_NETWORK_STATE` (`tools:node="remove"`). Network socket creation is blocked at the Linux kernel level.

---

## 📜 Legal & Compliance Documentation

This repository serves as the official public legal compliance and documentation host for TextSnap on the Google Play Store:

| Document | Format | Description |
| :--- | :--- | :--- |
| **Privacy Policy** | [🌐 Live Web](https://jaimin229.github.io/TextSnap/) • [📄 Markdown](PRIVACY_POLICY.md) | Compliant with India DPDP Act 2023, EU GDPR, UK GDPR, California CCPA/CPRA, and Google Play Data Safety policies. |
| **Terms of Service** | [🌐 Live Web](https://jaimin229.github.io/TextSnap/terms.html) • [📄 Markdown](TERMS_OF_SERVICE.md) | Terms governing app purchase, license grants, OCR disclaimers, BIPA biometric immunity, and binding individual dispute resolution. |

---

## 🛡️ Privacy & Data Safety Summary

- **Data Collected:** None. (0 bytes off-device transmission)
- **Data Shared:** None. (0 third-party SDKs, 0 tracking, 0 advertising)
- **Permissions:** Principle of least privilege. Uses Android system Photo Picker (`PickVisualMedia`) for zero-permission document importing.
- **Cloud Backups:** Disabled via `android:allowBackup="false"`.

---

## 📬 Contact & Grievance Redressal

- **Developer / Publisher:** Jaimin Prajapati (operating as "jaimin229" / JVerse)
- **Support & Developer Email:** [jaiminadac@gmail.com](mailto:jaiminadac@gmail.com)
- **DPDP Grievance Officer:** Jaimin Prajapati ([jaiminadac@gmail.com](mailto:jaiminadac@gmail.com))
- **Jurisdiction:** Gujarat, India

---

<p align="center">
  <sub>&copy; 2026 TextSnap • Jaimin Prajapati. All rights reserved. TextSnap is a proprietary mobile application distributed via the Google Play Store.</sub>
</p>
