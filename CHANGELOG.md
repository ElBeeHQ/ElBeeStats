# Changelog

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
