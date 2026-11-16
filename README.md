<p align="center">
  <img src="assets/icon.png" alt="ElBee Stats icon" width="128" height="128">
</p>

<h1 align="center">ElBee Stats</h1>

<p align="center">
  <strong>See how often your GitHub releases are downloaded, and how that changes over time.</strong><br>
  A native Mac app, built with SwiftUI and Swift Charts.
</p>

<p align="center">
  <a href="https://github.com/ElBeeHQ/ElBeeStats/releases/latest"><strong>Download the latest release</strong></a>
  &nbsp;·&nbsp;
  <a href="CHANGELOG.md">What's new</a>
  &nbsp;·&nbsp;
  <a href="https://github.com/ElBeeHQ/ElBeeStats/issues">Report a problem</a>
</p>

<p align="center">
  Free for personal use · macOS 14 or later · Apple Silicon and Intel · Updates itself
</p>

---

GitHub only tells you how many times each release file has been downloaded in total. ElBee Stats saves those totals
every time it refreshes, so you can see downloads per day, what changed this week, and how quickly people move to a
new release.

## Install

1. Download `ElBeeStats-x.y.z.dmg` from the [latest release](https://github.com/ElBeeHQ/ElBeeStats/releases/latest).
2. Open it and drag **ElBee Stats** onto **Applications** in the window that appears, then eject the disk image.
3. The app is not notarised by Apple, so the first time you open it macOS may say it cannot verify it. Open
   **System Settings → Privacy & Security**, scroll to the message about ElBee Stats and click **Open Anyway**.
   If macOS says the app is "damaged", run this once in Terminal and open it again:
   ```bash
   xattr -dr com.apple.quarantine "/Applications/ElBee Stats.app"
   ```
4. Press **⌘N** and enter a repository (`owner/repo` or its GitHub link) or a user or organisation name.

**Requirements:** macOS 14 Sonoma or later, on Apple Silicon or Intel.

## Updates

ElBee Stats updates itself. It checks once a day, or open **Settings → General → Updates** and choose **Check for
Updates Now…** (also in the **ElBee Stats** menu). Updates are downloaded from this repository and checked against
ElBee Stats' signing key before they're installed, then the app restarts. Your repositories, history and settings are
kept.

Version 1.0.0 can't update itself: download the newest disk image from the
[releases page](https://github.com/ElBeeHQ/ElBeeStats/releases) once and drag it onto Applications, choosing
**Replace**. See the [changelog](CHANGELOG.md) for what changed in each release.

## Highlights

- **Track repositories or whole accounts.** Follow a user or organisation and every repository in it is tracked, with
  new ones picked up automatically.
- **Overview:** total downloads, the latest release, downloads per day and the bandwidth served, with the change since
  the last refresh, over 24 hours and over 7 days.
- **Charts:** downloads per release, download history with each release marked, platforms and architectures, how
  quickly people upgrade, community growth (stars, forks, watchers and issues), and clone and view traffic.
- **Real downloads, not update checks:** update feeds and checksum files are left out of the totals and shown
  separately as Update Checks. Any file can be counted differently from its inspector.
- **Assets:** a sortable, searchable table of every file, with its details, SHA-256 digest, download link and release
  notes.
- **Menu bar:** downloads in the last 24 hours and 7 days, the total, and this week's top repositories. Refreshes keep
  running after the window is closed, and the app can open at login. Turn off **Show in Dock** to keep it in the menu
  bar only.
- **New installs vs updates:** see how many downloads are people installing for the first time and how many are
  installed copies updating (a .zip beside a .dmg, as Sparkle apps ship), per release and over the last 7 days.
- **Notes on charts:** mark what happened on a date, such as a post or an announcement, and see it on the history and
  trend charts next to your releases.
- **Star history:** your stars over the repository's whole life, from the date each one was given.
- **Release launches:** each release's first 30 days laid over the others, with downloads by day 1, 7 and 30.
- **Desktop widget:** total downloads, the last 24 hours and a 7-day chart for any public repository, on your
  desktop or in Notification Center.
- **Weekly summary** every Monday: your downloads this week against last week, and your top repositories.
- **Notifications** for download milestones, new releases, new repositories in accounts you follow, sudden jumps in
  downloads and refresh problems. Each can be turned off.
- **Share** a summary picture, or copy a download badge for your README.
- **Export** to CSV or JSON.

## GitHub token (optional)

Without a token, GitHub allows 60 requests an hour, which is enough for a handful of repositories. Add a
[Personal Access Token](https://github.com/settings/tokens) in **Settings (⌘,)** to raise that to 5,000 an hour, see
your private repositories and show clone and view traffic for repositories you own. A fine-grained token with
read-only access to **Contents** and **Administration** (for traffic) is enough.

## Keyboard shortcuts

| Shortcut | Action |
| --- | --- |
| ⌘N | Add a repository or account |
| ⌘R / ⇧⌘R | Refresh the selected repository / refresh all |
| ⇧⌘K | Check followed accounts for new repositories |
| ⌘1 / ⌘2 | Overview / Assets |
| ⇧⌘E / ⇧⌘J | Export CSV / JSON |
| ⌥⌘I | Show or hide the inspector |

## Privacy & Security

- **No telemetry, analytics, accounts, advertising or tracking.** Nothing is sent to the developer.
- **The only network connections it makes** are to GitHub, to read release, repository and traffic information and
  profile pictures, and to check for and download updates. You can turn automatic update checks off in Settings →
  General → Updates. As with any web request, GitHub can see your IP address and the app version.
- **Your token** is stored in the macOS Keychain and is only ever sent to GitHub.
- **The widget** reads public release information from GitHub by itself, without your token, and keeps its own short
  history on your Mac.
- **Your history** stays on your Mac, inside the app's sandbox.
- **App Sandbox:** the app runs in the macOS App Sandbox, with network access and access to the files you choose when
  you export, and nothing else.

## Support

Found a problem or have an idea? Open an [issue](https://github.com/ElBeeHQ/ElBeeStats/issues).

## Licence

Copyright (c) 2026 ElBeeHQ. All rights reserved. The app is available at no charge for personal, non-commercial use;
see [`LICENSE`](LICENSE). ElBee Stats is not affiliated with or endorsed by GitHub.
