# Multi Monitor Cropper

## 1. Description
Multi Monitor Cropper is a desktop software application for Microsoft Windows.
The application creates continuous wallpapers across multiple monitors.
The software calculates physical screen dimensions, monitor resolutions, and bezel gaps to remove image distortion.

## 2. Main Functions
- **Multi-Monitor Layouts**: Configure one, two, or three monitors.
- **Physical Alignment**: Set the physical size in inches and resolution for each display.
- **Bezel Compensation**: Add physical gaps between monitors to align the image continuously.
- **Offset Adjustment**: Set horizontal (X) and vertical (Y) offsets in centimeters.
- **Automatic Monitor Detection**: Read display count, resolution, and physical size directly from the operating system.
- **Image Positioning**: Drag the image in the preview window to change pan coordinates.
- **Fit Modes**:
  - **Crop**: Cut the image to match the monitor layout.
  - **Blur Fit**: Add blurred margins when the aspect ratio does not match.
- **Direct Wallpaper Application**: Export sliced images or set them directly to Windows desktop backgrounds.
- **Multi-Language Support**: English, Turkish, German, and French interfaces.

## 3. System Requirements
- Operating System: Microsoft Windows 10 or Microsoft Windows 11
- Architecture: 64-bit (x64)
- High-DPI support: Integrated automatically

## 4. Operation Instructions

### 4.1 Load an Image
1. Click **Select Image** or drag an image file onto the preview area.
2. The preview area displays the image with the monitor crop boundaries.

### 4.2 Configure Displays
1. Choose **Auto-Detect** to load hardware values automatically, or configure settings manually:
   - Select the number of displays (1, 2, or 3).
   - Enter the diagonal size in inches for each display.
   - Select or enter the resolution (Width, Height).
   - Set the physical bezel gap in centimeters.
   - Select the vertical alignment mode (Top, Center, or Bottom).

### 4.3 Adjust Image Position
1. Click and hold the left mouse button on the preview window.
2. Drag the pointer to pan the image.
3. Double-click the left mouse button to reset the position to center.

### 4.4 Export and Apply
1. Click **Export Only** to save the cropped files into a directory.
2. Click **Export & Apply** to save the cropped files and apply them to the desktop automatically.

## 5. Technical Details
- User Interface: Tkinter with Per-Monitor DPI awareness
- Image Processing: Pillow (PIL) with Lanczos resampling
- Desktop Wallpaper API: Windows `IDesktopWallpaper` COM interface via `comtypes`

## 6. License
This software is distributed under a Proprietary Freeware License.
Refer to the `LICENSE` file for conditions.
Reverse engineering, decompilation, and resale are prohibited.
