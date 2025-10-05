
---
<div dir="rtl" align="right">

# 🤖 درس ۶ — خودکارسازی با GitHub Actions (CI/CD)
---
## 🎯 هدف درس
در این درس یاد می‌گیری:
- CI/CD یعنی چی  
- GitHub Actions چیه و چه کاربردی داره  
- چطور workflow بنویسی که با هر push، پروژه‌ت تست و build بشه  
- چطور خطاهای CI رو تحلیل و رفع کنی  

---

## 🧠 مفهوم CI/CD

🔹 **CI (Continuous Integration)** یعنی:  
هر بار که کد جدید به مخزن push می‌کنی، به‌صورت خودکار تست‌ها و build پروژه اجرا می‌شن تا مطمئن بشی هیچ چیز خراب نشده.

🔹 **CD (Continuous Deployment / Delivery)** یعنی:  
اگر همه چیز درست بود، نسخه جدید پروژه به‌صورت خودکار روی سرور یا محیط واقعی منتشر بشه.

🧩 مثال ساده:
وقتی یه نفر Pull Request می‌فرسته، GitHub خودش کد رو build و تست می‌کنه تا قبل از merge مطمئن بشی همه چیز درسته ✅

---

## ⚙️ آشنایی با GitHub Actions

GitHub Actions بخشی از خود GitHub هست که بهت اجازه می‌ده با فایل‌های YAML عملیات خودکار بسازی.

📁 مسیر فایل‌ها:  
تمام workflowها داخل پوشه `.github/workflows/` ذخیره می‌شن.

---

## 🧱 گام ۱ — ساخت پوشه و فایل Workflow

در ریشه‌ی پروژه:
```bash
mkdir -p .github/workflows
touch .github/workflows/ci.yml
````

---

## 🧩 گام ۲ — نوشتن اولین workflow

فایل `.github/workflows/ci.yml` رو باز کن و بنویس:

```yaml
name: CI

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: 📥 دریافت سورس کد
        uses: actions/checkout@v4

      - name: ⚙️ نصب Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'

      - name: 📦 نصب وابستگی‌ها
        run: npm ci

      - name: 🧪 اجرای تست‌ها
        run: npm test
```

---

## 🔍 توضیح خط‌به‌خط فایل بالا

| بخش               | معنی                                           |
| ----------------- | ---------------------------------------------- |
| `name`            | اسم workflow (در صفحه Actions نمایش داده میشه) |
| `on.push`         | اجرای خودکار بعد از هر push روی شاخه main      |
| `on.pull_request` | اجرای خودکار هنگام باز شدن PR                  |
| `jobs.build`      | تعریف یک job (کار) با نام build                |
| `runs-on`         | سیستم عامل مجازی (مثلاً ubuntu)                |
| `steps`           | لیست گام‌هایی که باید انجام بشن                |
| `uses`            | استفاده از اکشن آماده (checkout, setup-node)   |
| `run`             | اجرای دستور دستی در ترمینال                    |

---

## 🧠 مفاهیم کلیدی در Actions

### 🔹 Jobs

هر job در یک محیط جدا (virtual machine) اجرا میشه.
می‌تونی چند job تعریف کنی مثلاً:

* یکی برای تست‌ها
* یکی برای build
* یکی برای deployment

### 🔹 Steps

هر job شامل چند step هست (مثل مراحل خط فرمان).

### 🔹 Actions

Actionها می‌تونن از Marketplace آماده گرفته بشن (مثل پلاگین‌ها).
مثلاً:

```yaml
uses: actions/setup-python@v5
```

### 🔹 Runs-on

تعیین می‌کنه workflow روی چه محیطی اجرا بشه:
`ubuntu-latest`, `windows-latest`, یا `macos-latest`

---

## ⚡ گام ۳ — مشاهده نتیجه در GitHub

1️⃣ تغییرات رو commit و push کن:

```bash
git add .github/workflows/ci.yml
git commit -m "افزودن GitHub Actions برای تست خودکار"
git push
```

2️⃣ در صفحه ریپوزیتوری برو به تب **Actions**
می‌بینی که workflow ات شروع شده 👀

3️⃣ روی workflow کلیک کن تا مراحل اجرای تست‌ها رو ببینی.
اگر همه سبز بود ✅ یعنی CI درست کار می‌کنه.

---

## 🧪 گام ۴ — تمرین: افزودن linting

می‌تونی گام جدیدی برای بررسی استایل کد اضافه کنی:

```yaml
- name: ✨ اجرای ESLint
  run: npm run lint
```

حالا هر بار کد جدید push بشه، ESLint هم خودکار اجرا میشه و اگه خطایی داشت، workflow fail میشه 🚫

---

## 🧩 گام ۵ — مثال حرفه‌ای‌تر (چند Job موازی)

```yaml
name: Build & Test

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: npm ci
      - run: npm test

  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: npm ci
      - run: npm run build
```

دو job موازی اجرا می‌شن: یکی تست، یکی build 🔄

---

## 💡 نکات کاربردی

✅ اگر فایل `ci.yml` درست نوشته شده باشه، GitHub خودش به‌صورت خودکار اونو شناسایی و اجرا می‌کنه.

✅ با بخش **Marketplace** در [GitHub Actions](https://github.com/marketplace?type=actions) می‌تونی اکشن‌های آماده زیادی پیدا کنی (مثل deploy به Vercel یا Firebase).

✅ می‌تونی workflowهای دستی هم بسازی که فقط با دکمه “Run Workflow” اجرا می‌شن.

---

## 🧾 خلاصه (Cheat Sheet)

| دستور / فایل                  | توضیح                   |
| ----------------------------- | ----------------------- |
| `.github/workflows/ci.yml`    | مسیر فایل اصلی workflow |
| `on.push`                     | اجرا هنگام push         |
| `on.pull_request`             | اجرا هنگام PR           |
| `runs-on: ubuntu-latest`      | محیط اجرای workflow     |
| `uses: actions/checkout@v4`   | گرفتن سورس کد پروژه     |
| `uses: actions/setup-node@v3` | نصب Node.js             |
| `run: npm test`               | اجرای تست‌ها            |

---

## 🧪 تمرین درس ۶

1️⃣ یک فایل workflow به نام `ci.yml` بساز.

2️⃣ دستورهای checkout، setup-node و npm test رو داخلش بنویس.

3️⃣ فایل رو commit و push کن.

4️⃣ نتیجه اجرای workflow رو در تب Actions ببین.

5️⃣ برای تمرین، یک مرحله lint اضافه کن و دوباره push کن.

6️⃣ در فایل `lesson6-ci.txt` بنویس workflowت چند مرحله داره و نتیجه‌اش چی بود.

---
