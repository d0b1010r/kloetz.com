# kloetz.com

Static sites for the kloetz.com domain. Each top-level folder is the document
root of its **own subdomain**, deployed independently:

| Folder   | Subdomain           | Deploy target (FTP)  |
| -------- | ------------------- | -------------------- |
| `www/`   | `kloetz.com` / `www.kloetz.com` | `httpdocs/www/`   |
| `david/` | `david.kloetz.com`  | `httpdocs/david/`    |
| `julia/` | `julia.kloetz.com`  | `httpdocs/julia/`    |

Because each folder is served as its own subdomain root, **root-absolute paths
(`/fonts/...`, `/img/...`) are correct** — they resolve relative to that
subdomain, not to the shared host root.

## Deployment

Pushing to `main` triggers `.github/workflows/main.yml`, which syncs each
folder to its subdomain via FTP. Other branches do not deploy.
