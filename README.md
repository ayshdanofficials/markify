<div align="center">

<img src="https://raw.githubusercontent.com/ayshdanofficials/Markify-Desktop-Bulk-Video-Watermarker/main/logos/logo.png" alt="Markify Logo" width="140"/>

# Markify

### Professional Bulk Video Watermarking — Built for Creators, Agencies & Businesses

<br/>

[![Version](https://img.shields.io/badge/version-1.1.0-6C63FF?style=for-the-badge)](https://github.com/ayshdanofficials/Markify-Desktop-Bulk-Video-Watermarker/releases)
[![Platform](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/ayshdanofficials/Markify-Desktop-Bulk-Video-Watermarker/releases)
[![Electron](https://img.shields.io/badge/Electron_31-47848F?style=for-the-badge&logo=electron&logoColor=white)](https://www.electronjs.org/)
[![FFmpeg](https://img.shields.io/badge/FFmpeg-007808?style=for-the-badge&logo=ffmpeg&logoColor=white)](https://ffmpeg.org/)
[![License](https://img.shields.io/badge/License-MIT-22C55E?style=for-the-badge)](LICENSE)

<br/>

**Markify** is a powerful desktop application that lets you watermark hundreds of videos in seconds — with full control over size, position, opacity, and rotation. It auto-detects video orientation and applies the right watermark settings for each format, automatically.

<br/>

[⬇️ Download Installer](#-download) · [🚀 Quick Start](#-quick-start) · [✨ Features](#-features) · [🛠️ Build from Source](#-build-from-source)

</div>

---

## 📸 Preview

<div align="center">
<img src="https://github.com/ayshdanofficials/Markify-Desktop-Bulk-Video-Watermarker/blob/main/Screenshot%202026-06-23%20042325.png?raw=true" alt="Markify Screenshot" width="85%" style="border-radius: 12px; margin: 16px 0;"/>
</div>

---

## ⬇️ Download

Choose your preferred installation method:

| Type | Link | Details |
|------|------|---------|
| 🔧 **Installer** *(Recommended)* | [Download `.exe` Setup](https://github.com/ayshdanofficials/Markify-Desktop-Bulk-Video-Watermarker/releases/download/v1.0.0/Markify.Setup.1.1.0.exe) | Full installation with Start Menu entry |
| 📦 **Portable** | [Download `.exe` Portable](https://github.com/ayshdanofficials/Markify-Desktop-Bulk-Video-Watermarker/releases/download/v1.0.0/Markify.1.1.0.exe) | Run anywhere — no installation needed |

> **Requires:** Windows 10 or later (64-bit)

---

## ✨ Features

### 🎬 Core Capabilities

- **Bulk Video Processing** — Add unlimited videos and watermark them all in a single click
- **Auto Orientation Detection** — Automatically identifies Reel (9:16 vertical) vs Landscape (16:9 horizontal) videos
- **Independent Watermark Settings** — Separate size, position, opacity, and rotation controls for each orientation
- **Live Interactive Preview** — See your watermark in real-time before processing begins

### 🎯 Watermark Controls

- **5-Point Position Grid** — Instantly snap to corners or center with one click
- **Free Drag Positioning** — Drag and drop the watermark anywhere on the preview for pixel-perfect placement
- **Opacity Control** — Adjust transparency from 10% to 100%
- **Rotation** — Rotate from -180° to +180°
- **Size Scaling** — Fine-tune watermark size independently per orientation

### ✂️ Video Tools

- **Built-in Crop Tool** — Crop with preset aspect ratios (1:1, 9:16, 16:9) or set a fully custom crop
- **Output Resolution Scaling** — Export at 720p, 1080p, 2K, or 4K

### 💡 App Experience

- **Dark / Light Theme** — Full theme support with persistent user preference
- **Keyboard Shortcuts** — Full video player control without touching your mouse
- **Settings Persistence** — Everything is saved locally and restored on next launch
- **Custom Video Player** — Built-in player with timeline, volume, and mute controls

---

## ⌨️ Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Space` | Play / Pause |
| `← Left Arrow` | Seek back 5 seconds |
| `→ Right Arrow` | Seek forward 5 seconds |
| `↑ Up Arrow` | Volume up |
| `↓ Down Arrow` | Volume down |
| `M` | Mute / Unmute |

---

## 🚀 Quick Start

```
1. Launch Markify
2. Click "Browse" → select your watermark image (PNG / JPG / WEBP)
3. Set your output folder
4. Drag & drop your videos into the queue (MP4, MOV, AVI, MKV, WEBM)
5. Adjust watermark settings for Reel and/or Landscape
6. Click any video to preview — drag the watermark to fine-tune position
7. Hit "Apply Watermark in Bulk" — done ✅
```

> You can also export individual videos using the export button on each queue item.

---

## 🛠️ Build from Source

```bash
# Clone the repository
git clone https://github.com/ayshdanofficials/Markify-Desktop-Bulk-Video-Watermarker.git
cd Markify-Desktop-Bulk-Video-Watermarker

# Install dependencies
npm install

# Run in development mode
npm start

# Build Windows installer
npm run package
```

---

## 🧱 Tech Stack

| Technology | Role |
|------------|------|
| **Electron v31** | Cross-platform desktop application framework |
| **FFmpeg** | Industry-standard video processing engine (bundled) |
| **FFprobe** | Video metadata & orientation detection (bundled) |
| **Fluent-FFmpeg** | Node.js API wrapper for FFmpeg |
| **Vanilla HTML / CSS / JS** | Zero-framework UI — lightweight and fast |

---

## 📁 Project Structure

```
markify/
├── main.js                 # Electron main process — IPC, FFmpeg, window management
├── preload.js              # Secure context bridge (main ↔ renderer)
├── package.json            # Dependencies, metadata, and build config
├── default_watermark.png   # Default bundled watermark image
├── build/
│   ├── icon.png            # Application icon
│   └── installer.nsh       # NSIS installer customization script
├── logos/
│   └── logo.png            # Brand logo asset
├── src/
│   ├── index.html          # Application UI layout
│   ├── renderer.js         # Queue, preview, and settings logic
│   ├── style.css           # Full styling — dark + light themes
│   ├── logo-white.png      # Header logo (dark theme)
│   └── logo-black.png      # Header logo (light theme)
└── dist/                   # Build output (auto-generated, git-ignored)
```

---

## 📋 Changelog

### `v1.1.0` — 2026-06-26

- 🐛 **Fixed** watermark not displaying on horizontal / landscape videos
- 🐛 **Fixed** crop box overlay misalignment on landscape videos
- 🐛 **Fixed** watermark drag positioning on landscape videos
- ♻️ Rewrote video render area calculation to correctly handle `object-fit: contain` with letterboxing/pillarboxing
- 📝 Full README documentation added

<details>
<summary><b>v1.0.0</b> — 2026-06-22 (Initial Release)</summary>

- 🎉 First public release
- ✅ Bulk video watermarking via FFmpeg
- ✅ Auto orientation detection (Reel vs Landscape)
- ✅ Independent watermark settings per orientation
- ✅ Live draggable watermark preview
- ✅ Built-in video crop tool with aspect ratio presets
- ✅ Output resolution scaling (720p → 4K)
- ✅ Dark and Light theme support
- ✅ Keyboard shortcuts
- ✅ Persistent settings
- ✅ Windows installer (NSIS) and portable builds

</details>

---

## 👨‍💻 Author

<div align="center">

**AYSHDAN Innovations**

[![Website](https://img.shields.io/badge/Website-ayshdan.com-6C63FF?style=for-the-badge&logo=google-chrome&logoColor=white)](http://www.ayshdan.com)
[![Email](https://img.shields.io/badge/Email-info.ayshdan@gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:info.ayshdan@gmail.com)
[![WhatsApp](https://img.shields.io/badge/WhatsApp-+92_347_7876648-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.me/923477876648)

</div>

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for full details.

---

<div align="center">

Made with ❤️ by **Ayshdan Innovations** · Pakistan 🇵🇰

<sub>Copyright © 2026 Markify. All rights reserved.</sub>

</div>
