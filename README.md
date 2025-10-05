
---

### ✅ نسخهٔ اصلاح‌شده و نهایی (کامل و آمادهٔ استفاده در GitHub)

<div dir="rtl" align="right">

# Git & GitHub از صفر تا پیشرفته — راهنمای عملی قدم‌به‌قدم

این ریپوزیتوری یک دورهٔ کاملاً عملی برای یادگیری **Git** و **GitHub** است؛ از نصب و راه‌اندازی تا شاخه‌بندی حرفه‌ای، رفع تعارض (merge conflict)، کار با `rebase`، امضای کامیت‌ها، هوک‌ها، و حتی CI/CD با GitHub Actions.  
هدف ما: **کسی که هیچ آشنایی با گیت ندارد** بتواند گام‌به‌گام به سطح حرفه‌ای برسد.

---

## 👥 این ریپو برای چه کسانی است؟
- 🧩 **مبتدی‌ها:** آشنایی صفر تا شروع اولین پروژه و اولین push به GitHub  
- ⚙️ **توسعه‌دهندگان در حال پیشرفت:** شاخه‌بندی اصولی، PR، rebase، stash، reset/revert  
- 🧑‍💻 **تیم‌ها:** جریان کار (workflow) استاندارد، قوانین شاخه‌ها، CI/CD سبک  

---

## 🧠 چه چیزهایی یاد می‌گیری؟
- نصب Git در Windows, macOS, Linux و پیکربندی اولیه (`user.name`, `user.email`)  
- ساخت کلید **SSH** و اتصال امن به GitHub  
- چرخهٔ کاری پایه: `status → add → commit → push → pull`  
- **Branching** حرفه‌ای: ساخت/سوئیچ، `merge` و `rebase`، حل conflict  
- تاریخچه و اشکال‌زدایی: `log`, `diff`, `blame`, `bisect`, `reflog`  
- مدیریت نسخه‌ها: `tag`  
- فایل‌های مهم: `.gitignore`، **Git LFS**، **submodule**  
- امنیت و امضا: **GPG/SSH signing**  
- **Hooks** محلی (pre-commit) و **GitHub Actions** برای CI ساده  

---

## 🧰 پیش‌نیازها
- یک کامپیوتر با دسترسی ترمینال یا پاورشِل  
- اکانت GitHub  

> اگر هیچ چیز از ترمینال نمی‌دانید، نگران نباشید — در هر درس دستورات با توضیح فارسی و مثال واقعی آمده است.

---

## ⚡ شروع سریع (Quick Start)

1️⃣ بررسی نصب گیت:
```bash
git --version
````

اگر نصب نبود، به درس [`01-install`](./01-install/01-Install.md) مراجعه کنید.

2️⃣ کلون کردن همین ریپو (اختیاری):

```bash
git clone <ssh-or-https-url>
cd <repo-folder>
```

3️⃣ مسیر یادگیری را به ترتیب دنبال کنید (از `01-install` شروع کنید).

---

## 📁 ساختار پوشه‌ها

<div dir="ltr" align="left">

```
/
├── README.md                # معرفی کلی و راهنمای اصلی دوره Git & GitHub
│
├── 01-install/              # نصب و پیکربندی Git در Windows, macOS, Linux + تنظیم user.name و user.email
│   └── 01-Install.md
│
├── 02-basics/               # مفاهیم پایه: init, add, commit, status, log, diff, push, pull, clone
│   └── 02-Basics.md
│
├── 03-ssh/                  # ساخت SSH Key، اتصال امن به GitHub و تست ارتباط
│   └── 03-ssh.md
│
├── 04-branches/             # شاخه‌ها: branch، checkout/switch، merge، rebase و حل تعارض‌ها (conflicts)
│   └── 04-branches.md
│
├── 05-advanced/             # دستورات پیشرفته: stash، reset، revert، cherry-pick، bisect، reflog، tag، submodule، LFS، GPG
│   └── 05-Advanced.md
│
├── 06-ci-cd/                # آموزش GitHub Actions (ایجاد CI ساده برای تست و Build خودکار)
│   └── 06-ci_cd.md
│
└── LICENSE                  # مجوز MIT برای استفاده آزاد و قانونی از محتوای پروژه
```

</div>

---

## 🧭 سرفصل‌ها (لینک مستقیم به هر درس)

| شماره | عنوان درس                      | لینک                                                       |
| ----- | ------------------------------ | ---------------------------------------------------------- |
| 1️⃣   | نصب و پیکربندی Git             | [01-install/01-Install.md](./01-install/01-Install.md)     |
| 2️⃣   | مفاهیم و دستورات پایه          | [02-basics/02-Basics.md](./02-basics/02-Basics.md)         |
| 3️⃣   | ساخت SSH Key و اتصال به GitHub | [03-ssh/03-ssh.md](./03-ssh/03-ssh.md)                     |
| 4️⃣   | شاخه‌ها، Merge و Rebase        | [04-branches/04-branches.md](./04-branches/04-branches.md) |
| 5️⃣   | دستورات پیشرفته Git            | [05-advanced/05-Advanced.md](./05-advanced/05-Advanced.md) |
| 6️⃣   | CI/CD با GitHub Actions        | [06-ci-cd/06-ci_cd.md](./06-ci-cd/06-ci_cd.md)             |
| 💡    | برگه‌های خلاصه Git             | [cheatsheets/](./cheatsheets/)                             |

---

## 🧩 نحوه استفاده

* هر پوشه یک **درس مستقل** است.
* داخل هر فایل `.md` موارد زیر را خواهید دید:

  * توضیح ساده + مفهوم اصلی
  * دستورها با کاربرد و مثال عملی
  * خطاهای رایج و راه‌حل‌ها
  * تمرین برای تثبیت یادگیری

> ترتیب را رعایت کنید؛ از `01-install` شروع کنید و مرحله‌به‌مرحله جلو بروید.

اگر فقط می‌خواهید مرور سریع داشته باشید، به [cheatsheets/](./cheatsheets/) سر بزنید.

---

## 🤝 مشارکت (Contribution)

پیشنهاد، اصلاح یا پرسش دارید؟

1. ریپو را **Fork** کنید
2. شاخه بسازید:

   ```bash
   git checkout -b feature/my-topic
   ```
3. تغییرات را Commit/Push کنید
4. **Pull Request** بفرستید ✅

---

## 💬 بازخورد

اگر جایی مبهم بود یا نیاز به مثال بیشتر داشتید،
Issue باز کنید — هدف ما ساختن یک منبع **استاندارد، فارسی و کاربردی** برای یادگیری Git/GitHub است.

</div>
```
