# CanopyTrace static site

This is a lightweight landing page bundle for **canopytrace.io**.

## Included files

- `index.html`
- `assets/logo-512.png`
- `assets/logo-256.png`
- `assets/logo-128.png`
- `assets/favicon.png`
- `CNAME.example`

## Quick local test

From this folder, run either:

```bash
python3 -m http.server 8080
```

Then open:

```text
http://localhost:8080
```

## Deploy to GitHub Pages

### Option A: branch-based Pages deployment

1. Create a new GitHub repository, for example `canopytrace-site`.
2. Upload everything in this folder to the repository root.
3. In GitHub, open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select the `main` branch and the `/ (root)` folder.
6. Save.
7. Wait for GitHub Pages to publish the site.

### Option B: GitHub Pages with a custom domain

GitHub recommends adding the custom domain in GitHub **before** changing DNS, and recommends verifying the domain to reduce takeover risk. See the official docs:
- Managing custom domains for GitHub Pages
- Verifying your custom domain for GitHub Pages

#### Verify the domain first
For an organization site:
1. In GitHub, open the **organization**.
2. Go to **Settings → Pages**.
3. Choose **Add a domain**.
4. Add `canopytrace.io`.
5. GitHub will show a TXT record to create at your DNS provider.
6. Add that TXT record.
7. After DNS propagates, return to GitHub and click **Verify**.

#### Configure the site domain
1. Go to the site repository.
2. Open **Settings → Pages**.
3. In **Custom domain**, enter `canopytrace.io`.
4. GitHub will create or update the `CNAME` record in the publishing source when publishing from a branch.

### DNS records
For an **apex domain** like `canopytrace.io`, GitHub Pages supports:
- `A`
- `ALIAS`
- `ANAME`

GitHub recommends also configuring a `www` subdomain so GitHub can redirect between apex and `www` when both are set up correctly.

Typical setup:
- Apex/root domain: point `canopytrace.io` to GitHub Pages using the records GitHub shows in the Pages settings.
- `www` subdomain: create a `CNAME` from `www.canopytrace.io` to your GitHub Pages host.

### HTTPS
After the custom domain and DNS are valid, GitHub can automatically provision HTTPS for the site.

## Notes

- Replace `hello@canopytrace.io` with your real mailbox.
- If you later add dedicated pages, good first routes are:
  - `/metrc-integration`
  - `/biotrack-integration`
  - `/cannabis-compliance-software`
- `CNAME.example` is included as a template only. Rename it to `CNAME` if you want to include it manually in a branch-based deploy.
