# M01 — نقشهٔ راه حرفه‌ای بازطراحی از ابتدا برای یک سایت واقعاً کاربردی

**Status:** `PROPOSAL / OWNER REVIEW PENDING / ALL R00–R25 UNCHECKED`  
**Date:** 2026-11-22  
**Project:** DJMRN ChatGPT Website Models → M01 (NOVA Atelier prototype)  
**Important:** این پیشنهاد **مسیر M01 را بر اساس هدف محصول و ترتیب علمی وابستگی‌ها بازطراحی می‌کند**، نه براساس اینکه پیش‌تر کدام S/P/I/T انجام شده است. تا تأیید مالک، [03-EXECUTION-ROADMAP.md](03-EXECUTION-ROADMAP.md) و شواهد گذشته دست‌نخورده می‌مانند؛ با تأیید، این سند به مرجع مراحل جدید بدل می‌شود و سند گذشته برچسب HISTORICAL/CROSSWALK می‌گیرد. هیچ مرحلهٔ R پیشاپیش PASS محسوب نمی‌شود.

## 0. تعریف دوبارهٔ موضوع واقعی

هدف مورد بررسی: یک وب‌سایت حرفه‌ای، چندزبانه، دارای خدمات، نمونه‌کارهای شفاف و اصیل، کاتالوگ/محصول، تجربهٔ طراحی ممتاز و واکنش‌گرا، **عضویت واقعی مشتری با تأیید ایمیل و تلفن، شناسهٔ عضویت، سفارش و سابقهٔ قابل پیگیری، درگاه پرداخت قانونی قابل جایگزینی در آینده، ورود و داشبورد مستقل مدیر**. سایت باید از حیث SEO، دسترس‌پذیری، امنیت، حریم خصوصی، پایداری، مدیریت داده، ارائهٔ تجاری و کیفیت بصری واقعاً کارآمد باشد. بخش‌های پژوهشی/نمایشی به‌عنوان منبع شواهد یا نسخهٔ آزمایش حفظ می‌شوند؛ ادعای مشتری، پرداخت یا سرویس واقعی بدون اجرای حقیقی مجاز نیست.

### تصمیم بنیادین معماری (قابل تغییر با شواهد)

**M01 به‌عنوان مدل فنی** HTML/CSS/JS استاتیک تعریف شده است. یک سایت با ثبت‌نام/سفارش/پرداخت واقعی نمی‌تواند فقط frontend استاتیک باشد. دو مسیر مشروع:
- **A: حفظ M01 به‌عنوان نمونهٔ static/DEMO**؛ ساخت یک مدل اجرایی جداگانهٔ M21 یا M22 برای backend و اتصال کنترل‌شدهٔ frontend M01 پس از مقایسه و تأیید. *ترکیب مدل‌ها را به‌صراحت مستند کنیم*.
- **B: بازتعریف استک محصول عملیاتی** و طبقه‌بندی مجدد معماری اگر بنابر شواهد مثلاً Astro/SSR/CMS/ecommerce مناسب‌تر است؛ نگه‌داشتن کد M01 به‌عنوان منبع قابل ارزیابی، نه constraint اجباری.

در هر دو حالت صرفاً **یک DB authoritative**، یک identity authority، مرز مجوز server-side و modular-monolith پیش‌فرض‌اند؛ نه تجمیع بی‌هدف MCP، دیتابیس و سرویس. ابزار حرفه‌ای و نرم‌افزار سنگین در صورت ارزش واقعی مجاز است؛ هدف ~۲GiB RAM آزاد قبل از اجرای بارهای سنگین فقط آماده‌سازی است، نه سقف کیفیت. حق انتخاب نهایی و استقرار نزد مالک است.

## 1. تمام تجربه‌ها و بازیگران هدف (قبل از فناوری)

- **بازدیدکنندهٔ ناشناس:** Home، دسته‌های خدمات، صفحات توضیحی، نمونه‌کارهای مستند با Demo label، مقایسه/جست‌وجوی بسته‌ها، اطلاعات قانونی، تماس و CTA مشخص؛ در دسترس و سریع روی گوشی و دسکتاپ.
- **کاربر تازه‌وارد:** فرم ثبت‌نام قابل فهم → تأیید مالکیت ایمیل با لینک یک‌بارمصرف → تأیید شمارهٔ موبایل با OTP واقعی و محدودیت کوشش/ارسال → صدور `customer_id` داخلی و `membership_code` یکتای غیرمحرمانه → ورود امن. **کد عضویت اعتبارنامهٔ ورود نیست**.
- **عضو فعال:** پروفایل، مدیریت ایمیل/شماره با تأیید مجدد، سفارش جدید با واحد پول واقعی از سرور، مشاهدهٔ سفارش‌های خودش، رسید/تحویل/درخواست بازپرداخت/ارتباط با پشتیبانی؛ غیرعضو checkout واقعی ندارد.
- **مدیر/کارمند:** **ثبت‌نام عمومی ندارد**؛ دعوت مجاز + MFA/passkey، session و role جدا از مشتری؛ کارتابل کاربران، محتوا، سفارش، صورتحساب، پشتیبانی، دسترسی‌های کارکنان و audit؛ هر API کنترل مجوز مستقل دارد.
- **اپراتور سیستم:** deployment، backups، secrets، Incident/alerts، costs، privacy requests، state recovery و rollback؛ نه یک پنل نمایشی.
- **ناظر انسانی:** بررسی ادعاهای محتوایی، طراحی، ترجمه، WCAG، حقوق تصاویر/صدا، امکان تجاری‌سازی و صحت سفارش‌ها.

## 2. مرحله‌بندی تازه؛ به ترتیب ساخت واقعی نه تاریخچهٔ قدیمی

**قاعدهٔ Rxx:** هر مرحله حداقل یک *input مشخص → artifact/real I/O → error paths → tests → evidence Git SHA → decision* دارد. R موفق بعدی تنها پس از prerequisites تأییدشده. R پیش از approval نمی‌تواند DONE باشد.

| گروه | شناسه و خروجی مورد انتظار | گیت عبور و اتصال به مراحل قدیمی |
|---|---|---|
| Discover | **R00 — بازیابی و ممیزی دارایی‌ها/معیارهای محصول** | inventory و rights، ۲۲ مدل/مخزن مستقل، ۷۷ فایل migrate، ابهام‌های source/آزمون. Crosswalk: S01, S02, P00, I00 |
| Discover | **R01 — هدف تجاری، مخاطب، نوع سفارش و jurisdiction** | مشخص‌کردن اینکه کدام کالای دیجیتال یا خدمت واقعاً فروخته می‌شود، صداقت ادعاها، روش تسویه/مقررات، legal region؛ بدون این انتخاب PSP معتبر نیست. S02, P00, I00 |
| Discover | **R02 — مقایسهٔ بازار و مدل‌های واقعی UX/فروشگاهی** | نمونه‌های موفق/ناموفق با provenance، فرصت تمایز، خطر و نیاز کاربر؛ نه کپی template. S03, RQ, B01 |
| Product | **R03 — نیازمندی و شکستن use-case به journeys و معیار پذیرش** | matrix بازدید→خدمت→نمونه→ثبت‌نام→تأیید→سفارش→تحویل؛ مسیر مدیر/بازیابی/اختلال، لیست الزامی و nice-to-have. S02, S05, P00 |
| Product | **R04 — معماری اطلاعات و نقشهٔ صفحات/URL** | Services/Work/Catalog/Account/Admin/Checkout/Legal/Support، navigation، permissions و deep link، بدون route بی‌هدف. S04, S09, P07 |
| Content | **R05 — زبان‌ها و قرارداد ترجمهٔ کل محصول** | fa/ar RTL و en/tr/de LTR، metadata، اعداد/فرمت تاریخ، پیام خطا/OTP/رسید، hreflang canonical، وضعیت review انسانی؛ زبان جدید gate مستقل. S07, S15 |
| Design | **R06 — research و تأیید art direction و brand** | سه کانسپت قابل مقایسه، حقوق تصاویر/فونت/داده، design tokens، تصویرسازی اصیل، بررسی معیارهای حرفه‌ای، owner selection. S03/S06 |
| Design | **R07 — design system کاربردی و اجزای قابل آزمون** | header/footer, typography, cards, forms, nav, drawers/modals, feedback, skeleton/loading, RTL/focus/reduced motion, errors/empty/disabled؛ فریم واقعی موبایل/تبلت/دسکتاپ. S06/S09/S10 |
| Architecture | **R08 — تصمیم استک: Pure M01 یا ترکیب/تغییر مدل** | ADR با مقایسهٔ A/B/C، reversibility، performance/cost/security و حقیقی‌بودن state؛ schema و provider انتخاب نشده قبل از مالک. S04/S05, P01/I04/I07 |
| Architecture | **R09 — مدل داده، مرز domain و کنترل دسترسی** | principal/internal ID, member code, staff permissions, content/price, orders/payments/fulfillment, session, audit; migrations/backups/unique+FK, negative tests. P02, I07/I08, T31–T38 |
| Infra | **R10 — طراحی کامل زیرساخت و free-provider gates** | I00–I20: domain/DNS/TLS/CDN/runtime/DB/Auth/email/SMS/payment/object storage/queue/WAF/logging/backup/CI/geo/billing، role و cost/overage و eligibility VERIFIED. P03, I00–I20, T46–T55 |
| Vertical | **R11 — کوچک‌ترین کار واقعی از مرورگر تا سرور تا DB** | اولین real HTTP request و durable state پس از restart، auth-free fixture، error/rollback، CI؛ local Node/SQLite/mock before cloud. P04, T48 |
| Presentation | **R12 — نمای عمومی، خدمات، نمونه‌ها و کاتالوگ** | ۵ زبان، کاربر واقعی/محتوای اصیل، 6 scopes product/6 services، keyboard/touch/noJS، linked routes، screenshots/HTML/a11y؛ ارزیابی مجدد reuse از S08–S12. S08–S12 |
| Identity | **R13 — عضویت، ایمیل و موبایل واقعیِ مجاز** | unique verified contacts, resend/expire/rate limits, pending→active, immutable internal ID+public member code, real approved delivery only after permission. P05–P07, I09–I11, T31–T33 |
| Identity | **R14 — ورود کاربر، recovery، session و پروفایل** | cookie/session revocation, CSRF, anti-enumeration, reset/reverify, owned data view, cross-account denial and tested accessibility. P08, T34/T36/T41 |
| Admin | **R15 — ورود مستقل مدیر، نقش‌ها و audit** | invite-only, strong MFA/passkey, separate session/domain policy and API authz; customer never admin; role revocation and audited recovery. P09, I12, T35/T42 |
| Commerce | **R16 — کالا/قیمت/موجودی یا ظرفیت خدمات** | data authority, price in minor units, currency, tax policy if applicable, edit/publish flows; separate DEMO_CREDIT from real money. P10, T37 |
| Commerce | **R17 — سبد و سفارش وابسته به حساب** | real server-owned order FK, line snapshot, idempotent create, allowed status transitions, concurrent click/retry and price tamper tests. P11, T38 |
| Payment | **R18 — PSP sandbox و بعد درگاه قانونیِ تصویب‌شده** | merchant eligibility, hosted checkout, signed webhook, fake/duplicate/out-of-order callbacks, refunds/reconciliation; no PAN storage. P12, I13, T39/T52 |
| Operations | **R19 — تحویل، رسید، پشتیبانی و refund** | outbox/retry, durable entitlements, receipt/history, cancellation/refund, contact/support; logs/recovery. P13, I14/I16, T40 |
| Admin | **R20 — داشبورد مدیریت واقعی + CMS محتوا** | permission-scoped customers/orders/payments/content/roles/analytics, masked PII, audit, workflow versioning. S14A local editor remains *different* from live admin. P14, T42 |
| Compliance | **R21 — حریم خصوصی، حقوق و سیاست‌ها** | retention/deletion/export, consent, legal forms, transactional policies, rights, terms/refund, lawful merchant/region, security notifications. P15, I19, T43 |
| Quality | **R22 — QA کل محصول و خودکارسازی امنیت/دسترس‌پذیری** | T01–T55 meaningful tests, mobile real device, zoom 200–400%, screen reader, multi-browser, negative authorization, load/concurrency, lighthouse/field budgets measured. P17, S15–S19 |
| Reliability | **R23 — CI/CD، مانیتور، disaster recovery و cost control** | environment isolation, health/errors, logs without PII, alerts, backup/restore, release gate, hard budget/OTP fraud caps, rollback rehearsal. P16/I05/I06/I08/I17/I18/I20 |
| Release | **R24 — staging، قرارداد پذیرش و تصمیم انتشار** | حقیقی user→email/SMS→membership→order→signed payment→delivery trace؛ test owner review، approval جدا برای launch، بلاک کامل هنگام unknown country/cost. P18/T45/T55 |
| Measure | **R25 — مشاهدهٔ استفاده، رفع مشکلات و توسعهٔ مدل‌ها** | public feedback, usage metrics with consent, reproducible defects, content freshness, next language/service justified by value; expansion only after release. S20 |

### چک‌باکس‌های اجرایی R00–R25 (همه باز؛ با تکمیل در همان ردیف بالا و سند ثبت کن)

- [ ] R00 — source/rights/requirements inventory
- [ ] R01 — business/jurisdiction approval
- [ ] R02 — current market/design evidence
- [ ] R03 — user journeys and acceptance
- [ ] R04 — information architecture
- [ ] R05 — complete i18n contract
- [ ] R06 — original art direction approval
- [ ] R07 — UI/UX design system and accessibility baseline
- [ ] R08 — tech stack/composition ADR
- [ ] R09 — durable data and authorization contract
- [ ] R10 — infrastructure/provider/cost authorization
- [ ] R11 — first real end-to-end local vertical
- [ ] R12 — public pages and catalog
- [ ] R13 — verified dual-channel customer registration
- [ ] R14 — user login/recovery/profile
- [ ] R15 — isolated staff/admin identity and RBAC
- [ ] R16 — operational product/price authority
- [ ] R17 — authenticated cart/order
- [ ] R18 — verified sandbox and lawful PSP adapter
- [ ] R19 — fulfillment, receipts, refunds and support
- [ ] R20 — admin portal and content editor ownership
- [ ] R21 — legal/privacy/data rights
- [ ] R22 — complete automated + real-device QA
- [ ] R23 — runtime observability, backups and CI
- [ ] R24 — staging/launch/owner acceptance
- [ ] R25 — measured improvements, maintained release

## 3. تطبیق بدون قربانی‌کردن برنامه با وضعیت گذشته

| منبع قدیمی | ارزش قابل بازیابی | قاعدهٔ ورود به برنامهٔ جدید |
|---|---|---|
| S01–S12 و خروجی‌های M01 | HTML واقعی در ۵ زبان، طراحی، محتوا، vector assets، تست ۴۰/۴۰، viewport QA | به‌عنوان **candidate reuse** در R05–R07/R12؛ عبور R صرفاً با retest و تأیید معیار امروز |
| S12A و S13–S20 / S14A | contract/QA/DEMO cart/local editor plan | زیر R03/R11/R17/R20/R22، نه زنجیره‌ای که همهٔ product phases را مجبور به تبعیت کند |
| P00–P18 | تحلیل domain عملیاتی: auth, staff, cart, payment, compliance, ops | R01/R08–R24، پوشش کامل بدون طرح backend زودهنگام |
| I00–I20 | ۲۱ dependency زیرساختی و هزینه/خطر/موجودی MCP | R10 و پیاده‌سازی در R11/R23/R24؛ ۲۱ SaaS جدا لازم نیست |
| T01–T55 | آزمون‌های demo + production/infra؛ متناسب با قابلیت | T به stage تست مرتبط bind شود؛ بدون real I/O برچسب PASS ممنوع |
| Parent M01–M22 | طبقه‌بندی **روش ساخت**، نه ۲۲ محصول تکمیل‌شده | R08 تعیین می‌کند M01 خالص کافی است یا composition/reclassification لازم است |

## 4. Definition of Done و ممنوعیت‌های کاذب

- **کد قابل اجرا و state پایدار، نه صرفاً صفحات/اسکرین‌شات**؛ flow واقعی از UI→API→DB→verification→order→payment→delivery با دادهٔ تست و trace قابل بازتولید.
- **قابلیت مستقل مدیر:** login/recovery/MFA/roles/audit، بدون API مشترکِ آزاد با customer.
- **دسترسی واقعی بدون دورزدن قانون:** HTTPS end-to-end، دامنه/DNS معتبر، region/merchant/sender eligibility، cost free-first/overage cap، restore rehearsal و permission minimum.
- **کیفیت حرفه‌ای بدون بهانهٔ محدودیت RAM:** ابزار سطح حرفه‌ای هنگام فایدهٔ واقعی با مدیریت منابع؛ responsive, accessible, performant, SEO/indexability, visual identity original, localization.
- **مراقبت حقوقی:** assetهای proprietary سایت مرجعِ 09 یا Flower Valley وارد M01 نمی‌شوند؛ تنها patternهای مجاز و اصیل پس از تأیید انتقال‌اند.
- **مرز هزینه/تأیید:** نصب/اتصال جدید، پرداخت، فعال‌سازی Auth/SMS/PSP، deployment عمومی، migration و تغییر مجوز حساس نیازمند proposal + approval صریح؛ هزینهٔ ناشناخته DENY.
- **ثبت متمرکز:** پس از تصویب فقط یک CURRENT برای roadmap M01؛ legacy `03` historical evidence/crosswalk، نقشهٔ ۲۲ مدل والد مستقل، Notion rationale و GitHub source/tests.
- **شرط پذیرش این پیشنهاد:** مالک نام/هدف/دامنه، ارتباط M01 با M21/M22 و tradeoffهای نسخهٔ static vs real را تأیید کند. تا آن زمان هیچ R مرحله‌ای تیک نمی‌خورد و تصمیم استک/سرویس قطعی نیست.

## 5. Next concrete action

**R00 → R01 → R03 → R08** ابتدا تصمیم هدف و مدل اجرای واقعی؛ می‌توان پژوهش R02/R06 را موازیِ محدود پیش برد. اولین پیاده‌سازی R11 باید real state محلی را اثبات کند و همان زمان تصمیم بگیرد کدام بخش از نسخهٔ S01–S12 بازاستفاده شود. الزام به ادامهٔ S13 فقط به این دلیل که S12 اجرا شده **حذف می‌شود**.

**Sources (historical/canonical evidence):** [03 legacy roadmap](03-EXECUTION-ROADMAP.md), [04 i18n & security contracts](04-I18N-SEO-COMMERCE-SECURITY.md), [05 QA/T01–T55](05-QA-AND-HANDOFF.md), [parent 22-model taxonomy](../../04-WEBSITE-BUILD-MODELS.md), [migration provenance](../../MIGRATION-PROVENANCE.md), OWASP ASVS 5, NIST 800-63B, W3C WCAG 2.2 and provider official docs linked in the legacy roadmap.
