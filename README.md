# 📚 Author Website Template

> **আপনার প্রিয় লেখকের জন্য একটি সম্পূর্ণ ওয়েবসাইট — বিনামূল্যে, ওপেন সোর্স।**
> A complete, free & open-source website for any author — with Android app support.

<p align="center">
  <img src="assets/images/logo.png" alt="শংকর রায়" width="320">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/PHP-8.0+-777BB4?style=flat-square&logo=php&logoColor=white">
  <img src="https://img.shields.io/badge/MySQL-Database-4479A1?style=flat-square&logo=mysql&logoColor=white">
  <img src="https://img.shields.io/badge/Android-APK-3DDC84?style=flat-square&logo=android&logoColor=white">
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square">
  <img src="https://img.shields.io/badge/Free%20Hosting-Compatible-orange?style=flat-square">
</p>

---

## 🤔 এটা কী? | What is this?

এটি একটি **ready-made ওয়েবসাইট টেমপ্লেট** — যেকোনো লেখকের জন্য।  
আপনি যদি কোনো লেখকের বই, জীবনী, এবং রচনাসমগ্র অনলাইনে সংরক্ষণ করতে চান — এই টেমপ্লেট ব্যবহার করে মাত্র কয়েক ঘণ্টায় একটি সম্পূর্ণ ওয়েবসাইট তৈরি করতে পারবেন।

This is a **ready-made website template** for any author's archive.  
If you want to put an author's books, biography, and writings online — use this template and have a full website running in a few hours. No coding experience needed for basic setup.

**Originally built for** → [Sankar Ray](https://sankarray.com) — Bengali author archive.

---

## 🎯 কীসের জন্য? | What is it for?

- 📖 কোনো লেখকের **সব বই একসাথে** রাখতে
- 🔍 বই **খোঁজার সুবিধা** (সার্চ + ক্যাটাগরি)
- 📱 **Android অ্যাপ** বানাতে (Capacitor দিয়ে)
- 🪪 **SmartCard সদস্যপদ** পরিচালনা করতে
- 🆓 **বিনামূল্যে হোস্টিং**-এ চালাতে (InfinityFree, 000webhost)

---

## ✨ Features

| Feature | Details |
|---|---|
| 📚 Book Archive | Search, filter by category, view count |
| 👤 Author Page | Photo, bio, birth/death year |
| 🪪 Membership | SmartCard registration system |
| 📱 Android APK | Capacitor — build from CMD, no Android Studio |
| 🌐 Bilingual | Bengali + English built-in |
| 🎨 Customizable | Colors, author name, bio — all in one config file |
| 🆓 Free Hosting | Works on InfinityFree and similar |
| 🔒 Secure | Credentials never exposed in code |

---

## 📸 Preview

> Screenshots coming soon! To add your own:
> 1. Take a screenshot of your running site
> 2. Upload to `docs/screenshots/`
> 3. Replace this section

```
Homepage → Book listing → Single book → About author
```

*Star ⭐ this repo and we'll add live demo screenshots soon!*

---

## 🚀 How to Use — ৩টি সহজ ধাপ

### ধাপ ১ — ডাউনলোড করুন

```bash
git clone https://github.com/YOUR_USERNAME/author-website-template.git
```

অথবা উপরে **"Code → Download ZIP"** বাটনে ক্লিক করুন।

---

### ধাপ ২ — config.php তৈরি করুন

`config.example.php` ফাইলটি কপি করুন → নাম দিন `config.php` → তারপর পূরণ করুন:

```php
// আপনার ডেটাবেস
define('DB_HOST', 'your_host');
define('DB_NAME', 'your_database');
define('DB_USER', 'your_username');
define('DB_PASS', 'your_password');

// লেখকের তথ্য
define('AUTHOR_NAME',    'Sankar Ray');
define('AUTHOR_NAME_BN', 'শংকর রায়');
define('AUTHOR_BIO',     'লেখক পরিচিতি এখানে লিখুন...');

// সাইটের তথ্য
define('SITE_NAME', 'আমার লেখক সাইট');
define('SITE_URL',  'https://yoursite.com');
```

> ⚠️ **`config.php` কখনও GitHub-এ আপলোড করবেন না!** এটি `.gitignore`-এ আছে, তাই স্বয়ংক্রিয়ভাবে সুরক্ষিত।

---

### ধাপ ৩ — হোস্টিং-এ আপলোড করুন

1. আপনার হোস্টিং-এর **phpMyAdmin**-এ `sql/database.sql` ইমপোর্ট করুন
2. **FTP** (FileZilla) দিয়ে সব ফাইল `public_html`-এ আপলোড করুন
3. `config.php` আলাদাভাবে FTP দিয়ে আপলোড করুন
4. সাইট ভিজিট করুন — হয়ে গেল! ✅

---

## 📱 Android APK বানাবেন?

`android/ANDROID_SETUP.md` ফাইলটি দেখুন — সম্পূর্ণ ধাপে ধাপে নির্দেশনা আছে।

Quick steps:
```bash
npm install @capacitor/core @capacitor/cli @capacitor/android
npx cap init "App Name" "com.yourname.app" --web-dir www
npx cap add android
npx cap sync android
cd android && gradlew assembleDebug
```

`android/capacitor.config.json` এ পরিবর্তন করুন:
```json
{
  "appId": "com.yourname.authorsite",
  "appName": "আপনার অ্যাপের নাম",
  "server": { "url": "https://yoursite.com" }
}
```

---

## 📁 ফাইল কাঠামো | File Structure

```
author-website-template/
│
├── 📄 config.example.php   ← এটা কপি করে config.php বানান
├── 📄 index.php            ← হোমপেজ
├── 📄 books.php            ← সব বইয়ের তালিকা
├── 📄 book.php             ← একটি বইয়ের পেজ
├── 📄 about.php            ← লেখক পরিচিতি
│
├── 📂 php/
│   ├── init.php            ← ডেটাবেস সংযোগ
│   ├── header.php          ← শেয়ার্ড হেডার
│   └── footer.php          ← শেয়ার্ড ফুটার
│
├── 📂 assets/
│   ├── css/style.css       ← ডিজাইন
│   ├── js/main.js          ← JavaScript
│   └── images/             ← লেখকের ছবি ইত্যাদি
│
├── 📂 sql/
│   └── database.sql        ← phpMyAdmin-এ ইমপোর্ট করুন
│
├── 📂 android/
│   ├── capacitor.config.json   ← APK কনফিগ
│   └── ANDROID_SETUP.md        ← APK বানানোর গাইড
│
└── 📄 .gitignore           ← config.php সুরক্ষিত রাখে
```

---

## 🎨 কাস্টমাইজেশন

সব কিছু `config.php` থেকে কন্ট্রোল করা যায়:

| কী পরিবর্তন করবেন | কোথায় |
|---|---|
| লেখকের নাম ও পরিচিতি | `config.php` |
| সাইটের রঙ | `config.php` + `assets/css/style.css` |
| লেখকের ছবি | `assets/images/author.jpg` |
| APK নাম | `android/capacitor.config.json` |
| সদস্যপদ চালু/বন্ধ | `config.php` → `ENABLE_MEMBERSHIP` |

---

## 🤝 Contributing — আপনিও অবদান রাখুন!

এই প্রজেক্টে যোগ দিতে স্বাগতম! 🙌

**কীভাবে করবেন:**

1. এই repo-টি **Fork** করুন (উপরে Fork বাটন)
2. আপনার পরিবর্তন করুন
3. **Pull Request** পাঠান

**কী ধরনের সাহায্য দরকার:**
- 🐛 বাগ খুঁজে পেলে → **Issue** খুলুন
- 💡 নতুন আইডিয়া → **Discussion**-এ জানান
- 🌐 অন্য ভাষায় অনুবাদ → Pull Request পাঠান
- 📸 স্ক্রিনশট যোগ করা → `docs/screenshots/` এ রাখুন
- ⭐ ভালো লাগলে → **Star** দিন!

---

## ❓ সমস্যা হচ্ছে?

- `config.php` পাওয়া যাচ্ছে না? → `config.example.php` কপি করুন
- ডেটাবেস সংযোগ ব্যর্থ? → DB_HOST, DB_NAME, DB_USER, DB_PASS চেক করুন
- APK সাদা স্ক্রিন দেখাচ্ছে? → `server.url` আপনার লাইভ সাইটের URL দিন
- অন্য সমস্যা? → **GitHub Issues** খুলুন

---

## 📜 License

MIT License — সম্পূর্ণ বিনামূল্যে ব্যবহার করুন, পরিবর্তন করুন, শেয়ার করুন।

---

<p align="center">
  বাংলা সাহিত্যের জন্য ভালোবাসা দিয়ে তৈরি 💙<br>
  <em>Made with love for Bengali literature</em><br><br>
  <a href="https://sankarray.com">Live Demo →</a>
</p>
