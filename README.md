# localevents.pl — Deployment notes

To serve this static site at `https://localevents.pl` using GitHub Pages, follow these steps.

1. Repository already contains `CNAME` with the custom domain.

2. Push the current changes to GitHub (this repository must be pushed to a repository you control):

```bash
git add .
git commit -m "Prepare site for GitHub Pages: set domain to localevents.pl"
git push origin main
```

3. Enable GitHub Pages for the `main` branch (root):

- Open GitHub → Settings → Pages and set Source to `main` branch, folder `/ (root)`.

Or use the GitHub CLI (if authenticated):

```bash
gh api --method PUT /repos/:owner/:repo/pages -f source.branch=main -f source.path="/"
```

4. Configure DNS at your domain registrar (make these DNS records for `localevents.pl`):

Add these A records (point apex to GitHub Pages):

- `185.199.108.153`
- `185.199.109.153`
- `185.199.110.153`
- `185.199.111.153`

Optionally add `www` as CNAME to `localeventsbiznes-ai.github.io` (or configure an ALIAS/ANAME).

5. Wait for DNS propagation and GitHub to provision TLS (can take minutes up to a few hours).

Notes and limitations:
- I cannot change DNS records or your registrar settings from this environment.
- Pushing and enabling Pages via `gh` require that this environment is authenticated with your GitHub account and has push rights.
- If push or API calls fail, perform the listed commands on your machine where you have credentials.

If you want, I can now try to commit & push and call the Pages API from this environment; confirm and I'll proceed.
# localevents.pl
LOCAL EVENTS
