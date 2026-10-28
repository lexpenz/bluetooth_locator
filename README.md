# Bluetooth Locator · website

Landing page, support, privacy policy and terms of use for the Bluetooth Locator
iPhone app. Plain static HTML and one stylesheet, served by GitHub Pages from
`main` (root).

| page | file | App Store Connect field |
| --- | --- | --- |
| Landing | `index.html` | Marketing URL |
| Support | `support.html` | Support URL |
| Privacy policy | `privacy.html` | Privacy Policy URL (and the app's Settings link) |
| Terms of use | `terms.html` | License agreement, if a custom EULA is ever set |

GitHub Pages serves each page with or without `.html` (`/privacy` works).

The look follows the app's `Theme.swift`: dark only, ink background, hairline
borders, phosphor green for live signal, amber for caution, sans for words and
mono for labels and numbers, "·" as the separator.

## Assets

`assets/` holds the app icon, the App Preview (`preview.mp4`, status bar
cropped, no sound) and iPhone 17 Pro Max captures from the app repo's
`fastlane screenshots` run, cropped below the status bar and scaled to 640 px
wide. To refresh one, for example after a UI change:

```sh
ffmpeg -i "fastlane/screenshots/en-US/iPhone 17 Pro Max-01_radar_close.png" \
  -vf "crop=1320:2696:0:172,scale=640:-2:flags=lanczos" -q:v 4 assets/radar_close.jpg
```

## When the app is live

Replace the two "app store · coming soon" chips in `index.html` with a link to
`https://apps.apple.com/app/id<APP_ID>`.

## Editing the policies

Update the "last updated" line at the top of `privacy.html` or `terms.html`
whenever its content changes.
