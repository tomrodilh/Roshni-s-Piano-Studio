# Roshni's Piano Studio — update notes

Everything you asked for is done. Two things need a 2-minute action from you (the photos and, optionally, the Google embed URL). Details below.

## 1. Add the 4 photos  ← only manual step required
The page points at an `images/` folder that sits next to `index.html`. Save the photos you sent with these **exact** filenames (lowercase, `.jpg`):

| Filename | Use the photo of… | Where it appears |
|---|---|---|
| `images/roshni-student.jpg` | Roshni standing with the young student at the black piano | Hero (top right) |
| `images/roshni-portrait.jpg` | A solo shot of Roshni *(if you don't have one, just copy `roshni-student.jpg` and rename it)* | About section |
| `images/online-class.jpg` | The Zoom grid of students at their keyboards | "How online lessons work" |
| `images/dog-piano.jpg` | The dog standing on the piano keys | The "studio dog" joke section |

That's it — no external hosting needed. The folder is already created for you; just drop the files in. JPG or PNG both work (keep the `.jpg` names, or update the `src=` in the HTML to match).

If a photo is missing, the page still loads — you'll just see the alt text in that spot until the file is added.

## 2. Booking calendar (Google appointment schedule)
- All **"Book a Trial"** buttons scroll to the booking section, which now embeds your Google calendar (`calendar.app.google/sutm3TSnArv4jF8v6`) directly in the page, with a fallback **"Open the booking page →"** button underneath.
- **Important:** Google sometimes blocks its *short* links from displaying inside an `<iframe>`. If the calendar shows up blank, grab Google's **official embed URL** (it always embeds):
  1. Google Calendar → Settings → **Appointment schedules** → open your schedule.
  2. Click **"Open booking page"**, then the **`< >` (embed)** button.
  3. Copy the URL inside the iframe code it gives you — it ends in `?gv=true`.
  4. In `index.html`, find `const bookUrl =` (near the bottom) and paste that URL in place of the short link.
- The fallback button always works regardless, so no student is ever stuck.

## 3. What else changed
- **WhatsApp** number updated to **+91 93260 03472** across every button (hero, booking, footer, final CTA, and the floating button). Pre-filled message: *"Hi Roshni, I'm interested in piano lessons. I'm based in [country/time zone] and I'd like to book a trial lesson."*
- **Mobile optimised:** removed sideways-scroll, collapsed the top nav on phones (logo + Book button stay), full-width tap-friendly buttons, and the floating WhatsApp shrinks to a circle so it never covers text.
- **Email** fixed — the old links were broken Cloudflare placeholders; they now open `roshnisridhar@gmail.com`.
- Added a warm, on-brand **dog joke** section ("Even the studio dog wanted lessons") that reinforces the "piano is for everyone" message — memorable and shareable.

## 4. Deploy
Drag the whole folder (`index.html`, `support.js`, and `images/`) onto **netlify.com/drop**, or push to GitHub and import into **Vercel**. Keep the three items together — `index.html` loads `support.js`, which renders the page.
