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

`assets/` holds the app icon, the App Preview (`preview.mp4`, no sound) and
iPhone 17 Pro Max captures from the app repo's `fastlane screenshots` run
(status bar at 9:41), whole and scaled to 640 px wide. The page draws the
phone around them the way `scripts/compose-screenshots.py` frames the App
Store screenshots (`.phone` in `style.css`). To refresh the captures, for
example after a UI change, run in the app repo

```sh
SCREENSHOT_LOCALES=en-US SCREENSHOT_DEVICES="iPhone 17 Pro Max" fastlane screenshots
```

and scale each one into this repo:

```sh
ffmpeg -i "fastlane/screenshots/en-US/iPhone 17 Pro Max-01_radar_close.png" \
  -vf "scale=640:-2:flags=lanczos" -q:v 4 assets/radar_close.jpg
```

## When the app is live

Replace the two "app store · coming soon" chips in `index.html` with a link to
`https://apps.apple.com/app/id<APP_ID>`.

## Editing the policies

Update the "last updated" line at the top of `privacy.html` or `terms.html`
whenever its content changes.
