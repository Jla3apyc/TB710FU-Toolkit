[🇬🇧 Read in English](TB710FU-bloatware-uninstaller.md)
# 🧹 Отключение OTA-обновлений, удаление мусорных приложений и фикс локалей в TB710FU

Легковесный портативный скрипт для удаления предустановленного мусорного ПО (bloatware), отключения OTA-обновлений и исправления региональных ограничений на **Lenovo Xiaoxin Pad Pro GT / Yoga Tab 11.1 (прошивка TB710FU)**.

> ⚠️ **ОТКАЗ ОТ ОТВЕТСТВЕННОСТИ: ВСЕ ДЕЙСТВИЯ НА СВОЙ СТРАХ И РИСК!**  
> Инструмент удаляет системные приложения через `pm uninstall --user 0`. Приложения удаляются **только для текущего пользователя** и могут быть восстановлены через ADB. Однако удаление некоторых пакетов может повлиять на стабильность системы или OTA-обновления. **Всегда просматривайте список пакетов перед запуском.**

---

## ✨ Возможности

- 🚀 **Без установки:** Просто распакуйте утилиту и запустите нужный `.bat` файл для вашей версии прошивки.
- 🌐 **Скрипты для разных регионов:** Отдельные скрипты для китайской (CN) и глобальной (EN/RU) прошивок.
- 🇷🇺 **Фикс RU-локали и Google (CN-скрипт):** CN-скрипт автоматически устанавливает русскую локаль и снимает ограничения на фоновую работу приложений Google.
- 🛡️ **Безопасное удаление:** Использует `pm uninstall --user 0` — приложения можно восстановить позже.
- 🔍 **Проверка устройства:** Проверяет подключение ADB перед продолжением.
- 📖 **Встроенная справка:** Пошаговое руководство по включению отладки по USB, если устройство не обнаружено.
- 🎯 **Точечное воздействие:** Специально настроено для bloatware Lenovo Xiaoxin Pad Pro GT / Yoga Tab 11.1.

---

## 📋 Требования

1. **Windows 10 / 11**
2. Установленные **ADB-драйверы** на ПК (MediaTek VCOM или Google USB Driver)
3. **Platform Tools (adb.exe)** — уже находится в подпапке `adb`
4. **Отладка по USB включена** на планшете (см. инструкцию ниже)

---

## 📦 Структура проекта

```text
TB710FU_bloatware_uninstaller/
├── 📄 TB710FU_CN_bloatware_uninstaller.bat  # Для китайской прошивки (выбор EN/RU)
├── 📄 TB710FU_EN_bloatware_uninstaller.bat  # Для глобальной прошивки (English)
├── 📄 TB710FU_RU_bloatware_uninstaller.bat  # Для глобальной прошивки (Русский)
└── 📁 adb/                                  # ⬇️ Сюда поместите Platform Tools
    ├── adb.exe
    ├── AdbWinApi.dll
    └── AdbWinUsbApi.dll
```

## 🚀 Как использовать

### Шаг 1: Включите отладку по USB на планшете

1. Откройте **Настройки → О планшете**
2. Нажмите на **Версия ПО** (или версия Android) 7 раз, пока не появится "Вы стали разработчиком!"
3. Вернитесь в **Настройки → Система → Для разработчиков**
4. Включите **Отладка по USB**
5. Подключите планшет к ПК через USB
6. Разрешите отладку в появившемся окне на экране планшета

### Шаг 2: Запустите скрипт

1. **Выберите нужный скрипт** в зависимости от региона вашей прошивки:
   - `TB710FU_CN_bloatware_uninstaller.bat` для китайской прошивки.
   - `TB710FU_EN_bloatware_uninstaller.bat` или `TB710FU_RU_bloatware_uninstaller.bat` для глобальной прошивки.
2. **Запустите** выбранный `.bat` файл.
3. **Выберите язык** (если запросит CN-скрипт) или продолжите сразу (EN/RU скрипты).
4. **Подтвердите**, что ваше устройство отображается в списке ADB.
5. Скрипт автоматически удалит все пакеты из списка и применит необходимые фиксы.

---

## 📦 Удаляемые пакеты по умолчанию

Скрипты удаляют следующий bloatware. Вы можете **отредактировать `.bat` файлы**, чтобы настроить списки.

### 🇨🇳 Для китайской (CN) прошивки
*Обрабатывается `TB710FU_CN_bloatware_uninstaller.bat`. Также применяет RU-локаль и исправляет фоновые ограничения Google.*

#### 🔴 Системные приложения ZUI и Lenovo
| Пакет | Описание |
|-------|----------|
| `com.zui.browser` | Браузер ZUI |
| `com.zui.calendar` и оверлеи | Календарь ZUI (и различные темы) |
| `com.zui.contacts` и оверлеи | Контакты ZUI |
| `com.zui.filemanager` | Файловый менеджер ZUI |
| `com.zui.gallery` | Галерея ZUI |
| `com.lenovo.club.app` | Lenovo Club |
| `com.lenovo.leos.appstore` | Магазин приложений Lenovo |
| `com.lenovo.leos.cloud.sync` | Облачная синхронизация Lenovo |
| `com.lenovo.office` | Lenovo Office |
| `com.lenovo.xbb` / `com.lenovo.xiaotian.trigger` | Сервисы Lenovo Xiaoxin |

#### 🟠 Китайские сторонние приложения
| Пакет | Описание |
|-------|----------|
| `com.sina.weibo` | Weibo |
| `com.ss.android.ugc.aweme` | Douyin (китайский TikTok) |
| `com.smile.gifmaker` | Kuaishou |
| `com.qiyi.video.pad` | iQiyi |
| `com.youku.phone` | Youku |
| `com.netease.cloudmusic` | NetEase Cloud Music |
| `com.sohu.inputmethod.sogou.oem` | Метод ввода Sogou |
| `cn.wps.moffice_eng` | WPS Office |
| `com.lemon.lv` / `pro` | CapCut (Jianying) |
| `com.qihoo.aiwork` | 360 AI / Безопасность |

#### 🟢 Игры и развлечения (CN)
| Пакет | Описание |
|-------|----------|
| `com.cybercat.acbridge` | Игра AC Bridge |
| `com.happyelements.AndroidAnimal` | Happy Elements |
| `com.lenovo.minigamelauncher` | Мини-игры Lenovo |

---

### 🌍 Для глобальной (EN/RU) прошивки
*Обрабатывается `TB710FU_EN_bloatware_uninstaller.bat` и `TB710FU_RU_bloatware_uninstaller.bat`.*

#### 🔵 Приложения Google
| Пакет | Описание |
|-------|----------|
| `com.google.android.apps.books` | Google Play Книги |
| `com.google.android.apps.kids.home` | Google Детское пространство |
| `com.google.android.apps.magazines` | Google Новости |
| `com.google.android.apps.messaging` | Google Сообщения |
| `com.google.android.apps.photos` | Google Фото |
| `com.google.android.apps.subscriptions.red` | Google One |
| `com.google.android.apps.tachyon` | Google Duo |
| `com.google.android.apps.youtube.kids` | YouTube Kids |
| `com.google.android.play.games` | Google Play Игры |
| `com.google.android.videos` | Google Play Фильмы |

#### 🟠 Приложения Lenovo / ZUI
| Пакет | Описание |
|-------|----------|
| `com.lenovo.appdaily` | Lenovo Daily (лента новостей) |
| `com.lenovo.ota` | OTA-обновления Lenovo |
| `com.lenovo.tbengine` | Lenovo TB Engine |
| `com.tblenovo.center` | Lenovo Center |
| `com.tblenovo.lenovowhatsnew` | Lenovo Что нового |
| `com.zui.adobeexpressapp` | ZUI Adobe Express |
| `com.zui.pengen` | ZUI Pengen |

#### 🟡 Сторонние и региональные приложения
| Пакет | Описание |
|-------|----------|
| `ai.perplexity.app.android` | Perplexity AI |
| `cn.wps.moffice_eng` | WPS Office |
| `com.adobe.lrmobile` | Adobe Lightroom |
| `com.lemon.lvoverseas` | CapCut |
| `com.opera.browser` / `preinstall` | Браузер Opera |
| `com.tophatch.concepts` | Concepts |
| `com.zhiliaoapp.musically` | TikTok |
| `jp.co.celsys.clipstudiopaint.googleplay` | Clip Studio Paint |
| `ru.yandex.*` / `ru.dublgis.dgismobile` | Приложения Яндекса и 2ГИС (RU регион) |

#### 🟢 Системные компоненты (опционально)
| Пакет | Описание |
|-------|----------|
| `com.android.bookmarkprovider` | Провайдер закладок |
| `com.android.providers.partnerbookmarks` | Партнерские закладки |
| `com.android.providers.partnerbrowsercustomizations` | Настройки партнерского браузера |

---

## 🛠️ Решение проблем

| Проблема | Решение |
|----------|---------|
| `ОШИБКА: adb.exe не найден!` | Скачайте Platform Tools и поместите `adb.exe` + DLL в папку `adb`. |
| Устройство не отображается в ADB | Включите отладку по USB на планшете. Проверьте встроенную справку (нажмите `Н` в запросе). |
| `unauthorized` в ADB | Разблокируйте экран планшета и нажмите "Разрешить отладку USB" в появившемся окне. |
| Приложение возвращается после перезагрузки | Этого не должно происходить с `--user 0`. Если происходит — приложение защищено системой. |
| `Failure [DELETE_FAILED_DEVICE_POLICY_MANAGER]` | Приложение защищено политикой устройства. Без root не удалить. |

---

## 🙏 Благодарности

* Вдохновлено проектами **ADB AppControl, QFIL, Software Fix (LMSA), LTBox** и исследованиями сообществ **4PDA**.
* Использует официальные **Android Platform Tools** от Google.

> *Этот инструмент предоставляется исключительно в ознакомительных и образовательных целях. Автор не несет ответственности за любой прямой или косвенный ущерб, причиненный вашему устройству.*
