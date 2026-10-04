# Cert Utils

Cert Utils inspects an X.509 certificate and splits a PFX into PEM keys. Parsing stays in the browser.

**Live app:** https://cert.sanjaysingh.net

## What it does

**Cert Viewer.** Paste PEM text or choose a certificate file, then parse it. The decoded certificate is shown in the result box.

**Split PFX.** Load a `.pfx` or `.p12` file with its password. The page separates the public certificate and the private key and downloads each as PEM.

The private key is decrypted locally so the PEM files can be saved. Do not use this page on a machine you do not trust.

## Privacy

Certificate material stays in the browser. There is no upload and no account.

## Run locally

Open `index.html` in a browser. The page uses the bundled `cert-browser.js`. To rebuild that bundle from `cert.js`:

```bash
npm install
npx browserify cert.js -o cert-browser.js
```

`node-forge` is the only dependency. No build step is required to use the page as it is committed.

## Deploy

Commits that land on `main` deploy to GitHub Pages at https://cert.sanjaysingh.net. Changes reach `main` through a pull request.
