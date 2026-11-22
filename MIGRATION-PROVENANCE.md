# منشأ مهاجرت و تضمین عدم گم‌شدن اطلاعات — 2026-11-22

## 1. Source snapshot: verified

- **Source repository (historical):** [DJMRN-Freelance-Operations](https://github.com/mohammadrezanabizadeh41-png/DJMRN-Freelance-Operations)
- **Model-specific branch:** `project/light-sites-m01-vanilla-20261121`
- **Pinned complete-source commit:** `509401524d3d6dd388fe14a38060d1f652181344`
- **Former subtree:** `10-chatgpt-light-sites/`
- **Source migration method:** `git archive HEAD:10-chatgpt-light-sites` از Git object tree، نه کپی صرف از Sparse Checkout.
- **Pre-edit reconciliation:** **۷۷/۷۷ فایل tracked با Git blob SHA-1 عیناً تطبیق داده شدند.** فایل‌ها پیش از افزودن wrapper جدید، دقیقاً با snapshot منبع برابر بودند.
- **Special original model:** `models/M01-vanilla-multilingual/` شامل کد HTML/CSS/JS، اسناد S01–S12، research، تصاویر SVG، QA/tests، محتوای ۵زبانه و مراحل I/P/T است.
- **Secondary old-parent branch:** `project/chatgpt-light-sites-20261121`، ref `b6d7079592db7beb80179b00bcb0a09d93f6cb17`. این شاخه **دو commit منحصر** داشت و پژوهش S03 نسخهٔ جدید `01-PROFESSIONAL-STAGES.md` (blob `e5fd87d78a996715ee4848f2280f73763d1b8dc1`) را نگه می‌داشت. نسخهٔ آن به این مخزن منتقل شد؛ دادهٔ S03 در نسخهٔ M01 وجود نداشت.
- **Parent checklist conflict:** `05-MODEL-BUILD-CHECKLIST.md` در شاخهٔ مادر هنوز S03/«ساخته‌نشده» را می‌گفت؛ شاخهٔ M01 توضیح محدودهٔ جدیدتر داشت اما شواهد S12 آن در ردیف اصلی به‌روز نشده بود. **ردیف M01 در این مخزن با وضعیت واقعی DEMO S12 تصحیح شده** و S03 تاریخی به سند مراحل وصل است. هیچ کدام به‌اشتباه DONE نیست.
- **New skeleton only:** برای `M02–M22` **۲۱ پوشهٔ READMEِ NOT STARTED** ایجاد شد. این پوشه‌ها clone یا اجرای فنی ندارند.
- **New M01 planning-only document:** `models/M01-vanilla-multilingual/06-REBUILD-MASTER-ROADMAP-PROPOSAL.md` پیشنهاد هدف‌محور، **نه ادعای اجرای مراحل** است.

## 2. Authority / history boundary

- **New source of truth (upon verified publication):** [DJMRN-ChatGPT-Website-Models](https://github.com/mohammadrezanabizadeh41-png/DJMRN-ChatGPT-Website-Models).
- **Old branch and commits:** remain intact for audit and diff. Previous independent 3D/Codex/Fernhollow source in `09-self-marketing-website/` is **not part of the migration**.
- **No force push, history rewriting, source deletion, paid provider, account credential, mass access changes, production deploy or model status inflation**.
- **Public-source scope:** only content already public in GitHub + documentation newly written for this public site-building lab. No PC-only archives, private raw vendor media, session data or secrets.

## 3. Traceability and validation contract

For final acceptance record:
- `SOURCE_COMMIT`, `SOURCE_TREE`, original 77 Git blob hashes, `DEST_COMMIT`, `DEST_TREE`.
- Count and inspect `models/M01-vanilla-multilingual/site/{fa,en,ar,tr,de}`, `tools/REGISTRY.md`, 21 model stubs, new roadmap.
- Execute local `node --test tests/*.test.mjs` inside M01 without external services; verify no code/assets lost.
- Verify public GitHub Raw/tree matches local generated Git tree, and keep old source unchanged.

**Status meaning:** migration PASS is about *content*, not execution of ۲۲ models or delivery of the real production website.

## 4. Post-publication canonical-path clarification (same migration; 2026-11-22)

After the first verified 102-file publication, the M01 `README.md` and `tools/README.md` headers were corrected to refer explicitly to the **new** GitHub repository, its `main` branch and relative paths. This documentation-only patch does not rewrite past source objects, alter M01 runtime, delete old branches, or confer implementation PASS. The machine-readable blob receipt in `provenance/SOURCE-BLOB-RECEIPT.json` is refreshed after the correction to show the additional source-relative README difference. GitHub and laptop trees are verified again after the documentation patch.
