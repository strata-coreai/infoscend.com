# infoscend.com

The Infoscend marketing site. Static HTML, no build step.

## Stack

- Plain HTML / CSS / a sprinkle of vanilla JS
- Google Fonts: Inter, Fraunces, JetBrains Mono
- Hosted on Cloudflare Pages
- Custom domain: infoscend.com

## Local preview

Any static server works:

```bash
python3 -m http.server 8080
# then http://localhost:8080
```

## Structure

```
/index.html                   homepage
/articles/*.html              38 knowledge-centre essays
/images/                      product UI screenshots
/images/articles/             per-article hero images
/videos/                      product demo videos
/styles.css                   single source of truth — homepage + articles
/favicon.svg                  Lift icon
/_headers                     Cloudflare Pages security + caching
/_redirects                   path aliases
/sitemap.xml                  search engines
/robots.txt
/llms.txt                     LLM crawler index
```

## Brand

- Sigil (primary wordmark): `info` in Ink + `scend` in Conductor Copper
- Lift mark (icon): three ascending stepped bars, top step copper
- Palette: Ink `#0E1116`, Bone `#F6F4EE`, Conductor Copper `#A86A2C`, Slate scale
- Typography: Inter (sans), Fraunces (serif, editorial), JetBrains Mono (numeric)

Full brand guidelines: see `../Techtuate/brand/infoscend-brand-guidelines.html`.

## Deployment — Cloudflare Pages

1. Push this folder to a new GitHub repo (e.g. `infoscend/infoscend.com`)
2. In Cloudflare dashboard: Pages → Create project → Connect to Git → select the repo
3. Build settings: leave build command blank, output directory `/`
4. Add custom domain `infoscend.com` (and `www.infoscend.com`)
5. DNS automatically configured if the domain is on Cloudflare; otherwise add CNAME records as instructed

No build step is required — Cloudflare serves files directly from the repo root.
