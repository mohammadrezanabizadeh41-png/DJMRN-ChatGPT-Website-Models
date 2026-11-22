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


## 5. Separate execution authority for M01 — 2026-11-22

- **Owner-requested split:** parent repository stays research/taxonomy/tools/master status registry for M01–M22. Each future implemented model receives its own implementation repository at activation, not 22 speculative repositories.
- **M01 canonical implementation:** [DJMRN-ChatGPT-Website-M01](https://github.com/mohammadrezanabizadeh41-png/DJMRN-ChatGPT-Website-M01) — private, own `main`, current README revision at commit `d35f45d9507c2290a4fd3f45e8b8967b404cfad4`.
- **Immutable source snapshot:** original parent `main` commit `d17c335a19c5b1914b643bf72caa8efd75456e46`; M01 source subtree `models/M01-vanilla-multilingual/` (69 blobs). Historical evidence in previous commits and in `provenance/SOURCE-BLOB-RECEIPT.json` remains historical and must not be treated as current live M01 implementation.
- **Migration check:** 69/69 source paths exist in child repo root, 63 unchanged blob hashes, 6 initially adapted docs; child root README subsequently reconciled to the latest source clarification. No site runtime code changed in extraction.
- **Parent after extraction:** Only a forwarding M01 README and references in this parent; 21 NOT STARTED model stubs remain. No unrelated 3D DJMRN / `09-self-marketing-website` code transferred.
- **Restoration:** historical original tree is available at the immutable source commit above; no forced push or Git history rewrite.
- **Status unchanged:** M01 is incomplete DEMO; M02–M22 NOT STARTED. Real accounts/orders/payments/deploy are not implemented or approved by this split.

## 6. Completed source/evidence boundary verification — 2026-11-22

- The private standalone M01 implementation repository is the only current code/test owner; this parent is solely research/taxonomy/tools/master 22-model checklist. Old Freelance branches and original parent pre-extraction commit remain historical recovery, not write targets.
- Old two-branch merge audited: all **nine** original common research files exist in parent (some explicitly modernized); all **68** original M01-specific files exist in child, with execution HTML/CSS/JS/SVG/tests byte-identical and six initial docs adapted for correct links. GitHub M01 post-migration files include separate new QA/preflight guards.
- Read-only functional verification of actual extracted M01 site: **45/45 Node tests** and **133/133 browser route/device/no-JS/security checks** PASS. Production auth, SMS, admin roles, payments, hosting remain not built.
- Private [historical QA archive](https://github.com/mohammadrezanabizadeh41-png/DJMRN-ChatGPT-Website-M01/tree/main/qa-evidence) holds 137 local QA source/evidence files and two OFL/font files as one whole-ZIP byte stream in 16 Git blobs with manifest; 16/16 blob SHA + 139/139 file SHA-256 + whole ZIP SHA verified. External reference screenshots stay internal research only. No original local files were deleted.
- **Remaining native laptop Git gate:** the laptop has the private M01 ZIP snapshot and isolated test artifacts but no Git credential authorized for native private-repo clone/push. The repository guard intentionally rejects a ZIP snapshot as a writable clone. Separate user-authorized official Git sign-in is required to enable normal laptop `git push`. This gate does not prevent the already connected GitHub tool from maintaining canonical M01 source.
- Historical local sibling workspaces remain unchanged until safe provenance-aware transition, protecting potentially running preview servers. Parent working tree status is not an authority if its branch lags `origin/main`.
