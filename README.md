# Smart Mobile Solution (SMS) — Website

Official static website for **Smart Mobile Solution (SMS)**, hosted with GitHub Pages.

- **Live website:** https://smartmobilesolution.github.io/sms-tools/
- **Repository:** https://github.com/SmartMobileSolution/sms-tools
- **Default branch:** `main`
- **Support:** help.mobilesolution@gmail.com
- **Last documented:** 23 November 2026

## Website pages

| Section | Path / URL |
|---|---|
| Home | `/` |
| App directory | `/apps/` |
| Pictarow detail | `/apps/pictarow/` |
| Kids Safe detail | `/apps/kids-safe/` |
| App Locker detail | `/apps/app-locker/` |
| Privacy directory | `/privacy/` |
| Contact | `/contact/` |
| Kids Safe Privacy Policy (English) | `/privacy/kids-safe/` |
| Kids Safe Privacy Policy (Vietnamese) | `/privacy/kids-safe/vi/` |
| App Locker Privacy Policy (English) | `/privacy/app-locker/` |
| Pictarow Privacy Policy (English) | `/privacy/pictarow/` |
| Pictarow Terms of Use (English) | `/terms/pictarow/` |

## Published apps

| App | Google Play | Website detail | Privacy Policy |
|---|---|---|---|
| Kids Safe: Parent Control | [Google Play](https://play.google.com/store/apps/details?id=org.app.kidsmode) · package `org.app.kidsmode` | [Kids Safe detail](/apps/kids-safe/) | English and Vietnamese |
| App Locker: Lock Apps | [Google Play](https://play.google.com/store/apps/details?id=org.app.secure.locker) · package `org.app.secure.locker` | [App Locker detail](/apps/app-locker/) | English only |
| Pictarow: Photo to Table | App Store listing not added here | [Pictarow detail](/apps/pictarow/) | [Privacy Policy](/privacy/pictarow/) · [Terms of Use](/terms/pictarow/) |

Google Play URLs were supplied by the site owner. Do not infer or invent additional store links.

## Project structure

```text
.
├── index.html
├── apps/
│   ├── index.html
│   ├── pictarow/
│   │   └── index.html
│   ├── app-locker/
│   │   └── index.html
│   └── kids-safe/
│       └── index.html
├── contact/
│   └── index.html
├── privacy/
│   ├── index.html
│   ├── app-locker/
│   │   └── index.html
│   └── kids-safe/
│       ├── index.html
│       └── vi/
│           └── index.html
├── assets/
│   ├── css/
│   │   └── styles.css
│   ├── js/
│   │   └── site.js
│   └── images/
│       ├── company-logo.png
│       ├── pictarow-icon.webp
│       ├── pictarow/
│       │   └── screenshots/
│       │       └── screen-01.webp … screen-05.webp
│       ├── kids-safe-icon.svg
│       ├── app-locker-icon.webp
│       └── app-locker/
│           └── screenshots/
│               ├── screen-01.webp … screen-05.webp
│               └── (Kids Safe: ../kids-safe/screenshots/screen-01.webp … screen-06.webp)
└── docs/
    └── Website_Handover_Smart_Mobile_Solution.md
```

This is a lightweight static website built with HTML, CSS and JavaScript. There is no documented frontend framework, package manager, or separate build pipeline. GitHub Pages deploys the static site.

## Current implementation notes

- The Home page lists Pictarow, Kids Safe and App Locker using the shared `.app-card` styling. Pictarow shows Android and iOS store CTA placeholders pending public listing URLs; the Android-only Kids Safe and App Locker cards each show a clickable Google Play tile.
- The Apps directory lists Pictarow, Kids Safe and App Locker. All three have dedicated detail pages.
- Pictarow detail is at `/apps/pictarow/`. It uses the approved 1024px Scan to Grid master exported as `assets/images/pictarow-icon.webp`, describes the confirmed product workflow and Free/Premium limits, and links to the existing Privacy Policy and Terms of Use. Google Play and App Store CTA placeholders are visible as “Coming soon” until public listing URLs are supplied.
- Pictarow detail includes a five-image promotional gallery using owner-committed WebP files `assets/images/pictarow/screenshots/screen-01.webp` through `screen-05.webp`. The images are 1320 × 2868 each, use lazy loading, and preserve their complete portrait artwork without cropping.
- App Locker's detail page contains a five-image promotional screenshot gallery. The gallery now uses optimized WebP files `screen-01.webp` through `screen-05.webp` under `assets/images/app-locker/screenshots/`, with lazy loading and responsive columns.
- App Locker's hero icon is displayed directly without an outer decorative card, frame, background panel, or glow layer.
- The Kids Safe and App Locker cards on both Home and the Apps directory use matching compact Google Play tiles that open their supplied Play Store URLs in a new tab. These two apps are Android-only; no App Store CTA is shown. Their detail-page Google Play CTAs remain unchanged.
- Each app has its own Privacy Policy URL. Do not copy one app's policy to another app without verifying that app's actual data practices and SDKs.

## Extending the website

- Keep `/apps/` as the central app directory.
- Give every app a stable lowercase slug, such as `kids-safe`.
- Use a consistent card structure: app name, icon, platform/category, short description, tags, and only the actions/links that exist for that app (Google Play, detail page, Privacy Policy).
- Add `/apps/<app-slug>/` when an app needs its own landing/detail page. Do not create a placeholder page merely because another app has one.
- Add an English Privacy Policy at `/privacy/<app-slug>/`; add `/privacy/<app-slug>/vi/` only when a Vietnamese version is supplied and approved.
- Keep `/privacy/` as the directory linking to each app's available policy language(s).
- As the catalogue grows, consider a central metadata source (for example, `assets/data/apps.json`) and shared templates/partials to reduce duplicated card markup. This is a future improvement, not an existing implementation. Any such change must remain compatible with GitHub Pages.
- Keep English and Vietnamese privacy pages aligned in meaning and navigation. Do not add unconfirmed data collection, processing, SDK, consent, or legal-compliance claims.

## Brand and image assets

- Company logo: `assets/images/company-logo.png`. This is the site owner's original PNG. Use it as-is; do not redraw, crop, recolor, recompress, or convert it. Adjust display size with CSS only.
- Kids Safe icon: `assets/images/kids-safe-icon.svg`. It is used unchanged on the Kids Safe detail page.
- Pictarow icon: `assets/images/pictarow-icon.webp`, a WebP web derivative of the owner-approved 1024×1024 master; the Library master PNG remains the source.
- App Locker icon: `assets/images/app-locker-icon.webp`, used on Home, Apps, the App Locker detail page, and its Privacy Policy.
- App Locker screenshots: five optimized WebP files at `assets/images/app-locker/screenshots/screen-01.webp` through `screen-05.webp`; the App Locker detail gallery references these WebP paths. Kids Safe screenshots: six WebP files at `assets/images/kids-safe/screenshots/screen-01.webp` through `screen-06.webp`. The Kids Safe icon remains `assets/images/kids-safe-icon.svg`.
- Search all HTML, CSS, favicon and JavaScript references before renaming or replacing any asset.

## Local preview

No special build step is required. From the repository root:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000/. When the repository is served beneath a parent directory as `/sms-tools/`, use http://localhost:8000/sms-tools/ instead.

## Repository working rules

The site owner has authorized direct work on `SmartMobileSolution/sms-tools`: edit files and commit/push to `main` when assigned a task.

- Do not merge pull requests or branches.
- Do not change repository settings, GitHub Pages configuration, workflows, branch protection, or other repository configuration unless the owner explicitly authorizes that specific change.
- Read the latest `main` files before editing; never assume previous notes are newer than the repository.
- Preserve unrelated content and assets.
- Use a descriptive commit message and verify the expected branch head before updating it.
- Verify the GitHub Pages workflow and live website before claiming a change is published.

## Change checklist

1. Read the current files on `main` before editing.
2. Identify every page and asset reference affected by the task.
3. Keep unrelated layout, copy and behavior unchanged.
4. Check relative paths at every directory depth, including images, CSS, JavaScript and favicons.
5. Check navigation, Privacy Policy links/language switches, external Google Play links and responsive behavior.
6. Review the diff and ensure no obsolete asset references remain.
7. Commit/push only within the owner's granted scope; never merge or alter repository configuration without explicit instruction.
8. Verify the GitHub Pages deployment and inspect the live page before reporting the change as live.

## Handover

Read **[Website Handover — Smart Mobile Solution (SMS)](docs/Website_Handover_Smart_Mobile_Solution.md)** before making substantial changes or handing the work to another agent. It records the app-specific details, confirmed Kids Safe privacy facts, current website state, asset rules, deployment checkpoint and a ready-to-use onboarding prompt.

This repository and these notes cover the **SMS website only**. They do not transfer or document the Android application source code for Kids Safe or App Locker.


## Store tile presentation

- Google Play and App Store tiles use a leading store icon followed by the store name on one line; no subtitle or arrow is shown.
- Pictarow store tiles remain non-clickable and retain a compact **Coming soon** status until official public listing URLs are supplied.
- Kids Safe and App Locker show only the Google Play tile, with their verified Play Store URLs; both are Android-only.
