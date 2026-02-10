+++
title = "Android Debloater Script"
date = 2023-07-14
description = "Debloater.sh — Android Debloater Script"
github = "https://github.com/patkarmandar/debloater.sh" # Optional
demo = "" # Optional
tags = ["bash", "android", "debloat"]
categories = ["script"]
featured = false
+++

Debloater.sh is a Bash-based Android debloating script that uses ADB (Android Debug Bridge) to disable and remove user data of pre-installed system applications (bloatware).

Debloating helps improve privacy, reduce background activity, and optimize battery performance by disabling unnecessary OEM or carrier-installed apps.

{{< alert type="warning" >}}
This script does not permanently uninstall system apps (root is not required). Instead, it removes app data from the user space, effectively disabling the app for the current user.
{{< /alert >}}

### How It Works (Technical Explanation)
- System applications reside in the /system partition, which is read-only and cannot be modified without root access.
- However, system apps also store user data and cache in the /data partition.
- This script removes the app’s user data and cache using ADB, making the app inactive.
- A factory reset restores all removed packages, as it wipes the /data partition.
- OTA updates may reinstall disabled system apps — the script should be re-run after updates.

{{< alert type="note" >}}
This method does not free system storage space, but significantly reduces background services and telemetry.
{{< /alert >}}

### Features
- [x] Search installed Android packages
- [x] List all system and user-installed packages
- [x] Uninstall (disable) a single package
- [x] Bulk uninstall multiple packages
- [ ] Restore previously removed packages

### Prerequisites
- Android device (non-rooted supported)
- USB cable
- ADB installed on host machine
- Developer Options & USB Debugging enabled on device
- Bash shell (Linux / macOS / WSL)

### Usage Instructions
1. Backup Your Device
{{< alert type="warning" >}}
Strongly recommended — Create a full device backup before proceeding.
{{< /alert >}}
2. Enable Developer Options
    - Go to Settings -> About Phone
    - Tap Build Number 7 times
    - Enable USB Debugging from Developer Options
3. Install ADB
    - Verify ADB installation: `adb version`
    - If not installed, install ADB via:
        - Linux: `sudo apt install adb`
        - macOS: `brew install android-platform-tools`
        - Windows: `Android SDK Platform Tools`
4. Run the Script
    - Connect your device via USB, then: `bash debloat.sh`
5. Follow the on-screen prompts to search, uninstall, restore, or bulk manage packages.

### Risks & Warnings
- Removing core or essential system packages may cause:
    - Boot loops
    - App crashes
- A factory reset will restore all removed packages
- This script cannot permanently brick your device
- Use at your own risk

### Disclaimer

{{< alert type="warning" >}}
This project is provided as-is.
The author is not responsible for data loss, device malfunction, or unintended behavior.
Always review packages carefully and keep backups.
{{< /alert >}}

### Use Cases
- Removing OEM bloatware
- Improving battery life
- Reducing background services
- Enhancing privacy on non-rooted devices
