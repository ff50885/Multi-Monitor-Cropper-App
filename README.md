# Multi Monitor Cropper

**Release Version:** 1.0 (Standalone Executable)  
**Target Platform:** Microsoft Windows (64-bit)

---

## 1. General Information

### 1.1 Purpose of the Software
**Multi Monitor Cropper** aligns, crops, and applies a single wallpaper image across multiple monitors of different physical sizes and resolutions.

The software uses physical screen dimensions in inches and centimeters instead of raw pixel counts. This calculation keeps straight lines continuous across monitor borders and physical bezels.

### 1.2 Key Capabilities
- **Physical Scale Alignment:** Matches pixel density across screens of different sizes (for example, a 24-inch 1080p monitor next to a 32-inch 4K monitor).
- **Bezel Compensation:** Hides image pixels behind physical monitor frames so objects do not jump across gaps.
- **Curved Display Projection:** Corrects horizontal width distortion for `1000R`, `1500R`, and `1800R` curved monitors.
- **2D Spatial Canvas:** Supports multi-row grids, vertical monitors, custom X/Y offsets, and freeform panel rotation (`-180°` to `+360°`).
- **Smart Subject Framing:** Detects the main visual subject and moves it away from monitor bezels.
- **HDR and High Bit-Depth Pipeline:** Preserves 10-bit, 16-bit, and 32-bit HDR color data and applies per-monitor tone mapping.
- **One-Click Wallpaper Assignment:** Exports cropped images and sets them as individual desktop backgrounds on Windows.

---

## 2. System Requirements

| Requirement | Specification |
| :--- | :--- |
| **Operating System** | Microsoft Windows 10 (64-bit) or Windows 11 (64-bit) |
| **Display Configuration** | 1 to 8 connected monitors |
| **Disk Space** | 250 MB of free disk space for the executable file |
| **Memory (RAM)** | Minimum 4 GB RAM (8 GB RAM recommended for 8K and 16K images) |

### 2.1 Supported Image Formats
The software accepts the following input file extensions:
- **Standard Formats:** `.jpg`, `.jpeg`, `.png`, `.bmp`, `.webp`
- **High Bit-Depth and HDR Formats:** `.tif`, `.tiff` (8-bit and 16-bit), `.avif`, `.heic`, `.heif`, `.exr` (OpenEXR), `.hdr` (Radiance RGBE)

---

## 3. Installation and Startup

The software is a standalone single-file executable (`Multi-Monitor-Cropper.exe`). You do not need to install Python or external libraries.

### 3.1 Start the Application
1. Copy `Multi-Monitor-Cropper.exe` to a folder on your computer.
2. Double-click `Multi-Monitor-Cropper.exe` to start the application.

> [!NOTE]
> At the first startup, Windows extracts the runtime files to a temporary folder. The main window opens in 3 to 5 seconds.

---

## 4. User Interface Overview

The main window contains four primary areas:

| Area | Location | Function |
| :--- | :--- | :--- |
| **Header Bar** | Top of the window | Contains hardware detection buttons, language selection, and window controls. |
| **Configuration Rack** | Left sidebar | Contains source media controls, global rig settings, per-monitor cards, and export buttons. |
| **Studio Canvas** | Center workspace | Shows the live wallpaper preview, monitor crop boxes, rulers, and framing tools. |
| **Telemetry Bar** | Bottom of the canvas | Shows active monitor count, alignment mode, scaling state, and hardware status. |

---

## 5. Operating Procedures

### 5.1 Load a Wallpaper Image

Use one of the three methods below to load an image into the software.

#### Method A: Use the File Browser
1. Click **Select Image** in the **Source Media** section on the left sidebar.
2. Select a supported image file from your computer.
3. Click **Open**.

#### Method B: Drag and Drop an Image
1. Drag an image file from Windows File Explorer.
2. Drop the file directly onto the **Studio Canvas** in the center of the window.

#### Method C: Load a Recent Image
1. Click **Recent Files** in the **Source Media** section.
2. Click a file name in the list to load that image again.

---

### 5.2 Detect and Identify Connected Monitors

The software can read your monitor sizes, resolutions, positions, and HDR state directly from Windows hardware records (EDID).

#### Enable Automatic Hardware Detection
1. Click **Auto-Detect: OFF** in the top header bar.
2. Verify that the button label changes to **Auto-Detect: ON** and the green indicator pulses.

#### Refresh Monitor Data
- Click **Refresh Displays** in the top header bar to scan connected monitors again.

#### Identify Physical Monitors
1. Click **Identify Displays** in the top header bar.
2. Look at your physical screens. A large number card (`1`, `2`, `3`, ...) appears in the center of each monitor for 3 seconds.
3. Match each number to the corresponding **Display** card in the left sidebar.

> [!NOTE]
> Automatic detection results can vary if Windows display scaling is active. Always verify the diagonal size on each display card.

---

### 5.3 Configure Global Rig Settings

Use the **Global Rig Setup** panel in the left sidebar to set parameters that apply to all monitors.

#### Set the Number of Displays
1. Locate **Total Displays** in the **Global Rig Setup** section.
2. Click the **Up** arrow to add a monitor, or click the **Down** arrow to remove a monitor (1 to 8 displays).

#### Set the Physical Bezel Gap
1. Measure the physical plastic frame thickness between your side-by-side monitors in centimeters.
2. Enter the horizontal gap value in the left **Bezel Gap (cm)** box (tooltip: **Horizontal Bezel**).
3. Enter the vertical gap value in the right **Bezel Gap (cm)** box (tooltip: **Vertical Bezel**).
4. Alternatively, click the **Up** or **Down** arrows to change both bezel values in `0.5 cm` steps.

#### Select Vertical Alignment and Fit Mode
1. Click the first dropdown menu next to **Align & Mode:** and select a baseline alignment:
   - **Bottom:** Aligns the bottom edges of all monitors in the same row.
   - **Top:** Aligns the top edges of all monitors in the same row.
   - **Center:** Aligns the horizontal center lines of all monitors in the same row.
2. Click the second dropdown menu next to **Align & Mode:** and select an image fitting mode:
   - **Crop:** Scales the source image to fill the entire monitor matrix without borders.
   - **Fit:** Fits the full source image inside the monitor matrix and fills empty areas with a soft blurred background.

---

### 5.4 Calibrate Individual Monitors

Each monitor has a dedicated card under the **Calibration Matrix** section in the left sidebar.

| Control | Function and Procedure |
| :--- | :--- |
| **Diag:** | Enter the physical screen diagonal size in inches (for example, `27.0` or `31.5`). |
| **Resolution Menu** | Select the native pixel resolution of the monitor (for example, `1920×1080`, `2560×1440`, or `3840×2160`). |
| **Hor / Ver Button** | Click **Hor** (`↔`) or **Ver** (`↕`) to switch the monitor between landscape and portrait orientation. |
| **Row:** | Enter the vertical grid row index (`0` for the top row, `1` for the second row). |
| **Col:** | Enter the horizontal grid column index (`0` for the leftmost monitor, `1` for the next monitor). |
| **Curvature Menu** | Select **Flat** for a flat screen, or select **1000R**, **1500R**, or **1800R** for a curved monitor. |
| **X (cm):** | Enter a custom horizontal position offset in centimeters. |
| **Y (cm):** | Enter a custom vertical position offset in centimeters (positive values move the screen down). |
| **Angle (°):** | Enter a custom tilt angle in degrees (`-180` to `360`), or click **↻** (**Rotate 90°**) to rotate the screen in 90-degree steps. |

---

### 5.5 Use the Interactive Studio Canvas

The **Studio Canvas** lets you position the wallpaper and move monitors directly with your mouse.

#### Pan and Zoom the Wallpaper
- **Zoom In / Out:** Scroll the mouse wheel up or down over the canvas (`1.0x` to `5.0x`).
- **Pan the Wallpaper:** Click and drag an empty background area on the canvas.
- **Pan Underneath a Monitor Box:** Hold the `Shift` key, then click and drag anywhere on the canvas.
- **Reset View:** Click **Fit** or **100%** in the top-right canvas toolbar, or double-click the canvas.

#### Move a Monitor Panel on the Canvas
1. Move the mouse pointer inside a monitor crop box on the canvas.
2. Click and drag the monitor box to its physical position.
3. Hold the `Alt` key while you drag to temporarily disable magnetic edge snapping.

#### Rotate a Monitor Panel on the Canvas
1. Locate the circular rotation handle (**↻**) above the top center of a monitor crop box.
2. Click and drag the rotation handle left or right to tilt the monitor.
3. The angle snaps to `0°`, `90°`, `180°`, and `-90°` within a `2°` tolerance. Hold the `Alt` key to rotate without angle snapping.

#### Use Canvas Toolbar Tools
- **Snap ≤5mm:** Click this button to turn magnetic edge snapping on or off. When active, monitor edges snap together when they come within `5 mm` of each other.
- **Rulers (mm):** Click this button to show or hide physical millimeter and centimeter scales along the top and left edges of each monitor box.
- **Smart Frame:** Click this button to automatically detect the main subject in the wallpaper and shift the crop area so monitor bezels do not cut through the subject.

---

### 5.6 Export and Apply Wallpapers

Use the two action buttons at the bottom of the left sidebar when your calibration is complete.

#### Export and Set Desktop Wallpaper Automatically
1. Click **Export & Apply**.
2. The software saves one cropped PNG image per monitor and assigns each image to the matching Windows display.
3. Click **OK** on the confirmation dialog.

#### Export Cropped Images to a Custom Folder Only
1. Click **Export Only**.
2. Select a destination folder in the **Select Output Directory** dialog.
3. Click **Select Folder**.
4. The software saves the cropped images (`monitor_1_WIDTHxHEIGHT.png`, `monitor_2_WIDTHxHEIGHT.png`, ...) in that folder without changing your current desktop background.

---

### 5.7 Change the Interface Language

1. Click the language button (`EN`, `TR`, `DE`, or `FR`) in the top-right corner of the header bar.
2. Select your preferred language from the dropdown menu:
   - **EN:** English
   - **TR:** Turkish (Türkçe)
   - **DE:** German (Deutsch)
   - **FR:** French (Français)

---

## 6. Status Indicators and Warnings

| Indicator | Location | Meaning and Action |
| :--- | :--- | :--- |
| **`⚠️ %XX` (Amber Border)** | Top header of a monitor crop box | **Low-Resolution Warning:** The cropped area has fewer pixels than the native resolution of the monitor. Use a higher-resolution source image or reduce the zoom level. |
| **`HDR` (Gold Badge)** | Monitor card in the left sidebar | The connected monitor supports or uses High Dynamic Range (HDR). |
| **`FORMAT HDR` (Green Badge)** | Source Media strip | The loaded image contains high bit-depth or HDR luminance data. |
| **Green Glowing Line** | Studio Canvas | **Magnetic Snap Guide:** Indicates that two monitor edges or center lines are aligned within `5 mm`. |
| **Dashed Green Box (`🎯 Smart Frame`)** | Studio Canvas | Shows the detected primary subject boundary when **Smart Frame** is active. |

---

## 7. Troubleshooting

| Problem | Probable Cause | Corrective Action |
| :--- | :--- | :--- |
| Diagonal lines do not align across two monitors. | The diagonal inch value or bezel gap does not match the physical hardware. | Measure the visible screen diagonal in inches and enter the exact value in **Diag:**. Measure and enter the frame width in **Bezel Gap (cm)**. |
| One monitor image is higher or lower than the next monitor. | The physical monitors sit at different heights on the desk. | Select the correct baseline in **Align & Mode:** or adjust the **Y (cm):** offset on the monitor card. |
| **Auto-Detect** shows an incorrect screen size. | Windows DPI scaling or generic monitor drivers report approximate EDID values. | Enter the exact manufacturer screen size manually in the **Diag:** box. |
| A monitor crop box shows an amber border and `⚠️`. | The source wallpaper resolution is lower than the monitor resolution. | Load a higher-resolution image (such as 4K or 8K) or click **Fit** in the zoom toolbar to reset zoom to `100%`. |
| **Export & Apply** does not change the background on one screen. | Windows Virtual Desktops or third-party wallpaper tools block the Windows Desktop Wallpaper COM interface. | Close third-party wallpaper tools, or click **Export Only** and assign the exported PNG files manually in Windows Display Settings. |

---

## 8. Local Data Files

The application stores user configuration and log files in your Windows user profile directory:

- **Path:** `%APPDATA%\MultiMonitorCropper\` (typically `C:\Users\<Username>\AppData\Roaming\MultiMonitorCropper\`)
  - `settings.json`: Stores your recent image file history.
  - `app.log`: Records operational events and error messages for troubleshooting.
  - `wallpaper\`: Stores the cropped PNG files generated when you click **Export & Apply**.
