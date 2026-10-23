[English](README.md) · [Українська](README.uk.md) · [Русский](README.ru.md)

# Smart Life for Windows

Smart Life sockets in a Windows window: tiles with buttons, timers, your own scenes and schedules.

A free Windows program that shows the sockets and switches of your Smart Life (Tuya) account in one tidy window. Switch them on and off with the mouse, set timers, build your own scenes, run schedules and open every home in a separate window. Sign-in needs no password: you scan the QR code in the program window once with the Smart Life scanner.

## Download

**Version 1.0.** [SmartLifeForWindows-Setup-1.0.exe](https://github.com/drugoj00/smart-life-for-windows/releases/latest) (Assets) · [Releases](https://github.com/drugoj00/smart-life-for-windows/releases)

SHA-256: `856687083e8f6f6ed2ea60a5db03d2f4694c36236c1a9ccd70ac3d53919538be`

## Features

- Socket tiles grouped by home: name, state (on, off, offline) and a large round power button like in the Smart Life app. The state refreshes by itself every 12 seconds.
- Wide tiles: any tile can be stretched to two columns with a right click (like the “P C” card in the app).
- Device window: click a tile to open a window with a big button, electricity (power, voltage, current, energy), the socket timer and settings, as in the Smart Life app.
- Tile order: drag tiles with the mouse, the order is remembered for each home (by default as Tuya returns it).
- A turn-off timer on every tile (15 minutes, 30 minutes, 1, 2 or 4 hours).
- Confirmation before turning off important sockets (computer, router and others; the list can be changed).
- A “Turn everything off” button for a home (important sockets are left alone).
- A separate window for each home: right-click the home button. Windows remember their size and position and reopen at start.
- Your own scenes: a set of sockets with “turn on” or “turn off”, run with one button.
- Schedules: at a chosen time and weekdays turn a socket on or off or run your own scene.
- Smart Life tap-to-run scenes appear on their own tab if you have any.
- Light and dark themes; Russian, Ukrainian and English (by Windows language or chosen manually).
- Tiles adapt to the window size: all of them fit, and when space is tight the window scrolls row by row.
- QR sign-in without a password (the user code is remembered) and a backup email and password sign-in with a country list.

## Screenshots

![Main window (dark theme): home tiles, a wide tile, a timer on a tile.](screenshots/en/01-main-dark.png)

![The “My scenes” tab.](screenshots/en/05-my-scenes.png)

![The “Schedules” tab.](screenshots/en/07-schedules.png)

![A separate home window (right-click the home button).](screenshots/en/04-home-window.png)

![Light theme.](screenshots/en/02-main-light.png)

![QR sign-in: point the Smart Life scanner at it.](screenshots/en/09-sign-in-qr.png)

## Requirements

Windows 10 or 11 (64-bit); a Smart Life (or Tuya Smart) account and a phone with the app for the first sign-in; internet. Administrator rights are optional.

## Detailed guide

### 1. Installation

Download the installer SmartLifeForWindows-Setup-1.0.exe (about 59 MB) and run it. Windows asks for permission: the program is installed into C:\Program Files\SmartLifeForWindows. If you decline, it goes into your user folder. In the installer window you can add a desktop shortcut (off by default) and launch the program right away. A Start menu shortcut is always created. The installer language (Russian, Ukrainian, English) follows the Windows language and can be changed with the list in the top right corner of the window.

Uninstall it the usual way: Windows Settings → Apps. The uninstaller asks whether to delete the saved sign-in too.

The installer is not signed with a publisher certificate yet, so Windows may show a SmartScreen warning (“Unknown publisher”): click “More info”, then “Run anyway”.

![The installer window.](screenshots/en/12-installer.png)

### 2. First sign-in (once)

The program asks for neither an email nor a password. Sign-in goes through a QR code, as in Home Assistant:

1. In the Smart Life app open “Profile” → gear icon → “Account and Security” → “User Code” and copy or remember it (about 7 characters).
2. In the program, on the “By code (QR)” tab, enter the code (if it is already in the clipboard it is filled in by itself) and press “Next”. A QR code appears.
3. In Smart Life open “Profile”, tap the scanner icon at the top right and point it at the QR code in the window. Confirm the sign-in on the phone.

You can sign in with an account created through Google or by email: the program never sees the password, it only receives permission from Tuya to control the sockets.

The user code is remembered. After that the program signs in by itself and renews the session by itself: no scanning is needed until you press “Sign out” or Tuya resets the session (once every few months). After “Sign out” the QR code appears at once, you only need to point the scanner.

![QR sign-in: point the Smart Life scanner at it.](screenshots/en/09-sign-in-qr.png)

### 3. Main window

At the top is a button with the name of the current home: click it and a list of all homes of the account opens (as in the Smart Life app); choose the one you need. The program remembers the last open home (the “My scenes” and “Schedules” tabs are not remembered). Next to it are the “My scenes” and “Schedules” tabs; on them a “← Back” button appears to the right of the home name and returns you to the home you were in. Below are the socket tiles of the selected home. A tile shows the name, the state (on, off, offline) and a round power button: green when on, grey when off, dimmed with a dashed border when the device is offline. Press the button to toggle the socket. The search box at the top finds sockets by name; “Refresh” updates the state at once (otherwise it updates by itself every 12 seconds). Sockets toggled on the phone are picked up within a few seconds.

![Main window (dark theme): home tiles, a wide tile, a timer on a tile.](screenshots/en/01-main-dark.png)

![Light theme.](screenshots/en/02-main-light.png)

### 4. Wide tiles

In the Smart Life app some cards (for example “P C”) take two columns. That depends on the app settings and is not visible in the device data, so in the program you choose the width yourself: right-click the tile → “Stretch to two columns” (and “Normal size” to undo). Wide tiles come first and the choice is remembered. You can also preset wide tiles with a list of names: the config.json file, key wide (for example, ["P C"]).

### 5. Device window

Click a tile (not the power button): the device window opens, as in the app. It has a big power button, electricity (power, voltage, current, accumulated energy, if the socket measures them), the socket timer (in how many minutes it switches itself), child lock and indicator light. Settings are available with the QR login; the data refreshes by itself. Tiles can still be dragged by their background: a click opens the window, a drag changes the order.

![The device window: button, electricity, socket timer, settings.](screenshots/en/13-device.png)

### 6. Tile order

Tuya gives third-party programs the devices in its own order (by the time they were added), while the order of cards in the Smart Life app (for example in “Favorites”) is stored inside the app and is not exposed. So the order is set separately in the program: take a tile with the mouse by its background (not by the power button) and drag it onto another tile; it takes that tile's place. The order is remembered for each home and is used in home windows. Dragging works in a home without a search filter. Menu “⋯” → “Reset tile order” returns Tuya's order. You can also preset the order in config.json: key order, for example {"Apartment": ["P C", "Printer"]}.

### 7. Turn-off timer

Click the alarm-clock icon in the tile corner and choose “Turn off in 15 minutes / 30 minutes / 1 hour / 2 hours / 4 hours”. If the socket is off, it is turned on first and then off by the timer. The tile shows the time left. The timer can be cancelled in the same menu. Timers work while the program is running and are shared by all program windows.

### 8. Important sockets and “Turn everything off”

Before turning off important sockets (by default “P C”, “K O M P”, “L E N O V O” and “Router”) the program asks for confirmation, so that an accidental click does not switch off your computer or internet. The list can be changed: the config.json file in the program data folder (see “Where the data is stored”), key protected.

The “Turn everything off” button switches off all sockets that are on in the selected home except the important ones, and asks for confirmation first. The same button is in separate home windows.

### 9. A separate window for each home

Click the home name button at the top → “Open in a separate window” → the home you need (or right-click that button: the window of the current home opens). A home window can be placed on a second monitor or next to other windows. It has its own search and a “Turn everything off” button. Windows remember their size and position, and the open ones reopen at the next start. Close a window with the cross or with the same menu (“Close separate window”). The state of the sockets and the timers are shared by all windows.

![A separate home window (right-click the home button).](screenshots/en/04-home-window.png)

### 10. My scenes

The “My scenes” tab: press “+ New scene”, type a name, tick sockets and choose “Turn on” or “Turn off” for each, press “Save”. A scene runs with the “Run” button on its tile. Right-click a tile: “Edit” or “Delete”. If a scene turns off important sockets, the program asks for confirmation. Your scenes are stored in the program (not in Smart Life) and work while the program is running.

![The “My scenes” tab.](screenshots/en/05-my-scenes.png)

![Creating a scene: name, sockets and the action.](screenshots/en/06-scene-dialog.png)

### 11. Schedules

The “Schedules” tab: “+ New schedule” → choose what to switch (a socket or your own scene), the action, the time and the weekdays. The “On/Off” switch on the tile disables a schedule temporarily; right-click: “Edit” or “Delete”. Schedules fire only while the program is running and the computer is awake. For round-the-clock operation use automations in Smart Life itself.

![The “Schedules” tab.](screenshots/en/07-schedules.png)

![Creating a schedule: what, action, time, weekdays.](screenshots/en/08-schedule-dialog.png)

### 12. Smart Life scenes

If you have “tap-to-run” scenes in the Smart Life app, the program shows a “Scenes” tab with a “Run” button for each. Smart Life automations (by schedule and conditions) are not provided to third-party programs by Tuya: they are not visible in the program and keep working in the app as before.

### 13. Theme, language, window size

The “⋯” button at the top right: “Light theme” / “Dark theme”, “Language” (Auto, Русский, Українська, English; the program restarts after you choose) and “Sign out”. The default language is taken from the Windows language.

On the very first start the window is narrow (two columns). Window sizes and positions are remembered. If all tiles do not fit, they become more compact; when it is tight even so, a scroll bar appears and the mouse wheel scrolls one row at a time, so the last row is never cut off.

![The “⋯” menu: theme, language, sign out.](screenshots/en/11-menu.png)

![A narrow two-column window (how the window opens the first time).](screenshots/en/03-two-columns.png)

### 14. Email and password sign-in (backup)

The sign-in screen has a “By email and password” tab: email, password, the account country (a list with flags) and the app type. This is an old Tuya method: it shows one flat list of devices without homes and without scenes, and it does not accept every account (for some accounts Tuya answers “wrong login” even when the password is right). Google sign-in is not possible here. QR sign-in is more reliable.

![Backup email sign-in: a country list with flags.](screenshots/en/10-sign-in-email.png)

### 15. Where the data is stored

All data lives in your Windows profile: %APPDATA%\SmartLifeForWindows\данные\.

- session.json: the access key to your sockets. Never share this file.
- settings.json: theme, language, window sizes and positions, your scenes and schedules, the user code.
- config.json: the list of important sockets (protected), tiles that are wide by default (wide), the default tile order (order) and the refresh period (refresh_seconds).

The program talks only to Tuya servers, sends nothing to the developer, and has no ads or analytics. It needs neither your password nor your email.

### 16. Limitations

- The program is unofficial and not affiliated with Tuya or Smart Life. For QR sign-in it uses the public identifier of the Home Assistant integration.
- Devices with a switch are controlled (sockets, relays, plain lamps). Sensors, cameras, colour lamps and the like are not controlled; a device without a switch is shown as “no switch”.
- Smart Life automations are not available through this interface.
- Your own scenes and schedules work only while the program is running.
- Tested on Windows 11 with a Smart Life account (two homes, about 30 sockets). 64-bit Windows 10 or 11 is required.

## Built with

Python and Qt (PySide6, LGPL), the official Tuya Device Sharing SDK (MIT), flag images from flagcdn.com. The program is unofficial and not affiliated with Tuya or Smart Life.

## News and help

- Telegram: [t.me/PhoneInWindowSound](https://t.me/PhoneInWindowSound)

## Support the project

The program is free. If it is useful to you, you can support its development by card, Google Pay or USDT. For USDT use the TRON (TRC20) network only: coins sent through another network are lost.

- By card or Google Pay (from 50 UAH): https://secure.wayforpay.com/button/bba92579a4647
- USDT (TRON TRC20): `TXk32CLkwJryTqhmkw6urcM5CacJgPsSpJ`
