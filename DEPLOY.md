# Deploying Jiacheng Liu’s academic website

The personal site is published at <https://jiachengliu12345.github.io/> from
`jiachengliu12345/jiachengliu12345.github.io`.

## Configuration

- `_config.yml` sets `url: https://jiachengliu12345.github.io` and leaves `baseurl:` empty.
- `_data/socials.yml` sets `github_username: jiachengliu12345`.
- `_bibliography/papers.bib` and `_projects/` own publication and research project links.
- `preview.html` is a standalone preview and keeps its links consistent with the site.

The repository name must match the current GitHub username followed by `.github.io`
to publish at the domain root. GitHub repository redirects do not restore the
previous `greenoso.github.io` website domain.

## Deployment

The existing `.github/workflows/deploy.yml` builds the site on pushes to `main`
and supports manual dispatch. It builds Jekyll in production mode, purges unused
CSS, and publishes the generated site to `gh-pages`.

Repository Settings → Pages must use **Deploy from a branch**, branch `gh-pages`,
folder `/`. This matches the existing deployment workflow; it does not upload a
GitHub Actions Pages artifact.

```bash
git clone https://github.com/jiachengliu12345/jiachengliu12345.github.io.git
cd jiachengliu12345.github.io
```

Follow `AGENTS.md` for formatting and local build checks before committing changes.
After deployment, verify the homepage, publications, project links, local assets,
canonical URLs, and sitemap at the published address.

The visitor-map identifier was registered for the previous domain. Its registration
must be checked with the external provider before relying on visitor counts for
the new domain; changing a GitHub username does not update that registration.
