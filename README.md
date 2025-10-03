# Marc's Portfolio

**Owner:** Marc Samuel Canales
**Contact:** [marcsamuelcanales.26@gmail.com](mailto:marcsamuelcanales.26@gmail.com) — (or schedule via Calendly: [https://calendly.com/your-username](https://calendly.com/your-username))

---

## About

This is the source for **Marc's personal portfolio**, a responsive, mobile-first website built with **Svelte + Vite**. It showcases projects, skills, and contact information (including social links and a Calendly booking button). It includes a preloader, project showcase, contact section with copy/visit buttons, optional background music toggle, and a scroll-to-top button.

---

## Features

* Responsive, mobile-first design (Tailwind utilities used).
* Project showcase grid with project cards.
* Contact section with:

  * Direct visit buttons for social profiles
  * Copy-to-clipboard buttons for links and email
  * Email compose button (`mailto:`) prefilled
  * External Calendly booking link
  * Modern toast notifications (upper-left)
* Background music toggle (floating, top-right)
* Scroll-to-top (floating, bottom-right)
* Accessible controls and keyboard-focusable buttons where applicable.

---

## Tech Stack

* Svelte (components)
* Vite (dev server / build)
* Tailwind CSS (utility-first styling)
* Optional: static files served from `static/` (music, images)

---

## Quick Start (Development)

1. Clone the repo (if you have access):

   ```bash
   git clone <repo-url>
   cd repo-folder
   ```
2. Install dependencies:

   ```bash
   npm install
   ```
3. Run development server:

   ```bash
   npm run dev
   ```
4. Build for production:

   ```bash
   npm run build
   ```
5. Preview production build:

   ```bash
   npm run preview
   ```

> Put assets like background music at `/static/music/background.mp3`.
> Ensure `main.js` mounts `App.svelte` and that your components live in `src/components/`.

---

## Project Structure (suggested)

```
src/
 ├─ components/
 │   ├─ Preloader.svelte
 │   ├─ Projects.svelte
 │   ├─ Contact.svelte
 │   ├─ MusicToggle.svelte
 │   └─ ScrollToTop.svelte
 ├─ App.svelte
 ├─ main.js
 └─ app.css
static/
 └─ music/background.mp3
index.html
package.json
vite.config.js
```

---

## Accessibility & Responsiveness Notes

* Use semantic HTML and `<button>` for interactive elements for keyboard accessibility.
* Provide `alt` attributes for images.
* Keep text contrast high on dark backgrounds (white on dark gray).
* Test on small viewports (mobile), mid (tablet), and large (desktop). Use `grid sm:grid-cols-1 md:grid-cols-2` patterns to ensure stacking.
* Be aware: some browsers block autoplaying audio with sound — the toggle handles user-start when needed.

---

## Customization

* Replace social URLs and email in `Contact.svelte` with your real links.
* Place media and screenshots in `static/` and update image `src` attributes.
* Adjust colors in Tailwind config or `app.css` to match brand.

---

## Contribution

This repository is **not open for public contribution or reuse**. Do **not** fork, copy, reuse, or republish this project or its assets without explicit, written permission from the owner (Marc Samuel Canales). If you want to request permission to use code or assets, contact the owner at the email above.

---

## License & Copyright — IMPORTANT

**All rights reserved © Marc Samuel Canales.**
This project and all included assets (code, images, audio, text, and design) are the exclusive property of Marc Samuel Canales.

* **Public availability does NOT grant permission** to reuse, redistribute, modify, or republish any part of this repository.
* **Unauthorized use is prohibited.** The owner reserves the right to take legal action (including DMCA takedown requests or civil action) against parties who copy, republish, or otherwise use the project without express written permission.

If you believe you have a legitimate use case, contact the owner at `marcsamuelcanales.26@gmail.com` to request a license or written permission. All requests will be considered on a case-by-case basis.

---

## Contact

* **Email:** [marcsamuelcanales.26@gmail.com](mailto:marcsamuelcanales.26@gmail.com)
* **Calendly:** [https://calendly.com/your-username](https://calendly.com/your-username)
* Socials: Facebook / Instagram / LinkedIn / GitHub (see Contact section in the site)

---

**Last updated:** October 3, 2025
