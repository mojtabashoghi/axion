# Axion

> **یک پلاگین همه‌کاره طراحی‌شده برای مطالعه و تحقیق روی فایل‌های PDF و یادگیری زبان.**
>
> **🌐 Language:** [English](README.md) · [فارسی](README_fa.md) · **📖 User Guide:** [English](USER_GUIDE.md) · [فارسی](USER_GUIDE_fa.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.md)
[![GitHub release](https://img.shields.io/github/v/release/mojtabashoghi/axion?include_prereleases)](https://github.com/mojtabashoghi/axion/releases)
[![Obsidian](https://img.shields.io/badge/Obsidian-1.4.0%2B-7C3AED)](https://obsidian.md)
[![Made with ONNX Runtime](https://img.shields.io/badge/ONNX%20Runtime-Web-005CED)](https://onnxruntime.ai)
[![Offline-first](https://img.shields.io/badge/offline--first-success)](https://github.com/mojtabashoghi/axion#-حریم-خصوصی)

> **مطالعه، تحقیق و یادگیری زبان، بدون اینکه از vault خود خارج شوید.**
> Axion، Obsidian + PDF را به یک فضای کاری کامل تبدیل می‌کند. هایلایت کنید، ترجمه کنید، بشنوید و حفظ کنید.

Axion، Obsidian + PDF را به یک **فضای کاری کامل برای یادگیری زبان** تبدیل می‌کند.  
همه‌چیز **آفلاین‌محور** است: مدل‌ها یک بار دانلود می‌شوند، بعد همه‌چیز روی دستگاه خودت اجرا می‌شود.

---

## ✨ قابلیت‌ها

### 🖍️ خواندن و تحقیق روی PDF
- **هایلایت** با ۶ رنگ و ۲ شکل (گوشه‌گرد / گوشه‌تیز).
- **استیکی نوت** متصل به هایلایت (با ترجمه و صدا)، یا **پین آزاد** در هر جای صفحه.
- **جعبهٔ متن** در هر جای صفحه، با کنترل کامل فونت و رنگ و ترازبندی.
- پاپ‌آپ‌هایی که نوت منبع را همان‌جا ویرایش می‌کنند — بدون جابه‌جایی پنجره.
- **بازیابی خودکار** هایلایت‌ها از مارکرهای `%%hl:…%%` اگر فایل JSON گم شود.
- **dock شناور** روی خود PDF با همهٔ دکمه‌های سریع.

### 🌍 ترجمه
- **Google Translate** (سریع، آنلاین).
- **NLLB-200 distilled 600M** آفلاین (~۹۰۰ مگابایت، اجرا با ONNX Runtime Web روی خود دستگاه).
- تشخیص خودکار زبان مبدأ.
- پشتیبانی بومی از **آلمانی، انگلیسی، فرانسوی، فارسی**.
- اصلاح خودکار علائم نگارشی فارسی، رندر درست RTL.

### 🔊 خواندن با صدای بلند (TTS)
- صداهای عصبی **Piper** که در یک Web Worker اجرا می‌شوند.
- ۲۷ صدا برای آلمانی، انگلیسی و فرانسوی.
- سرعت ۰.۵× تا ۲.۰×.
- صدا به‌صورت **WAV** در vault ذخیره می‌شود و بین نوت، استیکی نوت و فلش‌کارت مشترک است — هر جمله فقط یک بار تولید می‌شود.

### 🃏 فلش‌کارت با تکرار فاصله‌دار (SRS)
- **الگوریتم تکرار فاصله‌دار** الهام‌گرفته از Anki (نسخهٔ اصلاح‌شدهٔ SM-2).
- دو چیدمان: *یک‌رو* (همهٔ ترجمه‌ها روی یک رو) و *دورو* (جلو / پشت).
- ساخت کارت مستقیم داخل نوت:
  - `:: text` → کارت یک‌رو
  - `front ::: back` → کارت دورو
- **ساخت خودکار** از هر کلمه/جملهٔ paste‌شده (اختیاری).
- **Heatmap مرور** با روزهای پیاپی و رکورد.
- **خروجی به Anki** (`.apkg`) — کارت‌ها + صدا، سازگار با Anki Desktop و AnkiDroid.

### 📷 OCR
- **Tesseract.js** (WASM)، آفلاین کار می‌کند.
- PDFهایی که لایهٔ متنی واقعی دارند را **مستقیم** می‌خواند (دقیق + فوری).
- صفحات اسکن‌شده و تصاویر را با **OCR** می‌خواند و به کلیپ‌بورد کپی می‌کند.
- پیش‌پردازش: خاکستری + افزایش کنتراست + بزرگ‌نمایی.
- زبان‌ها: فارسی، انگلیسی، آلمانی، فرانسوی، عربی.

### ⏱️ پومودورو · ✅ لیست کارها · 📅 تقویم
- پومودورو کلاسیک (تمرکز / استراحت کوتاه / استراحت بلند، auto-advance، صدای پایان).
- لیست کارها با زمان شروع/پایان و آلارم.
- **تقویم شمسی (جلالی)** کنار تقویم میلادی — تسک‌های روزانه و یک‌روزه.

### 📸 Capture
- **اسکرین‌شات** با انتخاب ناحیه → کلیپ‌بورد (+ ذخیرهٔ اختیاری در پوشهٔ مطالعه).
- **ضبط صفحه** روی دسکتاپ (میکروفون + صدای سیستم روی ویندوز).
- روی موبایل: افزودن ویدیوی ضبط‌شده با ضبط‌کنندهٔ خود دستگاه.

### 🧩 امکانات اضافه
- **نوار دکمه‌های سریع** بالای پنل کناری.
- **دکمه‌های میانبر سفارشی**: اجرای برنامه / باز کردن فایل / باز کردن URL / ارسال ترکیب کیبورد.
- **منوی راست‌کلیک** روی متن انتخاب‌شده: *Axion: استیکی نوت + ترجمه*.
- **آیکون‌های سفارشی**: فایل‌های SVG خود را در پوشهٔ `icons/` قرار دهید.

---

## 📥 نصب

### از مرورگر Community Plugins
*(پس از پذیرش در دایرکتوری در دسترس خواهد بود)*

1. Settings → **Community plugins** → **Browse**
2. جستجوی **Axion** و نصب
3. فعال‌سازی پلاگین

### نصب دستی

1. سه فایل `main.js`، `manifest.json`، `styles.css` را از [آخرین ریلیز](https://github.com/mojtabashoghi/axion/releases) دانلود کن.
2. آن‌ها را داخل `YourVault/.obsidian/plugins/axion/` قرار بده.
3. در Obsidian: Settings → Community plugins → **Reload** → Axion را فعال کن.

---

## 🚀 شروع سریع

1. یک PDF باز کن. یک **dock شناور** بالای PDF ظاهر می‌شود.
2. روی **🖍️ highlight** کلیک کن → یک رنگ انتخاب کن → روی متن درگ بکش.
3. روی **📝 sticky** کلیک کن → روی صفحه کلیک کن → نوت باز می‌شود، شروع به تایپ کن.
4. با دکمهٔ **🌐** در نوار ابزار، یک ترجمه اضافه کن.
5. دکمهٔ **🃏 flashcard** را بزن تا استیکی نوت به فلش‌کارت تبدیل شود.
6. در پنل کناری → **Flashcards** → مرور کن.
7. وقتی تمام شد، **export به Anki** یا همه‌چیز را داخل Obsidian نگه دار.

---

## 📁 داده‌ها کجا ذخیره می‌شوند

برای هر PDF، Axion یک **پوشهٔ مطالعه** کنار PDF می‌سازد:


### مسیرهای سراسری

| داده | مسیر |
|---|---|
| دیتابیس فلش‌کارت‌ها | `.obsidian/plugins/axion/flashcards.json` |
| صداها و موتور دانلودشده | `.obsidian/plugins/axion/voices/` و `/runtime/` |
| مدل ترجمهٔ دانلودشده | `.obsidian/plugins/axion/nllb/` |
| فایل‌های OCR دانلودشده | `.obsidian/plugins/axion/ocr/` |
| پوشهٔ صوتی سراسری (نوت‌های بدون PDF) | `Language audio/` (قابل تنظیم) |
| override آیکون‌ها | `.obsidian/plugins/axion/icons/*.svg` |

---

## 🔒 حریم خصوصی

- **بدون telemetry. بدون analytics. بدون حساب کاربری.**
- هیچ‌چیز از دستگاهت خارج نمی‌شود مگر خودت بخواهی.
- **اولین بار** که از ترجمه، TTS یا OCR استفاده می‌کنی، مدل لازم از `jsdelivr.net` / `huggingface.co` دانلود و محلی cache می‌شود.
- بعد از آن، ترجمه (NLLB)، TTS (Piper) و OCR (Tesseract) **کاملاً آفلاین** کار می‌کنند.
- فقط **Google Translate** (اگر انتخاب شود) همیشه به اینترنت نیاز دارد.

---

## 🧱 تکنولوژی‌های استفاده‌شده

| لایه | فناوری |
|---|---|
| میزبان پلاگین | [Obsidian API](https://docs.obsidian.md/) |
| زبان | TypeScript / ESBuild |
| TTS | [Piper](https://github.com/rhasspy/piper) — مدل‌های ONNX، Web Worker |
| ترجمهٔ آفلاین | [NLLB-200](https://huggingface.co/facebook/nllb-200-distilled-600M) با [ONNX Runtime Web](https://onnxruntime.ai) |
| ترجمهٔ آنلاین | endpoint عمومی Google Translate |
| OCR | [Tesseract.js](https://github.com/naptha/tesseract.js) (WASM) |
| خروجی Anki | [sql.js](https://sql.js.org) + [fflate](https://github.com/101arrowz/fflate) |

---

## 🛠️ مشارکت

Issue و Pull Request استقبال می‌شود.  
لطفاً ابتدا [CONTRIBUTING.md](CONTRIBUTING.md) را بخوان.

آخرین تغییرات را در [CHANGELOG](CHANGELOG.md) ببین.

---

## 📜 لایسنس

[MIT License](LICENSE.md) © 2026 Mojtaba Shoghi Samani