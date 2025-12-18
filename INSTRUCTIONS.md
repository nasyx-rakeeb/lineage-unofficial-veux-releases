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
Our ROM supports seamless OTA updates via **Settings > System > System Updates**. If you are rooted with Magisk, follow these exact steps to update without losing root.

1.  **Download the Update**
    * Go to **Settings** > **System** > **System Updates**.
    * Click the refresh icon button in top right corner to download the new update.

2.  **⛔ DO NOT REBOOT YET!**
    * When the installation finishes and the "Reboot" button appears in the Updater app, **STOP**. Do not tap it. Go to your home screen.

3.  **Restore Root (Magisk)**
    * Open the **Magisk App**.
    * Tap **Install** (top card).
    * Select **Install to Inactive Slot (After OTA)**.
    * Click **Let's Go**.
    * *Note: If this option is missing, restart the Magisk app.*

4.  **Reboot**
    * Once Magisk finishes patching and says "All done", simply **Reboot** your device manually (using the Power Menu).

---

## ⚠️ Important: Updater App Behavior
The LineageOS Updater app works in the background, but there are two specific quirks you should know to avoid confusion:

### 1. Importing Local Updates (Do Not Minimize!)
If you choose to update via a local ZIP file ("Local Update"):
* When the "Importing local update" dialog appears, **you must stay on that screen**.
* **Do not** minimize the app or switch to another app during the import phase (approx. 1 minute).
* If you leave the screen, the import will fail. Wait for the "Install" button to appear before leaving.

### 2. Disappearing "Reboot" Button
Once the installation starts (progress bar appears), you *can* leave the screen and use your phone. However:
* If you return to the Updater app **after** the installation has reached 100%, the screen might look empty (no "Reboot" button shown).
* **Solution:** Don't panic. The update **is installed**.
    * **For Online Updates:** Tap the Refresh icon again. It will detect the installed update and show the Reboot button.
    * **For Local Updates:** Select the local file and click "Install" again. It will skip the installation (since it's done) and immediately show the Reboot button.
