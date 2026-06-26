# Markify — Bulk Video Watermarker

<p align="center">
  <img src="logos/logo.png" alt="Markify Logo" width="120">
</p>

<p align="center">
  <b>Professional bulk video watermarking tool for content creators, agencies, and businesses.</b><br>
  Auto-detects Reel (Vertical) and Landscape (Horizontal) videos. Independent watermark controls for each orientation.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/version-1.1.0-blue?style=flat-square" alt="Version">
  <img src="https://img.shields.io/badge/platform-Windows-0078D6?style=flat-square&logo=windows" alt="Platform">
  <img src="https://img.shields.io/badge/electron-31.x-47848F?style=flat-square&logo=electron" alt="Electron">
  <img src="https://img.shields.io/badge/license-MIT-green?style=flat-square" alt="License">
</p>

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| **Bulk Processing** | Add unlimited videos and watermark them all in one click |
| **Auto Orientation Detection** | Automatically detects Reel (9:16) vs Landscape (16:9) videos |
| **Independent Watermark Settings** | Separate size, position, opacity, rotation for each orientation |
| **Live Preview** | Real-time interactive watermark preview with draggable positioning |
| **5-Point Position Grid** | Quick-select watermark position: corners + center |
| **Custom Drag Positioning** | Drag the watermark anywhere on the preview for precise placement |
| **Adjustable Opacity** | Control watermark transparency from 10% to 100% |
| **Rotation Control** | Rotate watermark from -180° to +180° |
| **Video Cropping** | Built-in crop tool with preset aspect ratios (1:1, 9:16, 16:9) or custom |
| **Output Resolution Scaling** | Scale output to 720p, 1080p, 2K, or 4K |
| **Dark / Light Theme** | Full theme support with persistent preference |
| **Keyboard Shortcuts** | Play/Pause, Seek, Volume, Mute — all via keyboard |
| **Settings Persistence** | All settings saved locally and restored on next launch |
| **Custom Video Player** | Built-in player with timeline, volume, and mute controls |

## 📦 Installation

### Option 1: Download Installer (Recommended)
1. Go to [Releases](../../releases)
2. Download the latest `.exe` installer
3. Run the installer and follow the setup wizard

### Option 2: Download Portable
1. Go to [Releases](../../releases)
2. Download the portable `.exe` file
3. Run directly — no installation needed

### Option 3: Build from Source
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/markify.git
cd markify

# Install dependencies
npm install

# Run in development mode
npm start

# Build installer for Windows
npm run package
```

## 🚀 How to Use

1. **Set Logo**: Click "Browse" in the Logo section to select your watermark image (PNG, JPG, WEBP)
2. **Set Output Folder**: Choose where watermarked videos will be saved
3. **Add Videos**: Drag & drop videos or click the dropzone to browse (MP4, MOV, AVI, MKV, WEBM)
4. **Configure Watermark**: Adjust size, offset, opacity, rotation, and position for Reel and Landscape independently
5. **Preview**: Click any video in the queue to see a live watermark preview — drag the watermark to reposition
6. **Process**: Click "Apply Watermark in Bulk" to process all videos, or use the export button for individual files

## ⌨️ Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Space` | Play / Pause video |
| `← Left Arrow` | Seek backward 5 seconds |
| `→ Right Arrow` | Seek forward 5 seconds |
| `↑ Up Arrow` | Volume up |
| `↓ Down Arrow` | Volume down |
| `M` | Mute / Unmute |

## 🛠️ Tech Stack

- **Electron** v31 — Cross-platform desktop framework
- **FFmpeg** — Industry-standard video processing engine (bundled via `@ffmpeg-installer/ffmpeg`)
- **FFprobe** — Video metadata detection (bundled via `@ffprobe-installer/ffprobe`)
- **Fluent-FFmpeg** — Node.js FFmpeg API wrapper
- **Vanilla HTML/CSS/JS** — Zero frontend framework overhead

## 📁 Project Structure

```
markify/
├── main.js                 # Electron main process (IPC, FFmpeg, window management)
├── preload.js              # Secure context bridge between main and renderer
├── package.json            # Project metadata, dependencies, and build config
├── default_watermark.png   # Default bundled watermark image
├── build/
│   ├── icon.png            # Application icon
│   └── installer.nsh       # NSIS installer customization script
├── logos/
│   └── logo.png            # Brand logo asset
├── src/
│   ├── index.html          # Application UI layout
│   ├── renderer.js         # Renderer process logic (queue, preview, settings)
│   ├── style.css           # Complete application styling (dark + light themes)
│   ├── logo-white.png      # Header logo for dark theme
│   └── logo-black.png      # Header logo for light theme
└── dist/                   # Build output (generated, git-ignored)
```

## 🐛 Bug Fixes — v1.1.0

### Fixed: Watermark not showing on Horizontal (Landscape) videos
- **Root Cause**: The video preview used `object-fit: cover` which clipped landscape videos, causing the watermark positioning math to break. The coordinate system assumed the rendered video filled the entire wrapper, but with landscape videos the aspect ratio mismatch caused the watermark to render outside the visible area.
- **Fix**: Changed to `object-fit: contain` and rewrote the watermark positioning engine to compute the actual rendered video rectangle within the wrapper (accounting for letterboxing/pillarboxing). All coordinate calculations — watermark position, crop box overlay, drag bounds — now correctly offset for both vertical and horizontal video orientations.
- **Files Changed**: `src/style.css`, `src/renderer.js`

## 📋 Changelog

### v1.1.0 (2026-06-26)
- 🐛 **Fixed** watermark not displaying on horizontal/landscape videos
- 🐛 **Fixed** crop box overlay misalignment on landscape videos
- 🐛 **Fixed** watermark drag positioning on landscape videos
- ♻️ Rewrote video render area calculation to properly handle `object-fit: contain`
- 📝 Updated README with complete documentation

### v1.0.0 (2026-06-22)
- 🎉 Initial release
- ✅ Bulk video watermarking with FFmpeg
- ✅ Auto orientation detection (Reel vs Landscape)
- ✅ Independent watermark settings per orientation
- ✅ Live interactive watermark preview with drag positioning
- ✅ Video cropping with aspect ratio presets
- ✅ Output resolution scaling (720p, 1080p, 2K, 4K)
- ✅ Dark and Light theme support
- ✅ Keyboard shortcuts for video player
- ✅ Persistent settings storage
- ✅ Windows installer (NSIS) and portable builds

## 👨‍💻 Author

**AYSHDAN Innovations**
- 🌐 Website: [www.ayshdan.com](http://www.ayshdan.com)
- 📧 Email: info.ayshdan@gmail.com
- 📱 WhatsApp: +92 347 7876648

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

<p align="center">
  <sub>Copyright © 2026 Markify Pakistan. All rights reserved.</sub>
</p>
