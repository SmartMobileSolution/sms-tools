# Smart Mobile Solution (SMS) — Website

Official website for **Smart Mobile Solution (SMS)**, hosted with GitHub Pages.

- **Live website:** https://smartmobilesolution.github.io/sms-tools/
- **Repository:** https://github.com/SmartMobileSolution/sms-tools
- **Default branch:** `main`
- **Support:** help.mobilesolution@gmail.com

## Website sections

| Section | Path |
|---|---|
| Home | `/` |
| App directory | `/apps/` |
| Contact | `/contact/` |
| Kids Safe Privacy Policy (English) | `/privacy/kids-safe/` |
| Kids Safe Privacy Policy (Vietnamese) | `/privacy/kids-safe/vi/` |

## Project structure

```text
.
├── index.html
├── apps/
│   └── index.html
├── contact/
│   └── index.html
├── privacy/
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
│       └── kids-safe-icon.svg
└── docs/
    └── Website_Handover_Smart_Mobile_Solution.md
```

This is currently a lightweight static website built with HTML, CSS and JavaScript. Do not assume a frontend framework, package manager, or build pipeline unless one is deliberately introduced and documented.

## Extending the website

The site should remain easy to extend as SMS publishes more apps.

- Keep `/apps/` as the central app directory.
- Give every app a stable lowercase slug, such as `kids-safe`.
- Use a consistent structure for each app card: name, icon, platform, short description, tags, app-page URL and privacy-policy URL.
- Add an app landing page at `/apps/<app-slug>/` when an app needs its own detail page.
- Add the English privacy policy at `/privacy/<app-slug>/` and Vietnamese at `/privacy/<app-slug>/vi/`.
- As the app catalogue grows, prefer a central metadata source (for example, `assets/data/apps.json`) and shared page templates/partials over duplicated card markup. Keep any implementation compatible with the GitHub Pages hosting setup.
- Keep English and Vietnamese privacy pages aligned in meaning and navigation. Do not copy a policy to another app without checking that app's actual data practices and SDKs.

## Brand assets

- Company logo: `assets/images/company-logo.png`. This is the original PNG provided by the site owner. Use it as-is; do not redraw, crop, recolor, recompress, or convert it. Adjust its display size with CSS only.
- Kids Safe icon currently referenced by Home and Apps: `assets/images/kids-safe-icon.svg`. Inspect the actual asset before changing it; do not assume it is the original uploaded PNG.
- Search all HTML, CSS and favicon references before renaming or replacing an image.

## Local preview

No special build step is currently documented. To preview the static files locally, run a simple HTTP server from the repository root, for example:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000/sms-tools/ only if serving the parent directory with the repository nested under that path; otherwise open http://localhost:8000/.

## Change checklist

1. Read the current files on `main` before editing; this repository may have changed since earlier work.
2. Keep unrelated layout, copy and behavior unchanged.
3. Check relative paths at every directory depth, including images, CSS, JavaScript and favicons.
4. Check navigation, privacy language switch links and responsive behavior.
5. Review the diff and ensure no obsolete asset references remain.
6. Commit with a descriptive message. Report changed files and pages that should be checked.
7. Verify the deployed GitHub Pages site before claiming that a live change is visible.

## Handover to another agent

Read **[Website Handover — Smart Mobile Solution (SMS)](docs/Website_Handover_Smart_Mobile_Solution.md)** before making changes. It records the work completed so far, current URLs and files, confirmed Kids Safe policy details, expansion conventions, and a ready-to-use onboarding prompt.

Suggested handover procedure:

1. Attach the handover Markdown file to a new agent conversation.
2. Connect the agent to `SmartMobileSolution/sms-tools` and grant repository access if it needs to edit files.
3. Paste the onboarding prompt from Section 8 of the handover document.
4. Ask the agent to inspect the current `main` branch and confirm the actual repository state before making changes.
5. Give the agent the next concrete website task. Do not include access tokens, passwords, or other secrets in prompts.

## Scope

This repository and these notes cover the **SMS website only**. They do not transfer or document the Android application source code for Kids Safe.
