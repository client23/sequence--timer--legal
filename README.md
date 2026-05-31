# PhaseKit Support Site

This folder contains the static public support website for PhaseKit.

Contents:

- `index.html`
- `support.html`
- `privacy-policy.html`
- `terms.html`
- `404.html`
- `styles.css`
- `.well-known/apple-app-site-association.sample.json`

Purpose:

- App Store support URL
- App Store privacy policy URL
- public legal and support contact pages
- source of truth for the dedicated GitHub Pages repository

Public URLs:

- Main support page: `https://client23.github.io/sequence-timer-support/index.html`
- Privacy policy: `https://client23.github.io/sequence-timer-support/privacy-policy.html`
- Support page: `https://client23.github.io/sequence-timer-support/support.html`
- Terms of use: `https://client23.github.io/sequence-timer-support/terms.html`

Deployment:

- local/manual deployment uses `zsh SequenceTimer/Scripts/deploy_support_site.sh`
- CI deployment is wired through `.github/workflows/deploy-support-site.yml`
- CI syncs this folder into the dedicated support repository:
  - `git@github.com:client23/sequence-timer-support.git`

Required GitHub secret for CI:

- `SUPPORT_REPO_SSH_KEY`

That secret should contain an SSH private key with push access to the support repository.

Local preview:

```sh
cd SupportSite
python3 -m http.server 8000
```

Then open:

- `http://localhost:8000`

Notes:

- `404.html` keeps GitHub Pages fallback behavior clean
- `.well-known/apple-app-site-association.sample.json` is a placeholder template only; it is not active until renamed and populated with real app identifiers
- update these pages together with App Store pricing, in-app purchase, or privacy-impacting feature changes
