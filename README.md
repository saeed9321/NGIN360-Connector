<p align="center">
  <img src="assets/icon.svg" width="112" height="112" alt="NGIN360 Connector">
</p>

<h1 align="center">NGIN360 Connector</h1>

<p align="center">
  Let the agents in your NGIN360 threads work on your own computer, only where you say.
</p>

<p align="center">
  <a href="https://github.com/saeed9321/NGIN360-Connector/releases/latest"><b>Download the latest version</b></a>
  &nbsp;·&nbsp; macOS &nbsp;·&nbsp; Windows &nbsp;·&nbsp; Linux
</p>

---

## Download

Every file is on the [latest release](https://github.com/saeed9321/NGIN360-Connector/releases/latest).

| Your computer | Download |
| --- | --- |
| **macOS** 12 or later, Apple silicon and Intel | `NGIN360-Connector_<version>_universal.dmg` |
| **Windows** 10 and 11, 64-bit (Preview) | `NGIN360-Connector_<version>_x64-setup.exe` |
| **Linux** x64 desktop | `.AppImage`, `.deb` or `.rpm` |
| **Linux** server without a desktop | `ngin360-connector-headless_<version>_linux_x64.tar.gz` |

You don't need the other files on a release. `latest.json`, `connector-manifest.json` and the `.sig` files are
for automatic updates and for NGIN360, and `SHA256SUMS` is for [checking a download](#check-a-download).

## Install

**macOS:** open the `.dmg` and drag NGIN360 Connector to Applications. The app isn't notarized by Apple yet, so
macOS blocks it the first time you open it. Go to **System Settings → Privacy & Security** and choose
**Open Anyway**.

**Windows:** run the `-setup.exe`. It installs for your user only and doesn't need admin rights. The installer
isn't signed yet, so if Windows says it protected your PC, choose **More info → Run anyway**. After you connect,
choose **Set up protection** and approve the Windows prompt once.

**Linux:** use the `.deb` (Debian, Ubuntu) or `.rpm` (Fedora, openSUSE), or make the `.AppImage` executable and
run it. On a server, unpack the headless archive, run `./ngin360-connector pair` and then
`./ngin360-connector run`. `./ngin360-connector --help` lists every command.

## Connect

1. Open NGIN360 Connector and choose the folders agents can work in. By default that's a new `NGIN360` folder in
   your home folder.
2. Choose **Connect to NGIN360**. NGIN360 opens in your browser.
3. Type the number the app shows, then choose **Connect this computer**.

The Connector lives in your menu bar (macOS) or system tray (Windows, Linux). From there you can pause agents at
any time.

## What agents can and can't do

- **Your folders:** agents run commands and change files there.
- **Everywhere else is read-only:** changing anything outside your folders needs your yes on this computer.
- **Never shared:** passwords, keys, browser data and `.env` files stay closed, even if you say yes.
- **Personal folders** (Desktop, Documents, Downloads and so on) stay closed unless you add one.
- **Sandboxed:** every command runs in your system's sandbox, and the Connector never opens a port on your
  computer. It only connects out to NGIN360.

What agents read is sent to NGIN360 and to the AI model so that they can do the work.

## Updates

The desktop app updates itself when nothing is running. You can also check for updates in **Settings**.

## Check a download

Each release lists the SHA-256 of every file in `SHA256SUMS`.

```sh
# macOS and Linux, in the folder you downloaded to
shasum -a 256 -c SHA256SUMS --ignore-missing
```

```powershell
# Windows: compare the result with the line in SHA256SUMS
Get-FileHash .\NGIN360-Connector_<version>_x64-setup.exe -Algorithm SHA256
```

## Licenses

The licenses of the third-party software inside the app are in **Settings → Licenses**. On Linux, the engine the
Connector runs includes bubblewrap (LGPL-2.0-or-later). Its source is attached to every release as
`bubblewrap-source_codex-rust-v<version>.tar.gz`.

## Help

Something not working? [Open an issue](https://github.com/saeed9321/NGIN360-Connector/issues).
