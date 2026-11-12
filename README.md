# NAS Backup OAuth Verification Site

This repository hosts a simple GitHub Pages site used to satisfy the domain verification and branding requirements for a private Google Cloud OAuth application.

## 📌 Purpose

This project exists to provide a valid **Homepage URL** and **Privacy Policy URL** for a personal Google Cloud Project. 

By fulfilling these requirements, the private Google OAuth app can be pushed from "Testing" to "In Production" status. This prevents the OAuth authentication tokens from expiring every 7 days, allowing uninterrupted automated NAS backups.

## ⚙️ Background / Use Case

* **Hardware:** Synology NAS
* **Software:** Hyper Backup & `rclone` (via WebDAV/Docker)
* **Destination:** Google Drive
* **The Problem:** The native Synology Hyper Backup app shares a global API key, resulting in frequent `HTTP 403: Quota exceeded for quota metric 'Queries'` errors during uploads and backup rotation/deletion.
* **The Solution:** Routing the backup through a local `rclone` instance using a dedicated Google Cloud API key provides a private quota of 20,000 queries per minute, permanently solving the rate limit errors.

## 📂 Repository Contents

* `index.html` - A placeholder Homepage for the OAuth Consent Screen branding configuration.
* `privacy.html` - A minimal Privacy Policy stating that no user data is collected, as this is a single-user, private backup application.
* `README.md` - This documentation file.

## 🔒 Privacy & Security

This GitHub Pages site and its associated Google Cloud App are for **personal, private use only**. 
The application does not collect, store, or process any third-party user data. The OAuth app is configured as an "External" user type strictly because personal Google accounts cannot use the "Internal" Workspace configuration. No public access or third-party authentication is permitted.