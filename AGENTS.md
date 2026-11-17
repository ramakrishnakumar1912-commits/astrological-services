# AGENTS.md

## Project
Static marketing and booking site for Ambarisha Astrological Services (Dr. Y. V. V. Ramakrishna Kumar). It was migrated from a single self-contained HTML file built on another platform.

## Architecture
- No framework, no package.json, no build step. `netlify.toml` publishes `public/` directly.
- `public/index.html` holds the whole site, with all CSS in one `<style>` block in `<head>` and two small inline scripts (the starfield canvas and the marquee) at the end of `<body>`.
- `public/thank-you.html` is the success page for the booking form (`action="/thank-you"`, so the path has no extension).
- `public/img/` holds static images. Reference them through the Image CDN, e.g. `/.netlify/images?url=/img/dr-ramakrishna-kumar.jpg&amp;w=640&amp;fm=webp`. Do not inline base64 images.

## Netlify Forms
- The form is named `booking` and uses `data-netlify="true"` and the honeypot `bot-field`. Detection is enabled via the `.netlify/features/netlify-forms` marker.
- Fields are name, email, whatsapp, birth_date, birth_time, birth_place and questions. Renaming a field hides its old data in the UI, so add fields instead of renaming them.
- The hidden `subject` input sets the notification email subject.

## Conventions
- Keep it dependency-free static HTML unless a feature truly needs more.
- Design tokens: navy `--ink #050A18` / `--deep #0A132C`, gold `--gold #D4AF37`. Fonts are Cormorant Garamond (headings), Outfit (body) and IBM Plex Mono (labels/eyebrows).
- The contact numbers and UPI ID appear in several places, so update all of them together: phone +91 99402 23689, WhatsApp +91 73053 36617, UPI 9940223689@okaxis.
- Booking buttons link to the on-page `#booking-form` anchor. Never link back to the old `emergent.host` site.
