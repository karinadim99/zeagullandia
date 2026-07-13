# Zeagullandia 🐦

A roleplay website where you build a seagull persona, join **The Flock** (a social
feed of coastal & environmental news), and join or start **Flock Societies**.

This repo contains a single self-contained website — no build tools, no server,
no dependencies to install.

## Files in this repo

| File | What it's for |
|---|---|
| `index.html` | The entire website (HTML, CSS, and JS all in one file) |
| `favicon.ico` | Browser tab icon (works everywhere, incl. old browsers) |
| `favicon.svg` | Sharp browser tab icon for modern browsers |
| `favicon-16x16.png`, `favicon-32x32.png` | Fallback PNG icon sizes |
| `apple-touch-icon.png` | Icon used when someone adds the site to their iPhone/iPad home screen |
| `icon-512.png` | Large icon, handy if you add a PWA manifest later |

## 1. Add these files to your GitHub repo

**Option A — GitHub's web UI (easiest, no terminal needed)**
1. Open your repo on github.com.
2. Click **Add file → Upload files**.
3. Drag in all the files from this folder (`index.html`, `favicon.ico`, `favicon.svg`,
   `favicon-16x16.png`, `favicon-32x32.png`, `apple-touch-icon.png`, `icon-512.png`, `README.md`).
4. Scroll down, add a commit message like "Add Zeagullandia site", and click
   **Commit changes**.

**Option B — Git command line**
```bash
# from inside your local clone of the repo
cp /path/to/downloaded/files/* .
git add .
git commit -m "Add Zeagullandia site"
git push
```

Make sure `index.html` ends up at the **root** of the repo (not inside a
subfolder) — that's what GitHub Pages looks for by default.

## 2. Turn on GitHub Pages

1. In your repo, go to **Settings → Pages**.
2. Under "Build and deployment", set **Source** to **Deploy from a branch**.
3. Set **Branch** to `main` (or `master`) and folder to `/ (root)`.
4. Click **Save**.
5. GitHub will give you a URL, usually:
   `https://<your-username>.github.io/<repo-name>/`
   It can take a minute or two to go live the first time.

## 3. (Optional) Use your own domain

If you want `zeagullandia.com` instead of the github.io URL:
1. In **Settings → Pages**, enter your domain under "Custom domain."
2. At your domain registrar, add a `CNAME` record pointing to
   `<your-username>.github.io`.
3. GitHub will auto-create a `CNAME` file in your repo — leave it there.

## Good to know: accounts are stored in the browser (for now)

Signing up, posting, and joining societies all work — but the data is saved
using the browser's `localStorage`, not a real database. That means:

- Your account will still be there next time *you* open the site on the
  *same device/browser*.
- It will **not** be visible to anyone opening the site on a different
  computer — each visitor gets their own separate local copy.

This is normal for a first prototype and is easy to fix later by connecting
the site to a real backend (e.g. Firebase, Supabase, or a small custom
server) so accounts and posts are shared by everyone. Just ask if you'd like
help wiring that up.

## Making changes later

Everything — layout, colors, the avatar list, the seeded news posts — lives
in `index.html`. Open it in any text editor:
- Colors and fonts are defined near the top inside `<style>` under `:root`.
- The avatar options are defined in the `AVATARS` object in the `<script>`
  section.
- Seed content (starter news posts & societies) is in the `seedIfNeeded()`
  function.
