# M39 — Micro Frontend

**Status: NOT STARTED.** Owner approved catalog registration on 2026-11-26. Supplementary technical recipe/pattern; may overlap existing models and is not necessarily an independent architecture.

## Scope
رابط ماژولار با ماژول‌های مستقل.

## Candidate implementation / research
single-spa; only if independence proven. [Reference for further research](https://single-spa.js.org/docs/getting-started-overview). No final stack or provider selected; availability, commercial license, free tier/quota and eligibility remain to be verified.

## Acceptance starting point
ترکیب دو ماژول، قرارداد مشترک، شکست مستقل و مقایسه با یک frontend. At the start gate, define real use case and smallest adequate vertical, compare existing models and reuse, verify durable state where required, security, failure/recovery, observability, accessibility, responsive UI, tests and reproducible run/deploy path. No live data, payment, design choice, installation, implementation repository or deployment approved by registration.

## Canonical links
- [Model matrix](../../04-WEBSITE-BUILD-MODELS.md)
- [Single build checklist](../../05-MODEL-BUILD-CHECKLIST.md)
- [Common professional lifecycle](../../01-PROFESSIONAL-STAGES.md)
