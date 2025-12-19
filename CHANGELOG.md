# 📝 Changelog

## v2.0 - December Patch & Feature Drop (2025-12-19)
* **Status:** STABLE
* **System:**
    * Synced with latest LineageOS 23 source.
    * **Security:** Merged **December 2025 Security Patch**.
* **New Features (Plus Menu):**
    * **EdgeLink:** New sidebar multitasking tool. Launch apps in floating/desktop windows from any screen. (Includes layout & toggle fixes).
    * **Duress PIN:** Added plausible deniability. Entering a specific decoy PIN unlocks the device into a hidden profile to protect your data.
    * **Local ADB:** Enable ADB over localhost for on-device terminal use (Termux) without a PC.
* **Quick Settings (QS):**
    * **Private DNS Tile:** Switch DNS providers (Google, Cloudflare, AdGuard, etc.) instantly via a popup dialog.
    * **Force 5G/NR:** Force modem to use 5G/NR only.
    * **5G Toggle:** Quickly enable or disable 5G connectivity.
* **Launcher:**
    * Added "Force Stop" and "Uninstall" shortcuts to app icon long-press menu.

---

## v1.0 - Initial Official Release (2025-12-07)
* **Status:** STABLE / Daily Driver
* **Base:** Initial public release based on LineageOS 23 (Android 16).
* **Kernel:** Updated to `5.4.292-LineageOS/9f6863f2`.
* **Security:**
    * Signed with private **Release Keys** (not test-keys).
* **New Features:**
    * **Native OTA Infrastructure:** Implemented fully working System Updater.
    * **Root Preservation:** Added support for Magisk "Install to Inactive Slot".
    * **SEPolicy:** Enforcing.
