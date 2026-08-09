# 📡 VPN Subscription Panel — 3x-UI Template

<p align="center">
  <img
    src="https://raw.githubusercontent.com/ldwnil/sub-temp/main/image/sub.gif"
    alt="VPN Subscription Panel"
    width="500"
    
  >
</p>


<p align="center">

🇮🇷 **[فارسی](#فارسی)**    |    🇬🇧 **[English](#english)**

</p>

---

<a name="فارسی"></a>

# 🇮🇷 نسخه فارسی

## 📡 پنل اشتراک VPN — قالب 3x-UI

یک پنل کاربری **مدرن، سبک و واکنش‌گرا** برای سرویس‌های اشتراک VPN که برای استفاده به‌عنوان Subscription Template در **3x-UI** طراحی شده است.

این قالب با **HTML، CSS و JavaScript خالص** ساخته شده و به هیچ Framework خارجی نیاز ندارد.

تمام اجزای پنل در یک فایل `sub.html` قرار گرفته‌اند تا نصب، انتقال و شخصی‌سازی آن بسیار ساده باشد.


---

## ✨ امکانات

* 🔐 نمایش وضعیت اشتراک — فعال / غیرفعال
* 💧 نمایش میزان مصرف حجم با رابط Liquid
* 📊 نمودار مصرف ۷ روز اخیر
* 📋 نمایش لیست کانفیگ‌ها
* 📎 کپی سریع کانفیگ
* 📱 تولید QR Code برای کانفیگ‌ها
* ⏳ شمارش معکوس تا پایان اشتراک
* 📲 معرفی اپلیکیشن‌های پیشنهادی

  * Android
  * iOS
  * Windows
  * macOS
* 💰 بخش خدمات و قیمت‌گذاری
* 🌙 حالت تاریک / روشن
* 🌐 پشتیبانی از فارسی و انگلیسی
* 📱 پشتیبانی از PWA
* 📲 قابلیت نصب روی موبایل
* 📐 طراحی کاملاً Responsive
* ⚡ سبک و سریع
* 🚫 بدون Framework
* 📄 تمام کدها در یک فایل

---

## 📦 پیش‌نیازها

برای استفاده از این قالب نیاز دارید:

* یک سرور با **3x-UI** نصب‌شده
* نسخه‌ای از 3x-UI که از Custom Subscription Templates پشتیبانی کند
* دسترسی به مسیر `sub_templates`
* یک مرورگر مدرن

مسیر معمول قالب‌ها:

```bash
/etc/3x-ui/sub_templates/
```

مرورگرهای پیشنهادی:

* Google Chrome
* Microsoft Edge
* Mozilla Firefox
* Safari

---

# 🚀 نصب

### 1. کپی کردن قالب

فایل `sub.html` را در مسیر قالب‌های 3x-UI قرار دهید:

```bash
sudo cp sub.html /etc/3x-ui/sub_templates/
```

### 2. تنظیم Template در 3x-UI

وارد پنل مدیریت **3x-UI** شوید و به بخش:

```text
Subscription Settings
```

بروید.

مسیر زیر را به‌عنوان Template قرار دهید:

```text
/etc/3x-ui/sub_templates/sub.html
```

سپس تنظیمات را ذخیره کنید.

### 3. ری‌استارت سرویس

ری‌استارت کردن سرویس الزامی نیست، اما توصیه می‌شود:

```bash
sudo systemctl restart x-ui
```

### 4. مشاهده پنل

لینک Subscription ایجادشده توسط 3x-UI را در مرورگر باز کنید.

پنل جدید باید نمایش داده شود.

---

# ⚙️ تنظیمات

تنظیمات اصلی قالب در ابتدای بخش `<script>` فایل `sub.html` قرار دارند.

| Variable               | توضیحات                     | مقدار پیش‌فرض |
| ---------------------- | --------------------------- | ------------- |
| `ENABLE_INSTALL_POPUP` | فعال‌سازی Popup نصب PWA     | `true`        |
| `ENABLE_SERVICES_TAB`  | نمایش تب خدمات و قیمت‌ها    | `true`        |
| `SERVICES_PACKAGES`    | لیست بسته‌های خدماتی        | Array         |
| `STATIC_NEWS`          | اخبار و اطلاعیه‌های استاتیک | Array         |

---

## 💰 بسته‌های خدماتی

بسته‌های قابل نمایش در بخش Services را می‌توانید به‌راحتی تغییر دهید.

```js
const SERVICES_PACKAGES = [
  {
    label: "Lite",
    volume: "10 GB",
    days: 30,
    price: 170000
  },
  {
    label: "Plus",
    volume: "20 GB",
    days: 30,
    price: 300000,
    popular: true
  },
  {
    label: "Pro",
    volume: "30 GB",
    days: 30,
    price: 450000
  },
  {
    label: "Pro-Plus",
    volume: "40 GB",
    days: 30,
    price: 600000
  }
];
```

پارامترها:

| Property  | توضیحات                   |
| --------- | ------------------------- |
| `label`   | نام بسته                  |
| `volume`  | میزان حجم                 |
| `days`    | مدت اعتبار                |
| `price`   | قیمت                      |
| `popular` | نمایش به‌عنوان بسته محبوب |

برای مخفی کردن بخش Services:

```js
const ENABLE_SERVICES_TAB = false;
```

---

# 📰 اخبار و اطلاعیه‌ها

اخبار را می‌توانید از طریق `STATIC_NEWS` مدیریت کنید:

```js
const STATIC_NEWS = [
  {
    title: "New Server Available",
    body: "A new server has been added to the network.",
    date: "2026-08-01"
  },
  {
    title: "Service Update",
    body: "Network performance has been improved.",
    date: "2026-08-05"
  }
];
```

در حال حاضر سیستم اخبار به‌صورت Static کار می‌کند.

در آینده می‌توان آن را به API یا Backend متصل کرد.

---

# 🎨 شخصی‌سازی

### 🌙 حالت تاریک و روشن

کاربر می‌تواند با استفاده از دکمه Theme بین حالت‌های Dark و Light جابه‌جا شود.

تنظیم انتخاب‌شده در:

```text
localStorage
```

ذخیره می‌شود.

---

### 🎨 لوگو

برای تغییر لوگو، قسمت زیر را در `sub.html` پیدا کنید:

```html
<div class="brand-mark">
```

و SVG پیش‌فرض را با لوگوی خود جایگزین کنید.

---

### 🔤 فونت

برای زبان فارسی از **Vazirmatn** استفاده شده و برای زبان انگلیسی از فونت‌های سیستم استفاده می‌شود.

---

# 🌐 تغییر زبان

قالب از دو زبان پشتیبانی می‌کند:

* 🇮🇷 فارسی
* 🇬🇧 English

کاربر می‌تواند مستقیماً از داخل Header زبان را تغییر دهد.

تمام موارد زیر بر اساس زبان انتخاب‌شده تغییر می‌کنند:

* متن‌ها
* اعداد
* تاریخ‌ها
* واحدها
* منوها
* اطلاعات اشتراک
* خدمات

---

# 📱 PWA

قالب برای استفاده به‌عنوان **Progressive Web App** آماده شده است.

### Android

در صورت پشتیبانی مرورگر از:

```text
beforeinstallprompt
```

کاربر می‌تواند پنل را مستقیماً نصب کند.

همچنین امکان استفاده از:

```text
Add to Home Screen
```

وجود دارد.

### iOS

در iOS، Popup نصب مراحل اضافه کردن پنل به Home Screen را به کاربر نمایش می‌دهد.

---

# 📂 ساختار پروژه

تمام پروژه در یک فایل قرار گرفته است:

```text
panel.html
│
├── HTML
│   └── Panel Structure
│
├── CSS
│   ├── Responsive Design
│   ├── Theme
│   ├── Dark Mode
│   └── Components
│
└── JavaScript
    ├── 3x-UI Data
    ├── Subscription
    ├── Usage
    ├── Configurations
    ├── QR Code
    ├── Language
    ├── Theme
    ├── Services
    ├── News
    └── PWA
```

---

# 🔌 اتصال به 3x-UI

قالب از متغیرهایی که توسط 3x-UI ارسال می‌شوند استفاده می‌کند.

برای مثال:

```text
{{ .total }}
{{ .subUrl }}
```

متغیرهای قابل استفاده ممکن است بر اساس نسخه 3x-UI متفاوت باشند.

> ⚠️ اگر از نسخه قدیمی 3x-UI استفاده می‌کنید، ممکن است برخی متغیرها وجود نداشته باشند. در این حالت ممکن است بعضی قسمت‌ها خالی نمایش داده شوند، اما قالب نباید به‌طور کامل خراب شود.

---

# 📅 تاریخ و اعداد

برای نمایش صحیح تاریخ‌ها و اعداد، تنظیمات مربوط به Datepicker و Date Format در 3x-UI باید به‌درستی تنظیم شده باشند.

---

# ⚡ Performance

این قالب با هدف سبک بودن و اجرای سریع طراحی شده است.

هیچ‌کدام از موارد زیر مورد نیاز نیست:

* React
* Vue
* Angular
* Bootstrap
* jQuery

فقط از:

```text
HTML
CSS
Vanilla JavaScript
```

استفاده شده است.

---

# 🤝 مشارکت

Pull Request و Issue کاملاً پذیرفته می‌شوند.

اگر مشکلی پیدا کردید یا پیشنهادی برای بهبود دارید:

1. یک Issue ایجاد کنید.
2. مشکل یا پیشنهاد خود را توضیح دهید.
3. در صورت امکان Pull Request ارسال کنید.

---

# 🐛 گزارش خطا

هنگام گزارش مشکل، در صورت امکان موارد زیر را ارسال کنید:

* نسخه 3x-UI
* مرورگر و نسخه آن
* سیستم‌عامل
* Screenshot
* خطاهای Console
* تنظیمات مرتبط

---

# 📜 مجوز

این پروژه تحت مجوز **MIT License** منتشر شده است.

استفاده شخصی و تجاری، تغییر و انتشار مجدد پروژه آزاد است.

برای اطلاعات کامل به فایل `LICENSE` مراجعه کنید.

---


---

<p align="center">

🇮🇷 **[بازگشت به ابتدای README](#-vpn-subscription-panel--3x-ui-template)**

</p>

---

<a name="english"></a>

# 🇬🇧 English Version

## 📡 VPN Subscription Panel — 3x-UI Template

A **modern, lightweight, and responsive** subscription panel designed for VPN services using **3x-UI Subscription Templates**.

The template is built with **pure HTML, CSS, and JavaScript** and does not require any external framework.

Everything is contained in a single `sub.html` file, making deployment, customization, and maintenance simple.

> 🌐 Persian and English are integrated into the same template, allowing users to switch languages directly from the panel interface.

---

## ✨ Features

* 🔐 Subscription status — Active / Inactive
* 💧 Dynamic liquid usage indicator
* 📊 7-day traffic usage chart
* 📋 Configuration list
* 📎 One-click configuration copy
* 📱 QR code generation
* ⏳ Subscription expiration countdown
* 📲 Recommended VPN applications

  * Android
  * iOS
  * Windows
  * macOS
* 💰 Services & Pricing section
* 🌙 Dark / Light mode
* 🌐 Persian / English support
* 📱 PWA support
* 📲 Mobile installation
* 📐 Fully responsive design
* ⚡ Lightweight and fast
* 🚫 No frameworks
* 📄 Single-file deployment

---

## 📦 Requirements

You need:

* A server with **3x-UI** installed
* A 3x-UI version supporting custom subscription templates
* Access to the `sub_templates` directory
* A modern web browser

Typical template directory:

```bash
/etc/3x-ui/sub_templates/
```

Supported browsers:

* Google Chrome
* Microsoft Edge
* Mozilla Firefox
* Safari

---

# 🚀 Installation

### 1. Copy the template

Copy `panel.html` to the 3x-UI template directory:

```bash
sudo cp sub.html /etc/3x-ui/sub_templates/
```

### 2. Configure 3x-UI

Open the **3x-UI Admin Panel** and navigate to:

```text
Subscription Settings
```

Set the template path to:

```text
/etc/3x-ui/sub_templates/sub.html
```

Save the configuration.

### 3. Restart 3x-UI

Restarting is optional but recommended:

```bash
sudo systemctl restart x-ui
```

### 4. Open the subscription URL

Open the subscription URL generated by 3x-UI in your browser.

The custom subscription panel should now appear.

---

# ⚙️ Configuration

The main configuration options are located near the beginning of the `<script>` section inside `panel.html`.

| Variable               | Description                   | Default |
| ---------------------- | ----------------------------- | ------: |
| `ENABLE_INSTALL_POPUP` | Enable PWA installation popup |  `true` |
| `ENABLE_SERVICES_TAB`  | Enable Services & Pricing tab |  `true` |
| `SERVICES_PACKAGES`    | List of service packages      |   Array |
| `STATIC_NEWS`          | Static news and announcements |   Array |

---

## 💰 Service Packages

You can customize the packages displayed in the Services section.

```js
const SERVICES_PACKAGES = [
  {
    label: "Lite",
    volume: "10 GB",
    days: 30,
    price: 170000
  },
  {
    label: "Plus",
    volume: "20 GB",
    days: 30,
    price: 300000,
    popular: true
  },
  {
    label: "Pro",
    volume: "30 GB",
    days: 30,
    price: 450000
  },
  {
    label: "Pro-Plus",
    volume: "40 GB",
    days: 30,
    price: 600000
  }
];
```

Available properties:

| Property  | Description                  |
| --------- | ---------------------------- |
| `label`   | Package name                 |
| `volume`  | Traffic volume               |
| `days`    | Subscription duration        |
| `price`   | Package price                |
| `popular` | Marks the package as popular |

To disable the Services section:

```js
const ENABLE_SERVICES_TAB = false;
```

---

# 📰 News & Announcements

News can be managed using the `STATIC_NEWS` array:

```js
const STATIC_NEWS = [
  {
    title: "New Server Available",
    body: "A new server has been added to the network.",
    date: "2026-08-01"
  },
  {
    title: "Service Update",
    body: "Network performance has been improved.",
    date: "2026-08-05"
  }
];
```

The current implementation uses static news.

It can be connected to an API or backend in the future.

---

# 🎨 Customization

### 🌙 Dark / Light Mode

Users can switch between Dark and Light mode using the theme button.

The selected theme is stored in:

```text
localStorage
```

---

### 🎨 Logo

To replace the default logo, find:

```html
<div class="brand-mark">
```

inside `panel.html` and replace the default SVG with your own logo.

---

### 🔤 Font

The template uses **Vazirmatn** for Persian text and system fonts for English.

---

# 🌐 Language Switching

The template supports:

* 🇮🇷 Persian
* 🇬🇧 English

Users can switch languages directly from the Header.

The following elements automatically adapt to the selected language:

* Text
* Numbers
* Dates
* Units
* Navigation
* Subscription information
* Services

---

# 📱 PWA Support

The template is ready to be used as a **Progressive Web App**.

### Android

If the browser supports:

```text
beforeinstallprompt
```

users can install the panel directly.

Alternatively, they can use:

```text
Add to Home Screen
```

### iOS

On iOS, the installation popup provides instructions for adding the panel to the Home Screen.

---

# 📂 Project Structure

Everything is contained in a single file:

```text
panel.html
│
├── HTML
│   └── Panel Structure
│
├── CSS
│   ├── Responsive Design
│   ├── Theme
│   ├── Dark Mode
│   └── Components
│
└── JavaScript
    ├── 3x-UI Data
    ├── Subscription
    ├── Usage
    ├── Configurations
    ├── QR Code
    ├── Language
    ├── Theme
    ├── Services
    ├── News
    └── PWA
```

---

# 🔌 3x-UI Integration

The template uses variables provided by 3x-UI.

For example:

```text
{{ .total }}
{{ .subUrl }}
```

Available variables may vary depending on the 3x-UI version.

> ⚠️ Older versions of 3x-UI may not provide all variables used by the template. In that case, some sections may appear empty, but the template is designed to remain functional.

---

# 📅 Date & Number Formatting

For correct date and number formatting, make sure the relevant Datepicker and date configuration in 3x-UI are properly configured.

---

# ⚡ Performance

The template is designed to be lightweight and fast.

It does not require:

* React
* Vue
* Angular
* Bootstrap
* jQuery

It uses only:

```text
HTML
CSS
Vanilla JavaScript
```

---

# 🤝 Contributing

Pull Requests and Issues are welcome.

If you find a bug or have an improvement:

1. Open an Issue.
2. Describe the problem or suggestion.
3. Submit a Pull Request if you have a solution.

---

# 🐛 Bug Reports

When reporting an issue, please provide:

* 3x-UI version
* Browser and version
* Operating system
* Screenshot
* Browser console errors
* Relevant configuration

---

# 📜 License

This project is released under the **MIT License**.

You are free to use, modify, and distribute the project for personal or commercial purposes.

See the `LICENSE` file for the full license text.

---

<p align="center">

🇬🇧 **[Back to Top](#-vpn-subscription-panel--3x-ui-template)**

</p>
