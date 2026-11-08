# Patte Alerte — website

Static site (plain HTML + one CSS file, no build step), hosted on GitHub Pages.

| Page | French | English |
|---|---|---|
| Home | `/` | `/en/` |
| Privacy policy (App Store "Privacy Policy URL") | `/privacy/` | `/en/privacy/` |
| Support + legal notice (App Store "Support URL") | `/support/` | `/en/support/` |

## Before the App Store submission

Search the project for `TODO` and replace:
- `contact@example.com` → the real contact address (support, privacy and legal pages, FR + EN)
- `[NOM DE L'ÉDITEUR]` / `[PUBLISHER NAME]` → the publisher name (same as the App Store developer name)
- the "Bientôt sur l'App Store" buttons → the App Store link `https://apps.apple.com/app/id…`
  (the id appears in App Store Connect › App Information › Apple ID as soon as the app record exists)

Then update the privacy policy date if the text changed.

## Preview locally

Open `index.html` in a browser, or run `python3 -m http.server` in this folder and open http://localhost:8000.

## Custom domain (e.g. pattealerte.fr)

1. Buy the domain at a registrar (OVH, Gandi, Cloudflare, Namecheap…).
2. At the registrar's DNS settings, add:
   - 4 `A` records for the root (`@`): `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - (optional) 4 `AAAA` records: `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`
   - 1 `CNAME` record: `www` → `sofienazzouz.github.io`
3. On GitHub: repository › Settings › Pages › Custom domain → type the domain → Save
   (this creates a `CNAME` file in the repo). Wait for the DNS check, then tick **Enforce HTTPS**.
4. Recommended: GitHub › Settings (your account) › Pages › **Verify** the domain, so nobody else can use it.
5. Update the absolute URLs in the `<link rel="alternate">` tags and in the app (`Brand.privacyPolicyURL`).
