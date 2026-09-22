<img src="docs/assets/brand/cheer-kf-logo-1200.png" alt="CHEER kf*" width="520">

# cheerkf

Source of the CHEER Knowledge Framework site. Staging copy at github.com/etacir/cheerkf; on transfer to the
CHEER-Hub organization it publishes at https://cheer-hub.github.io/cheerkf/ through the workflow in
`.github/workflows/deploy.yml` on every push to `main`.

- Content lives in `docs/` as Markdown; navigation is in `mkdocs.yml`.
- To preview locally: `pip install -r requirements.txt` then `mkdocs serve`.
- Pages marked *to be confirmed* need input from the person named on that page.

Repository settings required once: **Settings > Pages > Source: GitHub Actions**.

Brand files are in `docs/assets/brand/`. For the repository's social preview image (Settings > General > Social
preview) use `cheer-kf-social-preview-1280x640.png`; for an organization avatar use `cheer-kf-avatar-512.png`.
