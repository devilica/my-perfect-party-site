# My Perfect Party — developer website

Static site for Google Play **Website** field and AdMob **app-ads.txt** verification.

## Contents

| File | Purpose |
| --- | --- |
| `index.html` | Developer / product landing page |
| `privacy.html` | Privacy Policy |
| `terms.html` | Terms of Use |
| `app-ads.txt` | AdMob publisher authorization |
| `styles.css` | Brand styles |

`app-ads.txt` line:

```txt
google.com, pub-5452343649745884, DIRECT, f08c47fec0942fa0
```

## Deploy (GitHub Pages — recommended)

1. Create a new GitHub repo (e.g. `my-perfect-party-site`).
2. Push this folder to the repo `main` branch.
3. GitHub → **Settings → Pages**
   - Source: **Deploy from a branch**
   - Branch: `main` / `/ (root)`
4. Wait for the site URL, e.g. `https://YOUR_USER.github.io/my-perfect-party-site/`

### Important for AdMob

AdMob looks for `app-ads.txt` at the **root of the domain you put on Play**.

- If Play Website is `https://YOUR_USER.github.io/my-perfect-party-site/`  
  then AdMob expects:  
  `https://YOUR_USER.github.io/my-perfect-party-site/app-ads.txt`  

  **Some AdMob crawls only work at domain root** (`https://YOUR_USER.github.io/app-ads.txt`).  
  If verification fails with a project-page URL, do one of these:

  **Option A — user site root (best)**  
  Create repo named `YOUR_USER.github.io`, put these files in that repo root.  
  Then Play Website = `https://YOUR_USER.github.io`  
  and `https://YOUR_USER.github.io/app-ads.txt` works.

  **Option B — custom domain**  
  Point a domain (e.g. `myperfectparty.app`) to GitHub Pages and set Play Website to that domain.

## Deploy (Netlify)

1. Drag this folder onto [Netlify Drop](https://app.netlify.com/drop), or connect the Git repo.
2. You get a URL like `https://random-name.netlify.app`.
3. Put that exact URL (or your custom domain) in Play Console → Website.
4. Confirm: `https://YOUR-SITE.netlify.app/app-ads.txt` opens in the browser.

## Play Console + AdMob checklist

1. Play Console → store listing / store settings → **Website** = your live site URL (exact domain).
2. Open `https://YOUR-DOMAIN/app-ads.txt` in a browser — must show the google.com line.
3. AdMob → app → verify / check for updates.
4. Wait (minutes to ~24h).

## Local preview

Open `index.html` in a browser, or:

```bash
npx --yes serve .
```
