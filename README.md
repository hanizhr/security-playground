# Mobile Security Playground 🚀

> یک پروژهٔ عملی برای آنالیز امنیتی اپ‌های اندروید (APK) و داشبورد گزارش‌ساز با **Django + DRF**  
> هدف: تمرین عملی، ساخت نمونه‌کار (portfolio) و تولید گزارش‌های قابل ارائه برای تست نفوذ و آنالیز اپ‌ها.

---

[![Status](https://img.shields.io/badge/status-in_progress-orange)]()
[![Python](https://img.shields.io/badge/python-3.10+-blue)]()
[![Django](https://img.shields.io/badge/django-4.x-green)]()
[![License](https://img.shields.io/badge/license-MIT-lightgrey)]()

---

## 🔎 خلاصهٔ پروژه
این ریپو دو بخش اصلی دارد:
1. **اسکریپت/ابزارِ استخراج ویژگی‌ها** (`scripts/extractor.py`) — دِکامپایل APK، استخراج permissions، strings حساس، و تولید JSON خروجی.  
2. **وب‌اپ Django + DRF** — API آپلود APK، اجرای آنالیز به‌صورت job، نمایش نتایج در داشبورد، و تولید گزارش PDF/HTML.

مناسب برای: مهندسین امنیت موبایل، تسترها، و هر کسی که می‌خواهد نمونه‌کار عملی در حوزهٔ Mobile App Security بسازد.

---

## ✨ ویژگی‌ها
- دِکامپایل خودکار APK با `apktool` و `jadx` (یا fallback به JADX-CLI).  
- استخراج permissions، hardcoded strings، activity/receiver/service list.  
- آنالیز داینامیک نمونه با پشتیبانی از Frida (اسکریپت نمونه).  
- صف‌بندی و اجرای آنالیزها (worker ساده یا Celery).  
- REST API برای آپلود، مشاهده وضعیت، و دریافت گزارش.  
- تولید گزارش PDF/HTML قابل دانلود.  
- Dockerized برای توسعه و استقرار ساده.

---

## 🧭 معماری خلاصه
- `scripts/` — اسکریپت‌های آنالیز و استخراج (پایتون).  
- `django_app/` — پروژهٔ Django + DRF، مدل‌ها، viewها، templates.  
- `workers/` — کدِ worker یا integration با Celery.  
- `reports/` — نمونهٔ گزارش‌های تولیدشده (HTML/PDF/JSON).  
- `docs/` — یادداشت‌ها، چک‌لیست‌های OWASP، و گزارش‌های نمونه.

---

## ⚙️ پیش‌نیازها
- Python 3.10+  
- Docker & docker-compose (برای استقرار توصیه می‌شود)  
- Java (برای jadx)  
- apktool, jadx, Frida و Android emulator (برای آنالیز داینامیک)  
- Git

---

## 🛠️ راه‌اندازی محلی (Quick Start)

### روش A — سریع با Docker (توصیه شده)
1. ریپو را کلون کن:
```bash
git clone https://github.com/<your-username>/mobile-security-playground.git
cd mobile-security-playground
```
