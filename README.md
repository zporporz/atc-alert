# ATC Alert

A Windows companion for IVAO Altitude, with desktop alarms, optional iPhone notifications through Bark, and active CTR airspace advisories.

**[Download the latest Windows release](https://github.com/zporporz/atc-alert/releases/latest)**

In the release's **Assets**, choose **ATCAlert-1.4.0-windows.zip** (or the newer versioned Windows ZIP). Extract all six files and run **ATCAlert.exe**. The automatically generated Source code downloads do not contain the application.

## Getting started

1. Extract the release ZIP to a writable folder on Windows 10/11 with .NET Framework 4.8 or later.
2. Open IVAO PilotUI, then ATC Alert. Enter the same callsign used in PilotUI.
3. For iPhone alerts, install [Bark](https://apps.apple.com/app/bark-custom-notifications/id1403753865), allow Notifications and Critical Alerts, and open **iPhone setup** in ATC Alert. Enter your own Bark key, send a test and save.
4. Open the included **START-HERE.html** for the full setup guide. Keep the computer awake with PilotUI and ATC Alert running.

## Features

- Repeating desktop alarm for matching incoming ATC contact requests; **Acknowledge** stops the computer sound.
- Optional Bark phone alarm, with Critical Alert support when permitted by iOS.
- Active CTR coverage advisories using public IVAO polygons, with a separate short Critical notification when a CTR comes online while you are already inside.
- Local airspace simulation and explicit phone tests, without requiring a controller to participate.
- Live release notifications, **Check now**, and one-click **Download & install** with automatic restart.

## Updating

Version 1.3.0 receives live release signals over a WebSocket relay. When a stable release is published, connected apps verify it with GitHub and show Update available without waiting for a polling interval. Network and service delays still apply. The app must be running and online. Automatic reconnect and six-hour fallback checks are included. You can disable automatic update notifications in the Updates window. Version 1.2.0 users can click Check now to get this release; earlier versions need a manual download.

From **1.4.0**, choose **Download & install** when a newer version is available. The app downloads and verifies the release, closes, installs it and reopens automatically. Your callsign, Bark settings and captures stay in place. Monitoring continues during download and pauses briefly to restart. Acknowledge any active ATC alert before installing. Downloads can be cancelled, and installation errors trigger rollback to the saved files.

**Already using 1.3.0 or earlier?** Install 1.4.0 manually once: close ATC Alert and extract all six files from the new ZIP into your existing folder. After that, future updates install from the app. Keep **ATCAlert.Updater.exe** and **update-source.json** beside **ATCAlert.exe**. A GitHub account is not required.

## Scope and local data

This is an independent utility, not an official IVAO product. Contact detection passively reads PilotUI debug messages and matches contact text; an identical manually typed message also triggers it. It cannot prove that a distinct FORCE ACT command was used. Compatibility has been verified on one Windows installation with Altitude 1.13.0.33.

Airspace advisories require published CTR polygons. There is no altitude filtering, and APP/TWR/GND/FSS coverage is not monitored. Check which controller actually applies to your flight. Public data and polling introduce delays.

The release ZIP contains no personal settings or capture logs. Each user enters their own callsign and Bark key. Settings and captures are stored beside the executable; Bark settings are encrypted for the current Windows account. Phone delivery sends relevant alert details through Bark. Update checks and the Cloudflare release relay receive no callsign, Bark key or logs. The relay carries public version hints and heartbeat messages; its hosting provider can see connection IP addresses.

The Windows executable is not code signed. This repository distributes release binaries and public instructions.
