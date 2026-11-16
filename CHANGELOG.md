# Changelog

## v1.3.0: Stars, launches and a desktop widget

See how your stars grew from the very first one, compare how each release launched, and keep an eye on downloads from your desktop.

### Added

- **Star history:** a new card on Overview draws your stars over the repository's whole life, from the date each one was given. Choose **Load Star History** to fetch it. Repositories with more than 2,400 stars are sampled, which keeps it to 24 requests.
- **Release launches:** lays each release's first 30 days over the others from the day it came out, so you can see whether launches are getting bigger. A table gives each release's downloads by day 1, day 7 and day 30. It appears once two releases have come out while ElBee Stats was refreshing.
- **Desktop widget:** add **Downloads** to your desktop or Notification Center, then right-click it, choose **Edit "Downloads"** and enter a repository. It shows total downloads, the last 24 hours and the latest release, and the medium size adds a chart of the last 7 days. The widget reads public repositories from GitHub by itself about once an hour, so recent figures fill in over its first day.

## v1.2.0: Installs, notes and a weekly summary

See who's installing for the first time and who's updating, mark what happened on your charts, and get a summary of your week every Monday.

### Added

- **New installs vs updates:** a new card on Overview splits downloads into new installs (installers such as a .dmg) and updates (the .zip that installed copies update from, as ElBee Stats and ElBee Player ship). It shows each total, the last 7 days, updates per install, and both for each recent release.
- **Notes on charts:** choose **Add Note…** on Download History to note something on a date, such as a post or an announcement. Notes show as solid lines on the history and trend charts, next to the dashed release lines, and are listed under the chart where you can delete them.
- **Weekly summary:** on Monday mornings, a notification gives your downloads in the last 7 days against the week before, and your top repositories. Turn it off in **Settings › Notifications**, or choose **Show This Week's Summary** to see it now.
- **Menu bar only:** turn off **Show in Dock** in **Settings › Background** to keep ElBee Stats in the menu bar without a Dock icon.

### Changed

- **Menu bar icon:** the menu bar now shows the app icon's monitor and rising arrow instead of a download arrow, so it no longer looks like a download manager.

## v1.1.1: Opens again

Version 1.1.0 quit as soon as it was opened. This release fixes that.

### Fixed

- **ElBee Stats quit at launch:** 1.1.0 couldn't load the part of the app that installs updates, so macOS closed it straight away. It opens normally again, and updates work from this version on.

## v1.1.0: Updates and token fixes

ElBee Stats now updates itself, and a GitHub token that stops working no longer stops you following accounts.

### Added

- **Updates:** ElBee Stats checks for new versions once a day and installs them for you, then restarts. Choose **Check for Updates…** in the ElBee Stats menu, or use **Settings › General › Updates** to check now or turn automatic checks off. Every update is checked against ElBee Stats' signing key before it's installed.

### Fixed

- **Following accounts with a token:** if GitHub rejected your saved token (for example because it had expired, been revoked or wasn't copied in full), following an account and refreshing repositories failed with "GitHub rejected the Personal Access Token". ElBee Stats now carries on with public access, says so in Settings and in the Add window, and notifies you once.
- **Saving a token:** a new token is now checked with GitHub before it's saved. If GitHub doesn't accept it, it isn't saved and the reason shows in red, so it can't replace a working one.

## v1.0.0: First release

The first public release of ElBee Stats, a Mac app that keeps track of how often your GitHub releases are downloaded.

### Added

- **Track repositories or whole accounts:** enter `owner/repo`, a GitHub link, or a user or organisation name. Follow an account and every repository in it is tracked, with new ones picked up automatically.
- **Overview:** total downloads, the latest release, downloads per day and the bandwidth served, with the change since the last refresh, over 24 hours and over 7 days.
- **Charts:** downloads per release, download history with each release marked, platforms and architectures, how quickly people move to a new release, community growth (stars, forks, watchers and issues), and clone and view traffic.
- **Real downloads, not update checks:** update feeds and checksum files are left out of the totals and shown separately as Update Checks. Any file can be counted differently from its inspector.
- **Assets:** a sortable, searchable table of every file, with its details, SHA-256 digest, download link and release notes.
- **Menu bar:** downloads in the last 24 hours and 7 days, the total, and this week's top repositories. Refreshes keep running after the window is closed, and the app can open at login.
- **Notifications** for download milestones, new releases, new repositories in accounts you follow, sudden jumps in downloads and refresh problems. Each can be turned off.
- **Share** a summary picture, or copy a download badge for a README.
- **Export** to CSV or JSON.
- **Optional GitHub token,** kept in your Keychain, for a higher request limit, private repositories and traffic data.
