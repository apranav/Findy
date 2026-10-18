# Privacy Policy for Findy

**Effective Date:** October 18, 2026  
**Last Updated:** October 18, 2026  
**Application:** Findy — Universal Link Organizer for Android  
**Developer:** Krishna Pranav ([@apranav](https://github.com/apranav))  
**Contact Email:** [a.krishna.pranav@gmail.com](mailto:a.krishna.pranav@gmail.com)  
**Repository & Privacy Policy:** [https://github.com/apranav/Findy](https://github.com/apranav/Findy)

---

## 🛡️ Summary (Privacy at a Glance)

Findy was built from the ground up on a **strict local-first, privacy-by-design architecture**. We believe your bookmarks, reading habits, and organized links are deeply personal.

- **No User Account Required:** You never need to sign up, log in, or provide an email or phone number to use Findy.
- **Zero Cloud Storage:** All links, titles, notes, tags, and collections are stored exclusively in an offline SQLite database on your device.
- **Zero Tracking & Analytics:** Findy contains **no** analytics SDKs (no Firebase Analytics, Google Analytics, Mixpanel, etc.), no telemetry, and no behavioral profiling.
- **No Advertisements:** Findy is 100% ad-free and contains no advertising networks or third-party trackers.
- **Full User Control:** You can backup, export to JSON, or delete all of your data at any time.

---

## 1. Information We Collect and Store

### A. Data Stored Locally on Your Device
When you use Findy, the following data is saved locally on your device using a private SQLite database via Drift:
- **Saved URLs & Web Metadata:** Web addresses (URLs) that you explicitly share or save to the app, along with metadata extracted from those pages (page title, description snippet, domain name, and thumbnail image preview).
- **User Annotations & Organization:** Custom titles, personal notes, favorite flags, archive status, tags, and custom folder collections you create.
- **Custom Rules & Preferences:** User category overrides, domain rules, theme mode (Light/Dark/System), default sort preferences, and duplicate link handling rules.

### B. Information We Do NOT Collect
- **No Personal Identifiable Information (PII):** We do not collect names, email addresses, phone numbers, contacts, physical addresses, or user IDs.
- **No Device Identifiers:** We do not read or record your IMEI, MAC address, Advertising ID (AAID), or hardware serial numbers.
- **No Location Data:** Findy does not request or access GPS or coarse network location.
- **No Background Clipboard Harvesting:** If clipboard detection is enabled in settings, Findy only inspects the clipboard when you open the application to check if a valid URL is present for quick adding. Clipboard contents are never logged, stored without your consent, or transmitted over the network.
- **No Keystroke Logging:** Your search queries are executed purely against your local on-device SQLite database.

---

## 2. Device Permissions and Usage

Findy requests the minimum permissions necessary to function:

| Permission | Android Identifier | Purpose |
| :--- | :--- | :--- |
| **Internet Access** | `android.permission.INTERNET` | Used solely for fetching public open-graph metadata (title, description, thumbnail) for links you save, and for opening external URLs in your browser or native apps. |
| **Biometric Authentication** | `android.permission.USE_BIOMETRIC` | Used solely for the optional biometric vault screen lock feature. |
| **System Share Sheet** | `android.intent.action.SEND`<br>`android.intent.action.SEND_MULTIPLE` | Allows Findy to receive text and links that you explicitly share to Findy from other applications. |

### How Internet Access is Handled Safely
- **Direct Anonymous Fetching:** When you save a link, Findy issues a standard HTTP `GET` request directly from your device to the target website to retrieve Open Graph preview metadata (title, description, and thumbnail).
- **No Middleman Servers:** Requests do not go through any Findy-owned or intermediate proxy server.
- **Anti-SSRF Protection:** Findy includes built-in Server-Side Request Forgery (SSRF) protections that block requests to private, loopback, or local network IP addresses (e.g., `127.0.0.1`, `192.168.x.x`, `10.x.x.x`).
- **No Personal Data Sent:** Network requests for metadata do not include cookies, tokens, or personal identifiers.

### How Biometric Authentication is Handled
- Findy utilizes Android's official `BiometricPrompt` (`local_auth`) framework.
- Authentication occurs entirely within Android's hardware-backed Trusted Execution Environment (TEE) or Secure Enclave.
- Findy **never** has access to your fingerprint, facial scan, PIN, or biometric biometric templates.

---

## 3. Third-Party Services & Links

- **No Third-Party SDKs:** Findy does not include third-party advertising SDKs, analytics packages, social network trackers, or error-reporting services that monitor user actions.
- **External Links:** When you tap a link to view it, Findy utilizes Android's `Intent.ACTION_VIEW` (`LaunchMode.externalApplication`) to open the link in the appropriate native app (such as YouTube, Instagram, Maps, or Amazon) or your default web browser. Once you leave Findy, your interactions on external services are governed by the respective third party's privacy policy.

---

## 4. Data Retention, Backup, and Deletion

You have complete ownership and sovereignty over your data:

- **Data Retention:** Data remains on your device until you manually delete it or uninstall the app.
- **Data Export & Portability:** You can export your entire link database or selective collections into a clean, unencrypted JSON file at any time from **Settings > Data & Backups > Export Data**.
- **Data Import & Restore:** You can restore backups from your JSON files at any time.
- **Data Deletion:**
  - You can delete individual links, notes, or collections directly from the app interface.
  - You can wipe all app data at once from Android's system settings (**Settings > Apps > Findy > Storage > Clear Data**).
  - Uninstalling Findy completely and permanently purges all SQLite databases, cached preview images, and preferences from your device.

---

## 5. Security

We take the security of your stored data seriously:
- **Application Sandbox:** All application files and SQLite databases are stored within Android's protected application sandbox, accessible only by Findy.
- **Biometric Vault Lock:** You can lock access to Findy using fingerprint or face unlock to prevent unauthorized local access if someone else uses your device.
- **Anti-SSRF Guardrails:** Metadata fetching verifies URLs against private network address blocks to protect against local intranet discovery.

---

## 6. Children's Privacy

Findy is a general utility tool and does not knowingly collect, store, or solicit personal information from children under the age of 13 (or under the age of 16 in the European Union). Because Findy does not collect personal data from any user, it fully complies with the requirements of the Children’s Online Privacy Protection Act (COPPA) and applicable global child data protection regulations.

---

## 7. Compliance with Global Privacy Laws

### European Economic Area (EEA) & UK — GDPR
Under the General Data Protection Regulation (GDPR), users have rights including access, rectification, portability, and erasure. Because Findy operates purely as a local-first application without server-side processing or personal data collection:
- **Data Controller:** You are the sole controller of your local data.
- **Right to Access & Portability:** Fulfilled via the built-in JSON export feature.
- **Right to Erasure:** Fulfilled via in-app deletion or clearing app storage.

### California Consumer Privacy Act (CCPA / CPRA)
- We do **not** sell or share your personal information with third parties.
- We do **not** collect sensitive personal information.
- We do **not** engage in cross-context behavioral advertising.

---

## 8. Changes to This Privacy Policy

We may update this Privacy Policy from time to time to reflect new features, legal requirements, or architectural updates. Any updates will be published in this repository with a revised "Last Updated" date.

---

## 9. Contact Us

If you have any questions, suggestions, or concerns regarding this Privacy Policy or Findy's privacy practices, please contact us:

- **Developer:** Krishna Pranav
- **Email:** [a.krishna.pranav@gmail.com](mailto:a.krishna.pranav@gmail.com)
- **GitHub Issues:** [https://github.com/apranav/Findy/issues](https://github.com/apranav/Findy/issues)
- **Project Repository:** [https://github.com/apranav/Findy](https://github.com/apranav/Findy)
