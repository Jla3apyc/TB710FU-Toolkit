[🇷🇺 Читать на русском](TB710FU-bloatware-uninstaller_ru.md)
# 🧹 TB710FU bloatware uninstaller, OTA disabler & locale fixer

A lightweight, portable script for disabling OTA updates, removing pre-installed bloatware, and fixing regional restrictions on **Lenovo Xiaoxin Pad Pro GT / Yoga Tab 11.1 (TB710FU firmware)**.

---

> ⚠️ **DISCLAIMER: USE AT YOUR OWN RISK!**  
> This tool removes system apps using `pm uninstall --user 0`. The apps are removed **only for the current user** and can be restored via ADB. However, removing certain packages may affect system stability. **Always review the list of packages before running the script.**

---

[Link to the release](https://github.com/Jla3apyc/TB710FU-Toolkit/releases/tag/TB710FU-bloatware-uninstaller)

---

## ✨ Features

- 🚀 **Zero Installation:** Just unpack the utility and run the appropriate `.bat` file for your firmware region.
- 🌐 **Region-Specific Scripts:** Dedicated scripts for Chinese (CN) and Global (EN/RU) firmware versions.
- 🌎 **Google Services & RU Locale Fix (CN Script):** The CN script automatically sets the Russian locale and whitelists Google apps for background activity.
- 🛡️ **Safe Removal:** Uses `pm uninstall --user 0` — apps can be restored later.
- 🔍 **Device Verification:** Checks ADB connection before proceeding.
- 📖 **Built-in Help:** Step-by-step guide for enabling USB Debugging if the device is not detected.
- 🎯 **Targeted:** Specifically tuned for Lenovo Xiaoxin Pad Pro GT (TB710_ZUXOS_1.5.04.470)/ Yoga Tab 11.1 (TB710FU_ZUI_17.5.04.070).

---

## 📋 Prerequisites

1. **Windows 10 / 11**
2. **ADB drivers** installed on your PC
3. **Platform Tools (adb.exe)** — already in the `adb` subfolder
4. **USB Debugging enabled** on the tablet (see instructions below)

---

## 📦 Project Structure

```text
TB710FU_bloatware_uninstaller/
├── 📄 TB710FU_CN_bloatware_uninstaller.bat  # For Chinese firmware (bilingual EN/RU)
├── 📄 TB710FU_EN_bloatware_uninstaller.bat  # For Global firmware (English)
├── 📄 TB710FU_RU_bloatware_uninstaller.bat  # For Global firmware (Russian)
└── 📁 adb/                                  # ⬇️ Place Platform Tools here
    ├── adb.exe
    ├── AdbWinApi.dll
    └── AdbWinUsbApi.dll
```

## 🚀 How to Use

### Step 1: Enable USB Debugging on Your Tablet

1. Open **Settings → About tablet → Android version**
2. Tap **Software version** 7 times until "You are now a developer!" appears
3. Return to **Settings → System → Developer options**
4. Enable **USB Debugging**
5. Connect the tablet to your PC via USB
6. Allow the debugging prompt on the tablet screen when it appears

### Step 2: Run the Script

1. **Choose the correct script** based on your tablet's firmware region:
   - `TB710FU_CN_bloatware_uninstaller.bat` for Chinese firmware.
   - `TB710FU_EN_bloatware_uninstaller.bat` or `TB710FU_RU_bloatware_uninstaller.bat` for Global firmware.
2. **Run** the selected `.bat` file.
3. **Select language** (CN script) or proceed directly (EN/RU scripts).
4. **Confirm** that your device appears in the ADB devices list.
5. The script will automatically remove all packages from the list and apply necessary fixes.

---

## 📦 Packages Removed by Default

The scripts remove the following bloatware. You can **edit the `.bat` files** to customize the lists.

### 🇨🇳 For Chinese (CN) Firmware
*Targeted by `TB710FU_CN_bloatware_uninstaller.bat`. Also applies RU locale and fixes Google background restrictions.*

#### 🔴 ZUI & Lenovo System Apps
| Package | Description |
|---------|-------------|
| `com.zui.browser` | ZUI Browser |
| `com.zui.calendar` & overlays | ZUI Calendar (and various theme overlays) |
| `com.zui.contacts` & overlays | ZUI Contacts |
| `com.zui.filemanager` | ZUI File Manager |
| `com.zui.gallery` | ZUI Gallery |
| `com.lenovo.club.app` | Lenovo Club |
| `com.lenovo.leos.appstore` | Lenovo App Store |
| `com.lenovo.leos.cloud.sync` | Lenovo Cloud Sync |
| `com.lenovo.office` | Lenovo Office |
| `com.lenovo.xbb` / `com.lenovo.xiaotian.trigger` | Lenovo Xiaoxin Services |

#### 🟠 Chinese Third-Party Apps
| Package | Description |
|---------|-------------|
| `com.sina.weibo` | Weibo |
| `com.ss.android.ugc.aweme` | Douyin (TikTok CN) |
| `com.smile.gifmaker` | Kuaishou |
| `com.qiyi.video.pad` | iQiyi |
| `com.youku.phone` | Youku |
| `com.netease.cloudmusic` | NetEase Cloud Music |
| `com.sohu.inputmethod.sogou.oem` | Sogou Input Method |
| `cn.wps.moffice_eng` | WPS Office |
| `com.lemon.lv` / `pro` | CapCut (Jianying) |
| `com.qihoo.aiwork` | 360 AI / Security |

#### 🟢 Games & Entertainment (CN)
| Package | Description |
|---------|-------------|
| `com.happyelements.AndroidAnimal` | Happy Elements |
| `com.lenovo.minigamelauncher` | Lenovo Mini Games |

---

### 🌍 For Global (EN/RU) Firmware
*`TB710FU_EN_bloatware_uninstaller.bat` and `TB710FU_RU_bloatware_uninstaller.bat` are used*

#### 🔵 Google Apps
| Package | Description |
|---------|-------------|
| `com.google.android.apps.books` | Google Play Books |
| `com.google.android.apps.kids.home` | Google Kids Space |
| `com.google.android.apps.magazines` | Google News |
| `com.google.android.apps.messaging` | Google Messages |
| `com.google.android.apps.photos` | Google Photos |
| `com.google.android.apps.subscriptions.red` | Google One |
| `com.google.android.apps.tachyon` | Google Duo |
| `com.google.android.apps.youtube.kids` | YouTube Kids |
| `com.google.android.play.games` | Google Play Games |
| `com.google.android.videos` | Google Play Movies |

#### 🟠 Lenovo / ZUI Apps
| Package | Description |
|---------|-------------|
| `com.lenovo.appdaily` | Lenovo Find Apps |
| `com.lenovo.ota` | Lenovo OTA Updates |
| `com.lenovo.tbengine` | Lenovo Updates |
| `com.tblenovo.center` | Lenovo Vantage |
| `com.tblenovo.lenovowhatsnew` | Lenovo What's New |
| `com.zui.adobeexpressapp` | Adobe Express |
| `com.zui.pengen` | Creation Tools |

#### 🟡 Third-Party & Regional Apps
| Package | Description |
|---------|-------------|
| `ai.perplexity.app.android` | Perplexity AI |
| `cn.wps.moffice_eng` | WPS Office |
| `com.adobe.lrmobile` | Adobe Lightroom |
| `com.lemon.lvoverseas` | CapCut |
| `com.opera.browser` / `preinstall` | Opera Browser |
| `com.tophatch.concepts` | Концепты |
| `com.zhiliaoapp.musically` | TikTok |
| `jp.co.celsys.clipstudiopaint.googleplay` | Clip Studio Paint |
| `ru.yandex.*` / `ru.dublgis.dgismobile` | Yandex Apps & 2GIS (RU region) |

#### 🟢 System Components (Optional)
| Package | Description |
|---------|-------------|
| `com.android.bookmarkprovider` | Bookmark Provider |
| `com.android.providers.partnerbookmarks` | Partner Bookmarks |
| `com.android.providers.partnerbrowsercustomizations` | Partner Browser Customizations |

---

## 🛠️ Troubleshooting

| Issue | Solution |
|-------|----------|
| Device not listed in ADB | Enable USB Debugging on the tablet. Check the built-in help (press `N` when prompted). |
| `unauthorized` in ADB | Unlock the tablet screen and tap "Allow USB debugging" on the prompt. |
| App reappears after reboot | This should not happen with `--user 0`. If it does, the app may be protected by the system. |
| `Failure [DELETE_FAILED_DEVICE_POLICY_MANAGER]` | The app is protected by device policy. Cannot be removed without root. |

---

## 🙏 Credits

* Inspired by the **ADB AppControl, QFIL, Software Fix (LMSA), LTBox** projects and community research on **4PDA**.
* Uses official **Android Platform Tools** from Google.

> *This tool is provided for educational and informational purposes only. The author is not responsible for any direct or indirect damage caused to your device.*
