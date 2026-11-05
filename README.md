# ✉️ Maily — Unraid Community Applications Docker Template

Official Unraid Docker repository and XML template for **[Maily](https://github.com/stormsia/maily)** — The Universal Temporary Email Gateway & REST API Platform.

[![Unraid](https://img.shields.io/badge/Unraid-Compatible-orange?logo=unraid)](https://unraid.net)
[![Docker GHCR](https://img.shields.io/badge/Docker-ghcr.io-blue?logo=docker&logoColor=white)](https://github.com/stormsia/maily/pkgs/container/maily)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/stormsia/maily/blob/main/LICENSE)

---

## 🦁 What is Maily?

**Maily** aggregates 8+ disposable email services (Mail.tm, TempMail Plus, Temp-Mail.io, NoopMail, DispoEmail, AnonymMail, Temp.tf, and Gmail OAuth2) under a single high-performance REST API, modern async Python SDK (`maily-client`), and a cyberpunk dark-mode web console.

### Key Highlights for Unraid Users
- ⚡ **Instant OTP Verification Extraction:** 1-line automatic verification code extraction for Playwright, Pytest, and QA bots.
- 🖥️ **Dark-Mode Web Dashboard:** Sleek web UI served directly at port `8477`.
- 💾 **Embedded SQLite WAL:** Zero external databases or Redis instances needed. Everything persists cleanly inside `/mnt/user/appdata/maily`.
- 🧹 **Automatic DB Maintenance:** Background retention sweeper with zero-downtime VACUUM defragmentation.
- 🔐 **Multi-Tenant API Keys:** Granular API token creation with Fernet-encrypted vault.

---

## 🚀 How to Add to Unraid

### Method 1: Community Applications Repository (Recommended)
1. On your Unraid web dashboard, go to the **Docker** tab (or **Settings** → **Docker**).
2. Ensure **Template Authoring Mode** or custom repositories are enabled.
3. In **Template repositories**, add:
   ```text
   https://github.com/stormsia/unraid-templates
   ```
4. Click **Save**. Maily will now appear under your Docker templates in the **Add Container** list.

### Method 2: Direct Template URL
1. Go to **Docker** → **Add Container**.
2. Paste the raw template URL into the **Template** field at the top:
   ```text
   https://raw.githubusercontent.com/stormsia/unraid-templates/main/templates/maily.xml
   ```
3. Click **Load File**.
4. Configure your `MAILY_API_KEY` (a master root key used to authenticate requests).
5. Click **Apply**.

---

## ⚙️ Default Container Configuration

| Parameter | Type | Default Value | Description |
|---|---|---|---|
| **WebUI & API Port** | Port | `8477:8477/TCP` | HTTP port for the dark web console and REST API |
| **Data Storage** | Path | `/mnt/user/appdata/maily` -> `/data` | Persistent SQLite database and Fernet keys |
| **MAILY_API_KEY** | Variable | *(your secret key)* | Master API key securing API endpoints and web UI |
| **MAILY_HOST** | Variable | `0.0.0.0` | Bind host address inside the container |
| **MAILY_PORT** | Variable | `8477` | Port inside the container |

---

## 🌐 Links & Documentation

- **Maily Project:** [https://github.com/stormsia/maily](https://github.com/stormsia/maily)
- **Interactive API Documentation:** [https://stormsia.github.io/maily/](https://stormsia.github.io/maily/)
- **Support & Issues:** [https://github.com/stormsia/maily/issues](https://github.com/stormsia/maily/issues)
- **PyPI Client SDK:** [https://pypi.org/project/maily-client/](https://pypi.org/project/maily-client/)
