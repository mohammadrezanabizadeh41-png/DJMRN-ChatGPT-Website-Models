# DJMRN — ساخت حرفه‌ای ۲۲ مدل سایت با ChatGPT

**Project ID:** DJMRN-CHATGPT-LIGHT-SITES-001
**Canonical GitHub:** https://github.com/mohammadrezanabizadeh41-png/DJMRN-ChatGPT-Website-Models
**Project boundary:** این مخزن مخصوص پژوهش، انتخاب فناوری، طراحی، کدنویسی و آزمون مدل‌های ساخت سایت `M01` تا `M22` با ChatGPT است. **هیچ ارتباط ساختاری/انتقال مالکیتی با پروژهٔ اصلی و سه‌بعدی `09-self-marketing-website` ندارد.**

## از کجا شروع کنیم؟

1. [مدل‌های ۲۲گانه](04-WEBSITE-BUILD-MODELS.md) — شش خانواده و ۲۲ معماری/استک قابل مقایسه؛ این‌ها ۲۲ سایتِ ازپیش‌ساخته نیستند.
2. [چک‌لیست واحد ۲۲ مدل](05-MODEL-BUILD-CHECKLIST.md) — مرجع وضعیت واقعی انجام هر مدل؛ هر مدل فقط پس از تست و تحویل PASS می‌شود.
3. [مراحل استاندارد ساخت](01-PROFESSIONAL-STAGES.md) — قرارداد عمومی پژوهش تا ساخت و تحویل، شامل S03 تاریخیِ شاخهٔ مادر.
4. [فهرست ابزارها و MCP](tools/REGISTRY.md) و [نگاشت ابزارهای قدیمی](tools/LEGACY-CROSSWALK.md) — انتخاب ابزار موجود، نیاز واقعی، Free-first.
5. [گیت‌های آزمایش و MCP](03-MCP-AND-TEST-GATES.md) — تعریف I/O، قابلیت، ریسک، تست و خطا برای هر خانواده.
6. [M01 — سایت پنج‌زبانهٔ Vanilla](models/M01-vanilla-multilingual/README.md) — نمونهٔ در حال توسعه با کد و پژوهش واقعی، نه پروژهٔ سایت DJMRN.
7. [نقشهٔ راه بازطراحی از صفر برای M01 — پیشنهاد](models/M01-vanilla-multilingual/06-REBUILD-MASTER-ROADMAP-PROPOSAL.md) — نظم جدید براساس محصول کامل، وابستگی‌ها و امنیت؛ **فعلاً PROPOSAL، نه پذیرش/اجرا**.
8. [سند منشأ و صحت مهاجرت](MIGRATION-PROVENANCE.md) — شاخه‌ها، Commitها، فایل‌ها و مرزهای غیرقابل‌انتقال.

## سازمان‌دهی پوشه‌ها

```text
/
├── README.md
├── MIGRATION-PROVENANCE.md
├── 01-PROFESSIONAL-STAGES.md
├── 02-TOOLS-CATALOG.md                # redirect/historical alias
├── 03-MCP-AND-TEST-GATES.md
├── 04-WEBSITE-BUILD-MODELS.md
├── 05-MODEL-BUILD-CHECKLIST.md         # status authority for M01–M22
├── tools/                              # REGISTRY, evidence, crosswalk
└── models/
    ├── M01-vanilla-multilingual/       # research + design + source + tests + QA
    ├── M02/ ... M08/                  # identity placeholders, NOT STARTED
    ├── M09/ ... M17/
    └── M18/ ... M22/
```

**M01 factual status as migrated (2026-11-22):** نمونهٔ آزمایشی NOVA Atelier دارای ۲۰ مسیر HTML پنج‌زبانه از ۳۰ مسیر برنامه، ۶ کیت نمایشی، کد اصلی و تصاویر SVG است؛ **S01–S12 فقط در محدودهٔ DEMO تأیید شده‌اند** و آزمون Node برابر ۴۰/۴۰ بوده است. S12A، S13–S20، S14A، I00–I20، P00–P18 و T31–T55 برای نسخهٔ واقعی هنوز **NOT RUN / NOT IMPLEMENTED** هستند. ثبت‌نام، ایمیل/SMS واقعی، دیتابیس عملیاتی، ورود ادمین و پرداخت واقعی ساخته نشده‌اند. ۲۱ مدل دیگر هنوز کار اجرایی ندارند.

## قرارداد Authority و تغییر

- **این مخزن:** مرجع جدید source، نقشهٔ راه، آزمایش و status همین ۲۲ مدل پس از مهاجرت. کد/تست و مستندات هر مدل فقط در پوشهٔ همان مدل؛ اشتراک mechanism در `tools/` یا کتابخانهٔ مشترک فقط بعد از اثبات نیاز تکرارشونده.
- **Notion:** تصمیمات معماری، تأییدها، علت انتخاب و پیوستگی؛ نه دادهٔ زندهٔ برنامه یا نسخهٔ دوم Git.
- **Runtime/DB آینده:** فقط مرجع واقعی state عملیاتی منتخب هر سایت؛ ChatGPT/MCP یک executor است نه جایگزین سرور.
- **مخزن اصلی قدیمی:** شواهد تاریخی و منبع مهاجرت؛ حذف، بازنویسی یا merge خودکار نمی‌شود.
- **Free-first:** پلن و هزینه، سهمیه، overage، صلاحیت جغرافیایی، امنیت و مجوز باید پیش از اتصال/نصب/مهاجرت/پرداخت بررسی و تأیید شوند؛ UNKNOWN = DENY.
- **حقوق:** فایل‌ها/شات‌های خصوصی سایت‌های مرجع، credentials و promptهای محدود به این مخزن عمومی وارد نمی‌شوند.

**دربارهٔ مرزبندی مهم M01:** مدل فنی M01 از اساس `HTML/CSS/vanilla JS static` است. اگر NOVA Atelier واقعاً ثبت‌نام دوکاناله، DB، سفارش، مدیریت و پرداخت بخواهد، دیگر «M01 به‌تنهایی» نیست؛ باید در گیت معماری بررسی شود که **frontend M01 با یک backend مدل M21/M22** تکمیل شود یا محصول از نظر مدل طبقه‌بندی جدید بگیرد. نام‌گذاری و معماری نباید برای حفظ کار قبلی تحریف شوند.

**Next:** اول مرور و تصویب هدف محصول و نقشهٔ راه پیشنهادی M01؛ بعد مرحلهٔ اجرایی از ابتدا با استفاده از کد موجود به‌عنوان دارایی قابل ارزیابی، نه یک الزام غیرقابل تغییر.
