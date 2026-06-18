# Saanvi's 1st Birthday — Invite & RSVP Site 🎂

A beautiful, mobile-first birthday invitation website with built-in RSVP form and email reminders.

**Live URL:** [https://shravanpn7.github.io/saanvi-turns-one/](https://shravanpn7.github.io/saanvi-turns-one/)

---

## How It Works

1. **Guests** open the link (shared via WhatsApp/text) → see the beautiful invite → fill out the RSVP form
2. **Form data** is sent to your Gmail via [FormSubmit.co](https://formsubmit.co) — each RSVP arrives as a nicely formatted email
3. **Guests** receive an automatic confirmation email after submitting
4. **You** send reminder emails via Google Apps Script before the party

---

## Quick Start

### Swap in Your Canva Invite Image

1. Export your Canva design as PNG (recommended: **1080×1350px** or **1080×1080px**)
2. Name it something like `invite.png` and place it in this folder
3. Open `index.html` and find this comment block:

```html
<!-- 🎨 CANVA INVITE IMAGE -->
```

4. Replace the entire `<div class="placeholder-invite">...</div>` block with:

```html
<img id="canva-invite-image"
     src="invite.png"
     alt="Saanvi's 1st Birthday Invitation"
     loading="eager" />
```

5. Commit and push to GitHub — the site updates automatically.

---

## Managing RSVPs

### How RSVPs arrive
Every RSVP submission sends a formatted email to **your email** with:
- Guest name, email, phone
- Number of adults & kids
- Dietary restrictions
- Personal message

**First-time activation:** The first RSVP submission will trigger a confirmation email from FormSubmit.co to your email. You must click the confirmation link to activate the form. Do this right away (or test-submit the form yourself).

### Optional: Track RSVPs in Google Sheets
You can forward the RSVP emails to a Google Sheet using:
- **Google Apps Script** — set up a script to parse incoming emails
- **Zapier/Make** — auto-forward FormSubmit emails to a Sheet
- **Manual entry** — just copy from emails (easiest for <50 guests)

---

## Email Reminders

### Setup (Google Apps Script)

1. Create a Google Sheet with RSVP data (columns: Timestamp, Name, Email, Phone, Adults, Kids, Dietary, Message, Status)
2. Go to **Extensions → Apps Script**
3. Paste the contents of `apps-script.js`
4. Click Save
5. Run `sendTestReminder` to verify it works (check your inbox)
6. Set up triggers:

| Reminder | Function | Date |
|----------|----------|------|
| 1-week reminder | `sendOneWeekReminder` | July 4, 2026 10:00 AM |
| 1-day reminder | `sendOneDayReminder` | July 10, 2026 10:00 AM |

**To add a trigger:**
- Click the ⏰ clock icon (Triggers) in Apps Script sidebar
- Click "+ Add Trigger"
- Choose the function, set "Time-driven" → "Specific date and time"
- Set the date and save

---

## GitHub Pages Deployment

The site is deployed via GitHub Pages from the `main` branch.

**To update:**
```bash
git add .
git commit -m "Update invite"
git push origin main
```

Changes go live within ~1 minute.

---

## Customization

### Colors (CSS variables in `index.html`)
```css
--blush: #F9E4E0;        /* Main pink */
--rose-deep: #D4749A;    /* Accent pink */
--gold: #D4A853;          /* Gold accents */
--cream: #FFFAF5;         /* Background */
```

### Party Details
Update these in `index.html`:
- Search for `July 11, 2026` to find all date references
- Search for `5:30 PM` for time references
- Search for `Almaden Community Center` for venue references
- Search for `formsubmit.co` to change the form endpoint email

### Open Graph Image
For a nice WhatsApp/social preview:
1. Export a 1200×630px image from Canva
2. Name it `og-image.png` and place in this folder
3. The `<meta>` tag in `index.html` already references it

---

## Tech Stack

- **Frontend:** Vanilla HTML, CSS, JS (no frameworks, no npm)
- **Form backend:** [FormSubmit.co](https://formsubmit.co) (free, no signup)
- **Email reminders:** Google Apps Script (free)
- **Hosting:** GitHub Pages (free)
- **Fonts:** Google Fonts (Playfair Display, Inter, Great Vibes)

**Total cost: $0.00** 🎉

---

## File Structure

```
saanvi-invite-site/
├── index.html          # The entire invite site (single file)
├── apps-script.js      # Google Apps Script for email reminders
├── og-image.png        # Social preview image (add your own)
├── invite.png          # Your Canva invite image (add your own)
└── README.md           # This file
```
