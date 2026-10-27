# Daybreak Releases

Download page for the Daybreak church app. The source code is maintained in a
private repository.

The page is served by GitHub Pages from `index.html` on `master`.

## Publishing a new version

The page finds the newest APK by itself — it reads this repository's latest
release and points its download button at the first `.apk` attached to it. So a
new version only needs a release; `index.html` does not need editing.

1. Build the APK (Expo → **church-app-mobile** → Build from GitHub → `master`,
   profile `preview`, Android) and download it when it finishes.
2. Here on GitHub: **Releases → Draft a new release**.
3. Tag it with the version, for example `v1.1.0`.
4. Attach the `.apk` file to the release.
5. Publish.

The download page picks it up immediately, and shows the version and file size
underneath the button.

The file name does not matter — the page takes the first `.apk` it finds — but
something like `Daybreak-1.1.0.apk` is kinder to whoever downloads it.

### Until the first release exists

The button ships with a hard-coded link to the August build, used only as a
fallback: if the release lookup finds nothing, or fails because the visitor is
offline or GitHub is rate limiting them, that link is what they get.

Once a release exists, replace that fallback `href` in `index.html` with
`https://github.com/lazkingdom/daybreak-releases/releases/latest`, so even the
fallback can never be out of date.

## The QR code

`install-qr.svg` encodes the address of this page, not of an APK, so it keeps
working across releases. It only needs regenerating if the page moves.
