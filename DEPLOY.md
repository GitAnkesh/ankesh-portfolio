# Deploy ankesh.dev

Your portfolio is a static site — no build step required. Upload the contents of this `portfolio/` folder to any static host.

## Option 1: Cloudflare Pages (recommended — free, fast)

1. Push this folder to a GitHub repo (e.g. `ankesh-portfolio`).
2. Go to [Cloudflare Dashboard](https://dash.cloudflare.com) → **Workers & Pages** → **Create** → **Pages**.
3. Connect your GitHub repo, or use **Direct Upload** and drag the `portfolio/` files.
4. Build settings: **None** (static HTML). Output directory: `/` (or `portfolio/` if repo root).
5. In Cloudflare, add your domain **ankesh.dev**:
   - **Websites** → your site → **Custom domains** → add `ankesh.dev` and `www.ankesh.dev`.
6. In **Spaceship** (where you bought the domain), point nameservers to Cloudflare (Cloudflare will show you the NS records), **or** add these DNS records at Spaceship if you keep their DNS:

   | Type  | Name | Value              |
   |-------|------|--------------------|
   | CNAME | @    | your-pages.pages.dev |
   | CNAME | www  | your-pages.pages.dev |

   (Use the exact target Cloudflare gives you.)

## Option 2: GitHub Pages

1. Create repo, copy `index.html`, `styles.css`, `script.js` to repo root.
2. **Settings** → **Pages** → Source: **main** branch, folder **/ (root)**.
3. Site will be at `https://<username>.github.io/<repo>/`.
4. For **ankesh.dev**: add `CNAME` file containing `ankesh.dev`, then at Spaceship set:
   - **A** records for `@` → GitHub IPs: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - **CNAME** for `www` → `<username>.github.io`

## Option 3: Spaceship hosting (if included)

If Spaceship offers web hosting with your domain:

1. Open their hosting panel → File Manager or FTP.
2. Upload `index.html`, `styles.css`, and `script.js` to the public web root (`public_html` or similar).
3. Ensure `index.html` is the default document.

## Preview locally

```bash
cd portfolio
python3 -m http.server 8080
```

Open http://localhost:8080

## Files to upload

- `index.html`
- `styles.css`
- `script.js`

No dependencies, no npm install.
