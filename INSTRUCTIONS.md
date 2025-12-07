# 📲 Flashing Instructions

## ⚠️ Pre-requisites
* **Unlocked Bootloader**: Ensure your device's bootloader is unlocked.
* **Latest Firmware**: You must be on the latest MIUI/HyperOS firmware for your region.
* **Backup**: Warning! Clean flashing will wipe ALL your data. Back up your files first.

---

## 🧼 Clean Flash Guide (First Time Install)
Follow these steps if you are coming from MIUI, HyperOS, or another custom ROM.

### 1. Download Files
* **ROM & Recovery Images**: Download the latest zip and `boot.img`, `dtbo.img`, `vendor_boot.img` from here:
  * 📥 **[Download Latest Build & Images](https://github.com/nasyx-rakeeb/lineage-unofficial-veux-releases/releases)**
* **Google Apps (Optional)**: If you want Play Store, download this specific package:
  * 📥 **[Download MindTheGapps (Android 16)](https://github.com/MindTheGapps/16.0.0-arm64/releases/tag/MindTheGapps-16.0.0-arm64-20250812_214353)**

### 2. Flash Recovery Images (Fastboot)
* Reboot your phone to **Fastboot Mode** (Vol Down + Power).
* Open a terminal/CMD on your PC folder where you downloaded the files.
* Run these commands:
    ```bash
    fastboot flash boot boot.img
    fastboot flash dtbo dtbo.img
    fastboot flash vendor_boot vendor_boot.img
    ```

### 3. Reboot to Recovery
* Use the Volume buttons to select "Recovery Mode" on the phone, or run:
    ```bash
    fastboot reboot recovery
    ```

### 4. Format Data
* In Lineage Recovery, go to **Factory Reset** > **Format data / factory reset**.
* Confirm by selecting **Format data**.

### 5. Flash the ROM
* Go back to the main menu > **Apply Update** > **Apply from ADB**.
* On your PC, run:
    ```bash
    adb sideload lineage-23.0-xxxx-UNOFFICIAL-veux.zip
    ```

### 6. Flash GApps (Optional)
* *Note: If you want Google Apps, you must flash them before booting!*
* On the phone, tap **Advanced** > **Reboot to Recovery**. (This switches slots to the new OS).
* Once back in recovery, go to **Apply Update** > **Apply from ADB**.
* Run:
    ```bash
    adb sideload MindTheGapps-xxxx.zip
    ```

### 7. Reboot
* Go back to the main menu and select **Reboot system now**.

---

## 🔄 OTA Update Guide (Keep Root)
Our ROM supports seamless OTA updates via **Settings > System > Updater**. If you are rooted with Magisk, follow these exact steps to update without losing root.

1.  **Download the Update**
    * Go to **Settings** > **System** > **Updater**.
    * Download and install the update.

2.  **⛔ DO NOT REBOOT YET!**
    * When the installation finishes and the "Reboot" button appears in the Updater app, **STOP**. Do not tap it. Go to your home screen.

3.  **Restore Root (Magisk)**
    * Open the **Magisk App**.
    * Tap **Install** (top card).
    * Select **Install to Inactive Slot (After OTA)**.
    * *Note: If this option is missing, restart the Magisk app.*

4.  **Reboot**
    * Once Magisk finishes patching, tap the **Reboot** button **inside the Magisk app**.

Your phone will reboot into the updated OS with Root access preserved!
