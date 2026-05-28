# Hernandez Electric — Project Handoff (saved May 28, 2026)

Use this file when you reopen the project on any Mac or in Cursor.

---

## Quick answers

| Question | Answer |
|----------|--------|
| Is Git push/pull working on **this** Mac? | **Yes** — SSH to GitHub is set up. |
| Live website | https://hernandezelectricinc.com |
| GitHub repo | https://github.com/fp4pomiliacivil/hernandezelectricinc.com |
| Does `git push` update the live site? | **Yes** — Netlify auto-deploys from `main`. |
| Folder to edit | `netlify-export/` only |

---

## This Mac (Desktop)

**Project path:**
```
/Users/fp4/Desktop/hernandez-electric-website
```

**Daily commands:**
```bash
cd ~/Desktop/hernandez-electric-website
git pull
# edit netlify-export/
git add netlify-export/
git commit -m "Describe your change"
git push
```

**Local preview:**
```bash
python3 -m http.server 3457 --directory netlify-export
```
Open http://localhost:3457

**Git remote (SSH):**
```
git@github.com:fp4pomiliacivil/hernandezelectricinc.com.git
```

**SSH key (this Mac only):**
- Private: `~/.ssh/id_ed25519_github`
- Public title on GitHub: “Mac Hernandez Electric website”
- Config: `~/.ssh/config` → `Host github.com` uses that key

---

## Other MacBook (first time)

1. Clone:
   ```bash
   cd ~/Desktop
   git clone git@github.com:fp4pomiliacivil/hernandezelectricinc.com.git
   ```
2. Add **your own** SSH key on that Mac → https://github.com/settings/ssh/new  
   (This Mac’s key does not transfer.)
3. Cursor → Open Folder → cloned repo.
4. Same `git pull` / `git push` / preview commands as above.

HTTPS clone (if no SSH): `git clone https://github.com/fp4pomiliacivil/hernandezelectricinc.com.git` — use a GitHub personal access token as password.

---

## Netlify (hosting)

| Item | Value |
|------|--------|
| Project name | `hernandezelectric` |
| Site ID | `2524ebd6-d3a8-4fa2-93ae-78dede4f3a5a` |
| Netlify login | fpomilia4@gmail.com |
| Dashboard | https://app.netlify.com/projects/hernandezelectric |
| Deploys | https://app.netlify.com/projects/hernandezelectric/deploys |
| Git repo linked | `fp4pomiliacivil/hernandezelectricinc.com` @ `main` |
| Publish directory | `netlify-export` (see `netlify.toml`) |
| Auto-publish | **On** — pushes to `main` go live |

**Build config** (`netlify.toml`):
```toml
[build]
  publish = "netlify-export"
```

**GitHub App:** Netlify is installed on account `fp4pomiliacivil` (all repos).

**Optional cleanup:** Revoke old Netlify API token “Hernandez Electric Git deploy” if still listed under User settings → Applications → Personal access tokens (only needed for one-time linking).

---

## Site pages (in `netlify-export/`)

| Path | Page |
|------|------|
| `index.html` | Home |
| `about/index.html` | About |
| `services/index.html` | Services |
| `contact/index.html` | Contact |
| `css/old-site.css` | Styles |
| `_redirects` | Apex redirects (no www loop) |
| `_headers` | Security headers |

**Do not edit** old root files (`index.html`, `css/`, `js/` at repo root) for production — they are not deployed.

---

## Business info (on site)

- **Hernandez Electric Inc.**
- Phone: (707) 354-8212
- Email: info@hernandezelectric.net / trino@hernandezelectric.net
- Address: 3721 Christy Court, Ukiah, CA 95482 (also 50 Orr Springs Rd. on older copy)
- License: C-10 #863889
- Service area: Lake, Sonoma, Mendocino counties
- Founded: 2005

---

## Domains & DNS

- **Primary:** hernandezelectricinc.com (apex, HTTPS)
- **www** redirects to apex
- DNS managed in Netlify for this domain

---

## Accounts

| Service | Account |
|---------|---------|
| GitHub | fp4pomiliacivil |
| Netlify | fpomilia4@gmail.com |
| Domain (registrar) | GoDaddy (DNS pointed to Netlify) |

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| `git push` asks for password / fails | On that Mac: set up SSH key or GitHub PAT |
| Live site didn’t update | Check https://app.netlify.com/projects/hernandezelectric/deploys for failed build |
| Wrong content live | Confirm you edited `netlify-export/` and pushed to `main` |
| Redirect loop | `_redirects` should force apex `https://hernandezelectricinc.com` |

---

## What was completed (session summary)

1. Static old-style site in `netlify-export/` deployed to hernandezelectricinc.com  
2. GitHub repo created and initial code pushed  
3. SSH auth on this Mac for push/pull  
4. Netlify linked to GitHub — auto-deploy on every push to `main`  
5. `netlify.toml` + README deploy instructions added  

---

*Last updated: May 28, 2026*
