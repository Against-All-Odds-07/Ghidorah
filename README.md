# Ghidorah

**Android app for remote control.**

Ghidorah runs on the Android device you want to access and works with **Ghoston**, the controller application, over **Tailscale VPN**.

---

## Features

* Remote screen sharing
* Remote touch and gesture control
* Keyboard and text input
* File access and transfer
* SMS and messaging support
* Clipboard sharing
* Device information
* Battery and storage information
* Device pairing and authentication

---

## How It Works

```text
┌──────────────┐
│   Ghoston    │
│  Controller  │
└──────┬───────┘
       │
   Tailscale
       │
       ▼
┌──────────────┐
│  Ghidorah    │
│    Target    │
└──────────────┘
```

Ghoston controls the device running Ghidorah through the Tailscale network.

Communication between the applications uses the Ghidorah WebSocket protocol.

---

## Requirements

* Android device
* [Tailscale](https://tailscale.com/)
* Ghidorah installed on the target device
* Ghoston installed on the controller device
* Required Android permissions

Some features depend on the Android version and the permissions available on the device.

---

## Installation

Download the latest APK and Windows client from the [Releases](../../releases) page.

Install **Ghidorah** on the Android device you want to control.

Make sure:

1. Tailscale is installed and connected.
2. Required Android permissions are enabled.
3. Ghidorah is running.
4. Ghoston is installed on the controller device.

Then pair the devices through Ghoston.

---

## Build

Clone the repository:

```bash
git clone https://github.com/Against-All-Odds-07/Ghidorah.git
cd Ghidorah
```

Build the debug APK:

```bash
./gradlew assembleDebug
```

The APK will be generated at:

```text
app/build/outputs/apk/debug/app-debug.apk
```

---

## Project Structure

```text
Ghidorah/
├── app/
│   ├── src/
│   └── build.gradle.kts
├── gradle/
├── gradlew
├── gradlew.bat
├── settings.gradle.kts
└── README.md
```

---

## Permissions

Depending on the enabled features, Ghidorah may require access to:

* Screen capture
* Accessibility
* Storage / files
* SMS
* Notifications
* Clipboard

Permissions are used only for their respective functionality.

---

## Security

Ghidorah is intended for **authorized access to devices you own or are permitted to manage**.

Use the application only on trusted devices and networks.

---

## Related Project

### Ghoston

Android controller application used to connect to Ghidorah.

```text
Ghoston → Tailscale → Ghidorah
```

---

## Windows Client

The Windows client is a Rust implementation ported from the Python client. It is the controller application for managing Ghidorah Android devices over Tailscale; it is separate from the Android app.

Download **Ghidorah Client.exe** from the repository's [Releases](../../releases) page. The executable is also present in [`windows-client/Control.exe`](windows-client/Control.exe) in the repository. See [`windows-client/README.md`](windows-client/README.md) for folder notes.

---

## Releases

The [Releases](../../releases) page contains the Android APK and the Windows client executable (**Ghidorah Client.exe**).

---

## License

See the [`LICENSE`](LICENSE) file for details.
