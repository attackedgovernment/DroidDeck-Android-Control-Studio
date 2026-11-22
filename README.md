<div align="center">
  <h1>DroidDeck</h1>
  [![Telegram](https://img.shields.io/badge/Telegram-Канал-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/attackdroiddeck)
  <p><strong>Универсальная студия управления Android для Windows в стиле Material 3 Expressive</strong></p>

  <p>
    <img src="https://img.shields.io/badge/Platform-Windows%2010%2F11-0078D6?style=for-the-badge&logo=windows" alt="Windows" />
    <img src="https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
    <img src="https://img.shields.io/badge/UI-Material%203%20Expressive-1a6b42?style=for-the-badge&logo=materialdesign&logoColor=white" alt="Material 3" />
    <img src="https://img.shields.io/badge/Android-12--16%20%7C%20HyperOS%20%7C%20AOSP-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Android" />
  </p>
</div>

---

**DroidDeck** — лёгкое десктопное приложение на базе `Python + pywebview` (системный движок Edge WebView2), объединяющее все популярные инструменты для обслуживания, оптимизации и прошивки Android-смартфонов (Xiaomi / Redmi / POCO, Google Pixel, Samsung, OnePlus, AOSP и кастомных ROM).

## Основные возможности

### 📱 Устройство, телеметрия и пульт управления
* **Мульти-устройства (USB + Wi-Fi ADB):** автоматическое определение модели, кодового имени (`codename`), оболочки (HyperOS, MIUI, One UI, OxygenOS, LineageOS, crDroid, Pixel) и переключение между активными сессиями без ошибок `more than one device`.
* **Беспроводной ADB:** поиск локального IP смартфона, перевод в `tcpip 5555` и подключение по Wi-Fi в один клик.
* **Пульт управления с ПК:** системные клавиши, управление медиаплеером, ввод текста и мгновенное открытие URL в браузере телефона.
* **Диагностика и захват:** чтение телеметрии (SoC, свободная ОЗУ, температура/напряжение/циклы АКБ, SELinux, Verified Boot), дамп последних ошибок `logcat (*:E)`, PNG-скриншоты, 15-секундная запись экрана MP4, бэкап `DCIM/Camera` и экспорт списка всех пакетов.
* **Системные права без Root:** запуск сервера **Shizuku**, выдача прав AppOps + ADB Permissions для **Battery Guru** и **SetEdit**.

### 🖥️ Вывод экрана (`scrcpy`)
* **Автоматическая установка:** сам находит и скачивает актуальный релиз `Genymobile/scrcpy` (win64) с GitHub и использует встроенный `adb.exe` без конфликта серверов.
* **Готовые профили:** *Игровой 120 FPS*, *Выключенный экран телефона*, *Режим веб-камеры (Android 12+)* и *Лёгкий для Wi-Fi*, а также тонкая настройка разрешения, FPS, битрейта, звука и режима «Поверх всех окон».

### 📂 Файловый менеджер и APK-экстрактор
* **Проводник `/sdcard`:** просмотр папок, скачивание файлов на ПК (`pull`), отправка файлов с ПК (`push`), создание каталогов и удаление.
* **Менеджер приложений:** фильтрация (*Пользовательские*, *Системные*, *Замороженные*), **извлечение `.apk` и Split-APK** с телефона на ПК, заморозка/разморозка (`disable-user` / `enable`), запуск, очистка данных и умная установка APK с обходом ограничений Android 14–16 (`--bypass-low-target-sdk-block`).

### ⚙️ Системные твики (28 настроек) и Debloat (30+ пакетов)
* **AOSP / Pixel и Android 14–16:** предиктивный жест «Назад», секунды в часах статус-бара, история уведомлений, отключение 7-дневного сброса ADB, принудительный Split-Screen и Desktop Mode.
* **HyperOS / MIUI и производительность:** фиксация 120 Гц (`user_refresh_rate`), ускорение анимаций `0.5x`, отключение Phantom Process Killer, заморозка кэшированных приложений в ОЗУ, ART-компиляция (`speed-profile` / `everything`), Aggressive Doze, отключение фонового сканирования Wi-Fi/BLE и системный Private DNS (**AdGuard DNS** / **Cloudflare 1.1.1.1**).
* **Debloat и живой сканер:** безопасное удаление рекламы и телеметрии для пользователя 0 с возможностью мгновенного возврата переключателем + сканирование всех установленных пакетов устройства.

### ⚡ Fastboot, прошивки и драйверы
* **Работа с разделами:** прошивка `init_boot`, `boot`, `vendor_boot`, `recovery`, `vbmeta` (`--disable-verity --disable-verification`), `dtbo`, `system` (GSI), временный `fastboot boot`, `adb sideload`, переключение слотов `A/B`, переход в **FastbootD** и запуск `.bat`-скриптов с предупреждением о блокировке загрузчика (`lock`).
* **Поиск прошивок и драйверов:** загрузка официальных образов HyperOS / MIUI (`.tgz` и `.zip`) с фильтрами по региону и типу, поиск веток прошивок на **4PDA**, быстрые ссылки для Pixel / LineageOS / crDroid / Samsung, а также скачивание Google USB Driver и установка `.inf` через `pnputil`.

### 💬 Встроенный консультант (API)
* Поддержка **Google Gemini API** и любых **OpenAI-совместимых API** (OpenRouter, Groq, DeepSeek, локальные Ollama / LM Studio) с автоматическим прикреплением логов консоли для разбора ошибок.

### 🎨 Дизайн Material 3 Expressive
* 4 динамические палитры **Monet** (*Emerald Forest*, *Pixel Iris*, *Pixel Cobalt*, *Xiaomi Terracotta*) с полной поддержкой тёмной и светлой темы.
* Анимированная морфинг-иконка, волнистый индикатор загрузки M3, интерактивные M3-переключатели и иконки эмодзи в стиле Apple iOS.

---

## Быстрый запуск (для пользователей)

1. Скачайте последний релиз **`DroidDeck.exe`** во вкладке [Releases](../../releases).
2. Включите **Отладку по USB** на смартфоне *(на Xiaomi дополнительно включите «Отладка по USB (Настройки безопасности)» для выдачи прав приложениям)*.
3. Запустите `DroidDeck.exe`. Для работы в режиме Fastboot установите драйверы (можно скачать прямо во вкладке **«Прошивки и Драйверы»**).

> **Примечание Windows SmartScreen:** поскольку `.exe` собран через PyInstaller без платной цифровой подписи, при первом запуске нажмите *«Подробнее» → «Выполнить в любом случае»*.

---

## Сборка из исходников

### Требования
* Windows 10 / 11 (с установленным Microsoft Edge WebView2 Runtime)
* Python 3.11+
* Официальные утилиты Google [SDK Platform-Tools](https://developer.android.com/tools/releases/platform-tools) в папке `platform-tools/` (`adb.exe`, `fastboot.exe`, `AdbWinApi.dll`, `AdbWinUsbApi.dll`)

### Структура проекта
```text
DroidDeck/
├── main.py              # Бэкенд: ADB/Fastboot, scrcpy, файловый менеджер, парсер прошивок, API
├── index.html           # Интерфейс Material 3 Expressive
├── icon.ico             # Иконка приложения
└── platform-tools/      # Официальные бинарники adb.exe и fastboot.exe
