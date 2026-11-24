# THE CONTROL — Version 1.0

A free, bilingual game development team management dashboard built with HTML, CSS, and vanilla JavaScript. Designed for GitHub Pages and responsive layouts from mobile to desktop.

## Features

- 48 distinct game development Skill profiles with English and Thai names, role descriptions, responsibilities, personality, capabilities, status, and assigned tasks.
- Free Guest mode: no registration; access to Skills 01–24.
- Free Member demo mode: access to Skills 01–48.
- Search, category filters, and status filters for Skills.
- Create, edit, assign, filter, update, and delete tasks.
- Create, edit, view, and delete projects; project progress is calculated from completed tasks.
- English/Thai interface switch.
- Browser `localStorage` persistence for language, package demo settings, Skill status, tasks, and projects.
- Responsive dark dashboard layout.

## Important: local Member demo is not secure authentication

Version 1.0 does not provide an online account system. The Member option is a local demonstration setting, stored in the browser's `localStorage`. It does not verify a user's identity, protect data, synchronize data across devices, or securely restrict access. Do not store sensitive information in this demo.

## Run locally

Keep `index.html`, `style.css`, and `script.js` in the same directory, then open `index.html` in a modern browser. No build step or paid service is required. Google Fonts are an optional external font enhancement; system font fallbacks are included.

## Publish with GitHub Pages

1. Add the four project files to the repository's root directory.
2. In the repository, open **Settings → Pages**.
3. Choose **Deploy from a branch**, select the branch and `/ (root)` folder, then save.
4. Open the published Pages URL after deployment completes.

The app is static and does not require a server, API key, or package installation.

## Data and privacy

App data is saved only in the current browser's `localStorage`. It remains after refresh in that browser, but is not shared across browsers or devices. Clearing browser site data removes it. Avoid using a shared device for private project information.

## Verification notes

This delivery has not been run through browser automation or tested on physical Android, tablet, or desktop devices. Before relying on it, manually verify both package modes, all 48 Skill profiles, filters, language switching, task and project CRUD, refresh persistence, and responsive layouts in your target browsers.
