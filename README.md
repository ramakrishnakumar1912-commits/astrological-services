# Ambarisha Astrological Services

The official website of Dr. Y. V. V. Ramakrishna Kumar, a third-generation Vedic astrologer (Ph.D., Bharatiya Vidya Bhavan) who offers 360° birth chart readings, Vedic numerology and Vastu Shastra consultations from Chennai and worldwide over Google Meet.

## What's on the site

- **Single landing page** (`public/index.html`): hero, lineage timeline, services and fees, how a consultation works, testimonials, booking, contact and footer.
- **Booking form**: visitors submit their name, email, WhatsApp number, date/time/place of birth and questions. Submissions are stored by Netlify Forms.
- **Thank-you page** (`public/thank-you.html`): shown after booking, with UPI payment instructions and a WhatsApp button for sending payment proof.

## Technologies

- Plain static HTML, CSS and vanilla JavaScript. There is no framework and no build step.
- Netlify Forms handles booking submissions (with a honeypot spam trap and Akismet filtering).
- Netlify Image CDN resizes the portrait and converts it to WebP.

## Running locally

```bash
netlify dev --port 8889
```

Or open `public/index.html` directly in a browser. Forms and image resizing only work under Netlify (`netlify dev` or a deploy).

## Common edits

| To change… | Edit |
|---|---|
| Fees, services, copy | `public/index.html` (search for the text) |
| Phone / WhatsApp / UPI ID | `public/index.html` and `public/thank-you.html` (search for `9940223689` / `7305336617`) |
| Colours | CSS variables at the top of `public/index.html` (`--gold`, `--ink`, …) |
| Portrait photo | Replace `public/img/dr-ramakrishna-kumar.jpg` |
| Testimonials | `#testimonials` section in `public/index.html` |

## Viewing bookings

Booking requests are listed in the Netlify dashboard under **Forms → booking**. To get an email for every new booking, open **Forms → Submission notifications** and add an email notification. The recipient must be a member of your Netlify team.
