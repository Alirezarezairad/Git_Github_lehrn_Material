<div dir="rtl" align="right">

# Git & GitHub از صفر تا پیشرفته — راهنمای عملی قدم‌به‌قدم

این ریپوزیتوری یک دورهٔ کاملاً عملی برای یادگیری **Git** و **GitHub** است؛ از نصب و راه‌اندازی تا شاخه‌بندی حرفه‌ای، رفع تعارض (merge conflict)، کار با `rebase`، امضای کامیت‌ها، هوک‌ها، و حتی CI/CD با GitHub Actions.  
هدف ما: **کسی که هیچ آشنایی با گیت ندارد** بتواند گام‌به‌گام به سطح حرفه‌ای برسد.

---

## این ریپو برای چه کسانی است؟
- مبتدی‌ها: آشنایی صفر تا شروع اولین پروژه و اولین push به GitHub
- توسعه‌دهندگان در حال پیشرفت: شاخه‌بندی اصولی، PR، rebase، stash، reset/revert
- تیم‌ها: جریان کار (workflow) استاندارد، قوانین شاخه‌ها، CI/CD سبک

---

## چه چیزهایی یاد می‌گیری؟
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

## پیش‌نیازها
- یک کامپیوتر با دسترسی ترمینال/پاورشل
- اکانت GitHub

> اگر هیچ چیز از ترمینال نمی‌دانید، نگران نباشید—در هر درس دستورات با توضیح فارسی و مثال واقعی آمده است.

---

## شروع سریع (Quick Start)
1) بررسی نصب گیت:
```bash
git --version
````

اگر نصب نبود، به درس `01-install` مراجعه کنید.

2. کلون کردن همین ریپو (اختیاری):

```bash
git clone <ssh-or-https-url>
cd <repo-folder>
```

3. مسیر یادگیری را به ترتیب دنبال کنید (از `01-install` شروع کنید).

---

## ساختار پوشه‌ها (در حال تکمیل گام‌به‌گام)

<div dir="ltr" align="left">

```

/
├─ README.md              # همین معرفی کلی
├─ 01-install/            # نصب و پیکربندی اولیه Git
├─ 02-basics/             # دستورات پایه: init, add, commit, push, pull, clone, status, log, diff
├─ 03-ssh/                # ساخت SSH key و اتصال به GitHub
├─ 04-branches/           # branch, checkout/switch, merge, rebase، حل conflict
├─ 05-advanced/           # stash, reset, revert, cherry-pick, bisect, reflog, tag, submodule, LFS, GPG
├─ 06-ci-cd/              # نمونهٔ ساده GitHub Actions
└─ cheatsheets/           # برگه‌های خلاصهٔ قابل چاپ
```
</div>
---

## چطور از این ریپو استفاده کنم؟

* هر پوشه یک «درس» است. در هر درس:

  * **توضیح کوتاه** مفهوم
  * **دستورها** + **کاربردشان به زبان ساده**
  * **مثال عملی** مرحله‌به‌مرحله
  * **خطاهای متداول** و روش رفع
  * **تمرین** برای تسلط
* ترتیب را رعایت کنید: از `01-install` شروع کنید و به جلو بروید.
* اگر عجله دارید، به **cheatsheets/** سر بزنید، اما برای یادگیری عمیق توصیه نمی‌شود.

---

## سرفصل‌ها (لینک‌ها پس از تکمیل هر درس فعال می‌شوند)

* [01) نصب Git و پیکربندی اولیه](./01-install/README.md)
* [02) مفاهیم و دستورات پایه](./02-basics/README.md)
* [03) ساخت SSH Key و اتصال به GitHub](./03-ssh/README.md)
* [04) شاخه‌ها، Merge و Rebase](./04-branches/README.md)
* [05) ابزارهای پیشرفته و رفع اشکال](./05-advanced/README.md)
* [06) CI/CD با GitHub Actions](./06-ci-cd/README.md)
* [Cheat Sheets](./cheatsheets/)

---

## مشارکت (Contribution)

پیشنهاد، اصلاح یا پرسش دارید؟

1. ریپو را **Fork** کنید
2. یک شاخه بسازید: `feature/my-topic`
3. تغییرات را Commit/Push کنید
4. **Pull Request** بفرستید



## بازخورد

اگر جایی مبهم بود یا نیاز به مثال بیشتر داشتید، Issue باز کنید. هدف ما یک منبع فارسی و استاندارد برای یادگیری حرفه‌ای Git/GitHub است.

</div>