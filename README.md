# Line Lab iOS

Native iOS wrapper for [Line Lab](https://kadenclegg.github.io/line-lab/) (Capacitor),
built from the live PWA snapshot in `www/`.

- Bundle ID: `com.kadenclegg.linelab`
- App name: Line Lab
- Web content: `www/` (synced into the Xcode project by `npx cap sync ios`)

## Build (GitHub Actions)

The workflow in `.github/workflows/ios.yml` runs on manual trigger
(`workflow_dispatch`) on a macOS runner: install, sync, archive with manual
signing, export, and upload to TestFlight via the App Store Connect API.

Required repo secrets (Settings > Secrets and variables > Actions):

- `IOS_CERTIFICATE_P12` — base64 of the .p12 distribution certificate
- `IOS_CERTIFICATE_PASSWORD` — password for that .p12
- `IOS_PROVISIONING_PROFILE` — base64 of the App Store provisioning profile
  for `com.kadenclegg.linelab`
- `APP_STORE_CONNECT_API_KEY_P8` — base64 of the App Store Connect API key (.p8)
- `API_KEY_ID` — the API key's Key ID
- `API_ISSUER_ID` — the API key's Issuer ID

Do NOT commit any of these values to the repo. The workflow is manual-trigger
only so no build runs by accident.

## Legal

- `privacy.html` — privacy policy draft for the App Store listing
- `terms.html` — terms of use draft
