# PhysioRetreat by Dr. Manasi Darekar — Website

A modern, interactive, single-file site. No backend, no build step — just one `index.html` you host anywhere.

## ✨ What makes it unique
- **Interactive body map** — patients tap *where it hurts* and instantly get the likely cause + matching recovery plan, which auto-fills the booking form.
- **Glassmorphic "health assistant" design** with a mesh-gradient backdrop, typewriter greeting, and animated counters.
- **Free first tele-consult** highlighted in the announcement bar, hero, services, packages and process.
- **Packages with an Online ↔ Home-visit price toggle** + a launch-offer strip.
- **Dual booking** — every request goes out via **WhatsApp _or_ Email**, pre-filled with the patient's chosen body area + package.
- Specialised positioning for **Back, Neck & Shoulder**.

## ✅ Before going live — edit the CONFIG block
Open **`index.html`**, scroll to the bottom `<script>`, edit the `CONFIG` object:

```js
const CONFIG = {
  whatsapp: "919999999999",          // international format, digits only (91 = India)
  email:    "hello@manasidarekar.com",
  phonePretty: "+91 99999 99999"     // shown on the page
};
```

## 💸 Pricing
Flat **₹700 per session** (same online or at home), with packages discounted from that. To change a price, search the package name in `index.html` and edit the `.price` value + the `.save` label.

| Package | Price | Per session |
|---|---|---|
| Free Tele-Consult | ₹0 | — |
| Single Session | ₹700 | ₹700 |
| Recovery Pack (5) | ₹2,975 | ₹595 (save 15%) |
| Total Care (10) | ₹5,250 | ₹525 (save 25%) |

## ✍️ Other things to personalise (Ctrl+F)
- **Stats** — "5+ years", "1500+ patients", "4.9★" (hero `data-count`).
- **Credentials** — "BPTh & MPTh", years (About section).
- **Testimonials** — replace the 3 sample stories with real ones.
- **Real photo** — hero body-map + About use designed placeholders; swap the `.about-photo` block for `<img src="manasi.jpg">` if you want her photo.
- **Body-map content** — the `ZONES` object in the script holds each area's description + recommended plan.

## 📲 How booking works
Patient fills the quick form (or taps a body area / package) → taps **Book via WhatsApp** (opens WhatsApp pre-filled to Manasi's number) **or** **Book via Email** (pre-filled email draft).

## 🗄️ Store every enquiry (recommended)
By default the site opens WhatsApp/email but doesn't *save* anything. To keep a record of every enquiry in a dashboard (and get an email for each one), connect **Web3Forms** — free, no server needed:

1. Go to **https://web3forms.com**, enter Manasi's email, and copy the **Access Key** they send (a long code like `a1b2c3d4-...`).
2. In `index.html`, find the `CONFIG` block and paste it:
   ```js
   web3formsKey: "PASTE-YOUR-ACCESS-KEY-HERE"
   ```
3. Done. Now every "Book via WhatsApp" or "Book via Email" **also** silently saves the enquiry (name, phone, area, package, date, notes) — Manasi gets an email instantly and can see all submissions in the Web3Forms dashboard. The toast confirms "✓ Enquiry saved".

> Leave the key empty and the site still works perfectly — it just won't store submissions.
> Prefer a different tool? Formspree, Getform or Basin work the same way; swap the URL in the `logEnquiry()` function.

## ▲ Deploy to Vercel
This is a static site — no build step. Two easy ways:

**A. From GitHub (easiest to update later)**
1. Put this folder in a GitHub repo (`git init`, commit, push).
2. Go to **https://vercel.com → Add New → Project → Import** your repo.
3. Framework preset: **Other**. Build command: *(leave empty)*. Output dir: *(leave empty / `.`)*. Click **Deploy**.
4. You get a live URL like `physioretreat.vercel.app`.

**B. From your computer (Vercel CLI)**
```
npm i -g vercel
cd "L:/claude webapps/manasi-physio"
vercel            # first run links the project
vercel --prod     # publishes to production
```

**Custom domain** (e.g. `physioretreat.in`): Vercel → Project → **Settings → Domains → Add**, then point your domain's DNS as Vercel instructs.

The included `vercel.json` is already configured (clean URLs + favicon caching) — no changes needed.

## 🚀 Publish (all free)
- **Netlify Drop** — drag this folder onto https://app.netlify.com/drop → instant URL.
- **GitHub Pages** — push to a repo, enable Pages.
- **Vercel** — `vercel` in this folder.
Point a custom domain like `manasidarekar.com` at any of them.

## 👀 Preview locally
```
python -m http.server 5544
```
Open http://localhost:5544
