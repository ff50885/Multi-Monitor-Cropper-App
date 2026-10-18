# Multi Monitor Cropper — Privacy Statement

**Last Updated:** October 2026  
**Applicable Release:** Multi Monitor Cropper v1.0 (Standalone Windows Release)

Your privacy is important to us. This Privacy Statement explains what data **Multi Monitor Cropper** ("the Application") accesses on your device, how that data is processed, and how you can control or delete it.

Multi Monitor Cropper is designed as a **local-first, offline-capable desktop utility**. We do not operate remote telemetry servers, we do not require user accounts, and we never upload your images or hardware configurations to the cloud.

---

## 1. Personal and Technical Data We Process

Multi Monitor Cropper does not collect, transmit, or store personal data on external servers. To provide its core multi-monitor wallpaper calibration features, the Application accesses the following categories of data **strictly on your local device**:

### A. User-Selected Media Files
- **What is accessed:** Image files (`.jpg`, `.jpeg`, `.png`, `.bmp`, `.webp`, `.tif`, `.tiff`, `.avif`, `.heic`, `.heif`, `.exr`, `.hdr`) that you explicitly select via the file browser or drag and drop onto the application window, along with embedded image metadata (resolution, bit depth, color space, and HDR luminance parameters).
- **Where it stays:** All image decoding, cropping, rotation, and tone-mapping operations occur exclusively in your computer's local memory (`RAM`) and local disk.

### B. Display Hardware and Configuration Data (EDID)
- **What is accessed:** When you use **Auto-Detect** or **Refresh Displays**, the Application queries standard Windows Display APIs (`user32` / `gdi32`) and read-only Windows Registry display records (`HKLM\SYSTEM\CurrentControlSet\Enum\DISPLAY`) to read Extended Display Identification Data (EDID). This includes monitor model names, physical screen dimensions (cm/inches), pixel resolutions, virtual desktop coordinates, and HDR luminance capabilities.
- **Where it stays:** This hardware telemetry is used only in local memory to calibrate monitor cards in the user interface and is never transmitted outside your device.

### C. Local Preferences and Recent File Paths
- **What is stored:** The Application saves a list of your most recently opened image file paths in a local configuration file (`%APPDATA%\MultiMonitorCropper\settings.json`) so you can reload them from the **Recent Files** menu.

---

## 2. How We Use Data

The Application processes local data solely to perform the functions you request:
1. **Physical Scale & Bezel Calibration:** Calculating pixel-per-centimeter ratios and bezel compensation across heterogeneous monitors.
2. **Wallpaper Export & Desktop Assignment:** Generating cropped PNG files in your selected output directory or in `%APPDATA%\MultiMonitorCropper\wallpaper\`, and invoking the native Windows `IDesktopWallpaper` COM interface when you click **Export & Apply**.
3. **Application Troubleshooting:** Writing operational events and error messages to a local log file on your computer.

---

## 3. Reasons We Share Data

**We do not share, sell, rent, or transmit your data to any third parties.**
- The Application contains no analytics SDKs, no crash-reporting uploaders, and no third-party tracking scripts.
- All data processed by Multi Monitor Cropper remains on your computer under your control.

---

## 4. How to Access and Control Your Data

Because all application data is stored locally on your Windows system, you have full ownership and control over it at all times:

| Data Type | Local Storage Path | How to Inspect or Delete |
| :--- | :--- | :--- |
| **Recent Files History** | `%APPDATA%\MultiMonitorCropper\settings.json` | Open or delete `settings.json` in Windows File Explorer. |
| **Diagnostic Logs** | `%APPDATA%\MultiMonitorCropper\app.log` | Open with any text editor or delete the file at any time. |
| **Applied Wallpapers** | `%APPDATA%\MultiMonitorCropper\wallpaper\` | View or delete generated `monitor_*.png` files in this folder. |
| **Complete Removal** | `%APPDATA%\MultiMonitorCropper\` | Delete the entire folder and `Multi-Monitor-Cropper.exe` to remove all traces of the Application. |

---

## 5. Cookies, WebEngine, and Network Requests

- **No Cookies or Tracking Identifiers:** The Application does not use tracking cookies, advertising identifiers, or browser fingerprinting.
- **Embedded Studio Interface (`QtWebEngine`):** The user interface runs inside a local embedded Chromium-based view (`PySide6.QtWebEngineWidgets`). When an internet connection is available, the local HTML interface loads UI stylesheet utilities and fonts from `https://cdn.tailwindcss.com` and `https://fonts.googleapis.com` / `https://fonts.gstatic.com`. These standard HTTP asset requests do not include any user files, hardware configurations, or application state.

---

## 6. Diagnostic Data

- The Application records operational status messages and error tracebacks exclusively to a local rotating log file located at `%APPDATA%\MultiMonitorCropper\app.log` (capped at `2 MB` per file with up to `3` backup files).
- Diagnostic logs are **never** sent automatically over the internet. They are only shared if you manually attach and send them when requesting technical support.

---

## 7. Smart Framing and Automated Image Analysis

- The **Smart Frame** feature uses deterministic mathematical saliency algorithms (spectral residual and gradient energy calculations via `NumPy`) to detect the primary visual subject in an image and prevent monitor bezels from intersecting key areas.
- All **Smart Frame** computations run **100% locally on your CPU**. No images or image thumbnails are sent to external AI services or cloud endpoints.

---

## 8. Data Storage and Security

- All files created by Multi Monitor Cropper are stored within your standard Windows user profile directory (`%APPDATA%\MultiMonitorCropper\`) and inherit your Windows operating system account permissions.
- The standalone executable (`Multi-Monitor-Cropper.exe`) is protected with **PyArmor** code obfuscation to safeguard application integrity against unauthorized tampering.

---

## 9. Children's Privacy

Multi Monitor Cropper is a general-audience desktop utility that does not collect personal information from any user, including children under the age of 13 (or the applicable age of digital consent in your jurisdiction).

---

## 10. Changes to This Privacy Statement

We may update this Privacy Statement when new features are introduced in future releases. Any updates will be published alongside the corresponding release documentation with a revised "Last Updated" date.

---

## 11. How to Contact Us

If you have questions, concerns, or feedback regarding this Privacy Statement or the privacy practices of Multi Monitor Cropper, please open an issue on our official GitHub repository:
- **GitHub Issues:** [https://github.com/ff50885/Multi-Monitor-Cropper/issues](https://github.com/ff50885/Multi-Monitor-Cropper/issues)
