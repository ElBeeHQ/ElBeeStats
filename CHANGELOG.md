# Changelog

## v1.4.0: What changed, and who downloaded it

*19 November 2026*

See what each refresh brought in, and how many of your downloads were likely people.

### Added

- **What changed since the last refresh.** After you refresh (the toolbar, the sidebar, ⌘R, ⇧⌘R or the menu bar), each repository in the sidebar whose downloads went up shows a small green "+50" under its count, and an account's **All Repositories** shows the sum. Point at a row to see its new downloads, stars, forks and releases. The figures stay for an hour or until your next refresh, then fade. After **Refresh All** or refreshing an account, a banner at the bottom of the window gives the totals, and the menu bar shows the same line, with "+N" beside each of the week's top repositories. Scheduled refreshes, a repository's first refresh and refreshes that fail don't show it.
- **Estimated People.** Turn on **Settings › General › Estimate downloads by people** to see an **Estimated People** card beside Total Asset Downloads. It leaves out downloads that look automated (bots, CI jobs or mirrors fetching files again): a burst far above the repository's usual rate, one file of a new release spiking far above the others, or every file rising by the same amount at once. Point at the card to see what was left out and why. It's an estimate, it covers only the time ElBee Stats has been taking snapshots, and the total itself never changes. Off by default.
- **Homebrew installs beside GitHub downloads.** Link a Homebrew cask or formula to a repository (right-click it in the sidebar and choose **Link Homebrew…**, or use the button in its Overview) and a **Downloads by Source** card shows GitHub downloads and Homebrew installs for the last 30, 90 or 365 days, with the total of every way people get it. A cask that downloads its file from your GitHub releases is already counted in GitHub's figure, so the card says so and doesn't add it twice. Homebrew only shares installs for the last 30, 90 and 365 days, never a lifetime total. The figures are fetched with your refreshes, at most once a day, from Homebrew's public website. No account or token is needed.

- **History with no gaps.** ElBee Stats can only take snapshots while it's running, so a sleeping Mac leaves gaps. A small GitHub Action you add to a repository of your own (private is fine) now saves your download counts, stars and traffic once a day, and ElBee Stats adds those to its history. It never changes the snapshots it took itself. Set it up in **Settings › History**: **Copy Workflow** and **Copy Repository List** give you the two files, and the steps are beside them.

### Fixed

- **Star history with a fine-grained token.** If your token isn't set up for a public repository, GitHub answers as if the repository didn't exist, so loading its star history said "Not found" and suggested the name was wrong. ElBee Stats now says your token can't reach that repository and how to fix it: add the repository to the token in GitHub's settings, or choose All repositories (read-only is enough). Refresh errors say the same.

### For contributors

- **Demo mode** has two more commands for captures: `refresh-change` shows the refresh banner, and `mirror-burst` gives the selected repository a mirror-like burst for the estimate.

## v1.3.4: Downloads per Release you can find your way around

*17 November 2026*

### Changed

- **Downloads per Release shows where you are.** When a repository has more releases than fit, the chart opens on the newest ones, and a line above it says which are showing and how many there are. Older and Newer buttons beside it page through the rest, so you can move along with a mouse, the keyboard or VoiceOver, as well as by scrolling sideways. Scrolling always comes to rest on whole bars.

### Fixed

- **Version numbers in Downloads per Release are no longer cut off.** They're written level and whole under each bar, and the chart shows only as many releases as their names fit at the window's width. The pop-up for a release you click sits just above its bar, inside the chart, so it's never cut off or drawn over the card's title. When the chart scrolls, the scroll bar sits between the bars and the version numbers, never on top of them.
- **New Installs vs Updates no longer squashes its version numbers together** in a narrow window. It shows the newest releases whose numbers fit and says how many of the last 12 are shown.

### For contributors

- **Demo mode** has a fourth made-up repository, `example-org/photo-tidy`, with 32 releases, so the scrolling chart can be checked and captured.

- **Debug builds have their own bundle identifier** (`io.github.elbeehq.ElBeeStats.debug`, and `.debug.Widget` for the widget). A Debug build, including the copy that hosts the unit tests, used to share the release's identifier while being signed with the development team, so macOS gave it the release's data container. A release that was already running was then refused its own container: it couldn't save settings, and updating failed with "An error occurred while downloading the update". A test checks the identifier, and `Scripts/publish-release.sh` stops a release whose identifier isn't `io.github.elbeehq.ElBeeStats`.

## v1.3.3: ElBeeHQ's wordmark

*16 November 2026*

### Changed

- **Made by ElBeeHQ:** the credit in the About window and **Settings › General** now uses ElBeeHQ's drawn wordmark, the same one as on ElBeeHQ's website and in its other apps. The About window also links to ElBeeHQ.com beneath it.

### Fixed

- **Star history without a token:** GitHub now shares stargazer dates only with a Personal Access Token. Without one, loading star history said the token had been rejected; the Star History card now explains that a token is needed, and the button waits until one is added.

### For contributors

- **Demo mode** (`ELBEE_STATS_DEMO=1`, for screenshots) shows made-up repositories and runs only in a demo copy with its own bundle identifier, made with `Scripts/make-demo-app.sh`, so a demo run can't change the real app's settings. It's compiled only into Debug builds and that demo copy (the `DEMO` condition), never into a release, and `Scripts/check-no-demo.sh` stops a release that contains any of it.

## v1.3.2: Made by ElBeeHQ

### Added

- **Made by ElBeeHQ:** the About window and **Settings › General** now show ElBeeHQ's logo. Click it in Settings to open ElBeeHQ on GitHub. ElBee Stats keeps its own icon.

## v1.3.1: A new icon

ElBee Stats has a new icon, so it no longer looks like ElBee Player.

### Changed

- **App icon:** a honeycomb cell with a rising line replaces the screen on a stand, which was too easy to mistake for ElBee Player's TV. It keeps the same cream, ink and amber. The menu bar icon and the mark beside the ElBee Stats name change to match.

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
