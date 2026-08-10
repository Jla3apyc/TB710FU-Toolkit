[🇷🇺 Читать на русском](README_RU.md)
# 🛠️ Lenovo Xiaoxin Pad Pro GT (TB710FU) Toolkit & Guides

A collection of utilities and detailed guides for managing, modifying, and flashing the **Lenovo Xiaoxin Pad Pro GT (TB710FU)**.

> ⚠️ **IMPORTANT:** All actions are performed at your own risk. Modifying system partitions may lead to loss of warranty or bricking your device. **Always make backups before proceeding.**

---

## 📚 Projects

This toolkit consists of interconnected projects. Choose the one that matches your task:

### 🧹 1. [TB710FU bloatware uninstaller](TB710FU-bloatware-uninstaller.md)
A lightweight, portable script for disabling OTA updates and removing pre-installed bloatware.
* **Purpose:** Automatically disables non-functional OTA updates and simplifies the removal of pre-installed bloatware on the Lenovo Xiaoxin Pad Pro GT (TB710FU) via ADB. 
* **Features:** Includes dedicated scripts for both Chinese (CN) and Global (EN/RU) firmware versions. Optimizes Google services and applies RU locale on Chinese firmware. Uses safe uninstallation via `pm uninstall --user 0` with the ability to fully restore apps. Easily customizable by editing the package list in the `.bat` file.

### 📖 2. [TB710FU flash guide](TB710FU-flash-guide.md) *(Coming soon)*
A step-by-step guide for complete flashing, recovery, and device maintenance using `Fastboot`, `MiFlash`, or `QFIL`.
* **Purpose:** Installing global firmware, unbricking the device, and restoring system partitions.
* **Features:** Detailed instructions for Snapdragon platforms, including driver setup, bootloader unlocking, and unbrick methods (EDL mode).

### 🌍 3. [TB710FU region code changer](TB710FU-region-code-changer.md) *(Coming soon)*
A minimalist, portable, and safe tool for changing the region code.
* **Purpose:** Activate Widevine L1 (HD video), Google Play certification, change regional settings, and enable local AI features.
* **Features:** Works via built-in PowerShell or ADB. No complex dependencies (like Python) required.

---

## 🙏 Acknowledgments
* The logic is inspired by projects such as **ADB AppControl**, **QFIL / MiFlash**, **LTBox** and research from the **4PDA** and **XDA** communities.
* Thanks to all the enthusiasts who share knowledge about the Snapdragon platform.

> *This project is provided for informational and educational purposes only. The author is not responsible for any direct or indirect damage caused to your device.*
